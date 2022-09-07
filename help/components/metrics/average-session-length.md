---
title: Genomsnittlig sessionslängd (mobil)
description: Den genomsnittliga sessionslängden för den mobila enheten.
feature: Metrics
exl-id: e33ac9ca-f1be-4d9c-9247-c5db8fb0102e
source-git-commit: 47d5a532505aff48d43972836c78620870bd8221
workflow-type: tm+mt
source-wordcount: '89'
ht-degree: 0%

---

# Genomsnittlig sessionslängd (mobil)

Mätvärdet för genomsnittlig sessionslängd (mobil) visar den genomsnittliga tiden som en given dimensionspost finns per dimensionspost. Det liknar [Tid per besök [sekunder]](https://experienceleague.adobe.com/docs/analytics/components/metrics/time-spent-per-visit.html) Mått, förutom det här måttet, använder SDK-specifika komponenter för mobilen som en del av beräkningen.

## Hur det här måttet beräknas

Det här måttet beräknas med [mobilstatistik](https://experienceleague.adobe.com/docs/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html) `'Total session length' / ('Launches' - 'First launches'`.
