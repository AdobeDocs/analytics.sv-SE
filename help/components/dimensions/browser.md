---
title: Webbläsare
description: Namnet på och versionen av den webbläsare som används.
feature: Dimensions
exl-id: 2bdf2a5a-3482-43fa-b2e1-fbea892918fb
source-git-commit: 206df584deab5f6f9b8eeb09d9c8ad4983424eea
workflow-type: tm+mt
source-wordcount: '192'
ht-degree: 0%

---

# Webbläsare

[!UICONTROL Browser] [dimension](overview.md) rapporterar namnet och versionen på den webbläsare som skickar träffen. Den här dimensionen är användbar när du vill mäta de vanligaste webbläsarna som besökarna använder. När du testar nya versioner av din webbplats kan du köra testerna i de vanligaste webbläsarna i den här dimensionen för att maximera kvalitetskontrollen.

## Fyll den här dimensionen med data

Den här dimensionen refererar till en uppslagstabell som är intern för Adobe. Uppslagsvärdet baseras på HTTP-huvudet `User-Agent` i bildbegäranden. Adobe samarbetar med [DeviceAtlas](https://deviceatlas.com/) för att upprätthålla sökningar mellan användaragenten och webbläsaren.

* För implementeringar av AppMeasurement fungerar den här dimensionen som standard.
* Aktivera [!UICONTROL Device Lookup] när [konfigurerar ett datastream](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html?lang=sv-SE) för Web SDK-implementeringar.

## Dimensioner

Bland Dimensionerna finns webbläsarnamnen och versionerna. Olika versioner av samma webbläsare är separata dimensionsobjekt.

Vissa dimensionsobjekt innehåller `"(unknown version)"` i stället för versionsnumret. Dimensionsobjektet refererar till en ny webbläsarversion som Adobe ännu inte har lagt till i sina sökregister. Eftersom webbläsare uppdateras ofta är `"(unknown version)"` för en viss webbläsare vanlig och tillfällig. Adobe uppdaterar vanligtvis tabeller under månadsvisa underhållsutgåvor.