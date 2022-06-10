---
title: linkTrackEvents
description: Bestäm vilka händelser som ska ingå i förfrågningar om länkspårningsbilder.
feature: Variables
exl-id: 53c9e122-425c-4ec3-8a32-96e4d112f348
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '320'
ht-degree: 2%

---

# linkTrackEvents

Vissa implementeringar vill inte inkludera alla variabler i alla bildbegäranden för länkspårning. Använd [`linkTrackVars`](linktrackvars.md) och `linkTrackEvents` variabler för att selektivt inkludera mått och mätvärden i [`tl()`](../functions/tl-method.md) samtal.

Den här variabeln används inte för sidvisningsanrop ([`t()`](../functions/t-method.md) metod).

## Avgöra vilka analyshändelser som ska ingå i en XDM-händelse med Web SDK

Web SDK utesluter inte vissa fält för länkspårningsanrop. Du kan dock använda `onBeforeEventSend` återanrop för att rensa eller ange önskade fält innan data skickas till Adobe. Se [Ändra händelser globalt](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/tracking-events.html#modifying-events-globally) i Web SDK-dokumentationen om du vill ha mer information.

## Händelser i länkspårningsanrop med Adobe Analytics-tillägget

Adobe Experience Platform inkluderar automatiskt definierade händelser i länkspårningstips om du inte använder anpassad kod.

>[!IMPORTANT]
>
>Om du anger händelser i den anpassade kodredigeraren för Analytics-tillägget måste du inkludera händelsen i `linkTrackEvents` även med egen kod.

## s.linkTrackEvents i AppMeasurement och den anpassade kodredigeraren i Analytics-tillägget

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
