---
title: Genomsnittlig sessionslängd (mobil)
description: Den genomsnittliga sessionslängden för den mobila enheten.
exl-id: e33ac9ca-f1be-4d9c-9247-c5db8fb0102e
source-git-commit: f669af03a502d8a24cea3047b96ec7cba7c59e6f
workflow-type: tm+mt
source-wordcount: '81'
ht-degree: 0%

---

# Genomsnittlig sessionslängd (mobil)

Mätvärdet för genomsnittlig sessionslängd (mobil) visar den genomsnittliga tiden som en given dimensionspost finns per dimensionspost. Den liknar måttet [Genomsnittlig tid på platsen](average-time-on-site.md), förutom att det här måttet använder SDK-specifika komponenter för mobilen som en del av beräkningen.

## Hur det här måttet beräknas

Det här måttet beräknas med [mobilmåtten](https://experienceleague.adobe.com/docs/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html) `'Total session length' / ('Launches' - 'First launches'`.
