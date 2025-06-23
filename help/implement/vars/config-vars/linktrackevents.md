---
title: linkTrackEvents
description: Bestäm vilka händelser som ska ingå i förfrågningar om länkspårningsbilder.
feature: Appmeasurement Implementation
exl-id: 53c9e122-425c-4ec3-8a32-96e4d112f348
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '313'
ht-degree: 0%

---

# linkTrackEvents

Vissa implementeringar vill inte inkludera alla variabler i alla bildbegäranden för länkspårning. Använd variablerna [`linkTrackVars`](linktrackvars.md) och `linkTrackEvents` för att selektivt inkludera mått och mått i [`tl()`](../functions/tl-method.md) anrop.

Den här variabeln används inte för sidvisningsanrop ([`t()`](../functions/t-method.md)-metod).

## Ta reda på vilka Analytics-händelser som ska inkluderas i en XDM-händelse med hjälp av Web SDK

SDK-webben utesluter inte vissa fält för länkspårningsanrop. Du kan dock använda återanropet `onBeforeEventSend` för att rensa eller ange önskade fält innan data skickas till Adobe. Mer information finns i [Ändra händelser globalt](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/tracking-events.html?lang=sv-SE#modifying-events-globally) i Web SDK-dokumentationen.

## Händelser i länkspårningsanrop med Adobe Analytics-tillägget

Adobe Experience Platform inkluderar automatiskt definierade händelser i länkspårningstips om du inte använder anpassad kod.

>[!IMPORTANT]
>
>Om du anger händelser i den anpassade kodredigeraren för Analytics-tillägget måste du även inkludera händelsen i `linkTrackEvents` med anpassad kod.

## s.linkTrackEvents i AppMeasurement och den anpassade kodredigeraren för Analytics-tillägget

Variabeln `s.linkTrackEvents` är en sträng som innehåller en kommaavgränsad lista med händelser som du vill ta med i förfrågningar om länkspårningsbilder (`tl()` metod). Följande tre villkor måste vara uppfyllda för att du ska kunna ta med mätvärden i länkspårningsträffar:

* Ange önskad händelse i variabeln [`events`](../page-vars/events/events-overview.md). Exempel: `s.events = "event1";`.
* Ange variabeln `events` i `linkTrackVars`. Exempel: `s.linkTrackVars = "events";`.
* Ange önskad händelse i variabeln `linkTrackEvents`. Exempel: `s.linkTrackEvents = "event1";`.

```js
s.linkTrackEvents = "event1,event2,event3,purchase";
```

Standardvärdet för variabeln är en tom sträng. Om den här variabeln inte är definierad inkluderas alla händelser i förfrågningar om länkspårningsbilder. Observera att den här variabeln fylls i automatiskt baserat på händelser som angetts i gränssnittet, så den ställs alltid in för implementeringar som använder taggar i Adobe Experience Platform.

>[!TIP]
>
>Undvik att använda objektidentifieraren för Analytics (`s.`) när du anger händelser i den här variabeln. `s.linkTrackEvents = "event1";` är till exempel korrekt, medan `s.linkTrackEvents = "s.event1";` är felaktigt.

## Exempel

Följande länkspårningsfunktion innehåller bara `event1` (inte `event2`) i bildbegäran som skickas till Adobe:

```js
s.events = "event1,event2";
s.linkTrackVars = "events";
s.linkTrackEvents = "event1";
s.tl(this,"o","Example Custom Link");
```
