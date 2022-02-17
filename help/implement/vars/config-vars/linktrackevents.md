---
title: linkTrackEvents
description: Bestäm vilka händelser som ska ingå i förfrågningar om länkspårningsbilder.
feature: Variables
exl-id: 53c9e122-425c-4ec3-8a32-96e4d112f348
source-git-commit: b3c74782ef6183fa63674b98e4c0fc39fc09441b
workflow-type: tm+mt
source-wordcount: '258'
ht-degree: 3%

---

# linkTrackEvents

Vissa implementeringar vill inte inkludera alla variabler i alla bildbegäranden för länkspårning. Använd [`linkTrackVars`](linktrackvars.md) och `linkTrackEvents` variabler för att selektivt inkludera mått och mätvärden i [`tl()`](../functions/tl-method.md) samtal.

Den här variabeln används inte för sidvisningsanrop ([`t()`](../functions/t-method.md) metod).

## Händelser i länkspårningsanrop med hjälp av taggar i Adobe Experience Platform

Adobe Experience Platform inkluderar automatiskt definierade händelser i länkspårningstips om du inte använder anpassad kod.

>[!IMPORTANT]
>
>Om du anger händelser i användargränssnittet för datainsamling med den anpassade kodredigeraren måste du inkludera händelsen i `linkTrackEvents` även med egen kod.

## s.linkTrackEvents i AppMeasurement och anpassad kodredigerare

The `s.linkTrackEvents` variabeln är en sträng som innehåller en kommaavgränsad lista med händelser som du vill ta med i bildbegäran för länkspårning (`tl()` metod). Följande tre villkor måste vara uppfyllda för att du ska kunna inkludera mått i länkspårningsträffar:

* Ange önskad händelse i dialogrutan [`events`](../page-vars/events/events-overview.md) variabel. Exempel, `s.events = "event1";`.
* Ange `events` variabel i `linkTrackVars`. Exempel, `s.linkTrackVars = "events";`.
* Ange önskad händelse i dialogrutan `linkTrackEvents` variabel. Exempel, `s.linkTrackEvents = "event1";`.

```js
s.linkTrackEvents = "event1,event2,event3,purchase";
```

Standardvärdet för den här variabeln är en tom sträng. Om den här variabeln inte är definierad inkluderas alla händelser i förfrågningar om länkspårningsbilder. Observera att den här variabeln fylls i automatiskt baserat på händelser som angetts i gränssnittet, så den ställs alltid in för implementeringar som använder taggar i Adobe Experience Platform.

>[!TIP]
>
>Undvik att använda objektidentifieraren för Analytics (`s.`) när händelser anges i den här variabeln. Till exempel: `s.linkTrackEvents = "event1";` är korrekt, while `s.linkTrackEvents = "s.event1";` är felaktigt.

## Exempel

Följande funktion för länkspårning innehåller bara `event1` (inte `event2`) i bildbegäran som skickas till Adobe:

```js
s.events = "event1,event2";
s.linkTrackVars = "events";
s.linkTrackEvents = "event1";
s.tl(this,"o","Example Custom Link");
```
