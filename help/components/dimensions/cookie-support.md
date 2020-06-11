---
title: Cookie-stöd
description: Anger om webbläsaren stöder cookies.
translation-type: tm+mt
source-git-commit: a8dc233e962a49674a30ff3c9f0b5d0d45b09f24
workflow-type: tm+mt
source-wordcount: '187'
ht-degree: 0%

---


# Cookie-stöd

Dimensionsrapporten &#39;Cookie support&#39; om webbläsaren stöder cookies för en viss träff. Det är användbart att bestämma hur många besökare som använder webbläsare som stöder cookies och vilka som avsiktligt inaktiverar dem.

## Fyll den här dimensionen med data

Den här dimensionen samlar in data från [`k` frågesträngen](/help/implement/validate/query-parameters.md) i bildbegäranden. AppMeasurement försöker ange en cookie med namnet `s_cc`och identifierar sedan om cookien finns. Resultatet är parametervärdet för frågesträngen `Y` (om webbläsaren stöder och har aktiverat cookies) eller `N` (om webbläsaren har inaktiverat cookies). Om du använder AppMeasurement (till exempel via Adobe Experience Platform Launch) fungerar den här dimensionen som den ska. Om du använder en datainsamlingsmetod utanför AppMeasurement (till exempel via API:t) måste du ta med frågesträngsparametern för varje träff med värdet `k` eller `Y` `N`.

## Dimensionsvärden

Dimensionsvärdena inkluderar `Enabled`, `Disabled`och `Unknown`.

* **`Enabled`**: Webbläsaren stöder cookies och har dem aktiverade.
* **`Disabled`**: Webbläsaren stöder inte cookies eller så inaktiverades de av besökaren.
* **`Unknown`**: AppMeasurement kunde inte fastställa stöd för cookies. Frågesträngen fanns inte i bildbegäran `k` .
