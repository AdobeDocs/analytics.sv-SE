---
title: händelser
description: Ange variabeln events, som styr de flesta mätvärden på din webbplats.
exl-id: 6ef99ee5-40c3-4ff2-a75d-c97f2e8ec1f8
source-git-commit: 1a49c2a6d90fc670bd0646d6d40738a87b74b8eb
workflow-type: tm+mt
source-wordcount: '668'
ht-degree: 0%

---

# händelser

Dimensioner och mätvärden är viktiga komponenter i rapporter. Variabeln `events` ansvarar för datainsamling av många mätvärden på din webbplats. Händelser ökar vanligtvis [måtten](/help/components/metrics/overview.md) i rapporter.

Innan du implementerar händelser måste du skapa och konfigurera dem under [Slutförda händelser](/help/admin/admin/c-success-events/success-event.md) i inställningarna för rapportsviten. Om du tänker använda anpassade händelser i länkspårningsträffar måste du se till att [`linkTrackVars`](../../config-vars/linktrackvars.md) och [`linkTrackEvents`](../../config-vars/linktrackevents.md) är rätt inställda.

## Händelser som använder taggar i Adobe Experience Platform

Du kan ange händelser antingen när du konfigurerar Analytics-tillägget (globala variabler) eller under regler.

1. Logga in på [användargränssnittet för datainsamling](https://experience.adobe.com/data-collection) med inloggningsuppgifterna för ditt Adobe-ID.
2. Klicka på önskad egenskap.
3. Gå till fliken [!UICONTROL Rules] och klicka sedan på önskad regel (eller skapa en regel).
4. Klicka på en befintlig [!UICONTROL Adobe Analytics - Set Variables]-åtgärd under [!UICONTROL Actions] eller klicka på +-ikonen.
5. Ange listrutan [!UICONTROL Extension] till Adobe Analytics och [!UICONTROL Action Type] till [!UICONTROL Set Variables].
6. Gå till avsnittet [!UICONTROL Events].

Flera funktioner är tillgängliga:

* I en listruta kan du välja vilken händelse som ska inkluderas
* Ett valfritt textfält för serialisering. Mer information finns i [händelseserialisering](event-serialization.md).
* Ett valfritt textfält för ett händelsevärde. Du kan inkludera valuta för valutakurshändelser eller ett heltal för händelser som inte är valutaväxlar om du vill öka den flera gånger. Om du t.ex. väljer `event1` under listrutan och tar med `10` i det här fältet ökas `event1` med 10 i rapporteringen.
* En knapp för att lägga till en annan händelse. Det finns ingen rimlig gräns för hur många händelser du kan inkludera i en träff.

## s.events i AppMeasurement och anpassad kodredigerare

Variabeln `s.events` är en sträng som innehåller en kommaavgränsad lista med händelser som ska ingå i träffen. Det finns ingen bytegräns för den här variabeln, så den trunkeras inte. Giltiga värden är:

* `event1` -  `event1000`: Ange anpassade händelser hur du vill. Registrera hur du använder varje händelse i organisationens [lösningsdesigndokument](../../../prepare/solution-design.md). Antalet tillgängliga händelser beror på organisationens Analytics-kontrakt. De flesta organisationer som har kontrakt som inte är äldre har 1 000 anpassade händelser tillgängliga. Kontakta din organisations kontoansvarige om du inte är säker på hur många anpassade händelser som är tillgängliga för dig.
* `purchase`: Ökar  [orderns ](/help/components/metrics/orders.md) mätvärde med 1 och tar värden som anges i  `products` variabeln för att beräkna  [&#39;Enheter&#39;](/help/components/metrics/units.md) och  [&#39;Intäkter&#39;](/help/components/metrics/revenue.md). Mer information finns i [purchase event](event-purchase.md).
* `prodView`: Ökar  [måtten för ](/help/components/metrics/product-views.md) produktvyer.
* `scOpen`: Ökar  [&#39;Carts&#39;](/help/components/metrics/carts.md) metric.
* `scAdd`: Ökar  [måtten för ](/help/components/metrics/cart-additions.md) &quot;Cart Additions&quot;.
* `scRemove`: Ökar  [Cart Removals ](/help/components/metrics/cart-removals.md) metric.
* `scView`: Ökar  [Cart Views ](/help/components/metrics/cart-views.md) mått.
* `scCheckout`: Ökar  [måttet ](/help/components/metrics/checkouts.md) &#39;Utcheckningar&#39;.

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

Du kan ändra en anpassad händelse så att den använder valuta i stället för heltal. Valutahändelser konverteras automatiskt till rapportsvitens valuta om rapportsvitens valuta och variabeln `currencyCode` inte stämmer överens. De är användbara för att beräkna fraktkostnader, rabatter eller återbetalningar. Du kan ange valutakändelser i variabeln `products` om du vill att händelsen bara ska vara den produkten.

Innan du implementerar valutakändelser måste du se till att du ställer in den önskade händelsen på Currency under [Success events](/help/admin/admin/c-success-events/success-event.md) i inställningarna för rapportsviten.

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
>Om du anger ett valutavärde i både variabeln `events` och variabeln `products` används valutavärdet i `events`. Undvik att ange valutavärden i både `events`- och `products`-variablerna.

### Använd numeriska händelser

Du kan ändra en anpassad händelse och acceptera decimalvärden i stället för heltal. Numeriska händelser fungerar på ungefär samma sätt som valutakändelser, förutom att de inte använder valutakonvertering. Du kan ange numeriska händelser i variabeln `products` om du vill att händelsen bara ska vara den produkten.

Innan du implementerar numeriska händelser bör du kontrollera att du har angett den önskade händelsen till Numeric under [Success events](/help/admin/admin/c-success-events/success-event.md) i inställningarna för rapportsviten.

```js
// Send 4.5 in event1 using the events variable. Make sure the event type for event1 is Numeric in Report suite settings
s.events = "event1=4.5";

// Send 4.5 in event1 using the products variable. Make sure the event type for event1 is Numeric in Report suite settings
s.events = "event1";
s.products = "Example category;Example product;1;0;event1=4.5";
```

>[!NOTE]
>
>Om du anger ett numeriskt värde i både variabeln `events` och variabeln `products` används det numeriska värdet i `events`. Undvik att ange numeriska värden i både `events`- och `products`-variablerna.
