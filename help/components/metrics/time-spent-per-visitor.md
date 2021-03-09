---
title: Tid per besökare (sekunder)
description: Mätvärdet"Tid per besökare (sekunder)" visar den genomsnittliga tid som besökarna interagerar med ett visst dimensionsobjekt under en besökares hela livstid.
translation-type: tm+mt
source-git-commit: 4d0d5ca99049e48fcf1f248f78ecef94534b6815
workflow-type: tm+mt
source-wordcount: '174'
ht-degree: 0%

---


# Tid per besökare (sekunder)

Måttet [!UICONTROL Time spent per visitor (seconds)] visar den genomsnittliga tiden som besökare interagerar med ett visst dimensionsobjekt under en besökares hela livstid.

Det här måttet är inte tillgängligt i Data warehouse på grund av dess olika bearbetningsarkitektur.

## Hur det här måttet beräknas

Det här måttet använder formeln [`Total seconds spent`](total-seconds-spent.md) `divided by` [`Unique visitors`](unique-visitors.md).

## Procent över 100 %

Det här måttet innehåller ofta procenttal över 100 %. Nämnaren är hela dimensionens tid per besökare, och täljaren är dimensionsobjektets tid per besökare. Om hela dimensionens tid per besökare är mindre än en given dimensionsposts tid per besökare, kommer du att se procenttal över 100 %. Sortering av rankade rapporter efter det här måttet visar onormal tid per besökarvärde, vilket vanligtvis inte är värdefullt. Adobe rekommenderar sortering efter ett annat mått, som [Besök](visits.md), i rankade rapporter.

Mer allmän information om hur lång tid du tillbringar finns i [Översikt över tidsåtgången](time-spent.md).
