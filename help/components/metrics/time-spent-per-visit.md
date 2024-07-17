---
title: Tid per besök (mätvärden)
description: Den tid som tillbringats per besök för dimensionsobjektet.
feature: Metrics
exl-id: 0f951196-66a2-4733-bb62-4555a9331efb
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '263'
ht-degree: 0%

---

# Tid per besök (sekunder)

*Den här hjälpsidan beskriver hur&quot;Tid per besök&quot; fungerar som ett mått. Mer information finns i dimensionen [Tid per besök](../dimensions/time-spent-per-visit.md).*

[Mätvärdet](overview.md) för hur lång tid som tillbringats per besök (sekunder) visar den genomsnittliga tid som besökarna interagerar med ett visst dimensionsobjekt under varje besök.

Det här måttet är inte tillgängligt i Data Warehouse på grund av dess olika bearbetningsarkitektur.

## Hur det här måttet beräknas

Detta mått använder formeln [`[Total seconds spent]`](total-seconds-spent.md) `divided by (`[`[Visits]`](visits.md) `minus` [`[Bounces]`](bounces.md)`)`.

## Jämförelse med genomsnittlig tid på plats

Det här måttet och [Genomsnittlig tid på platsen](average-time-on-site.md) är lika, men har flera viktiga skillnader. I båda mätvärdena används&quot;Totalt antal sekunder som spenderas&quot; som täljare. I&quot;Genomsnittlig tid på plats&quot; används sekvenser som innehåller en dimensionspost som nämnare. Tid per besök använder besöket som nämnare.

Därför ger dessa mätvärden liknande resultat på besöksnivå, men skiljer sig åt på en träffnivå.

## Procent över 100 %

Det här måttet innehåller ofta procenttal över 100 %. Nämnaren är hela dimensionens tid per besök och täljaren är dimensionspostens tid per besök. Om hela dimensionens tid per besök är kortare än en given dimensionsposts tid per besök kommer du att se procenttal över 100 %. Sortering av rankade rapporter efter detta mätresultat visar onormal tid per besöksvärde, vilket vanligtvis inte är värdefullt. Adobe rekommenderar sortering efter ett annat mått, som [Besök](visits.md), i rankade rapporter.

Mer allmän information om hur lång tid du tillbringar finns i [Tidsåtgång - översikt](time-spent.md).
