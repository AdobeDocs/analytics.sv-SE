---
title: Typ av webbläsare
description: Organisationen som skapade webbläsaren.
translation-type: tm+mt
source-git-commit: 4a7b3a00bdbf557c219de530e3e692c2b2db4a84
workflow-type: tm+mt
source-wordcount: '133'
ht-degree: 0%

---


# Typ av webbläsare

Dimensionen Webbläsartyp visar organisationer som har skapat den webbläsare som besökaren använder. Den här dimensionen är användbar när du vill se vilka webbläsare besökarna använder. Den ger ett värde över dimensionen &quot;Webbläsare&quot; eftersom den inte listar olika versioner av samma webbläsare som separata dimensionsvärden.

## Fyll den här dimensionen med data

Den här dimensionen refererar till en söktabell som är intern för Adobe. Uppslagsvärdet baseras på HTTP-huvudet i bildbegäranden `User-Agent` . Om du använder ett AppMeasurement-bibliotek (till exempel via Adobe Experience Platform Launch) fungerar den här dimensionen som den ska.

## Dimensionsvärden

Dimensionsvärden är organisationer som skapar webbläsare. Vanliga dimensionsvärden är `"Google"` (de som skapat [!DNL Chrome]), `"Apple"` (de som skapat [!DNL Safari]), `"Microsoft"` (de som skapat [!DNL Edge]) och `"Mozilla"` (de som skapat [!DNL Firefox]).
