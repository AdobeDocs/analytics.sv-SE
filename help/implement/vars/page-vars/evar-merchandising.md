---
title: eVar (variabeln Merchandising)
description: Egna variabler som knyts till enskilda produkter.
feature: Appmeasurement Implementation
exl-id: 26e0c4cd-3831-4572-afe2-6cda46704ff3
mini-toc-levels: 3
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '574'
ht-degree: 0%

---

# eVar (Merchandising)

*Den här hjälpsidan beskriver hur du implementerar eVars för varuexponering. Mer information om hur marknadsföring av eVars fungerar som en dimension finns i [eVars (marknadsföringsdimension)](/help/components/dimensions/evar-merchandising.md) i användarhandboken för komponenter.*

En detaljerad diskussion om hur eVars marknadsförs finns i [Merchandising eVars and product finding methods](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/conversion-variables/merchandising-evars.html).

## Konfigurera eVars i inställningarna för rapportsviten

Innan du använder eVars i implementeringen måste du konfigurera eVar till önskad syntax i rapportsvitens inställningar. Se [Konverteringsvariabler](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/conversion-var-admin.md) i administrationshandboken.

>[!WARNING]
>
>Om det inte går att konfigurera eVars för försäljning korrekt resulterar det i oväntade värden eller dataförlust för variabeln. Kontrollera att den är korrekt konfigurerad för din implementering.

## Implementera med produktsyntax

När Produktsyntax är aktiverat fylls försäljningskategorin i direkt i variabeln `products`, så det är inte nödvändigt att välja och ställa in en bindningshändelse. Detta är den rekommenderade metoden och bör användas om inte värdet inte är tillgängligt för att anges i `products` när händelsen success inträffar.

```js
// The bare minimum to set a merchandising eVar with product syntax
s.products = ";Example product;;;;eVar1=Example merchandising value";

// An example single product with product syntax
s.products = "Example category;Example product;1;5.99;event1=1;eVar1=Turtles";

// Tie a merchandising eVar to a different values on two different products
s.products = "Birds;Scarlet Macaw;1;4200;;eVar1=talking bird,Birds;Turtle dove;2;550;;eVar1=love birds";
```

Värdet för `eVar1` har tilldelats produkten. Alla efterföljande lyckade händelser som berör den här produkten krediteras eVar-värdet.

### Produktsyntax med Web SDK

Om du använder [**XDM-objektet**](/help/implement/aep-edge/xdm-var-mapping.md) använder produktsyntaxvariabler följande XDM-fält:

* E-variabler för produktsyntaxmarknadsföring mappas under `xdm.productListItems[]._experience.analytics.customDimensions.eVars.eVar1` till `xdm.productListItems[]._experience.analytics.customDimensions.eVars.eVar250`.
* Försäljningshändelser för produktsyntax mappas under `xdm.productListItems[]._experience.analytics.event1to100.event1.value` till `xdm.productListItems[]._experience.analytics.event901to1000.event1000.value`. [Händelseserialisering](events/event-serialization.md) XDM-fält mappas under `xdm.productListItems[]._experience.analytics.event1to100.event1.id` till `xdm.productListItems[]._experience.analytics.event901to1000.event1000.id`.

>[!NOTE]
>
>När du anger händelser under `productListItems` behöver du inte ange dem i händelsesträngen. Om de anges på båda platserna har värdet i händelsesträngen företräde.

I följande exempel visas en enskild [product](products.md) som använder flera eVars- och händelsemeddelanden för marknadsföring:

```json
"productListItems": [
  {
    "name": "Bahama Shirt",
    "priceTotal": "12.99",
    "quantity": 3,
    "_experience": {
      "analytics": {
        "customDimensions" : {
          "eVars" : {
            "eVar10" : "green",
            "eVar33" : "large"
          }
        },
        "event1to100" : {
          "event4" : {
            "value" : 1
          },
          "event10" : {
            "value" : 2,
            "id" : "abcd"
          }
        }
      }
    }
  }
]
```

Ovanstående exempelobjekt skickas till Adobe Analytics som `";Bahama Shirt;3;12.99;event4|event10=2:abcd;eVar10=green|eVar33=large"`.

Om du använder [**dataobjektet**](/help/implement/aep-edge/data-var-mapping.md) använder eVar-marknadsföring `data.__adobe.analytics.eVar1` - `data.__adobe.analytics.eVar250` efter AppMeasurement-syntax.

## Implementera med konverteringsvariabelsyntax

Konverteringsvariabelsyntax används när eVar-värdet inte är tillgängligt för att anges i variabeln `products`. Det här scenariot innebär vanligtvis att sidan inte har något sammanhang för försäljningskanalen eller sökmetoden. I dessa fall ställer du in variabeln för försäljning innan du kommer till produktsidan, och värdet kvarstår tills bindningshändelsen inträffar.

När bindningshändelsen som väljs under konfigurationen inträffar, kopplas det beständiga värdet för eVar till produkten. Om till exempel `prodView` anges som bindningshändelse är marknadsföringskategorin bunden till den aktuella produktlistan endast när händelsen inträffar. Endast efterföljande bindningshändelser kan uppdatera en eVar som redan har tilldelats en produkt.

```js
// Place on the same or previous page before the binding event:
s.eVar1 = "Aviary";

// Place on the page where the binding event occurs:
s.events = "prodView";
s.products = ";Canary";
```

Värdet `"Aviary"` för `eVar1` tilldelas produkten `"Canary"`. Alla efterföljande lyckade händelser som berör den här produkten krediteras `"Canary"`. Dessutom är det aktuella värdet av variabeln merchandising knutet till alla efterföljande produkter tills något av följande villkor uppfylls:

* EVar förfaller (baserat på inställningen &quot;Förfaller efter&quot;)
* Försäljningen av eVar har skrivits över med ett nytt värde.

### Konvertera variabelsyntax med Web SDK

Om du använder [**XDM-objektet**](/help/implement/aep-edge/xdm-var-mapping.md) fungerar syntaxen på samma sätt som andra [eVars](evar.md)- och [händelser](events/events-overview.md) implementeras. XDM-speglingen av exemplet ovan skulle se ut så här:

Ställ in eVar på samma eller föregående event call:

```json
"_experience": {
  "analytics": {
    "customDimensions": {
      "eVars": {
        "eVar1" : "Aviary"
      }
    }
  }
}
```

Ange bindningshändelse och värden för produktsträngen:

```json
"commerce": {
  "productViews" : {
    "value" : 1
  }
},
"productListItems": [
  {
    "name": "Canary"
  }
]
```

Om du använder [**dataobjektet**](/help/implement/aep-edge/data-var-mapping.md) ser dataobjekten som motsvarar exemplet ovan ut så här:

Ställ in eVar på samma eller föregående event call:

```json
"data": {
  "__adobe": {
    "analytics": {
      "eVar1": "Aviary"
    }
  }
}
```

Ange bindningshändelse och värden för produktsträngen:

```json
"data": {
  "__adobe": {
    "analytics": {
      "events": "prodView",
      "products": ";Canary"
    }
  }
}
```
