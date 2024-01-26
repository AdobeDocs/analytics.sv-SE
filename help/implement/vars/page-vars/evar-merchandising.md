---
title: eVar (variabeln Merchandising)
description: Egna variabler som knyts till enskilda produkter.
feature: Variables
exl-id: 26e0c4cd-3831-4572-afe2-6cda46704ff3
mini-toc-levels: 3
role: Admin, Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '528'
ht-degree: 0%

---

# eVar (varuexponering)

*Den här hjälpsidan beskriver hur du implementerar eVars för varuexponering. Mer information om hur eVars marknadsförs fungerar som en dimension finns i [eVars (marknadsföringsdimension)](/help/components/dimensions/evar-merchandising.md) i användarhandboken för komponenter.*

Mer information om hur du marknadsför eVars finns i [Merchandising eVars and product finding methods](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/conversion-variables/merchandising-evars.html).

## Konfigurera eVars i inställningarna för rapportsviten

Innan du använder eVars i implementeringen måste du konfigurera eVarna till önskad syntax i rapportsvitens inställningar. Se [Konverteringsvariabler](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/conversion-var-admin.md) i administrationshandboken.

>[!WARNING]
>
>Om det inte går att konfigurera eVars för försäljning korrekt resulterar det i oväntade värden eller dataförlust för variabeln. Kontrollera att den är korrekt konfigurerad för din implementering.

## Implementera med produktsyntax

När Produktsyntax är aktiverad fylls kategorin i direkt i `products` -variabel, så det är inte nödvändigt att välja och ställa in en bindningshändelse. Detta är den rekommenderade metoden och bör användas om inte värdet är tillgängligt för att anges i `products` när framgångshändelsen äger rum.

```js
// The bare minimum to set a merchandising eVar with product syntax
s.products = ";Example product;;;;eVar1=Example merchandising value";

// An example single product with product syntax
s.products = "Example category;Example product;1;5.99;event1=1;eVar1=Turtles";

// Tie a merchandising eVar to a different values on two different products
s.products = "Birds;Scarlet Macaw;1;4200;;eVar1=talking bird,Birds;Turtle dove;2;550;;eVar1=love birds";
```

Värdet för `eVar1` är tilldelad produkten. Alla efterföljande lyckade händelser som berör den här produkten krediteras eVarna.

### Produktsyntax med Web SDK

Variabler för produktsyntax: [mappas för Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/implementation/aep-edge/variable-mapping.html) under flera olika XDM-fält.

* Produktsyntaxmarknadsföring eVars mappas under `productListItems[]._experience.analytics.customDimensions.eVars.eVar1` till `productListItems[]._experience.analytics.customDimensions.eVars.eVar250`.
* Försäljningshändelser för produktsyntax mappas under `productListItems[]._experience.analytics.event1to100.event1.value` till `productListItems[]._experience.analytics.event901to1000.event1000.value`. [Händelseserialisering](events/event-serialization.md) XDM-fält mappas under `productListItems[]._experience.analytics.event1to100.event1.id` till `productListItems[]._experience.analytics.event901to1000.event1000.id`.

>[!NOTE]
>
>När du anger händelser under `productListItems`behöver du inte ange dem i händelsesträngen. Om de anges på båda platserna har värdet i händelsesträngen företräde.

I följande exempel visas en [produkt](products.md) använda flera eVars och events:

```js
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

## Implementera med konverteringsvariabelsyntax

Konverteringsvariabelsyntaxen används när eVarna inte är tillgänglig för att anges i `products` variabel. Det här scenariot innebär vanligtvis att sidan inte har något sammanhang för försäljningskanalen eller sökmetoden. I dessa fall ställer du in variabeln för försäljning innan du kommer till produktsidan, och värdet kvarstår tills bindningshändelsen inträffar.

När bindningshändelsen som valts under konfigurationen inträffar, kopplas eVarnas beständiga värde till produkten. Om `prodView` anges som bindningshändelse, är marknadsföringskategorin knuten till den aktuella produktlistan endast när händelsen inträffar. Endast efterföljande bindningshändelser kan uppdatera en eVar som redan har tilldelats en produkt.

```js
// Place on the same or previous page before the binding event:
s.eVar1 = "Aviary";

// Place on the page where the binding event occurs:
s.events = "prodView";
s.products = ";Canary";
```

Värdet `"Aviary"` for `eVar1` har tilldelats produkten `"Canary"`. Alla efterföljande lyckade händelser som berör den här produkten krediteras `"Canary"`. Dessutom är det aktuella värdet av variabeln merchandising knutet till alla efterföljande produkter tills något av följande villkor uppfylls:

* EVarna förfaller (baserat på inställningen &quot;Förfaller efter&quot;)
* Försäljningsvärdet skrivs över med ett nytt eVar.

### Konvertera variabelsyntax med Web SDK

Konvertering av variabelsyntax med Web SDK fungerar på samma sätt som implementering av andra [eVars](evar.md) och [händelser](events/events-overview.md). XDM-speglingen av exemplet ovan skulle se ut så här:

Ange eVarna för samma eller föregående händelseanrop:

```js
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

```js
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
