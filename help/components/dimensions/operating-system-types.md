---
title: Operativsystemstyper
description: Operativsystemet oavsett version.
feature: Dimensions
exl-id: 0afd5261-98e8-4247-865a-1b8844c53ff4
source-git-commit: 35413ac43eed5ab7218794f26e4753acf08f18ee
workflow-type: tm+mt
source-wordcount: '113'
ht-degree: 0%

---

# Operativsystemstyper

Dimensionen &#39;Operativsystemtyper&#39; visar det operativsystem som besökaren använde, oavsett vilka versioner det gäller. Den här dimensionen är användbar för att förstå inte bara vilket operativsystem och vilken version som är vanligast, utan även vilka typiska operativsystemsplattformsbesökare använder.

## Fyll den här dimensionen med data

Den här dimensionen refererar till en uppslagstabell som är intern för Adobe. Uppslagsvärdet baseras på `User-Agent` HTTP-huvud i bildbegäranden. Om du använder ett AppMeasurement-bibliotek (till exempel via taggar i Adobe Experience Platform) fungerar den här dimensionen direkt.

## Dimensioner

Dimensionen omfattar vilken typ av operativsystem som används. Exempel `"Microsoft Windows"`, `"Apple Macintosh"`, `"Google Android"`och `"Apple iOS"`.
