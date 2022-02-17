---
title: Operativsystem
description: Operativsystemet för besökaren.
feature: Dimensions
exl-id: e3911ae0-d242-4da2-a4bc-b2f4877f9dd2
source-git-commit: 35413ac43eed5ab7218794f26e4753acf08f18ee
workflow-type: tm+mt
source-wordcount: '105'
ht-degree: 0%

---

# Operativsystem

Dimensionen &#39;Operativsystem&#39; visar det operativsystem och den version som besökaren använde. Om du har funktioner som är operativsystemsspecifika på din webbegenskap, hjälper den här dimensionen dig att förstå vilka operativsystem som är vanligaste.

## Fyll den här dimensionen med data

Den här dimensionen refererar till en uppslagstabell som är intern för Adobe. Uppslagsvärdet baseras på `User-Agent` HTTP-huvud i bildbegäranden. Om du använder ett AppMeasurement-bibliotek (till exempel via taggar i Adobe Experience Platform) fungerar den här dimensionen direkt.

## Dimensioner

Dimensionen innehåller operativsystem som besökarna använder. Exempel `"Windows 10"`, `"OS X 10.15"`och `"Android 9"`.
