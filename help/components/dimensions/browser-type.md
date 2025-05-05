---
title: Typ av webbläsare
description: Organisationen som skapade webbläsaren.
feature: Dimensions
exl-id: 2a88ebc6-879e-4e5b-a8e5-40a32d54ac1b
source-git-commit: e32821dd3f30404166554b8437c508172e4764e5
workflow-type: tm+mt
source-wordcount: '147'
ht-degree: 0%

---

# Typ av webbläsare

Webbläsartypen [dimension](overview.md) visar de organisationer som har gjort webbläsaren som besökaren använder. Den här dimensionen är användbar när du vill se vilka webbläsare besökarna använder. Den ger värde över dimensionen &quot;Webbläsare&quot; eftersom den inte listar olika versioner av samma webbläsare som separata dimensionsobjekt.

## Fyll den här dimensionen med data

Den här dimensionen refererar till en uppslagstabell som är intern för Adobe. Uppslagsvärdet baseras på HTTP-huvudet `User-Agent` i bildbegäranden. Adobe samarbetar med [DeviceAtlas](https://deviceatlas.com/) för att upprätthålla sökningar mellan användaragenten och webbläsaren.

* För implementeringar av AppMeasurement fungerar den här dimensionen som standard.
* Aktivera [!UICONTROL Device Lookup] när [konfigurerar ett datastream](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html?lang=sv-SE) för Web SDK-implementeringar.

## Dimensioner

Bland Dimensionerna finns organisationer som gör webbläsare. Vanliga dimensionsobjekt är `"Google"` (skaparna av [!DNL Chrome]), `"Apple"` (skaparna av [!DNL Safari]), `"Microsoft"` (skaparna av [!DNL Edge]) och `"Mozilla"` (skaparna av [!DNL Firefox]).
