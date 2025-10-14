---
title: Webbläsarhöjd - blockerad
description: Webbläsarfönstrets höjd i pixlar.
feature: Dimensions
exl-id: bdfd2ef5-c200-4d6e-b478-3917fca66227
source-git-commit: 2601b0e5c3fa78237ce693801b8dd8c95b853b81
workflow-type: tm+mt
source-wordcount: '272'
ht-degree: 0%

---

# Webbläsarhöjd

Webbläsarhöjden - bucketed [dimension](overview.md) visar webbläsarfönstrets höjd, som delas in i fördefinierade grupper. Den här dimensionen är användbar när du vill förstå var&quot;vikningen&quot; finns på din webbplats för besökare. Genom att förstå var ditt viknät är kan du optimera innehållet för visning.

Den här dimensionen skiljer sig från skärmhöjden. Webbläsarhöjden är antalet pixlar i det visningsbara webbläsarutrymmet, medan skärmhöjden är höjden på hela skärmen i pixlar. Om du vill se skillnaden mellan dessa två variabler på din egen dator öppnar du webbläsarkonsolen (F12 i de flesta webbläsare) och kopierar och klistrar in följande kod i konsolen:

```javascript
console.log(`Browser height: ${window.innerHeight} pixels\nScreen height: ${screen.height} pixels`);
```

Webbläsarhöjden är alltid mindre än eller lika med skärmhöjden eftersom webbläsarhöjden inte inkluderar webbläsarnavigering eller kantlinjer.

## Fyll den här dimensionen med data

Den här dimensionen hämtar data från [`bh`-frågesträngen &#x200B;](/help/implement/validate/query-parameters.md) i bildbegäranden. AppMeasurementet samlar in dessa data med JavaScript-variabeln `window.innerHeight` i webbläsaren. Om du använder ett AppMeasurementen bibliotek (till exempel via taggar i Adobe Experience Platform) fungerar den här dimensionen automatiskt. Om du använder en datainsamlingsmetod utanför AppMeasurementet (till exempel via API:t), måste du ta med frågesträngsparametern `bh` vid den första träffen vid varje besök.

Adobe har kvar webbläsarhöjden för ett besök. Om webbläsarhöjden justeras mitt på besöket registreras inte justeringen.

## Dimensioner

Dimensionerna innehåller alla insamlade webbläsarhöjder, indelade i fördefinierade grupper. Om webbläsarhöjden för en träff till exempel är `720` grupperas den i dimensionsobjektet `700 to 799`.
