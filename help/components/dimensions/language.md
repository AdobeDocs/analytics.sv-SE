---
title: Språk
description: Den språkinställning du föredrar i webbläsaren.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '157'
ht-degree: 1%

---


# Språk

Dimensionen Språk visar de översta språk som besökare föredrar att se innehåll på. Den här dimensionen är värdefull när du vill förstå besökarnas mest populära språk för att underlätta lokaliseringsarbetet.

>[!NOTE]
>
>Den här dimensionen samlar inte in språket för din webbplats. Om du vill samla in språket för din webbplats i en dimension rekommenderar Adobe att du använder en anpassad variabel, till exempel en [eVar](evar.md).

## Fyll den här dimensionen med data

Den här dimensionen refererar till en söktabell som är intern för Adobe. Uppslagsvärdet baseras på HTTP-huvudet i bildbegäranden `Accept-Language` . Om du använder ett AppMeasurement-bibliotek (till exempel via Adobe Experience Platform Launch) fungerar den här dimensionen direkt.

## Dimensionsobjekt

Dimensionsobjekten innehåller egna namn på de språk besökarna föredrar. Exempel är `"English (United States)"`, `"English (United Kingom)"`, `"Chinese (China)"`och `"Spanish (Spain)"`. Om en bildbegäran inte innehåller ett giltigt språk i HTTP-huvudet är dimensionsobjektet `"None"`.
