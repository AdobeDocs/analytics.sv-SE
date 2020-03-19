---
title: produkter
description: Skicka data runt vilka produkter som visas eller i kundvagnen.
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# produkter

Variabeln `products` spårar produkter och egenskaper som är knutna till dem. Den här variabeln ställs vanligtvis in på enskilda produktsidor, kundvagnssidor och bekräftelsesidor för inköp. Det är en variabel med flera värden, vilket innebär att du kan skicka flera produkter i samma träff och Adobe tolkar värdet i separata dimensionsvärden.

> [!NOTE] Om den här variabeln anges i en träff utan en kundvagnshändelse i [`events`](events/events-overview.md) variabeln ökar måttet&quot;Produktvyer&quot; med 1. Se till att du ställer in rätt kundvagnshändelse för varje träff.

## Produkter i Adobe Experience Platform Launch

Det finns inget dedikerat fält i Launch för att ställa in den här variabeln. Det finns dock flera tillägg från tredje part som kan vara till hjälp.

1. Logga in på [launch.adobe.com](https://launch.adobe.com) med inloggningsuppgifterna för ditt AdobeID.
2. Klicka på önskad egenskap.
3. Gå till [!UICONTROL Extensions] fliken och klicka sedan på [!UICONTROL Catalog] för att visa alla tillgängliga tillägg.
4. Sök efter termen &quot;product&quot;, som visar flera tillgängliga tillägg som kan hjälpa dig att ange variabeln.

Du kan använda något av dessa tillägg eller så kan du använda den anpassade kodredigeraren efter AppMeasurement-syntaxen nedan.

## s.products in AppMeasurement and Launch custom code editor

Variabeln `s.products` är en sträng som innehåller flera avgränsade fält per produkt. Varje enskild produkt kan innehålla upp till 100 byte i alla fält. Avgränsa varje fält med ett semikolon (`;`) i strängen.

* **Kategori** (valfritt): Den övergripande produktkategorin. Din organisation bestämmer hur produkter ska grupperas i kategorier.
* **Produktnamn** (obligatoriskt): Produktens namn.
* **Kvantitet** (valfritt): Hur många av dessa produkter finns i varukorgen. Det här fältet gäller endast för träffar med händelsen purchase.
* **Pris** (valfritt): Produktens totala pris i decimalform. Om kvantiteten är mer än en, ange priset till det totala och inte till det enskilda produktpriset. Justera valutan för det här värdet så att den matchar [`currencyCode`](../config-vars/currencycode.md) variabeln. Inkludera inte valutasymbolen i det här fältet. Det här fältet gäller endast för träffar med händelsen purchase.
* **Händelser** (valfritt): Händelser som är kopplade till produkten. Avgränsa flera händelser med en pipe (`|`). Mer information finns i [Händelser](events/events-overview.md) .
* **eVars** (valfritt): Merchandising eVars knutna till produkten. Avgränsa flera eVars-handlare med ett rör (`|`). Mer information finns i [Varor](../../../components/c-variables/c-merch-variables/var-merchandising.md) .

```js
// Set a single product using all available fields
s.products = "Example category;Example product;1;3.50;event1=4.99|event2=5.99;eVar1=Example merchandising value 1|eVar2=Example merchandising value 2";
```

Den här variabeln har stöd för flera produkter i samma träff. Det är värdefullt för kundvagn och inköp som innehåller flera produkter. Även om det finns en gräns på 100 byte per produkt är den totala längden för `products` variabeln 64 kB. Separera varje produkt med ett komma (`,`) i strängen.

```js
// Set multiple products - useful for when a visitor views their shopping cart
s.products = "Example category 1;Example product 1;1;3.50,Example category 2;Example product 2,1,5.99";
```

> [!IMPORTANT] Ta bort alla semikolon, komman och rör från produktnamn, kategorier och eVar-värden. Om ett produktnamn innehåller kommatecken tolkas det som början av en ny produkt i AppMeasurement. Denna felaktiga tolkning leder till att resten av produktsträngen avbryts, vilket ger felaktiga data i dimensioner och rapporter.

## Exempel

Variabeln är flexibel när du utelämnar fält och inkluderar flera produkter. `products` Denna flexibilitet kan göra det enkelt att missa en avgränsare, vilket gör att implementeringen skickar felaktiga data till Adobe.

```js
// Include only product and category. Common on individual product pages
s.products = "Example category;Example product";

// Include only product name if you do not want to use product category
s.products = ";Example product";

// One product has a category, the other does not. Note the comma and adjacent semicolon to omit category
s.products = "Example category;Example product,;Example product";

// A visitor purchases a single product; record quantity and price
s.events = "purchase";
s.products = "Example category;Example product;1;6.99";

// A visitor purchases multiple products with different quantities
s.events = "purchase";
s.products = "Example category;Example product 1;9;26.91,Example category;Example product 2;4;9.96";

// Attribute currency event1 only to product 2 and not product 1
s.events = "event1";
s.products = "Example category 1;Example product 1;1;1.99,Example category 2;Example product 2;1;2.69;event1=1.29";

// Use multiple numeric events in the product string
s.events = "event1,event2";
s.products = "Example category;Example product;1;4.20;event1=2.3|event2=5";

// Use merchandising eVars without any events. Note the adjacent semicolons to skip events
s.products = "Example category;Example product;1;6.69;;eVar1=Merchandising value";

// Use merchandising eVars without category, quantity, price, or events
s.products = ";Example product;;;;eVar1=Merchandising value";

// Multiple products using multiple different events and multiple different merchandising eVars
s.events = "event1,event2,event3,event4,purchase";
s.products = "Example category 1;Example product 1;3;12.60;event1=1.4|event2=9;eVar1=Merchandising value|eVar2=Another merchandising value,Example category 2;Example product 2;1;59.99;event3=6.99|event4=1;eVar3=Merchandising value 3|eVar4=Example value four";
```
