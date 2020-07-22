---
title: Tid per besökare (sekunder)
description: null
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '153'
ht-degree: 0%

---


# Tid per besökare (sekunder)

Mätvärdet&quot;Tid per besökare (sekunder)&quot; visar den genomsnittliga tid som besökarna interagerar med ett visst dimensionsobjekt under en besökares hela livstid.

Det här måttet är inte tillgängligt i Data warehouse på grund av dess olika bearbetningsarkitektur.

## Hur det här måttet beräknas

Det här måttet använder formeln [`Total seconds spent`](total-seconds-spent.md) `divided by` [`Unique visitors`](unique-visitors.md).

## Procent över 100 %

Det här måttet innehåller ofta procenttal över 100 %. Nämnaren är hela dimensionens tid per besökare, och täljaren är dimensionsobjektets tid per besökare. Om hela dimensionens tid per besökare är mindre än en given dimensionsposts tid per besökare, kommer du att se procenttal över 100 %. Sortering av rankade rapporter efter det här måttet visar onormal tid per besökarvärde, vilket vanligtvis inte är värdefullt. Adobe rekommenderar sortering efter andra mätvärden, till exempel [Besök](visits.md), i rankade rapporter.

Mer allmän information om hur lång tid du tillbringar finns i [Tidsåtgång - översikt](time-spent.md) .
