---
title: Tid per besökare (sekunder)
description: Mätvärdet"Tid per besökare (sekunder)" visar den genomsnittliga tid som besökarna interagerar med ett visst dimensionsobjekt under en besökares hela livstid.
feature: Metrics
exl-id: 80f38bab-2ee1-4d0d-ba53-9b2c7c85e481
source-git-commit: 7d5383e1ee3bee189d3dd48bc6b899f4108f7ba8
workflow-type: tm+mt
source-wordcount: '174'
ht-degree: 0%

---

# Tid per besökare (sekunder)

The [!UICONTROL Time spent per visitor (seconds)] mätvärdet visar den genomsnittliga tiden som besökare interagerar med ett visst dimensionsobjekt under besökarens hela livstid.

Det här måttet är inte tillgängligt i Data warehouse på grund av dess olika bearbetningsarkitektur.

## Hur det här måttet beräknas

Det här måttet använder formeln [`Total seconds spent`](total-seconds-spent.md) `divided by` [`Unique visitors`](unique-visitors.md).

## Procent över 100 %

Det här måttet innehåller ofta procenttal över 100 %. Nämnaren är hela dimensionens tid per besökare, och täljaren är dimensionsobjektets tid per besökare. Om hela dimensionens tid per besökare är mindre än en given dimensionsposts tid per besökare, kommer du att se procenttal över 100 %. Sortering av rankade rapporter efter det här måttet visar onormal tid per besökarvärde, vilket vanligtvis inte är värdefullt. Adobe rekommenderar sortering med ett annat mått, som [Besök](visits.md), i rankade rapporter.

Se [Tidsåtgång - översikt](time-spent.md) om du vill ha mer allmän information om hur länge du har tillbringat.
