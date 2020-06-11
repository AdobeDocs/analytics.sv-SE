---
title: Operativsystem
description: Operativsystemet för besökaren.
translation-type: tm+mt
source-git-commit: ad206649488a1a2dead717cdfe53f4c630ba3f3b
workflow-type: tm+mt
source-wordcount: '104'
ht-degree: 0%

---


# Operativsystem

Dimensionen &#39;Operativsystem&#39; visar det operativsystem och den version som besökaren använde. Om du har funktioner som är operativsystemsspecifika på din webbegenskap, hjälper den här dimensionen dig att förstå vilka operativsystem som är vanligaste.

## Fyll den här dimensionen med data

Den här dimensionen refererar till en söktabell som är intern för Adobe. Uppslagsvärdet baseras på HTTP-huvudet i bildbegäranden `User-Agent` . Om du använder ett AppMeasurement-bibliotek (till exempel via Adobe Experience Platform Launch) fungerar den här dimensionen som den ska.

## Dimensionsvärden

Dimensionsvärdena inkluderar operativsystem som besökarna använder. Exempel är `"Windows 10"`, `"OS X 10.15"`, och `"Android 9"`.
