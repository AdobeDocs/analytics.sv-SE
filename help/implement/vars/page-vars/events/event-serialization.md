---
title: Händelseserialisering
description: Hjälper dig att deduplicera mätvärden på din webbplats.
exl-id: 54de0fd7-9056-44af-bd59-b8eb55fc816e
translation-type: tm+mt
source-git-commit: 71581f49eb7ef13577a05c05daee737eeb9e6218
workflow-type: tm+mt
source-wordcount: '317'
ht-degree: 1%

---

# Händelse-ID-serialisering

Händelseserialisering är processen att implementera åtgärder för att förhindra att dubbletthändelser anges i analysrapporter. Det är viktigt att deduplicera händelser i fall där du inte vill att besökarna ska uppdatera sidan ska få statistik som ökar.

>[!NOTE]
>
>Datakällor stöder inte händelseserialisering eller borttagning av dubbletter.

## Konfigurera händelseserialisering

Du måste först ange en händelses [!UICONTROL Unique Event Recording] till [!UICONTROL Use Event ID] i inställningarna för rapportsviten. Se [Success Events](/help/admin/admin/c-success-events/success-event.md) i användarhandboken för Admin.

När du använder händelse-ID:n utförs borttagning av dubbletter på följande nivåer:

* Varje variabel använder sin egen tabell för borttagning av dubbletter. Till exempel räknas både `event1:ABC` och `event2:ABC` i rapporteringen.
* Deduplicering sker globalt för alla besökare. Om besökare A skickar `event1:ABC`, skickar besökare B även `event1:ABC`, ignorerar Adobe den andra instansen från besökare B.
* Borttagning av dubbletter upphör inte att gälla. Om en besökare skickar `event1:ABC` och sedan kommer tillbaka två år senare och skickar `event1:ABC` igen, ignorerar Adobe den andra instansen.

>[!TIP]
>
>Om du vill avduplicera händelsen [`purchase`](event-purchase.md) ska du använda variabeln [`purchaseID`](../purchaseid.md) i stället.

## Använd händelse-ID:n i Adobe Experience Platform Launch

Du kan ange fältet för händelse-ID när du konfigurerar Analytics-tillägget (globala variabler) eller som en åtgärd i en regel.

1. Logga in på [launch.adobe.com](https://launch.adobe.com) med inloggningsuppgifterna för ditt Adobe-ID.
2. Klicka på önskad egenskap.
3. Gå till fliken [!UICONTROL Rules] och klicka sedan på önskad regel (eller skapa en regel).
4. Klicka på en befintlig [!UICONTROL Adobe Analytics - Set Variables]-åtgärd under [!UICONTROL Actions] eller klicka på +-ikonen.
5. Ange listrutan [!UICONTROL Extension] till Adobe Analytics och [!UICONTROL Action Type] till [!UICONTROL Set Variables].
6. Leta reda på avsnittet [!UICONTROL Events], där varje händelse innehåller ett [!UICONTROL Event ID]-fält.

Giltiga värden är alfanumeriska tecken som är upp till 20 byte långa. Om du anger ett värde som är längre än 20 byte trunkeras det till de första 20 byten.

## Använd händelse-ID:n i AppMeasurement och starta en anpassad kodredigerare

Händelseserialisering är en del av variabeln `s.events`. Tilldela ett ID till varje händelse med ett kolon i strängen.

```js
// Assign custom ID serialization to a single value
s.events = "event1:ABC123";

// Assign custom ID serialization to multiple values
s.events = "event1:ABC123,event2:ABC123";
```

Om en händelse har serialisering aktiverat men inte innehåller något serialiserings-ID räknas alltid händelsen.
