---
title: produkter
description: Skicka data runt vilka produkter som visas eller i kundvagnen.
feature: Variables
exl-id: f26e7c93-f0f1-470e-a7e5-0e310ec666c7
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '569'
ht-degree: 0%

---

# produkter

The `products` variabelspårar produkter och egenskaper som är knutna till dem. Den här variabeln ställs vanligtvis in på enskilda produktsidor, kundvagnssidor och bekräftelsesidor för inköp. Det är en variabel med flera värden, vilket innebär att du kan skicka flera produkter i samma träff och att Adobe tolkar värdet i separata dimensionsobjekt.

>[!NOTE]
>
>Om variabeln anges i en träff utan [`events`](events/events-overview.md) variabel, [Produktvyer](/help/components/metrics/product-views.md) måttsteg med 1. Se till att du anger lämpliga händelser för varje träff med `products` variabel.

## Produkter som använder Web SDK

Produkterna är [mappas för Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/implementation/aep-edge/variable-mapping.html) under flera XDM-fält:

* Kategorin är mappad till `productListItems[].name`.
* Produkten är mappad till `productListItems[]._id`.
* Kvantitet har mappats till `productListItems[].quantity`.
* Priset är mappat till `productListItems[].priceTotal`.
* Merchandising eVars mappas till `productListItems._experience.analytics.customDimensions.eVars.eVar1` till `productListItems._experience.analytics.customDimensions.eVars.eVar250`, beroende på vilken eVar du vill binda till en produkt.
* Marknadsföringshändelser mappas till `productListItems[]._experience.analytics.event1to100.event1.value` till `productListItems._experience.analytics.event901to1000.event1000.value`, beroende på vilken händelse du vill binda till en produkt.

## Produkter som använder Adobe Analytics-tillägget

Det finns inget dedikerat fält i Adobe Experience Platform Data Collection för att ställa in den här variabeln. Det finns dock flera tillägg från tredje part som kan vara till hjälp.

1. Logga in på [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) med inloggningsuppgifterna för ditt AdobeID.
2. Klicka på den önskade taggegenskapen.
3. Gå till [!UICONTROL Extensions] tabbtangenten och sedan klicka [!UICONTROL Catalog] om du vill se alla tillgängliga tillägg.
4. Sök efter termen &quot;product&quot;, som visar flera tillgängliga tillägg som kan hjälpa dig att ange variabeln.

Du kan använda något av dessa tillägg eller så kan du använda den anpassade kodredigeraren efter AppMeasurement-syntaxen nedan.

## s.products in AppMeasurement and the Analytics extension custom code editor

The `s.products` variabeln är en sträng som innehåller flera avgränsade fält per produkt. Avgränsa varje fält med ett semikolon (`;`) i strängen.

* **Kategori** (valfritt): Produktkategorin. Den maximala längden för det här fältet är 100 byte.
* **Produktnamn** (obligatoriskt): Produktens namn. Den maximala längden för det här fältet är 100 byte.
* **Kvantitet** (valfritt): Hur många av dessa produkter finns i varukorgen. Det här fältet gäller endast för träffar med händelsen purchase.
* **Pris** (valfritt): Produktens totala pris i decimalform. Om kvantiteten är mer än en, ange priset till det totala och inte till det enskilda produktpriset. Justera valutan för det här värdet så att den matchar [`currencyCode`](../config-vars/currencycode.md) variabel. Inkludera inte valutasymbolen i det här fältet. Det här fältet gäller endast för träffar med händelsen purchase.
* **Händelser** (valfritt): Händelser som är kopplade till produkten. Avgränsa flera händelser med en pipe (`|`). Se [händelser](events/events-overview.md) för mer information.
* **eVars** (valfritt): Merchandising eVars knutna till produkten. Avgränsa flera eVars-produkter för försäljning med ett rör (`|`). Se [varuexponering eVars](evar-merchandising.md) för mer information.

```js
// Set a single product using all available fields
s.products = "Example category;Example product;1;3.50;event1=4.99|event2=5.99;eVar1=Example merchandising value 1|eVar2=Example merchandising value 2";
```

Den här variabeln har stöd för flera produkter i samma träff. Det är värdefullt för kundvagn och inköp som innehåller flera produkter. Maximal längd för hela `products` strängen är 64 kB. Avgränsa varje produkt med kommatecken (`,`) i strängen.

```js
// Set multiple products - useful for when a visitor views their shopping cart
s.products = "Example category 1;Example product 1;1;3.50,Example category 2;Example product 2;1;5.99";
```

>[!WARNING]
>
>Ta bort alla semikolon, kommatecken och rör från produktnamn, kategorier och försäljningsvärden för eVar. Om ett produktnamn innehåller kommatecken tolkas det som början av en ny produkt i AppMeasurement. Denna felaktiga tolkning leder till att resten av produktsträngen avbryts, vilket ger felaktiga data i dimensioner och rapporter.

## Exempel

The `products` variabeln är flexibel när du utelämnar fält och inkluderar flera produkter. Denna flexibilitet kan göra det enkelt att missa en avgränsare, vilket gör att implementeringen skickar felaktiga data till Adobe.

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

Om du använder `digitalData` [datalager](../../prepare/data-layer.md)kan du iterera genom `digitalData.product` objektarray:

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
