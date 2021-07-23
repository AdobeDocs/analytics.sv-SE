---
title: Typ av webbläsare
description: Organisationen som skapade webbläsaren.
exl-id: 2a88ebc6-879e-4e5b-a8e5-40a32d54ac1b
source-git-commit: e6f3beadfba340cea07f5fd2694105ad31de9751
workflow-type: tm+mt
source-wordcount: '134'
ht-degree: 0%

---

# Typ av webbläsare

Dimensionen Webbläsartyp visar organisationer som har skapat den webbläsare som besökaren använder. Den här dimensionen är användbar när du vill se vilka webbläsare besökarna använder. Den ger värde över dimensionen &quot;Webbläsare&quot; eftersom den inte listar olika versioner av samma webbläsare som separata dimensionsobjekt.

## Fyll den här dimensionen med data

Den här dimensionen refererar till en uppslagstabell som är intern för Adobe. Uppslagsvärdet baseras på HTTP-huvudet `User-Agent` i bildbegäranden. Om du använder ett AppMeasurement-bibliotek (till exempel via taggar i Adobe Experience Platform) fungerar den här dimensionen direkt.

## Dimensioner

Bland Dimensionerna finns organisationer som gör webbläsare. Vanliga dimensionsobjekt är `"Google"` (de som skapat [!DNL Chrome]), `"Apple"` (de som skapat [!DNL Safari]), `"Microsoft"` (de som skapat [!DNL Edge]) och `"Mozilla"` (de som skapat [!DNL Firefox]).
