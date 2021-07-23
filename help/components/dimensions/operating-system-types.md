---
title: Operativsystemstyper
description: Operativsystemet oavsett version.
exl-id: 0afd5261-98e8-4247-865a-1b8844c53ff4
source-git-commit: e6f3beadfba340cea07f5fd2694105ad31de9751
workflow-type: tm+mt
source-wordcount: '113'
ht-degree: 0%

---

# Operativsystemstyper

Dimensionen &#39;Operativsystemtyper&#39; visar det operativsystem som besökaren använde, oavsett vilka versioner det gäller. Den här dimensionen är användbar för att förstå inte bara vilket operativsystem och vilken version som är vanligast, utan även vilka typiska operativsystemsplattformsbesökare använder.

## Fyll den här dimensionen med data

Den här dimensionen refererar till en uppslagstabell som är intern för Adobe. Uppslagsvärdet baseras på HTTP-huvudet `User-Agent` i bildbegäranden. Om du använder ett AppMeasurement-bibliotek (till exempel via taggar i Adobe Experience Platform) fungerar den här dimensionen direkt.

## Dimensioner

Dimensionen omfattar vilken typ av operativsystem som används. Exempel är `"Microsoft Windows"`, `"Apple Macintosh"`, `"Google Android"` och `"Apple iOS"`.
