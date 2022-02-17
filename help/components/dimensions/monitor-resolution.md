---
title: Bildskärmsupplösning
description: Upplösningen för besökarens bildskärm i pixlar.
feature: Dimensions
exl-id: 6bae65eb-4546-4d07-877d-6e257fbe6cfa
source-git-commit: 35413ac43eed5ab7218794f26e4753acf08f18ee
workflow-type: tm+mt
source-wordcount: '240'
ht-degree: 0%

---

# Bildskärmsupplösning

Dimensionen Bildskärmsupplösning visar den aktiva visningens höjd och bredd i pixlar. Den här dimensionen är användbar när du vill förstå var&quot;vika&quot; finns på webbplatsen för besökare eller hur breda besökare kan skapa sitt webbläsarfönster. Genom att förstå var ditt viknät är kan du optimera innehållet för visning.

Den här dimensionen skiljer sig från webbläsarens höjd och bredd. Webbläsarens höjd/bredd är antalet pixlar i det visningsbara webbläsarutrymmet, medan skärmupplösningen är antalet pixlar i hela skärmen. Om du vill se skillnaden mellan dessa två variabler på din egen dator öppnar du webbläsarkonsolen (F12 i de flesta webbläsare) och kopierar och klistrar in följande kod i konsolen:

```js
"Monitor resolution: " + screen.width + "x" + screen.height + "\nBrowser resolution: " + window.innerWidth + "x" + window.innerHeight;
```

Webbläsardimensionerna är alltid mindre än skärmupplösningen eftersom webbläsardimensionerna inte inkluderar webbläsarnavigering eller kantlinjer.

## Fyll den här dimensionen med data

Den här dimensionen hämtar data från [`s` frågesträng](/help/implement/validate/query-parameters.md) i bildbegäranden. AppMeasurement samlar in dessa data med JavaScript-variabeln `screen.width` och `screen.height` i webbläsaren. Om du använder ett AppMeasurement-bibliotek (till exempel via taggar i Adobe Experience Platform) fungerar den här dimensionen direkt. Om du använder en datainsamlingsmetod utanför AppMeasurement (till exempel via API:t) måste du ta med `s` frågesträngsparameter i bildbegäranden.

## Dimensioner

Dimensionen innehåller alla insamlade skärmupplösningar. Exempelvärden innehåller `1920 x 1080`, `1366 x 768`och `1280 x 720`.
