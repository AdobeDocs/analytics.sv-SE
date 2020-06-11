---
title: Tid per besök
description: Den tid som spenderats per besök för dimensionsvärdet.
translation-type: tm+mt
source-git-commit: 5282ad3f6fdd2853979cbfb2707cc07a698f63a7
workflow-type: tm+mt
source-wordcount: '259'
ht-degree: 0%

---


# Tid per besök (sekunder)

*Den här hjälpsidan beskriver hur&quot;Tid per besök&quot; fungerar som ett mått. Mer information finns i[tidsåtgången per besök](../dimensions/time-spent-per-visit.md).*

Mätvärdet&quot;Tid per besök (sekunder)&quot; visar den genomsnittliga tid som besökarna interagerar med ett visst dimensionsvärde under varje besök.

Det här måttet är inte tillgängligt i datalagret på grund av dess olika bearbetningsarkitektur.

## Hur det här måttet beräknas

Det här måttet använder formeln [`Total seconds spent`](total-seconds-spent.md) ( `divided by`[`Visits`](visits.md)`minus` [`Bounces`](bounces.md)).

## Jämförelse med genomsnittlig tid på plats

Detta mått och [genomsnittlig tid på platsen](average-time-on-site.md) är lika, men har flera viktiga skillnader. I båda mätvärdena används&quot;Totalt antal sekunder som spenderas&quot; som täljare. I&quot;Genomsnittlig tid på plats&quot; används sekvenser som innehåller en dimensionspost som nämnare. Tid per besök använder besöket som nämnare.

Därför ger dessa mätvärden liknande resultat på besöksnivå, men skiljer sig åt på en träffnivå.

## Procent över 100 %

Det här måttet innehåller ofta procenttal över 100 %. Nämnaren är hela dimensionens tid per besök, och täljaren är dimensionvärdets tid per besök. Om hela dimensionens tid per besök är kortare än den tid som en viss dimension tillbringar per besök, kommer du att se procenttal över 100 %. Sortering av rankade rapporter efter detta mätresultat visar onormal tid per besöksvärde, vilket vanligtvis inte är värdefullt. Adobe rekommenderar sortering efter andra mätvärden, till exempel [Besök](visits.md), i rankade rapporter.

Mer allmän information om hur lång tid du tillbringar finns i [Tidsåtgång - översikt](time-spent.md) .
