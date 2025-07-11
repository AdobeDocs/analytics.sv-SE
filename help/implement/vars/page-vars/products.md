---
title: produkter
description: Skicka data runt vilka produkter som visas eller i kundvagnen.
feature: Appmeasurement Implementation
exl-id: f26e7c93-f0f1-470e-a7e5-0e310ec666c7
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '656'
ht-degree: 0%

---

# produkter

Variabeln `products` spårar produkter och egenskaper som är kopplade till dem. Den här variabeln ställs vanligtvis in på enskilda produktsidor, kundvagnssidor och bekräftelsesidor för inköp. Det är en variabel med flera värden, vilket innebär att du kan skicka flera produkter i samma träff och att Adobe tolkar värdet i separata dimensionsobjekt.

>[!NOTE]
>
>Om den här variabeln anges i en träff utan variabeln [`events`](events/events-overview.md) ökas måttet för [ produktvyer ](/help/components/metrics/product-views.md) med 1. Se till att du anger lämpliga händelser för varje träff med variabeln `products`.

## Produkter som använder Web SDK

Om du använder [**XDM-objektet**](/help/implement/aep-edge/xdm-var-mapping.md) mappas produkterna till följande variabler:

* Kategorin har mappats till `xdm.productListItems[].productCategories[].categoryID`. Det använder det första objektet i `productCategories[]`-arrayen. `lineItemId` mappar också korrekt, men Adobe rekommenderar `categoryID` eftersom det är standard-XDM. Om båda XDM-fälten finns har `lineItemId` företräde.
* Produkten är mappad till `xdm.productListItems[].SKU` eller `xdm.productListItems[].name`. Om båda XDM-fälten finns används `xdm.productListItems[].SKU`.
* Kvantitet har mappats till `xdm.productListItems[].quantity`.
* Priset har mappats till `xdm.productListItems[].priceTotal`.
* Marknadsföringsvariabler är mappade till `xdm.productListItems._experience.analytics.customDimensions.eVars.eVar1` till `xdm.productListItems._experience.analytics.customDimensions.eVars.eVar250`, beroende på vilken eVar du vill binda till en produkt.
* Marknadsföringshändelser mappas till `xdm.productListItems[]._experience.analytics.event1to100.event1.value` till `xdm.productListItems._experience.analytics.event901to1000.event1000.value`, beroende på vilken händelse du vill binda till en produkt. Om du anger en händelse i något av dessa fält inkluderas den automatiskt i strängen [event](events/events-overview.md) som skickas till Adobe Analytics.

```json
{
  "xdm": {
    "productListItems": [{
      "productCategories": [{
        "categoryID": "Men's"
      }],
      "name": "Hiking boot",
      "quantity": 1,
      "priceTotal": 49.99
    },
    {
      "productCategories": [{
        "categoryID": "Camping"
      }],
      "name": "Hunting blind",
      "quantity": 3,
      "priceTotal": 699.69
    }]
  }
}
```

Om du använder [**dataobjektet**](/help/implement/aep-edge/data-var-mapping.md) använder variabeln products `data.__adobe.analytics.products` efter AppMeasurement-syntax. Om du anger det här fältet skrivs alla produkter som anges i XDM-objektet över och skickas inte till Adobe Analytics.

```json
{
  "data": {
    "__adobe": {
      "analytics": {
        "products": "Archery;Fletched arrow;12;159.99"
      }
    }
  }
}
```

## Produkter som använder Adobe Analytics-tillägget

Det finns inget dedikerat fält i Adobe Experience Platform Data Collection för att ställa in den här variabeln, men det finns flera tredjepartstillägg som kan vara till hjälp.

1. Logga in på [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) med dina inloggningsuppgifter för AdobeID.
2. Klicka på den önskade taggegenskapen.
3. Gå till fliken [!UICONTROL Extensions] och klicka sedan på [!UICONTROL Catalog] för att visa alla tillgängliga tillägg.
4. Sök efter termen &quot;product&quot;, som visar flera tillgängliga tillägg som kan hjälpa dig att ange variabeln.

Du kan använda något av dessa tillägg eller så kan du använda den anpassade kodredigeraren enligt AppMeasurement syntax nedan.

## s.products in AppMeasurement and the Analytics extension custom code editor

Variabeln `s.products` är en sträng som innehåller flera avgränsade fält per produkt. Avgränsa varje fält med ett semikolon (`;`) i strängen.

* **Kategori** (valfritt): Produktkategorin. Den maximala längden för det här fältet är 100 byte.
* **Produktnamn** (obligatoriskt): Produktens namn. Den maximala längden för det här fältet är 100 byte.
* **Kvantitet** (valfritt): Hur många av den här produkten finns i kundvagnen. Det här fältet gäller endast för träffar med händelsen purchase.
* **Pris** (valfritt): produktens totala pris i decimalform. Om kvantiteten är mer än en, ange priset till det totala och inte till det enskilda produktpriset. Justera valutan för det här värdet så att den matchar variabeln [`currencyCode`](../config-vars/currencycode.md). Inkludera inte valutasymbolen i det här fältet. Det här fältet gäller endast för träffar med händelsen purchase.
* **Händelser** (valfritt): Händelser som är kopplade till produkten. Avgränsa flera händelser med en pipe (`|`). Mer information finns i [events](events/events-overview.md).
* **eVars** (valfritt): Merchandising eVars knutna till produkten. Avgränsa flera eVars-handlare med en pipe (`|`). Mer information finns i [Försäljning av eVars](evar-merchandising.md).

```js
// Set a single product using all available fields
s.products = "Example category;Example product;1;3.50;event1=4.99|event2=5.99;eVar1=Example merchandising value 1|eVar2=Example merchandising value 2";
```

Den här variabeln har stöd för flera produkter i samma träff. Det är värdefullt för kundvagn och inköp som innehåller flera produkter. Den maximala längden för hela strängen `products` är 64 kB. Avgränsa varje produkt med ett kommatecken (`,`) i strängen.

```js
// Set multiple products - useful for when a visitor views their shopping cart
s.products = "Example category 1;Example product 1;1;3.50,Example category 2;Example product 2;1;5.99";
```

>[!WARNING]
>
>Ta bort alla semikolon, komman och rör från produktnamn, kategorier och försäljning av eVar-värden. Om ett produktnamn innehåller kommatecken tolkar AppMeasurement det som början på en ny produkt. Denna felaktiga tolkning leder till att resten av produktsträngen avbryts, vilket ger felaktiga data i dimensioner och rapporter.

## Exempel

Variabeln `products` är flexibel när du utelämnar fält och inkluderar flera produkter. Denna flexibilitet kan göra det enkelt att missa en avgränsare, vilket gör att implementeringen skickar felaktiga data till Adobe.

```js
// Include only product and category. Common on individual product pages
s.products = "Example category;Example product";

// Include only product name
s.products = ";Example product";

// One product has a category, the other does not. Note the comma and adjacent semicolon to omit category
s.products = "Example category;Example product 1,;Example product 2";

// A visitor purchases a single product; record quantity and price
s.events = "purchase";
s.products = ";Example product;1;6.99";

// A visitor purchases multiple products with different quantities
s.events = "purchase";
s.products = ";Example product 1;9;26.91,Example category;Example product 2;4;9.96";

// Attribute currency event1 only to product 2 and not product 1
s.events = "event1";
s.products = ";Example product 1;1;1.99,Example category 2;Example product 2;1;2.69;event1=1.29";

// Use multiple numeric events in the product string
s.events = "event1,event2";
s.products = ";Example product;1;4.20;event1=2.3|event2=5";

// Use merchandising eVars without any events. Note the adjacent semicolons to skip events
s.products = ";Example product;1;6.69;;eVar1=Merchandising value";

// Use merchandising eVars without category, quantity, price, or events
s.products = ";Example product;;;;eVar1=Merchandising value";

// Multiple products using multiple different events and multiple different merchandising eVars
s.events = "event1,event2,event3,event4,purchase";
s.products = "Example category 1;Example product 1;3;12.60;event1=1.4|event2=9;eVar1=Merchandising value|eVar2=Another merchandising value,Example category 2;Example product 2;1;59.99;event3=6.99|event4=1;eVar3=Merchandising value 3|eVar4=Example value four";
```

Om du använder datalagret `digitalData` [data](../../prepare/data-layer.md) kan du iterera genom objektarrayen `digitalData.product`:

```js
for(var i = 0; i < digitalData.product.length; i++) {
    // Add individual product info to the product string
    s.products += digitalData.product[i].category.primaryCategory + ";" + digitalData.product[i].productInfo.productName;
    // If there are more products, add a comma
    if(i != digitalData.product.length - 1) {
        s.products += ",";
    }
}
```
