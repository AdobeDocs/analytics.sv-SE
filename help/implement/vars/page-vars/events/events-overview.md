---
title: händelser
description: Ange variabeln events, som styr de flesta mätvärden på din webbplats.
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '580'
ht-degree: 0%

---


# händelser

Dimensioner och mätvärden är viktiga komponenter i rapporter. Variabeln `events` används för datainsamling av många mätvärden på din webbplats.

## Händelser i Adobe Experience Platform Launch

Du kan ange händelser antingen när du konfigurerar Analytics-tillägget (globala variabler) eller enligt regler.

1. Logga in på [launch.adobe.com](https://launch.adobe.com) med inloggningsuppgifterna för ditt AdobeID.
2. Klicka på önskad egenskap.
3. Gå till [!UICONTROL Rules] fliken och klicka sedan på önskad regel (eller skapa en regel).
4. Under [!UICONTROL Actions]klickar du på en befintlig [!UICONTROL Adobe Analytics - Set Variables] åtgärd eller på +-ikonen.
5. Ställ in listrutan [!UICONTROL Extension] på Adobe Analytics och [!UICONTROL Action Type] till [!UICONTROL Set Variables].
6. Leta rätt på [!UICONTROL Events] avsnittet.

Flera funktioner är tillgängliga:

* I en listruta kan du välja vilken händelse som ska inkluderas
* Ett valfritt textfält för serialisering. Mer information finns i [händelseserialisering](event-serialization.md) .
* Ett valfritt textfält för ett händelsevärde. Du kan inkludera valuta för valutakurshändelser eller ett heltal för händelser som inte är valutaväxlar om du vill öka den flera gånger. Om du till exempel väljer `event1` under listrutan och inkluderar `10` i det här fältet ökas `event1` med 10 i rapporteringen.
* En knapp för att lägga till en annan händelse. Det finns ingen rimlig gräns för hur många händelser du kan inkludera i en träff.

## s.events i AppMeasurement and Launch custom code editor

Variabeln `s.events` är en sträng som innehåller en kommaavgränsad lista med händelser som ska ingå i träffen. Det finns ingen bytegräns för den här variabeln, så den trunkeras inte. Giltiga värden är:

* `event1` - `event1000`: Ange anpassade händelser hur du vill. Registrera hur du använder varje händelse i organisationens [lösningsdesigndokument](../../../prepare/solution-design.md). Antalet tillgängliga händelser beror på organisationens Analytics-kontrakt. De flesta organisationer som har kontrakt som inte är äldre har 1 000 anpassade händelser tillgängliga. Kontakta din organisations kontoansvarige om du inte är säker på hur många anpassade händelser som är tillgängliga för dig.
* `purchase`: Ökar [orderns](/help/components/metrics/orders.md) mätvärde med 1 och tar värden som anges i `products` variabeln för att beräkna [&#39;Enheter&#39;](/help/components/metrics/units.md) och [&#39;Intäkter&#39;](/help/components/metrics/revenue.md). Se [köphändelse](event-purchase.md) för mer information.
* `prodView`: Ökar måttet för [&#39;Produktvyer&#39;](/help/components/metrics/product-views.md) .
* `scOpen`: Ökar [&#39;Carts&#39;](/help/components/metrics/carts.md) -måttet.
* `scAdd`: Ökar måttet för [inledande](/help/components/metrics/cart-additions.md) tillägg.
* `scRemove`: Ökar måttet [&quot;Cart Removals&quot;](/help/components/metrics/cart-removals.md) .
* `scView`: Ökar måttet för [kundvagnsvyer](/help/components/metrics/cart-views.md) .
* `scCheckout`: Ökar måttet [&quot;Utcheckningar&quot;](/help/components/metrics/checkouts.md) .

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

Du kan ändra en anpassad händelse så att den använder valuta i stället för heltal. Valutahändelser konverteras automatiskt till rapportsvitens valuta om rapportsvitens valuta och `currencyCode` variabeln inte stämmer överens. De är användbara för att beräkna fraktkostnader, rabatter eller återbetalningar. Du kan ange valutakändelser i `products` variabeln om du bara vill tilldela händelsen till den produkten.

```js
// Send $9.99 USD in event1 using the events variable. Make sure the event type for event1 is Currency in report suite settings
s.currencyCode = "USD";
s.events = "event1=9.99";

// Send $9.99 USD in event1 using the products variable. Make sure the event type for event1 is Currency in report suite settings
s.currencyCode = "USD";
s.events = "event1";
s.products = "Example category;Example product;1;0;event1=9.99";
```

>[!NOTE]
>
>Om du anger ett valutavärde i både `events` -variabeln och `products` -variabeln `events` används valutavärdet i. Undvik att ange valutavärden i både `events` - och `products` -variabler.

### Använd numeriska händelser

Du kan ändra en anpassad händelse och acceptera decimalvärden i stället för heltal. Numeriska händelser fungerar på ungefär samma sätt som valutakändelser, förutom att de inte använder valutakonvertering. Du kan ange numeriska händelser i `products` variabeln om du vill att händelsen bara ska vara den produkten.

```js
// Send 4.5 in event1 using the events variable. Make sure the event type for event1 is Numeric in report suite settings
s.events = "event1=4.5";

// Send 4.5 in event1 using the products variable. Make sure the event type for event1 is Numeric in report suite settings
s.events = "event1";
s.products = "Example category;Example product;1;0;event1=4.5";
```

>[!NOTE]
>
>Om du anger ett numeriskt värde i både variabeln `events` och `products` variabeln `events` används det numeriska värdet i. Undvik att ange numeriska värden i både `events` - och `products` -variabler.
