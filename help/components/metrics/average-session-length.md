---
title: Genomsnittlig sessionslängd (mobil)
description: Den genomsnittliga sessionslängden för den mobila enheten.
feature: Metrics
exl-id: e33ac9ca-f1be-4d9c-9247-c5db8fb0102e
source-git-commit: e32821dd3f30404166554b8437c508172e4764e5
workflow-type: tm+mt
source-wordcount: '69'
ht-degree: 0%

---

# Genomsnittlig sessionslängd (mobil)

Sessionens genomsnittliga längd (mobil) [mått](overview.md) visar den genomsnittliga tiden som ett angivet dimensionsobjekt finns per dimensionsobjekt. Det liknar måttet [[!UICONTROL Time spent per visit (seconds)]](time-spent-per-visit.md), förutom att det här måttet använder SDK-specifika komponenter för mobilen som en del av beräkningen.

## Hur det här måttet beräknas

Det här måttet beräknas med [Livscykelmåtten](https://developer.adobe.com/client-sdks/documentation/mobile-core/lifecycle/metrics/) `'Total Session length' / ('Launches' - 'First launches'`.
