---
title: Operativsystemstyper
description: Operativsystemet oavsett version.
feature: Dimensions
exl-id: 0afd5261-98e8-4247-865a-1b8844c53ff4
source-git-commit: e32821dd3f30404166554b8437c508172e4764e5
workflow-type: tm+mt
source-wordcount: '134'
ht-degree: 0%

---

# Operativsystemstyper

Operativsystemtyper [dimension](overview.md) visar det operativsystem som besökaren använde, oavsett version. Den här dimensionen är användbar för att förstå inte bara vilket operativsystem och vilken version som är vanligast, utan även vilka typiska operativsystemsplattformsbesökare använder.

## Fyll den här dimensionen med data

Den här dimensionen refererar till en uppslagstabell som är intern för Adobe. Uppslagsvärdet baseras på `User-Agent` HTTP-huvud i bildbegäranden. Adobe samarbetar med [DeviceAtlas](https://deviceatlas.com/) för att upprätthålla sökningar mellan användaragent och operativsystemtyp.

* För implementeringar av AppMeasurement fungerar den här dimensionen som standard.
* Aktivera för Web SDK-implementeringar [!UICONTROL Device Lookup] när [konfigurera ett datastream](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html).

## Dimensioner

Dimensionen innehåller vilken typ av operativsystem som används. Exempel: `"Microsoft Windows"`, `"Apple Macintosh"`, `"Google Android"`och `"Apple iOS"`.
