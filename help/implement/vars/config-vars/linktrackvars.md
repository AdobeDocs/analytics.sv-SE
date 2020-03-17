---
title: linkTrackVars
description: Ange vilka variabler som ska ingå i förfrågningar om länkspårningsbilder.
translation-type: tm+mt
source-git-commit: 4a6cfa479559a644588613bd127c5b45ee8787e6

---


# linkTrackVars

Vissa implementeringar vill inte inkludera alla variabler i alla bildbegäranden för länkspårning. Använd variablerna `linkTrackVars` och `linkTrackEvents` för att selektivt inkludera mått och mätvärden i `tl()` anrop.

Den här variabeln används inte för sidvisningsanrop (`t()` funktion).

## Variabler i länkspårningsanrop med hjälp av Adobe Experience Platform Launch

Launch fyller automatiskt i den här variabeln på serverdelen baserat på variabler som angetts i gränssnittet, så den ställs alltid in i implementeringar med Launch.

> [!IMPORTANT] Om du anger variabler i Launch med den anpassade kodredigeraren måste du ta med variabeln även i `linkTrackVars` med anpassad kod.

## s.linkTrackVars i AppMeasurement and Launch custom code editor

Variabeln är en sträng som innehåller en kommaavgränsad lista med variabler som du vill ta med i bildbegäran för länkspårning ( `s.linkTrackVars``tl()` funktion). Båda följande villkor måste vara uppfyllda för att du ska kunna ta med dimensioner i länkspårningsträffar:

* Ange önskat variabelvärde. Exempel, `s.eVar1 = "Example value";`.
* Ange önskad variabel i `linkTrackVars` variabeln. Exempel, `s.linkTrackEvents = "eVar1";`.

```js
s.linkTrackVars = "eVar1,eVar2,events,channel,products";
```

Standardvärdet för den här variabeln är en tom sträng. Adobe tillhandahöll emellertid AppMeasurement-kod i kodhanteraren där variabeln är inställd på `"None"`. Giltiga värden är alla sidnivåvariabler som fyller i en dimension.

* Om variabeln inte är definierad eller inställd på en tom sträng inkluderas *alla* variabler i förfrågningar om länkspårningsbilder.
* Om variabeln är inställd på `"None"`inkluderas *inga* variabler i förfrågningar om länkspårningsbilder.

> [!TIP] Undvik att använda objektidentifieraren (`s.`) för Analytics när du anger variabler i den här variabeln. Till exempel `s.linkTrackVars = "eVar1";` är korrekt medan `s.linkTrackVars = "s.eVar1";` är felaktig.

## Exempel

Följande funktion för länkspårning innehåller bara `eVar1` (inte `eVar2`) i bildbegäran som skickas till Adobe:

```js
s.eVar1 = "Example value 1";
s.eVar2 = "Example value 2";
s.linkTrackVars = "eVar1";
s.tl(this,"o","Example Custom Link");
```
