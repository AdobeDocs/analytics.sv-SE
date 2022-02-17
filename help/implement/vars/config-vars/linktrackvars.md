---
title: linkTrackVars
description: Ange vilka variabler som ska ingå i förfrågningar om länkspårningsbilder.
feature: Variables
exl-id: b884f6e9-45d9-49f0-ac74-ea6f4f01020a
source-git-commit: b3c74782ef6183fa63674b98e4c0fc39fc09441b
workflow-type: tm+mt
source-wordcount: '275'
ht-degree: 2%

---

# linkTrackVars

Vissa implementeringar vill inte inkludera alla variabler i alla bildbegäranden för länkspårning. Använd `linkTrackVars` och [`linkTrackEvents`](linktrackevents.md) variabler för att selektivt inkludera mått och mätvärden i [`tl()`](../functions/tl-method.md) samtal.

Den här variabeln används inte för sidvisningsanrop ([`t()`](../functions/t-method.md) metod).

## Variabler i länkspårningsanrop med hjälp av taggar i Adobe Experience Platform

Adobe Experience Platform fyller automatiskt i den här variabeln på serverdelen baserat på variabler som anges i gränssnittet, så den ställs alltid in i implementeringar med hjälp av taggar i Adobe Experience Platform.

>[!IMPORTANT]
>
>Om du anger variabler med den anpassade kodredigeraren måste du ta med variabeln i `linkTrackVars` även med egen kod.

## s.linkTrackVars i AppMeasurement och anpassad kodredigerare

The `s.linkTrackVars` variabeln är en sträng som innehåller en kommaavgränsad lista med variabler som du vill ta med i bildbegäran för länkspårning (`tl()` metod). Båda följande villkor måste vara uppfyllda för att du ska kunna ta med dimensioner i länkspårningsträffar:

* Ange önskat variabelvärde. Exempel, `s.eVar1 = "Example value";`.
* Ange önskad variabel i dialogrutan `linkTrackVars` variabel. Exempel, `s.linkTrackVars = "eVar1";`.

```js
s.linkTrackVars = "eVar1,eVar2,events,channel,products";
```

Standardvärdet för den här variabeln är en tom sträng. Adobe tillhandahöll emellertid AppMeasurement-kod i kodhanteraren där variabeln är inställd på `"None"`. Giltiga värden är alla sidnivåvariabler som fyller i en dimension.

* Om variabeln inte är definierad eller inställd på en tom sträng, *alla* variabler tas med i förfrågningar om länkspårningsbilder.
* Om variabeln är inställd på `"None"`, *no* variabler tas med i förfrågningar om länkspårningsbilder.

>[!TIP]
>
>Undvik att använda objektidentifieraren för Analytics (`s.`) när variabler anges i den här variabeln. Till exempel: `s.linkTrackVars = "eVar1";` är korrekt, while `s.linkTrackVars = "s.eVar1";` är felaktigt.

## Exempel

Följande funktion för länkspårning innehåller bara `eVar1` (inte `eVar2`) i bildbegäran som skickas till Adobe:

```js
s.eVar1 = "Example value 1";
s.eVar2 = "Example value 2";
s.linkTrackVars = "eVar1";
s.tl(this,"o","Example Custom Link");
```
