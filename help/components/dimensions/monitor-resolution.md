---
title: Bildskärmsupplösning
description: Upplösningen för besökarens bildskärm i pixlar.
translation-type: tm+mt
source-git-commit: ad206649488a1a2dead717cdfe53f4c630ba3f3b
workflow-type: tm+mt
source-wordcount: '239'
ht-degree: 0%

---


# Bildskärmsupplösning

Dimensionen Bildskärmsupplösning visar den aktiva visningens höjd och bredd i pixlar. Den här dimensionen är användbar när du vill förstå var&quot;vika&quot; finns på webbplatsen för besökare eller hur breda besökare kan skapa sitt webbläsarfönster. Genom att förstå var ditt viknät är kan du optimera innehållet för visning.

Den här dimensionen skiljer sig från webbläsarens höjd och bredd. Webbläsarens höjd/bredd är antalet pixlar i webbläsarutrymmet, medan skärmupplösningen är antalet pixlar i hela bildskärmen. Om du vill se skillnaden mellan dessa två variabler på din egen dator öppnar du webbläsarkonsolen (F12 i de flesta webbläsare) och kopierar och klistrar in följande kod i konsolen:

```js
"Monitor resolution: " + screen.width + "x" + screen.height + "\nBrowser resolution: " + window.innerWidth + "x" + window.innerHeight;
```

Webbläsardimensionerna är alltid mindre än skärmupplösningen eftersom webbläsardimensionerna inte inkluderar webbläsarnavigering eller kantlinjer.

## Fyll den här dimensionen med data

Den här dimensionen hämtar data från [`s` frågesträngen](/help/implement/validate/query-parameters.md) i bildbegäranden. AppMeasurement samlar in dessa data med JavaScript-variabeln `screen.width` och `screen.height` i webbläsaren. Om du använder ett AppMeasurement-bibliotek (till exempel via Adobe Experience Platform Launch) fungerar den här dimensionen som den ska. Om du använder en datainsamlingsmetod utanför AppMeasurement (till exempel via API:t), måste du ta med frågesträngsparametern i bildbegäranden. `s`

## Dimensionsvärden

Dimensionsvärden innehåller alla insamlade skärmupplösningar. Exempelvärdena inkluderar `1920 x 1080`, `1366 x 768`och `1280 x 720`.
