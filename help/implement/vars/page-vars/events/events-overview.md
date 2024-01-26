---
title: händelser
description: Ange variabeln events, som styr de flesta mätvärden på din webbplats.
feature: Variables
exl-id: 6ef99ee5-40c3-4ff2-a75d-c97f2e8ec1f8
role: Admin, Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '802'
ht-degree: 0%

---

# händelser

Dimensioner och mätvärden är viktiga komponenter i rapporter. The `events` variabeln ansvarar för datainsamling av många mätvärden på din webbplats. Händelser som vanligen ökar [mått](/help/components/metrics/overview.md) i rapporter.

Innan du implementerar händelser måste du skapa och konfigurera dem under [Slutförda händelser](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/c-success-events/success-event.md) i Rapportsvitens inställningar. Om du tänker använda anpassade händelser i länkspårningstips måste du se till att [`linkTrackVars`](../../config-vars/linktrackvars.md) och [`linkTrackEvents`](../../config-vars/linktrackevents.md) är korrekt inställda.

## Händelser som använder Web SDK

Anpassade händelser är [mappas för Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/implementation/aep-edge/variable-mapping.html) under följande XDM-fält:

* Anpassade händelser 1-100 mappas till `_experience.analytics.event1to100.event1` - `_experience.analytics.event1to100.event100`.
* Anpassade händelser 101-200 mappas till `_experience.analytics.event101to200.event100` - `_experience.analytics.event101to200.event200`.
* Det här mönstret upprepas var 100:e händelse till `_experience.analytics.event901to1000.event901` - `_experience.analytics.event901to1000.event1000`. `eventx.value` används för att ange mängden som ska ökas. `eventx.id` används för [serialisering](event-serialization.md).
* Order mappas till `commerce.purchases.value`.
* Enheter mappas till summan av alla `productListItems[].quantity` fält.
* Intäkterna är mappade till summan av alla `productListItems[].priceTotal` fält.
* Produktvyer mappas till `commerce.productListViews.value`.
* Korten mappas till `commerce.productListOpens.value`.
* Kundtillägg mappas till `commerce.productListAdds.value`.
* Cart Removals är mappade till `commerce.productListRemovals.value`.
* Vyer för kundvagn mappas till `commerce.productListViews.value`.
* Utcheckningar är mappade till `commerce.checkouts.value`.

>[!NOTE]
>
>Om en händelse anges under `productListItems` (till exempel `productListItems._experience.analytics.event1.value`) och den händelsen ännu inte finns i det här fältet läggs händelsen automatiskt till i det här fältet.

## Händelser som använder Adobe Analytics-tillägget

Du kan ange händelser antingen när du konfigurerar Analytics-tillägget (globala variabler) eller under regler.

1. Logga in på [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) med inloggningsuppgifterna för ditt AdobeID.
2. Klicka på den önskade taggegenskapen.
3. Gå till [!UICONTROL Rules] och sedan klicka på önskad regel (eller skapa en regel).
4. Under [!UICONTROL Actions]klickar du på en befintlig [!UICONTROL Adobe Analytics - Set Variables] eller klicka på +-ikonen.
5. Ange [!UICONTROL Extension] nedrullningsbar lista till Adobe Analytics och [!UICONTROL Action Type] till [!UICONTROL Set Variables].
6. Leta reda på [!UICONTROL Events] -avsnitt.

Flera funktioner är tillgängliga:

* En nedrullningsbar lista där du kan välja vilken händelse som ska inkluderas
* Ett valfritt textfält för serialisering. Se [händelseserialisering](event-serialization.md) för mer information.
* Ett valfritt textfält för ett händelsevärde. Du kan inkludera valuta för valutakurshändelser eller ett heltal för händelser som inte är valutaväxlar om du vill öka den flera gånger. Välj till exempel `event1` i den nedrullningsbara listan med `10` i detta fält stegvis `event1` efter 10 i rapporteringen.
* En knapp för att lägga till en annan händelse. Du kan lägga till så många händelser som du vill för en enskild regel av olika skäl.

## s.events i AppMeasurementet och den anpassade kodredigeraren för Analytics-tillägget

The `s.events` variabeln är en sträng som innehåller en kommaavgränsad lista med händelser som ska ingå i träffen. Variabeln tillåter upp till 64 000 byte, vilket ger så många händelser som en träff behöver. Giltiga värden är:

* `event1` - `event1000`: Anpassade händelser, ange hur du vill. Registrera hur du använder varje händelse i organisationens [konstruktionsdokument](../../../prepare/solution-design.md). Antalet tillgängliga händelser beror på organisationens Analytics-kontrakt. De flesta organisationer som har kontrakt som inte är äldre har 1 000 anpassade händelser tillgängliga. Kontakta kontoteamet på Adobe om du inte är säker på hur många anpassade händelser som är tillgängliga för dig.
* `purchase`: Ökar [&#39;Beställningar&#39;](/help/components/metrics/orders.md) metrisk med 1 och tar värden som anges i `products` variabel som ska beräknas [&#39;Enheter&#39;](/help/components/metrics/units.md) och [Intäkter](/help/components/metrics/revenue.md). Se [köphändelse](event-purchase.md) för mer information.
* `prodView`: Ökar [&#39;Produktvyer&#39;](/help/components/metrics/product-views.md) mätvärden.
* `scOpen`: Ökar [&quot;Carts&quot;](/help/components/metrics/carts.md) mätvärden.
* `scAdd`: Ökar [&quot;Cart Additions&quot;](/help/components/metrics/cart-additions.md) mätvärden.
* `scRemove`: Ökar [&quot;Cart Removals&quot;](/help/components/metrics/cart-removals.md) mätvärden.
* `scView`: Ökar [&quot;Vyer för kundvagn&quot;](/help/components/metrics/cart-views.md) mätvärden.
* `scCheckout`: Ökar [&#39;Utcheckningar&#39;](/help/components/metrics/checkouts.md) mätvärden.

>[!NOTE]
>
>Den här variabeln är skiftlägeskänslig. Undvik att händelsevärden med felaktig skiftläge för att säkerställa korrekt datainsamling.

```js
// Set the events variable to a single value
s.events = "event1";

// Set the events variable to multiple values
s.events = "event1,event13,purchase";
```

### Öka räknarhändelser flera gånger

Du kan räkna anpassade händelser mer än en gång om du vill. Tilldela ett heltal till önskad händelse i strängen. Händelser som skapas i rapportsvitens inställningar är räknarhändelser som standard.

```js
// Count event1 ten times
s.events = "event1=10";

// Count event1 twice and event2 once
s.events = "event1=2,event2";
```

>[!NOTE]
>
>Räknarhändelser stöder inte valuta- eller decimalvärden. Använd valutakändelser för valuta eller numeriska händelser för decimalvärden.

### Använd valutakändelser

Du kan ändra en anpassad händelse så att den använder valuta i stället för heltal. Valutahändelser konverteras automatiskt till rapportsvitens valuta om rapportsvitens valuta och `currencyCode` variabeln matchar inte. De är användbara för att beräkna fraktkostnader, rabatter eller återbetalningar. Du kan ställa in valutatjänster i dialogrutan `products` om du vill att händelsen bara ska tilldelas den produkten.

Innan du implementerar valutakurser måste du ställa in den önskade händelsen till &quot;Valuta&quot; under [Slutförda händelser](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/c-success-events/success-event.md) i Rapportsvitens inställningar.

```js
// Send $9.99 USD in event1 using the events variable. Make sure the event type for event1 is Currency in Report suite settings
s.currencyCode = "USD";
s.events = "event1=9.99";

// Send $9.99 USD in event1 using the products variable. Make sure the event type for event1 is Currency in Report suite settings
s.currencyCode = "USD";
s.events = "event1";
s.products = "Example category;Example product;1;0;event1=9.99";
```

>[!NOTE]
>
>Om du anger ett valutavärde i båda `events` variabeln och `products` variabel, valutavärdet i `events` används. Undvik att ange valutavärden i båda `events` och `products` variabler.

### Använd numeriska händelser

Du kan ändra en anpassad händelse och acceptera decimalvärden i stället för heltal. Numeriska händelser fungerar på ungefär samma sätt som valutakändelser, förutom att de inte använder valutakonvertering. Du kan ange numeriska händelser i dialogrutan `products` om du vill att händelsen bara ska tilldelas den produkten.

Innan du implementerar numeriska händelser måste du ställa in den önskade händelsen på Numeric under [Slutförda händelser](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/c-success-events/success-event.md) i Rapportsvitens inställningar.

```js
// Send 4.5 in event1 using the events variable. Make sure the event type for event1 is Numeric in Report suite settings
s.events = "event1=4.5";

// Send 4.5 in event1 using the products variable. Make sure the event type for event1 is Numeric in Report suite settings
s.events = "event1";
s.products = "Example category;Example product;1;0;event1=4.5";
```

>[!NOTE]
>
>Om du anger ett numeriskt värde i båda `events` variabeln och `products` variabel, det numeriska värdet i `events` används. Undvik att ange numeriska värden i båda `events` och `products` variabler.
