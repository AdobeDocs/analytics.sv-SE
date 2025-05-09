---
title: Bildskärmsupplösning
description: Upplösningen för besökarens bildskärm i pixlar.
feature: Dimensions
exl-id: 6bae65eb-4546-4d07-877d-6e257fbe6cfa
source-git-commit: e3a1c1fde3809cb73b1bda091b8be43778515d1a
workflow-type: tm+mt
source-wordcount: '261'
ht-degree: 0%

---

# Bildskärmsupplösning

Skärmupplösningen [dimension](overview.md) visar höjden och bredden på den aktiva visningen i pixlar. Den här dimensionen är användbar när du vill förstå var&quot;vika&quot; finns på webbplatsen för besökare eller hur breda besökare kan skapa sitt webbläsarfönster. Genom att förstå var ditt viknät är kan du optimera innehållet för visning.

Den här dimensionen skiljer sig från webbläsarens [höjd](browser-height.md) och [bredd](browser-width.md). Webbläsarens höjd/bredd är antalet pixlar i det visningsbara webbläsarutrymmet, medan skärmupplösningen är antalet pixlar i hela skärmen. Om du vill se skillnaden mellan dessa två variabler på din egen dator öppnar du webbläsarkonsolen (F12 i de flesta webbläsare) och kopierar och klistrar in följande kod i konsolen:

```js
"Monitor resolution: " + screen.width + "x" + screen.height + "; Browser resolution: " + window.innerWidth + "x" + window.innerHeight;
```

Webbläsardimensionerna är alltid mindre än skärmupplösningen eftersom webbläsardimensionerna inte inkluderar webbläsarnavigering eller kantlinjer.

## Fyll den här dimensionen med data

Den här dimensionen hämtar data från [`s`-frågesträngen ](/help/implement/validate/query-parameters.md) i bildbegäranden. AppMeasurement samlar in dessa data med JavaScript-variabeln `screen.width` och `screen.height` i webbläsaren. Om du använder ett AppMeasurement-bibliotek (till exempel via taggar i Adobe Experience Platform) fungerar den här dimensionen som standard.

Om du använder en datainsamlingsmetod utanför AppMeasurement (till exempel via API:t) måste du ta med frågesträngsparametern `s` i bildbegäranden. Om frågesträngen `s` saknas eller om ett datainsamlingsbibliotek annars inte kan samla in skärmupplösning, listas dessa data under [!UICONTROL `Not Specified`].

## Dimension-objekt

Dimension innehåller alla samlade skärmupplösningar. Exempelvärden är `1920 x 1080`, `1366 x 768` och `1280 x 720`.
