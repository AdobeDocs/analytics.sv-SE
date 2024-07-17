---
title: Söknyckelord
description: Det söknyckelord som besökaren använde för att nå din webbplats.
feature: Dimensions
exl-id: 5a1236a6-f94b-4679-906a-b539afe36887
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '250'
ht-degree: 0%

---

# Söknyckelord

Söknyckelordet [dimension](overview.md) rapporterar söknyckelorden som besökarna använder för att nå din webbplats.

>[!IMPORTANT]
>
>De flesta sökmotorer skickar inte längre sökordet på grund av ökad sekretess. Träffar där Adobe känner igen en sökmotor men saknar en nyckelordsgrupp under dimensionsobjektet `"Keyword unavailable"`.

En referent måste uppfylla båda följande för att kunna klassificeras som ett söknyckelord:

* Den refererande domänen känns igen av Adobe som en giltig [sökmotor](search-engine.md);
* Det finns en nyckelordsfrågesträngsparameter i den refererande URL:en. Om nyckelordsfrågesträngen finns men inte innehåller något värde grupperas den under dimensionsobjektet `"Keyword unavailable"`.

Om du vill skilja på betald och naturlig sökning måste du [identifiera betald sökning](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/paid-search-detection/paid-search-detection.md). Det finns flera dimensioner för söknyckelord:

* **Söknyckelord**: Söknyckelordet som används för att nå din webbplats, oavsett om det är betalt eller naturligt.
* **Söknyckelord - betald**: Söknyckelordet som används för att nå din webbplats, vilket matchade betald sökningsidentifiering.
* **Söknyckelord - naturligt**: Det söknyckelord som användes för att nå din webbplats, vilket inte matchade betald sökidentifiering.

## Fyll den här dimensionen med data

Den här dimensionen refererar till flera uppslagstabeller som är interna för Adobe. Varje värde baseras på [referenten](referrer.md) för träffen, som är beroende av [interna URL-filter](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/internal-url-filter-admin.md). Kontrollera att referensdimensionen och interna URL-filter är korrekt konfigurerade.

## Dimensioner

Bland Dimensionerna finns söknyckelord som används för att nå din webbplats. Dimensionsobjektet `"Unspecified"` är all trafik som inte söks.
