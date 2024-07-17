---
title: Operativsystemstyper
description: Operativsystemet oavsett version.
feature: Dimensions
exl-id: 0afd5261-98e8-4247-865a-1b8844c53ff4
source-git-commit: e32821dd3f30404166554b8437c508172e4764e5
workflow-type: tm+mt
source-wordcount: '128'
ht-degree: 0%

---

# Operativsystemstyper

Operativsystemstyperna [dimension](overview.md) visar det operativsystem som besökaren använde, oavsett vilka versioner det gäller. Den här dimensionen är användbar för att förstå inte bara vilket operativsystem och vilken version som är vanligast, utan även vilka typiska operativsystemsplattformsbesökare använder.

## Fyll den här dimensionen med data

Den här dimensionen refererar till en uppslagstabell som är intern för Adobe. Uppslagsvärdet baseras på HTTP-huvudet `User-Agent` i bildbegäranden. Adobe samarbetar med [DeviceAtlas](https://deviceatlas.com/) för att upprätthålla sökningar mellan användaragenten och operativsystemstypen.

* För implementeringar av AppMeasurement fungerar den här dimensionen som standard.
* Aktivera [!UICONTROL Device Lookup] när [konfigurerar ett datastream](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html) för Web SDK-implementeringar.

## Dimensioner

Dimensionen innehåller vilken typ av operativsystem som används. Exempel är `"Microsoft Windows"`, `"Apple Macintosh"`, `"Google Android"` och `"Apple iOS"`.
