---
title: Webbläsarbredd - blockerad
description: Webbläsarfönstrets bredd i pixlar.
feature: Dimensions
exl-id: f0cb28b6-260b-4c3d-bbf8-17fae7ef22a0
source-git-commit: 35413ac43eed5ab7218794f26e4753acf08f18ee
workflow-type: tm+mt
source-wordcount: '274'
ht-degree: 0%

---

# Bredd på webbläsare

Dimensionen Webbläsarbredd - bucketed visar webbläsarfönstrets bredd, som delas in i grupper om 100 pixlar. Den här dimensionen är användbar när du vill förstå hur breda besökare ser ditt innehåll. Genom att förstå hur brett innehållet vanligtvis visas kan du optimera innehållet för visning.

Den här dimensionen skiljer sig från skärmbredden. Bredden på webbläsaren är antalet pixlar i den visningsbara webbläsarrymden, medan skärmbredden är bredden på hela skärmen i pixlar. Om du vill se skillnaden mellan dessa två variabler på din egen dator öppnar du webbläsarkonsolen (F12 i de flesta webbläsare) och kopierar och klistrar in följande kod i konsolen:

```javascript
"Browser width: " + window.innerWidth + " pixels\nScreen width: " + screen.width + " pixels";
```

Bredden på webbläsaren är alltid mindre än eller lika med skärmbredden eftersom webbläsarbredden inte innehåller rullningslister eller kantlinjer.

## Fyll den här dimensionen med data

Den här dimensionen hämtar data från [`bw` frågesträng](/help/implement/validate/query-parameters.md) i bildbegäranden. AppMeasurement samlar in dessa data med JavaScript-variabeln `window.innerWidth` i webbläsaren. Om du använder ett AppMeasurement-bibliotek (till exempel via taggar i Adobe Experience Platform) fungerar den här dimensionen direkt. Om du använder en datainsamlingsmetod utanför AppMeasurement (till exempel via API:t) måste du ta med `bw` frågesträngsparameter vid den första träffen av varje besök.

Adobe bibehåller webbläsarbredden för ett besök. Om webbläsarbredden justeras mitt i besöket registreras inte justeringen.

## Dimensioner

Dimensionen innehåller alla insamlade webbläsarbredder, som delas in i grupper om 100 pixlar. Om webbläsarbredden för en träff till exempel är `1280`grupperas den i dimensionsposten `1200 to 1299`.
