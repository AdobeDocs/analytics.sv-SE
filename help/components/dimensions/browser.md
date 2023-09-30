---
title: Webbläsare
description: Namnet på och versionen av den webbläsare som används.
feature: Dimensions
exl-id: 2bdf2a5a-3482-43fa-b2e1-fbea892918fb
source-git-commit: 206df584deab5f6f9b8eeb09d9c8ad4983424eea
workflow-type: tm+mt
source-wordcount: '198'
ht-degree: 1%

---

# Webbläsare

The[!UICONTROL Browser]&#39; [dimension](overview.md) rapporterar namnet på och versionen av den webbläsare som skickar träffen. Den här dimensionen är användbar när du vill mäta de vanligaste webbläsarna som besökarna använder. När du testar nya versioner av din webbplats kan du köra testerna i de vanligaste webbläsarna i den här dimensionen för att maximera kvalitetskontrollen.

## Fyll den här dimensionen med data

Den här dimensionen refererar till en uppslagstabell som är intern för Adobe. Uppslagsvärdet baseras på `User-Agent` HTTP-huvud i bildbegäranden. Adobe samarbetar med [DeviceAtlas](https://deviceatlas.com/) för att upprätthålla sökningar mellan användaragenten och webbläsaren.

* För implementeringar av AppMeasurement fungerar den här dimensionen som standard.
* Aktivera för Web SDK-implementeringar [!UICONTROL Device Lookup] när [konfigurera ett datastream](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html).

## Dimensioner

Bland Dimensionerna finns webbläsarnamnen och versionerna. Olika versioner av samma webbläsare är separata dimensionsobjekt.

Vissa dimensionsobjekt innehåller `"(unknown version)"` i stället för versionsnumret. Dimensionsobjektet refererar till en ny webbläsarversion som Adobe ännu inte har lagt till i sina sökregister. Eftersom webbläsarna uppdateras ofta visas `"(unknown version)"` för en viss webbläsare är vanlig och tillfällig. Adobe uppdaterar vanligtvis tabeller under månadsvisa underhållsutgåvor.