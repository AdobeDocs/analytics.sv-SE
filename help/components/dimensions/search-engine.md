---
title: Sökmotor
description: Sökmotorn som besökaren använde för att nå din webbplats.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '224'
ht-degree: 0%

---


# Sökmotor

Dimensionen Sökmotor rapporterar sökmotorer som besökarna använder för att nå din webbplats. En referent måste uppfylla båda följande för att kunna klassificeras som sökmotor:

* Den refererande domänen är erkänd av Adobe som en giltig sökmotor.
* Det finns en nyckelordsfrågesträngsparameter i den refererande URL:en. Frågesträngsparametern kan vara tom (vilket är fallet med flera sökmotorer på grund av sekretesspraxis).

Om du vill kunna skilja på betald och naturlig sökning måste du identifiera [betald sökning](/help/admin/admin/paid-search-detection/paid-search-detection.md) . Det finns flera dimensioner för sökmotorer:

* **Sökmotor**: Sökmotorn som används för att nå din webbplats, oavsett om den är betald eller naturlig.
* **Sökmotor - betald**: Sökmotorn som användes för att nå din webbplats, vilket matchade betald sökningsidentifiering.
* **Sökmotor - naturlig**: Sökmotorn som användes för att nå din webbplats, vilket inte matchade betalsökningsidentifiering.

## Fyll den här dimensionen med data

Den här dimensionen refererar till flera uppslagstabeller som är interna för Adobe. Varje värde baseras på [träffens](referrer.md) referens, som är beroende av [interna URL-filter](/help/admin/admin/internal-url-filter-admin.md). Kontrollera att referensdimensionen och interna URL-filter är korrekt konfigurerade.

## Dimensionsobjekt

Dimensionsobjekten inkluderar sökmotorer som används för att nå din webbplats. Exempelvärdena inkluderar `"Google"`, `"Microsoft Bing"`och `"DuckDuckGo"`. Dimensionsobjektet `"Unspecified"` är all trafik som inte söks.
