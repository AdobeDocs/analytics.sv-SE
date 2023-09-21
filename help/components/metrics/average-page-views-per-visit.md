---
title: Genomsnittlig sidvisning per besök
description: Genomsnittligt antal gånger en given dimensionspost påträffades vid ett besök.
feature: Metrics
exl-id: fef6e803-e819-4f0f-8cb0-c565328a8bea
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '212'
ht-degree: 0%

---

# Genomsnittlig sidvisning per besök

Dimensionen för genomsnittlig sidvisning per besök visar hur många sidvisningar som i genomsnitt inträffade mot den önskade dimensionen. När det gäller tidsbaserade dimensioner kan du se hur det genomsnittliga antalet sidvisningar inom en besökstrender över tid. Detta [mått](overview.md) är användbart när du vill veta hur ofta dimensionsobjekt visas vid ett besök.

>[!TIP]
>
>Använd det här måttet tillsammans med ett annat mått (som [Besök](visits.md)) för att få bättre insikter. Om du bara använder det här måttet får du dimensionsobjekt som innehåller avvikande sidvisningar per besök, vilket vanligtvis inte är värdefullt.

## Hur det här måttet beräknas

Det här måttet beräknas med hjälp av formeln [`Page views`](page-views.md)` divided by `[`Visits`](visits.md).

## Procent över 100 %

Det här måttet innehåller ofta procenttal över 100 %. Nämnaren är hela dimensionens genomsnittliga sidvisningar per besök, och täljaren är dimensionsobjektets genomsnittliga sidvisningar per besök. Om den genomsnittliga sidvisningen per besök för hela dimensionen är lägre än den genomsnittliga sidvisningen per besök för en viss dimensionspost, kommer du att se procenttal över 100 %. Sortering av rankade rapporter efter det här måttet visar en onormal genomsnittlig sidvisning per besöksvärde, vilket vanligtvis inte är värdefullt. Adobe rekommenderar sortering med ett annat mått, som [Besök](visits.md), i rankade rapporter.
