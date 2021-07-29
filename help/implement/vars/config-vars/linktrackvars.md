---
title: linkTrackVars
description: Ange vilka variabler som ska ingå i förfrågningar om länkspårningsbilder.
exl-id: b884f6e9-45d9-49f0-ac74-ea6f4f01020a
source-git-commit: 9a70d79a83d8274e17407229bab0273abbe80649
workflow-type: tm+mt
source-wordcount: '275'
ht-degree: 2%

---

# linkTrackVars

Vissa implementeringar vill inte inkludera alla variabler i alla bildbegäranden för länkspårning. Använd variablerna `linkTrackVars` och [`linkTrackEvents`](linktrackevents.md) för att selektivt inkludera mått och mått i [`tl()`](../functions/tl-method.md)-anrop.

Den här variabeln används inte för sidvisningsanrop ([`t()`](../functions/t-method.md) metod).

## Variabler i länkspårningsanrop med hjälp av taggar i Adobe Experience Platform

Adobe Experience Platform fyller automatiskt i den här variabeln på serverdelen baserat på variabler som anges i gränssnittet, så den ställs alltid in i implementeringar med hjälp av taggar i Adobe Experience Platform.

>[!IMPORTANT]
>
>Om du anger variabler med den anpassade kodredigeraren måste du även inkludera variabeln i `linkTrackVars` med anpassad kod.

## s.linkTrackVars i AppMeasurement och anpassad kodredigerare

Variabeln `s.linkTrackVars` är en sträng som innehåller en kommaavgränsad lista med variabler som du vill ta med i bildbegäranden för länkspårning (`tl()` metod). Båda följande villkor måste vara uppfyllda för att du ska kunna ta med dimensioner i länkspårningsträffar:

* Ange önskat variabelvärde. Exempel, `s.eVar1 = "Example value";`.
* Ange önskad variabel i variabeln `linkTrackVars`. Exempel, `s.linkTrackVars = "eVar1";`.

```js
s.linkTrackVars = "eVar1,eVar2,events,channel,products";
```

Standardvärdet för den här variabeln är en tom sträng. Adobe tillhandahöll emellertid AppMeasurement-kod i kodhanteraren där variabeln är inställd på `"None"`. Giltiga värden är alla sidnivåvariabler som fyller i en dimension.

* Om den här variabeln inte är definierad eller inställd på en tom sträng inkluderas *alla*-variabler i förfrågningar om länkspårningsbilder.
* Om variabeln är inställd på `"None"` inkluderas *inga*-variabler i förfrågningar om länkspårningsbilder.

>[!TIP]
>
>Undvik att använda objektidentifieraren för Analytics (`s.`) när du anger variabler i den här variabeln. Till exempel är `s.linkTrackVars = "eVar1";` korrekt medan `s.linkTrackVars = "s.eVar1";` är felaktigt.

## Exempel

Följande funktion för länkspårning innehåller endast `eVar1` (inte `eVar2`) i bildbegäran som skickas till Adobe:

```js
s.eVar1 = "Example value 1";
s.eVar2 = "Example value 2";
s.linkTrackVars = "eVar1";
s.tl(this,"o","Example Custom Link");
```
