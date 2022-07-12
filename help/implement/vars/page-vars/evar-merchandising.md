---
title: eVar-variabler
description: Egna variabler som knyts till enskilda produkter.
feature: Variables
exl-id: 26e0c4cd-3831-4572-afe2-6cda46704ff3
mini-toc-levels: 3
source-git-commit: 9a94e910d4e837bb9808b5662beebe6214ed4174
workflow-type: tm+mt
source-wordcount: '523'
ht-degree: 0%

---

# eVar (Merchandising)

*Den här hjälpsidan beskriver hur du implementerar eVars för varuexponering. Mer information om hur eVars marknadsförs fungerar som en dimension finns i [eVars (Merchandising)](/help/components/dimensions/evar-merchandising.md) i användarhandboken för komponenter.*

Mer information om hur du marknadsför eVars finns i [Merchandising eVars and product finding methods](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/conversion-variables/merchandising-evars.html?lang=en).

## Konfigurera eVars i inställningarna för rapportsviten

Innan du använder eVars i implementeringen måste du konfigurera eVar till önskad syntax i rapportsvitens inställningar. Se [Konverteringsvariabler](/help/admin/admin/conversion-var-admin/conversion-var-admin.md) i administrationshandboken.

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

Värdet för `eVar1` har tilldelats produkten. Alla efterföljande lyckade händelser som berör den här produkten krediteras eVar.

### Använda XDM för Edge Collection

Varje fält i variabeln&quot;products&quot; fylls i med ett motsvarande XDM-fält. Du kan se en lista över alla mappningar från XDM till analysparametrar [här](https://experienceleague.adobe.com/docs/analytics/implementation/aep-edge/variable-mapping.html?lang=en). Nedan visas ett exempel som visar hur XDM-fälten productListItems kombineras för att skapa en produktvariabel.

XDM-struktur:

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

Resultatparametern &quot;products&quot; skickades till Analytics:

```js
pl = ”;Bahama Shirt;3;12.99;event4|event10=2:abcd;eVar10=green|eVar33=large”
```

## Implementera med konverteringsvariabelsyntax

Konverteringsvariabelsyntaxen används när eVar inte är tillgängligt för att anges i `products` variabel. Det här scenariot innebär vanligtvis att sidan inte har något sammanhang för försäljningskanalen eller sökmetoden. I dessa fall ställer du in variabeln för försäljning innan du kommer till produktsidan, och värdet kvarstår tills bindningshändelsen inträffar.

När bindningshändelsen som väljs under konfigurationen inträffar, associeras det beständiga värdet för eVar med produkten. Om `prodView` anges som bindningshändelse, är marknadsföringskategorin knuten till den aktuella produktlistan endast när händelsen inträffar. Endast efterföljande bindningshändelser kan uppdatera en försäljningsprodukt som redan har tilldelats en eVar.

```js
// Place on the same or previous page before the binding event:
s.eVar1 = "Aviary";

// Place on the page where the binding event occurs:
s.events = "prodView";
s.products = ";Canary";
```

Värdet `"Aviary"` for `eVar1` har tilldelats produkten `"Canary"`. Alla efterföljande lyckade händelser som berör den här produkten krediteras `"Canary"`. Dessutom är det aktuella värdet av variabeln merchandising knutet till alla efterföljande produkter tills något av följande villkor uppfylls:

* eVar förfaller (baserat på inställningen &quot;Förfaller efter&quot;)
* eVar för försäljning skrivs över med ett nytt värde.

### Använda XDM för Edge Collection

Du kan ange samma information med hjälp av XDM-fält som mappas till Analytics-fält. Du kan se en lista över alla mappningar från XDM till analysparametrar [här](https://experienceleague.adobe.com/docs/analytics/implementation/aep-edge/variable-mapping.html?lang=en). XDM-speglingen av exemplet ovan skulle se ut så här:

Ange eVar för samma eller föregående händelseanrop:

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
