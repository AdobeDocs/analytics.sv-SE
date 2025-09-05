---
title: Sökmotor
description: Sökmotorn som besökaren använde för att nå din webbplats.
feature: Dimensions
exl-id: 2815f1fa-d938-4d2b-b864-c4ed834f3ed3
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '224'
ht-degree: 0%

---

# Sökmotor

Sökmotorn [dimension](overview.md) rapporterar sökmotorerna som besökarna använder för att nå din webbplats. En referent måste uppfylla båda följande för att kunna klassificeras som sökmotor:

* Den refererande domänen känns igen av Adobe som en giltig sökmotor.
* Det finns en nyckelordsfrågesträngsparameter i den refererande URL:en. Frågesträngsparametern kan vara tom (vilket är fallet med flera sökmotorer på grund av sekretesspraxis).

Om du vill skilja på betald och naturlig sökning måste du [identifiera betald sökning](/help/admin/tools/manage-rs/edit-settings/general/paid-search-detection/paid-search-detection.md). Det finns flera dimensioner för sökmotorer:

* **Sökmotor**: Sökmotorn som används för att nå din webbplats, oavsett om den är betald eller naturlig.
* **Sökmotor - betald**: Sökmotorn som användes för att nå din webbplats, vilket matchade betald sökningsidentifiering.
* **Sökmotor - naturlig**: Sökmotorn som användes för att nå din webbplats, vilket inte matchade betalsökningsidentifiering.

## Fyll den här dimensionen med data

Den här dimensionen refererar till flera uppslagstabeller som är interna för Adobe. Varje värde baseras på [referenten](referrer.md) för träffen, som är beroende av [interna URL-filter](/help/admin/tools/manage-rs/edit-settings/general/internal-url-filter-admin.md). Kontrollera att referensdimensionen och interna URL-filter är korrekt konfigurerade.

## Dimension-objekt

Dimension objekt innehåller sökmotorer som används för att nå din webbplats. Exempelvärden är `"Google"`, `"Microsoft Bing"` och `"DuckDuckGo"`. Dimensionsobjektet `"Unspecified"` är all trafik som inte söks.
