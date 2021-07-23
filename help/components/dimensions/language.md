---
title: Språk
description: Den språkinställning du föredrar i webbläsaren.
exl-id: 590406a4-d336-42c7-8048-e7cd8e611d43
source-git-commit: e6f3beadfba340cea07f5fd2694105ad31de9751
workflow-type: tm+mt
source-wordcount: '158'
ht-degree: 1%

---

# Språk

Dimensionen Språk visar de översta språk som besökare föredrar att se innehåll på. Den här dimensionen är värdefull när du vill förstå besökarnas mest populära språk för att underlätta lokaliseringsarbetet.

>[!NOTE]
>
>Den här dimensionen samlar inte in språket för din webbplats. Om du vill samla in språket för din webbplats i en dimension rekommenderar Adobe att du använder en anpassad variabel, till exempel en [eVar](evar.md).

## Fyll den här dimensionen med data

Den här dimensionen refererar till en uppslagstabell som är intern för Adobe. Uppslagsvärdet baseras på HTTP-huvudet `Accept-Language` i bildbegäranden. Om du använder ett AppMeasurement-bibliotek (till exempel via taggar i Adobe Experience Platform) fungerar den här dimensionen direkt.

## Dimensioner

Dimensionen innehåller egna namn på de språk besökarna föredrar. Exempel är `"English (United States)"`, `"English (United Kingom)"`, `"Chinese (China)"` och `"Spanish (Spain)"`. Om en bildbegäran inte innehåller ett giltigt språk i HTTP-huvudet är dimensionsobjektet `"None"`.
