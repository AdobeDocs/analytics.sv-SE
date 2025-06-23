---
title: händelser
description: Ange variabeln events, som styr de flesta mätvärden på din webbplats.
feature: Appmeasurement Implementation
exl-id: 6ef99ee5-40c3-4ff2-a75d-c97f2e8ec1f8
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '833'
ht-degree: 0%

---

# händelser

Dimensioner och mätvärden är viktiga komponenter i rapporter. Variabeln `events` ansvarar för datainsamling av många mätvärden på din webbplats. Händelser ökar vanligtvis [måtten](/help/components/metrics/overview.md) i rapporter.

Innan du implementerar händelser måste du skapa och konfigurera dem under [Slutförda händelser](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/c-success-events/success-event.md) i inställningarna för rapportsviten. Om du tänker använda anpassade händelser i länkspårningsträffar kontrollerar du att [`linkTrackVars`](../../config-vars/linktrackvars.md) och [`linkTrackEvents`](../../config-vars/linktrackevents.md) har angetts korrekt.

## Evenemang som använder Web SDK

Om du använder [XDM-objektet](/help/implement/aep-edge/xdm-var-mapping.md) använder anpassade händelser följande XDM-fält:

* Anpassade händelser 1-100 mappas till `xdm._experience.analytics.event1to100.event1` - `xdm._experience.analytics.event1to100.event100`.
* Anpassade händelser 101-200 mappas till `xdm._experience.analytics.event101to200.event100` - `xdm._experience.analytics.event101to200.event200`.
* Det här mönstret upprepas var 100:e händelse till `xdm._experience.analytics.event901to1000.event901` - `xdm._experience.analytics.event901to1000.event1000`. `eventx.value` används för att ange mängden som ska ökas. `eventx.id` används för [serialisering](event-serialization.md).
* Beställningar har mappats till `xdm.commerce.purchases.value`.
* Enheter mappas till summan av alla `productListItems[].quantity` fält.
* Intäkter mappas till summan av alla `productListItems[].priceTotal` fält.
* Produktvyer har mappats till `xdm.commerce.productViews.value`.
* Kortplatser har mappats till `xdm.commerce.productListOpens.value`.
* Kundvagnstillägg mappas till `xdm.commerce.productListAdds.value`.
* Cart Removals är mappade till `xdm.commerce.productListRemovals.value`.
* Vyer för kundvagn mappas till `xdm.commerce.productListViews.value`.
* Utcheckningar har mappats till `xdm.commerce.checkouts.value`.

>[!NOTE]
>
>Om en händelse anges under `productListItems` (till exempel `productListItems._experience.analytics.event1.value`) och den händelsen ännu inte finns i det här fältet, läggs den händelsen automatiskt till i det här fältet.

Om du använder [**dataobjektet**](/help/implement/aep-edge/data-var-mapping.md) använder alla händelser `data.__adobe.analytics.events` och följer AppMeasurement strängsyntax. Om du anger det här fältet skrivs alla händelser som anges i XDM-objektet över och skickas inte till Adobe Analytics.

## Händelser som använder Adobe Analytics-tillägget

Du kan ange händelser antingen när du konfigurerar Analytics-tillägget (globala variabler) eller under regler.

1. Logga in på [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) med dina inloggningsuppgifter för AdobeID.
2. Klicka på den önskade taggegenskapen.
3. Gå till fliken [!UICONTROL Rules] och klicka sedan på önskad regel (eller skapa en regel).
4. Klicka på en befintlig [!UICONTROL Adobe Analytics - Set Variables]-åtgärd under [!UICONTROL Actions] eller klicka på +-ikonen.
5. Ange Adobe Analytics i listrutan [!UICONTROL Extension] och [!UICONTROL Action Type] till [!UICONTROL Set Variables].
6. Leta reda på avsnittet [!UICONTROL Events].

Flera funktioner är tillgängliga:

* En nedrullningsbar lista där du kan välja vilken händelse som ska inkluderas
* Ett valfritt textfält för serialisering. Mer information finns i [händelseserialisering](event-serialization.md).
* Ett valfritt textfält för ett händelsevärde. Du kan inkludera valuta för valutakurshändelser eller ett heltal för händelser som inte är valutaväxlar om du vill öka den flera gånger. Om du t.ex. väljer `event1` under listrutan och inkluderar `10` i det här fältet ökas `event1` med 10 i rapporteringen.
* En knapp för att lägga till en annan händelse. Du kan lägga till så många händelser som du vill för en enskild regel av olika skäl.

## s.events i AppMeasurement och den anpassade kodredigeraren för Analytics-tillägget

Variabeln `s.events` är en sträng som innehåller en kommaavgränsad lista med händelser som ska ingå i träffen. Variabeln tillåter upp till 64 000 byte, vilket ger så många händelser som en träff behöver. Giltiga värden är:

* `event1` - `event1000`: Ange anpassade händelser hur du vill. Registrera hur du använder varje händelse i din organisations [lösningsdesigndokument](../../../prepare/solution-design.md). Antalet tillgängliga händelser beror på organisationens Analytics-kontrakt. De flesta organisationer som har kontrakt som inte är äldre har 1 000 anpassade händelser tillgängliga. Kontakta ditt Adobe-kontoteam om du inte är säker på hur många anpassade händelser som är tillgängliga för dig.
* `purchase`: Ökar måttet [&#39;Orders&#39;](/help/components/metrics/orders.md) med 1 och tar värden som anges i variabeln `products` för att beräkna [&#39;Units&#39;](/help/components/metrics/units.md) och [&#39;Revenue&#39;](/help/components/metrics/revenue.md). Mer information finns i [köphändelse](event-purchase.md).
* `prodView`: Ökar måttet för [&#39;Produktvyer&#39;](/help/components/metrics/product-views.md).
* `scOpen`: Ökar måttet [&#39;Carts&#39;](/help/components/metrics/carts.md).
* `scAdd`: Ökar måttet [&#39;Cart Additions&#39; ](/help/components/metrics/cart-additions.md).
* `scRemove`: Ökar måttet [&#39;Cart Removals&#39;](/help/components/metrics/cart-removals.md).
* `scView`: Ökar måttet ](/help/components/metrics/cart-views.md) för [ kundvagnsvyer.
* `scCheckout`: Ökar måttet [&#39;Checkouts&#39;](/help/components/metrics/checkouts.md).

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

Du kan ändra en anpassad händelse så att den använder valuta i stället för heltal. Valutahändelser konverteras automatiskt till rapportsvitens valuta om rapportsvitens valuta och variabeln `currencyCode` inte matchar. De är användbara för att beräkna fraktkostnader, rabatter eller återbetalningar. Du kan ange valutakändelser i variabeln `products` om du bara vill tilldela händelsen till den produkten.

Innan du implementerar valutakändelser måste du se till att du ställer in den önskade händelsen på Currency under [Success events](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/c-success-events/success-event.md) i inställningarna för rapportsviten.

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
>Om du anger ett valutavärde i både variabeln `events` och variabeln `products` används valutavärdet i `events`. Undvik att ange valutavärden i både variabeln `events` och `products`.

### Använd numeriska händelser

Du kan ändra en anpassad händelse och acceptera decimalvärden i stället för heltal. Numeriska händelser fungerar på ungefär samma sätt som valutakändelser, förutom att de inte använder valutakonvertering. Du kan ange numeriska händelser i variabeln `products` om du vill att händelsen bara ska vara den produkten.

Innan du implementerar numeriska händelser bör du kontrollera att du har angett den önskade händelsen till Numeric under [Success events](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/c-success-events/success-event.md) i inställningarna för rapportsviten.

```js
// Send 4.5 in event1 using the events variable. Make sure the event type for event1 is Numeric in Report suite settings
s.events = "event1=4.5";

// Send 4.5 in event1 using the products variable. Make sure the event type for event1 is Numeric in Report suite settings
s.events = "event1";
s.products = "Example category;Example product;1;0;event1=4.5";
```

>[!NOTE]
>
>Om du anger ett numeriskt värde i både variabeln `events` och variabeln `products` används det numeriska värdet i `events`. Undvik att ange numeriska värden i både variabeln `events` och `products`.
