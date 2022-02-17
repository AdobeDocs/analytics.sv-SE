---
title: Typ av webbläsare
description: Organisationen som skapade webbläsaren.
feature: Dimensions
exl-id: 2a88ebc6-879e-4e5b-a8e5-40a32d54ac1b
source-git-commit: 35413ac43eed5ab7218794f26e4753acf08f18ee
workflow-type: tm+mt
source-wordcount: '134'
ht-degree: 0%

---

# Typ av webbläsare

Dimensionen Webbläsartyp visar organisationer som har skapat den webbläsare som besökaren använder. Den här dimensionen är användbar när du vill se vilka webbläsare besökarna använder. Den ger värde över dimensionen &quot;Webbläsare&quot; eftersom den inte listar olika versioner av samma webbläsare som separata dimensionsobjekt.

## Fyll den här dimensionen med data

Den här dimensionen refererar till en uppslagstabell som är intern för Adobe. Uppslagsvärdet baseras på `User-Agent` HTTP-huvud i bildbegäranden. Om du använder ett AppMeasurement-bibliotek (till exempel via taggar i Adobe Experience Platform) fungerar den här dimensionen direkt.

## Dimensioner

Bland Dimensionerna finns organisationer som gör webbläsare. Vanliga dimensionsobjekt inkluderar `"Google"` (skapare av [!DNL Chrome]), `"Apple"` (skapare av [!DNL Safari]), `"Microsoft"` (skapare av [!DNL Edge]), och `"Mozilla"` (skapare av [!DNL Firefox]).
