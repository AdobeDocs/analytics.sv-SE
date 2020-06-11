---
title: Webbläsarbredd - blockerad
description: Webbläsarfönstrets bredd i pixlar.
translation-type: tm+mt
source-git-commit: 87d0c7e20594e2e39f55284e8d50d425cc1cdacf
workflow-type: tm+mt
source-wordcount: '273'
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

Den här dimensionen hämtar data från [`bw` frågesträngen](/help/implement/validate/query-parameters.md) i bildbegäranden. AppMeasurement samlar in dessa data med JavaScript-variabeln `window.innerWidth` i webbläsaren. Om du använder ett AppMeasurement-bibliotek (till exempel via Adobe Experience Platform Launch) fungerar den här dimensionen som den ska. Om du använder en datainsamlingsmetod utanför AppMeasurement (till exempel via API:t) måste du ta med frågesträngsparametern vid den första träffen vid varje besök. `bw`

Adobe fortsätter att ha en webbläsarbredd på ett besök. Om webbläsarbredden justeras mitt i besöket registreras inte justeringen.

## Dimensionsvärden

Dimensionsvärdena innehåller alla insamlade webbläsarbredder, som delas in i grupper om 100 pixlar. Om webbläsarbredden för en träff till exempel är `1280`grupperad den i dimensionsvärdet `1200 to 1299`.
