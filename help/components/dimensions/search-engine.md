---
title: Sökmotor
description: Sökmotorn som besökaren använde för att nå din webbplats.
feature: Dimensions
exl-id: 2815f1fa-d938-4d2b-b864-c4ed834f3ed3
source-git-commit: 35413ac43eed5ab7218794f26e4753acf08f18ee
workflow-type: tm+mt
source-wordcount: '224'
ht-degree: 0%

---

# Sökmotor

Dimensionen Sökmotor rapporterar sökmotorer som besökarna använder för att nå din webbplats. En referent måste uppfylla båda följande för att kunna klassificeras som sökmotor:

* Den refererande domänen känns igen av Adobe som en giltig sökmotor.
* Det finns en nyckelordsfrågesträngsparameter i den refererande URL:en. Frågesträngsparametern kan vara tom (vilket är fallet med flera sökmotorer på grund av sekretesspraxis).

Om du vill skilja på betald och naturlig sökning [Påvisande av betald sökning](/help/admin/admin/paid-search-detection/paid-search-detection.md) krävs. Det finns flera dimensioner för sökmotorer:

* **Sökmotor**: Sökmotorn som används för att nå din webbplats, oavsett om den är betald eller naturlig.
* **Sökmotor - betald**: Sökmotorn som användes för att nå din webbplats, vilket matchade betald sökningsidentifiering.
* **Sökmotor - naturlig**: Sökmotorn som användes för att nå din webbplats, vilket inte matchade betalsökningsidentifiering.

## Fyll den här dimensionen med data

Den här dimensionen refererar till flera uppslagstabeller som är interna för Adobe. Varje värde baseras på [hänvisare](referrer.md) av träffen, som är beroende av [Interna URL-filter](/help/admin/admin/internal-url-filter-admin.md). Kontrollera att referensdimensionen och interna URL-filter är korrekt konfigurerade.

## Dimensioner

Bland Dimensionerna finns sökmotorer som används för att nå din webbplats. Exempelvärden innehåller `"Google"`, `"Microsoft Bing"`och `"DuckDuckGo"`. The `"Unspecified"` dimensionsobjektet är all trafik som inte söks.
