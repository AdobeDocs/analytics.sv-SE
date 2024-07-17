---
title: linkTrackVars
description: Ange vilka variabler som ska ingå i förfrågningar om länkspårningsbilder.
feature: Variables
exl-id: b884f6e9-45d9-49f0-ac74-ea6f4f01020a
role: Admin, Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '331'
ht-degree: 0%

---

# linkTrackVars

Vissa implementeringar vill inte inkludera alla variabler i alla bildbegäranden för länkspårning. Använd variablerna `linkTrackVars` och [`linkTrackEvents`](linktrackevents.md) för att selektivt inkludera mått och mått i [`tl()`](../functions/tl-method.md) anrop.

Den här variabeln används inte för sidvisningsanrop ([`t()`](../functions/t-method.md)-metod).

## Avgöra vilka variabler som ska ingå i en XDM-händelse med Web SDK

Web SDK utesluter inte vissa fält för länkspårningsanrop. Du kan dock använda återanropet `onBeforeEventSend` för att rensa eller ange önskade fält innan data skickas till Adobe. Mer information finns i [Ändra händelser globalt](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/tracking-events.html#modifying-events-globally) i Web SDK-dokumentationen.

## Variabler i länkspårningsanrop med Adobe Analytics-tillägget

Den här variabeln fylls i automatiskt på baksidan baserat på variabler som anges i gränssnittet, så den ställs alltid in i implementeringar med Adobe Analytics-tillägget.

>[!IMPORTANT]
>
>Om du anger variabler med den anpassade kodredigeraren måste du även inkludera variablerna i `linkTrackVars` med anpassad kod.

## s.linkTrackVars i AppMeasurementet och den anpassade kodredigeraren i Analytics-tillägget

Variabeln `s.linkTrackVars` är en sträng som innehåller en kommaavgränsad lista med variabler som du vill ta med i förfrågningar om länkspårningsbilder (`tl()` metod). Båda följande villkor måste vara uppfyllda för att du ska kunna ta med dimensioner i länkspårningsträffar:

* Ange önskat variabelvärde. Exempel: `s.eVar1 = "Example value";`.
* Ange önskad variabel i variabeln `linkTrackVars`. Exempel: `s.linkTrackVars = "eVar1";`.

```js
s.linkTrackVars = "eVar1,eVar2,events,channel,products";
```

Standardvärdet för variabeln är en tom sträng. Adobe tillhandahöll dock kodvyn i kodhanteraren där AppMeasurementet är inställd på `"None"`. Giltiga värden är alla sidnivåvariabler som fyller i en dimension.

* Om variabeln inte är definierad eller inställd på en tom sträng, inkluderas *alla* -variabler i förfrågningar om länkspårningsbilder.
* Om variabeln är inställd på `"None"` inkluderas *no*-variabler i förfrågningar om länkspårningsbilder.

>[!TIP]
>
>Undvik att använda objektidentifieraren för Analytics (`s.`) när du anger variabler i den här variabeln. `s.linkTrackVars = "eVar1";` är till exempel korrekt, medan `s.linkTrackVars = "s.eVar1";` är felaktigt.

## Exempel

Följande funktion för länkspårning innehåller bara `eVar1` (inte `eVar2`) i bildbegäran som skickas till Adobe:

```js
s.eVar1 = "Example value 1";
s.eVar2 = "Example value 2";
s.linkTrackVars = "eVar1";
s.tl(this,"o","Example Custom Link");
```
