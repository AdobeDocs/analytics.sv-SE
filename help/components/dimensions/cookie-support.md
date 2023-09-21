---
title: Cookie-stöd
description: Anger om webbläsaren stöder cookies.
feature: Dimensions
exl-id: 07d4fe12-0d60-469d-98b1-e93ce5a0fd21
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '188'
ht-degree: 0%

---

# Cookie-stöd

Cookie-stöd [dimension](overview.md) rapporterar om webbläsaren stöder cookies för en viss träff. Det är användbart att bestämma hur många besökare som använder webbläsare som stöder cookies och vilka som avsiktligt inaktiverar dem.

## Fyll den här dimensionen med data

Den här dimensionen samlar in data från [`k` frågesträng](/help/implement/validate/query-parameters.md) i bildbegäranden. AppMeasurementet försöker ange en cookie med namnet `s_cc`identifierar sedan om cookien finns. Resultatet är frågesträngens parametervärde `Y` (om webbläsaren stöder och har aktiverat cookies) eller `N` (om webbläsaren har inaktiverat cookies). Om du använder AppMeasurement (till exempel via taggar i Adobe Experience Platform) fungerar den här dimensionen automatiskt. Om du använder en datainsamlingsmetod utanför AppMeasurementet (till exempel via API:t) måste du ta med `k` frågesträngsparameter för varje träff med värdet `Y` eller `N`.

## Dimensioner

Dimensionerna innehåller `Enabled`, `Disabled`och `Unknown`.

* **`Enabled`**: Webbläsaren stöder cookies och har dem aktiverade.
* **`Disabled`**: Webbläsaren stöder inte cookies eller så har besökaren inaktiverat dem.
* **`Unknown`**: AppMeasurementet kunde inte fastställa stöd för cookies. The `k` frågesträngen fanns inte i bildbegäran.
