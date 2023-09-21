---
title: Språk
description: Den språkinställning du föredrar i webbläsaren.
feature: Dimensions
exl-id: 590406a4-d336-42c7-8048-e7cd8e611d43
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '158'
ht-degree: 1%

---

# Språk

Språket [dimension](overview.md) visar de populäraste språk som besökare föredrar att se innehåll på. Den här dimensionen är värdefull när du vill förstå besökarnas mest populära språk för att underlätta lokaliseringsarbetet.

>[!NOTE]
>
>Den här dimensionen samlar inte in språket för din webbplats. Om du vill samla in språket för din webbplats i en dimension rekommenderar Adobe att du använder en anpassad variabel, till exempel en [eVar](evar.md).

## Fyll den här dimensionen med data

Den här dimensionen refererar till en uppslagstabell som är intern för Adobe. Uppslagsvärdet baseras på `Accept-Language` HTTP-huvud i bildbegäranden. Om du använder ett AppMeasurementen bibliotek (till exempel via taggar i Adobe Experience Platform) fungerar den här dimensionen automatiskt.

## Dimensioner

Dimensionen innehåller egna namn på de språk besökarna föredrar. Exempel: `"English (United States)"`, `"English (United Kingom)"`, `"Chinese (China)"`och `"Spanish (Spain)"`. Om en bildbegäran inte innehåller ett giltigt språk i HTTP-huvudet är dimensionsobjektet `"None"`.
