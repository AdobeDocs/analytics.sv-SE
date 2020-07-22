---
title: Genomsnittlig sessionslängd (mobil)
description: Den genomsnittliga sessionslängden för den mobila enheten.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '83'
ht-degree: 0%

---


# Genomsnittlig sessionslängd (mobil)

Mätvärdet för genomsnittlig sessionslängd (mobil) visar den genomsnittliga tiden som en given dimensionspost finns per dimensionspost. Det liknar [medeltiden på platsens](average-time-on-site.md) mått, men det här måttet använder SDK-specifika komponenter för mobilen som en del av beräkningen.

## Hur det här måttet beräknas

Det här måttet beräknas med hjälp av [mobilstatistik](https://docs.adobe.com/content/help/en/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html) `'Total session length' / ('Launches' - 'First launches'`.
