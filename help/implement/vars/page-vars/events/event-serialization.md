---
title: Händelseserialisering
description: Hjälper dig att deduplicera mätvärden på din webbplats.
feature: Variables
exl-id: 54de0fd7-9056-44af-bd59-b8eb55fc816e
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '401'
ht-degree: 0%

---

# Händelse-ID-serialisering

Händelseserialisering är processen att implementera åtgärder för att förhindra att dubbletthändelser anges i analysrapporter. Det är viktigt att deduplicera händelser i fall där du inte vill att besökarna ska uppdatera sidan ska få statistik som ökar.

>[!NOTE]
>
>Datakällor stöder inte händelseserialisering eller borttagning av dubbletter.

## Konfigurera händelseserialisering

Du måste först ange en händelses [!UICONTROL Unique Event Recording] till [!UICONTROL Use Event ID] i rapportsvitens inställningar. Se [Success Events](/help/admin/admin/c-success-events/success-event.md) i användarhandboken för Admin.

När du använder händelse-ID:n utförs borttagning av dubbletter på följande nivåer:

* Varje variabel använder sin egen tabell för borttagning av dubbletter. Till exempel: `event1:ABC` och `event2:ABC` räknas båda i rapporteringen.
* Deduplicering sker globalt för alla besökare. Om besökare A skickar `event1:ABC` besökare B skickar också `event1:ABC`ignorerar Adobe den andra instansen från besökaren B.
* Borttagning av dubbletter upphör inte att gälla. Om en besökare skickar `event1:ABC` kommer tillbaka 2 år senare och skickar `event1:ABC` Adobe ignorerar återigen den andra instansen.

>[!TIP]
>
>Om du vill deduplicera [`purchase`](event-purchase.md) -händelse, använd [`purchaseID`](../purchaseid.md) i stället.

## Använd händelse-ID:n med Web SDK

Händelseserialiseringen är [mappas för Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/implementation/aep-edge/variable-mapping.html) under den önskade händelsens XDM-fält `id`. Den fullständiga XDM-sökvägen beror på vilken händelse du vill serialisera.

Om du till exempel vill serialisera måttet för kundvagnstillägg anger du `commerce.productListAdds.id` XDM-fält till önskat serialiseringsvärde. Om du vill serialisera anpassad händelse 20 anger du `_experience.analytics.event1to100.event20` XDM-fält till önskat serialiseringsvärde.

## Använd händelse-ID:n med Adobe Analytics-tillägget

Du kan ange fältet för händelse-ID när du konfigurerar Analytics-tillägget (globala variabler) eller som en åtgärd i en regel.

1. Logga in på [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) med inloggningsuppgifterna för ditt AdobeID.
2. Klicka på den önskade taggegenskapen.
3. Gå till [!UICONTROL Rules] och sedan klicka på önskad regel (eller skapa en regel).
4. Under [!UICONTROL Actions]klickar du på en befintlig [!UICONTROL Adobe Analytics - Set Variables] eller klicka på +-ikonen.
5. Ange [!UICONTROL Extension] till Adobe Analytics och [!UICONTROL Action Type] till [!UICONTROL Set Variables].
6. Leta reda på [!UICONTROL Events] -avsnitt, där varje händelse innehåller [!UICONTROL Event ID] fält.

Giltiga värden är alfanumeriska tecken som är upp till 20 byte långa. Om du anger ett värde som är längre än 20 byte trunkeras det till de första 20 byten.

## Använd händelse-ID:n i AppMeasurement och den anpassade kodredigeraren för Analytics-tillägget

Händelseserialisering är en del av `s.events` variabel. Tilldela ett ID till varje händelse med ett kolon i strängen.

```js
// Assign custom ID serialization to a single value
s.events = "event1:ABC123";

// Assign custom ID serialization to multiple values
s.events = "event1:ABC123,event2:ABC123";
```

Om en händelse har serialisering aktiverat men inte innehåller något serialiserings-ID räknas alltid händelsen.
