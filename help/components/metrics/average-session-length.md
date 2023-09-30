---
title: Genomsnittlig sessionslängd (mobil)
description: Den genomsnittliga sessionslängden för den mobila enheten.
feature: Metrics
exl-id: e33ac9ca-f1be-4d9c-9247-c5db8fb0102e
source-git-commit: e32821dd3f30404166554b8437c508172e4764e5
workflow-type: tm+mt
source-wordcount: '75'
ht-degree: 0%

---

# Genomsnittlig sessionslängd (mobil)

Sessionslängden i genomsnitt (mobil) [mått](overview.md) visar den genomsnittliga tiden som en given dimensionsuppgift finns per dimensionsuppgift. Det liknar [[!UICONTROL Time spent per visit (seconds)]](time-spent-per-visit.md) Mått, förutom det här måttet, använder SDK-specifika mobilkomponenter som en del av beräkningen.

## Hur det här måttet beräknas

Det här måttet beräknas med [Livscykelstatistik](https://developer.adobe.com/client-sdks/documentation/mobile-core/lifecycle/metrics/) `'Total Session length' / ('Launches' - 'First launches'`.
