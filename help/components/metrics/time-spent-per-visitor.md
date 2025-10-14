---
title: Tid per besökare (sekunder)
description: Mätvärdet"Tid per besökare (sekunder)" visar den genomsnittliga tid som besökarna interagerar med ett visst dimensionsobjekt under en besökares hela livstid.
feature: Metrics
exl-id: 80f38bab-2ee1-4d0d-ba53-9b2c7c85e481
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '177'
ht-degree: 0%

---

# Tid per besökare (sekunder)

[!UICONTROL Time spent per visitor (seconds)] [Måttet &#x200B;](overview.md) visar den genomsnittliga tiden som besökare interagerar med ett visst dimensionsobjekt under en besökares hela livstid.

Det här måttet är inte tillgängligt i Data Warehouse på grund av dess olika bearbetningsarkitektur.

## Hur det här måttet beräknas

Detta mått använder formeln [`Total seconds spent`](total-seconds-spent.md) `divided by` [`Unique visitors`](unique-visitors.md).

## Procent över 100 %

Det här måttet innehåller ofta procenttal över 100 %. Nämnaren är hela dimensionens tid per besökare, och täljaren är dimensionsobjektets tid per besökare. Om hela dimensionens tid per besökare är mindre än en given dimensionsposts tid per besökare, kommer du att se procenttal över 100 %. Sortering av rankade rapporter efter det här måttet visar onormal tid per besökarvärde, vilket vanligtvis inte är värdefullt. Adobe rekommenderar sortering efter ett annat mått, som [Besök](visits.md), i rankade rapporter.

Mer allmän information om hur lång tid du tillbringar finns i [Tidsåtgång - översikt](time-spent.md).
