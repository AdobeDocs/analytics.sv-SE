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

Vissa implementeringar vill inte inkludera alla variabler i alla bildbegäranden för länkspårning. Använd `linkTrackVars` och [`linkTrackEvents`](linktrackevents.md) variabler för att selektivt inkludera mått och mätvärden i [`tl()`](../functions/tl-method.md) samtal.

Den här variabeln används inte för sidvisningsanrop ([`t()`](../functions/t-method.md) metod).

## Avgöra vilka variabler som ska ingå i en XDM-händelse med Web SDK

Web SDK utesluter inte vissa fält för länkspårningsanrop. Du kan dock använda `onBeforeEventSend` återanrop för att rensa eller ange önskade fält innan data skickas till Adobe. Se [Ändra händelser globalt](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/tracking-events.html#modifying-events-globally) finns i Web SDK-dokumentationen.

## Variabler i länkspårningsanrop med Adobe Analytics-tillägget

Den här variabeln fylls i automatiskt på baksidan baserat på variabler som anges i gränssnittet, så den ställs alltid in i implementeringar med Adobe Analytics-tillägget.

>[!IMPORTANT]
>
>Om du anger variabler med den anpassade kodredigeraren måste du ta med variablerna i `linkTrackVars` även med egen kod.

## s.linkTrackVars i AppMeasurementet och den anpassade kodredigeraren i Analytics-tillägget

The `s.linkTrackVars` variabeln är en sträng som innehåller en kommaavgränsad lista med variabler som du vill ta med i bildbegäran för länkspårning (`tl()` metod). Båda följande villkor måste vara uppfyllda för att du ska kunna ta med dimensioner i länkspårningsträffar:

* Ange önskat variabelvärde. Till exempel: `s.eVar1 = "Example value";`.
* Ange önskad variabel i dialogrutan `linkTrackVars` variabel. Till exempel: `s.linkTrackVars = "eVar1";`.

```js
s.linkTrackVars = "eVar1,eVar2,events,channel,products";
```

Standardvärdet för variabeln är en tom sträng. Koden för AppMeasurementet som tillhandahålls av Adobe i kodhanteraren där variabeln är inställd på `"None"`. Giltiga värden är alla sidnivåvariabler som fyller i en dimension.

* Om variabeln inte är definierad eller inställd på en tom sträng, *alla* variabler tas med i förfrågningar om länkspårningsbilder.
* Om variabeln är inställd på `"None"`, *no* variabler tas med i förfrågningar om länkspårningsbilder.

>[!TIP]
>
>Undvik att använda objektidentifieraren för Analytics (`s.`) när du anger variabler i den här variabeln. Till exempel: `s.linkTrackVars = "eVar1";` är korrekt, while `s.linkTrackVars = "s.eVar1";` är felaktigt.

## Exempel

Följande funktion för länkspårning innehåller bara `eVar1` (inte `eVar2`) i bildbegäran som skickas till Adobe:

```js
s.eVar1 = "Example value 1";
s.eVar2 = "Example value 2";
s.linkTrackVars = "eVar1";
s.tl(this,"o","Example Custom Link");
```
