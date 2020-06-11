---
title: Webbläsarhöjd - blockerad
description: Webbläsarfönstrets höjd i pixlar.
translation-type: tm+mt
source-git-commit: 87d0c7e20594e2e39f55284e8d50d425cc1cdacf
workflow-type: tm+mt
source-wordcount: '273'
ht-degree: 0%

---


# Webbläsarhöjd

Dimensionen &#39;Webbläsarhöjd - bucklad&#39; visar höjden på webbläsarfönstret, som delas in i grupper om 100 pixlar. Den här dimensionen är användbar när du vill förstå var&quot;vikningen&quot; finns på webbplatsen för besökarna. Genom att förstå var ditt viknät är kan du optimera innehållet för visning.

Den här dimensionen skiljer sig från skärmhöjden. Webbläsarhöjden är antalet pixlar i det visningsbara webbläsarutrymmet, medan skärmhöjden är höjden på hela skärmen i pixlar. Om du vill se skillnaden mellan dessa två variabler på din egen dator öppnar du webbläsarkonsolen (F12 i de flesta webbläsare) och kopierar och klistrar in följande kod i konsolen:

```javascript
"Browser height: " + window.innerHeight + " pixels\nScreen height: " + screen.height + " pixels";
```

Webbläsarhöjden är alltid mindre än eller lika med skärmhöjden eftersom webbläsarhöjden inte inkluderar webbläsarnavigering eller kantlinjer.

## Fyll den här dimensionen med data

Den här dimensionen hämtar data från [`bh` frågesträngen](/help/implement/validate/query-parameters.md) i bildbegäranden. AppMeasurement samlar in dessa data med JavaScript-variabeln `window.innerHeight` i webbläsaren. Om du använder ett AppMeasurement-bibliotek (till exempel via Adobe Experience Platform Launch) fungerar den här dimensionen som den ska. Om du använder en datainsamlingsmetod utanför AppMeasurement (till exempel via API:t) måste du ta med frågesträngsparametern vid den första träffen vid varje besök. `bh`

Adobe besöker webbläsaren på ett besök. Om webbläsarhöjden justeras mitt på besöket registreras inte justeringen.

## Dimensionsvärden

Dimensionsvärdena innehåller alla samlade webbläsarhöjder, som delas in i grupper om 100 pixlar. Om webbläsarhöjden för en träff till exempel är `720`grupperad den i dimensionsvärdet `700 to 799`.
