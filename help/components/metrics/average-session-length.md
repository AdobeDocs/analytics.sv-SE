---
title: Genomsnittlig sessionslängd (mobil)
description: Den genomsnittliga sessionslängden för den mobila enheten.
translation-type: tm+mt
source-git-commit: 625af73ad2fbe4b44bce00a122c4e65d8964323f
workflow-type: tm+mt
source-wordcount: '83'
ht-degree: 0%

---


# Genomsnittlig sessionslängd (mobil)

Mätvärdet för genomsnittlig sessionslängd (mobil) visar den genomsnittliga tiden som ett givet dimensionsvärde finns per dimensionsvärde. Det liknar [medeltiden på platsens](average-time-on-site.md) mått, men det här måttet använder SDK-specifika komponenter för mobilen som en del av beräkningen.

## Hur det här måttet beräknas

Det här måttet beräknas med hjälp av [mobilstatistik](https://docs.adobe.com/content/help/en/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html) `'Total session length' / ('Launches' - 'First launches'`.
