---
title: linkTrackEvents
description: Bestäm vilka händelser som ska ingå i förfrågningar om länkspårningsbilder.
translation-type: tm+mt
source-git-commit: 4a6cfa479559a644588613bd127c5b45ee8787e6

---


# linkTrackEvents

Vissa implementeringar vill inte inkludera alla variabler i alla bildbegäranden för länkspårning. Använd variablerna `linkTrackVars` och `linkTrackEvents` för att selektivt inkludera mått och mätvärden i `tl()` anrop.

Den här variabeln används inte för sidvisningsanrop (`t()` funktion).

## Händelser i anrop för länkspårning med Adobe Experience Platform Launch

Launch identifierar automatiskt händelser som definierats i gränssnittet och inkluderar dem i länkspårningsträffar.

> [!IMPORTANT] Om du anger händelser i Launch med den anpassade kodredigeraren måste du även inkludera händelsen i `linkTrackEvents` att använda anpassad kod.

## s.linkTrackEvents i AppMeasurement and Launch custom code editor

Variabeln är en sträng som innehåller en kommaavgränsad lista med händelser som du vill ta med i bildbegäran för länkspårning ( `s.linkTrackEvents``tl()` funktion). Följande tre villkor måste vara uppfyllda för att du ska kunna ta med mätvärden i länkspårningsträffar:

* Ange önskad händelse i `events` variabeln. Exempel, `s.events = "event1";`.
* Ange `events` variabeln i `linkTrackVars`. Exempel, `s.linkTrackVars = "events";`.
* Ange önskad händelse i `linkTrackEvents` variabeln. Exempel, `s.linkTrackEvents = "event1";`.

```js
s.linkTrackEvents = "event1,event2,event3,purchase";
```

Standardvärdet för den här variabeln är en tom sträng. Om den här variabeln inte är definierad inkluderas alla händelser i förfrågningar om länkspårningsbilder. Observera att Launch automatiskt fyller i den här variabeln baserat på händelser som angetts i gränssnittet, så den anges alltid i implementeringar med Launch.

> [!TIP] Undvik att använda objektidentifieraren för Analytics (`s.`) när du anger händelser i den här variabeln. Till exempel `s.linkTrackEvents = "event1";` är korrekt medan `s.linkTrackEvents = "s.event1";` är felaktig.

## Exempel

Följande funktion för länkspårning innehåller bara `event1` (inte `event2`) i bildbegäran som skickas till Adobe:

```js
s.events = "event1,event2";
s.linkTrackVars = "events";
s.linkTrackEvents = "event1";
s.tl(this,"o","Example Custom Link");
```
