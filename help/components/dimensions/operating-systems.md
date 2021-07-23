---
title: Operativsystem
description: Operativsystemet för besökaren.
exl-id: e3911ae0-d242-4da2-a4bc-b2f4877f9dd2
source-git-commit: e6f3beadfba340cea07f5fd2694105ad31de9751
workflow-type: tm+mt
source-wordcount: '105'
ht-degree: 0%

---

# Operativsystem

Dimensionen &#39;Operativsystem&#39; visar det operativsystem och den version som besökaren använde. Om du har funktioner som är operativsystemsspecifika på din webbegenskap, hjälper den här dimensionen dig att förstå vilka operativsystem som är vanligaste.

## Fyll den här dimensionen med data

Den här dimensionen refererar till en uppslagstabell som är intern för Adobe. Uppslagsvärdet baseras på HTTP-huvudet `User-Agent` i bildbegäranden. Om du använder ett AppMeasurement-bibliotek (till exempel via taggar i Adobe Experience Platform) fungerar den här dimensionen direkt.

## Dimensioner

Dimensionen innehåller operativsystem som besökarna använder. Exempel är `"Windows 10"`, `"OS X 10.15"` och `"Android 9"`.
