---
title: linkTrackEvents
description: Bestäm vilka händelser som ska ingå i förfrågningar om länkspårningsbilder.
exl-id: 53c9e122-425c-4ec3-8a32-96e4d112f348
source-git-commit: 9a70d79a83d8274e17407229bab0273abbe80649
workflow-type: tm+mt
source-wordcount: '258'
ht-degree: 3%

---

# linkTrackEvents

Vissa implementeringar vill inte inkludera alla variabler i alla bildbegäranden för länkspårning. Använd variablerna [`linkTrackVars`](linktrackvars.md) och `linkTrackEvents` för att selektivt inkludera mått och mått i [`tl()`](../functions/tl-method.md)-anrop.

Den här variabeln används inte för sidvisningsanrop ([`t()`](../functions/t-method.md) metod).

## Händelser i länkspårningsanrop med hjälp av taggar i Adobe Experience Platform

Adobe Experience Platform inkluderar automatiskt definierade händelser i länkspårningstips om du inte använder anpassad kod.

>[!IMPORTANT]
>
>Om du anger händelser i användargränssnittet för datainsamling med den anpassade kodredigeraren måste du även inkludera händelsen i `linkTrackEvents` med anpassad kod.

## s.linkTrackEvents i AppMeasurement och anpassad kodredigerare

Variabeln `s.linkTrackEvents` är en sträng som innehåller en kommaavgränsad lista med händelser som du vill ta med i begäranden om länkspårningsbilder (`tl()` metod). Följande tre villkor måste vara uppfyllda för att du ska kunna inkludera mått i länkspårningsträffar:

* Ange önskad händelse i variabeln [`events`](../page-vars/events/events-overview.md). Exempel, `s.events = "event1";`.
* Ange variabeln `events` i `linkTrackVars`. Exempel, `s.linkTrackVars = "events";`.
* Ange önskad händelse i variabeln `linkTrackEvents`. Exempel, `s.linkTrackEvents = "event1";`.

```js
s.linkTrackEvents = "event1,event2,event3,purchase";
```

Standardvärdet för den här variabeln är en tom sträng. Om den här variabeln inte är definierad inkluderas alla händelser i förfrågningar om länkspårningsbilder. Observera att den här variabeln fylls i automatiskt baserat på händelser som angetts i gränssnittet, så den ställs alltid in för implementeringar som använder taggar i Adobe Experience Platform.

>[!TIP]
>
>Undvik att använda objektidentifieraren för Analytics (`s.`) när du anger händelser i den här variabeln. Till exempel är `s.linkTrackEvents = "event1";` korrekt medan `s.linkTrackEvents = "s.event1";` är felaktigt.

## Exempel

Följande funktion för länkspårning innehåller endast `event1` (inte `event2`) i bildbegäran som skickas till Adobe:

```js
s.events = "event1,event2";
s.linkTrackVars = "events";
s.linkTrackEvents = "event1";
s.tl(this,"o","Example Custom Link");
```
