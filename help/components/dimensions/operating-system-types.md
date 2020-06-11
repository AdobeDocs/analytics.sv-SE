---
title: Operativsystemstyper
description: Operativsystemet oavsett version.
translation-type: tm+mt
source-git-commit: ad206649488a1a2dead717cdfe53f4c630ba3f3b
workflow-type: tm+mt
source-wordcount: '112'
ht-degree: 0%

---


# Operativsystemstyper

Dimensionen &#39;Operativsystemtyper&#39; visar det operativsystem som besökaren använde, oavsett vilka versioner det gäller. Den här dimensionen är användbar för att förstå inte bara vilket operativsystem och vilken version som är vanligast, utan även vilka typiska operativsystemsplattformsbesökare använder.

## Fyll den här dimensionen med data

Den här dimensionen refererar till en söktabell som är intern för Adobe. Uppslagsvärdet baseras på HTTP-huvudet i bildbegäranden `User-Agent` . Om du använder ett AppMeasurement-bibliotek (till exempel via Adobe Experience Platform Launch) fungerar den här dimensionen som den ska.

## Dimensionsvärden

Dimensionsvärden är den typ av operativsystem som används. Exempel är `"Microsoft Windows"`, `"Apple Macintosh"`, `"Google Android"`och `"Apple iOS"`.
