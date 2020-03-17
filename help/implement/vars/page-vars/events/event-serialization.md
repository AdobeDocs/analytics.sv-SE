---
title: Händelseserialisering
description: Hjälper dig att deduplicera mätvärden på din webbplats.
translation-type: tm+mt
source-git-commit: c5a60bc9756af2742740dbc6a26a081f55ee3235

---


# Händelse-ID-serialisering

Händelseserialisering är processen att implementera åtgärder för att förhindra att dubbletthändelser anges i analysrapporter. Det är viktigt att deduplicera händelser i fall där du inte vill att besökarna ska uppdatera sidan ska få statistik som ökar.

> [!NOTE] Datakällor stöder inte händelseserialisering eller borttagning av dubbletter.

## Konfigurera händelseserialisering

Du måste först ange att en händelse ska [!UICONTROL Unique Event Recording] anges [!UICONTROL Use Event ID] i inställningarna för rapportsviten. Se [Success Events](../../../../admin/admin/c-success-events/success-event.md) i användarhandboken för Admin.

När du använder händelse-ID:n utförs borttagning av dubbletter på följande nivåer:

* Varje variabel använder sin egen tabell för borttagning av dubbletter. Till exempel `event1:ABC` och `event2:ABC` räknas båda i rapporteringen.
* Deduplicering sker globalt för alla besökare. Om besökare A skickar `event1:ABC` så ignorerar Adobe den andra förekomsten från besökare B `event1:ABC`också.
* Borttagning av dubbletter upphör inte att gälla. Om en besökare skickar tillbaka `event1:ABC` sedan två år tillbaka och skickar `event1:ABC` igen, ignorerar Adobe den andra förekomsten.

> [!TIP] Om du vill avduplicera `purchase` händelsen använder du `purchaseID` variabeln i stället.

## Använd händelse-ID:n i Adobe Experience Platform Launch

Du kan ange fältet för händelse-ID när du konfigurerar Analytics-tillägget (globala variabler) eller som en åtgärd i en regel.

1. Logga in på [launch.adobe.com](https://launch.adobe.com) med inloggningsuppgifterna för ditt AdobeID.
2. Klicka på önskad egenskap.
3. Gå till [!UICONTROL Rules] fliken och klicka sedan på önskad regel (eller skapa en regel).
4. Under [!UICONTROL Actions]klickar du på en befintlig [!UICONTROL Adobe Analytics - Set Variables] åtgärd eller på +-ikonen.
5. Ställ in listrutan till Adobe Analytics och [!UICONTROL Extension] till [!UICONTROL Action Type] [!UICONTROL Set Variables].
6. Leta reda på [!UICONTROL Events] avsnittet där varje händelse innehåller ett [!UICONTROL Event ID] fält.

Giltiga värden är alfanumeriska tecken som är upp till 20 byte långa.

## Använd händelse-ID:n i AppMeasurement och starta en anpassad kodredigerare

Händelseserialisering är en del av `s.events` variabeln. Tilldela ett ID till varje händelse med ett kolon i strängen.

```js
// Assign custom ID serialization to a single value
s.events = "event1:ABC123";

// Assign custom ID serialization to multiple values
s.events = "event1:ABC123,event2:ABC123";
```

Om en händelse har serialisering aktiverat men inte innehåller något serialiserings-ID räknas alltid händelsen.
