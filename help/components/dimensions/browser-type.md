---
title: Typ av webbläsare
description: Organisationen som skapade webbläsaren.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '133'
ht-degree: 0%

---


# Typ av webbläsare

Dimensionen Webbläsartyp visar organisationer som har skapat den webbläsare som besökaren använder. Den här dimensionen är användbar när du vill se vilka webbläsare besökarna använder. Den ger värde över dimensionen &quot;Webbläsare&quot; eftersom den inte listar olika versioner av samma webbläsare som separata dimensionsobjekt.

## Fyll den här dimensionen med data

Den här dimensionen refererar till en söktabell som är intern för Adobe. Uppslagsvärdet baseras på HTTP-huvudet i bildbegäranden `User-Agent` . Om du använder ett AppMeasurement-bibliotek (till exempel via Adobe Experience Platform Launch) fungerar den här dimensionen direkt.

## Dimensionsobjekt

Dimensionsobjekten är organisationer som gör webbläsare. Vanliga dimensionsobjekt är `"Google"` (de som skapat [!DNL Chrome]), `"Apple"` (de som skapat [!DNL Safari]), `"Microsoft"` (de som skapat [!DNL Edge]) och `"Mozilla"` (de som skapat [!DNL Firefox]).
