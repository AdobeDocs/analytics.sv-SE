---
title: Söknyckelord
description: Det söknyckelord som besökaren använde för att nå din webbplats.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '250'
ht-degree: 0%

---


# Söknyckelord

Dimensionen Sök nyckelord rapporterar söknyckelorden som besökarna använder för att nå din webbplats.

>[!IMPORTANT]
>
>De flesta sökmotorer skickar inte längre sökordet på grund av ökad sekretess. Slutar där Adobe känner igen en sökmotor men saknar en nyckelordsgrupp under dimensionsobjektet `"Keyword unavailable"`.

En referent måste uppfylla båda följande för att kunna klassificeras som ett söknyckelord:

* Den refererande domänen är erkänd av Adobe som en giltig [sökmotor](search-engine.md).
* Det finns en nyckelordsfrågesträngsparameter i den refererande URL:en. Om nyckelordsfrågesträngen finns men inte innehåller något värde grupperas den under dimensionsobjektet `"Keyword unavailable"`.

Om du vill kunna skilja på betald och naturlig sökning måste du identifiera [betald sökning](/help/admin/admin/paid-search-detection/paid-search-detection.md) . Det finns flera dimensioner för söknyckelord:

* **Söknyckelord**: Söknyckelordet som används för att nå din webbplats, oavsett om det är betalt eller naturligt.
* **Söknyckelord - betalt**: Det söknyckelord som användes för att nå din webbplats, vilket matchade betald sökningsidentifiering.
* **Söknyckelord - naturligt**: Det söknyckelord som användes för att nå din webbplats, vilket inte matchade betald sökningsidentifiering.

## Fyll den här dimensionen med data

Den här dimensionen refererar till flera uppslagstabeller som är interna för Adobe. Varje värde baseras på [träffens](referrer.md) referens, som är beroende av [interna URL-filter](/help/admin/admin/internal-url-filter-admin.md). Kontrollera att referensdimensionen och interna URL-filter är korrekt konfigurerade.

## Dimensionsobjekt

Dimensionsobjekten innehåller söknyckelord som används för att nå din webbplats. Dimensionsobjektet `"Unspecified"` är all trafik som inte söks.
