---
title: Genomsnittlig sidvisning per besök
description: Genomsnittligt antal gånger en given dimensionspost påträffades vid ett besök.
translation-type: tm+mt
source-git-commit: 226bbce18750825d459056ac2a87549614eb3c2c
workflow-type: tm+mt
source-wordcount: '212'
ht-degree: 0%

---


# Genomsnittlig sidvisning per besök

Dimensionen för genomsnittlig sidvisning per besök visar hur många sidvisningar som i genomsnitt inträffade mot den önskade dimensionen. När det gäller tidsbaserade dimensioner kan du se hur det genomsnittliga antalet sidvisningar inom en besökstrender över tid. Detta mått är användbart när du vill förstå hur ofta dimensionsobjekt visas vid ett besök.

>[!TIP]
>
>Använd det här måttet tillsammans med andra mätvärden (till exempel [Besök](visits.md)) för att få bättre insikter. Om du bara använder det här måttet får du dimensionsobjekt som innehåller avvikande sidvisningar per besök, vilket vanligtvis inte är värdefullt.

## Hur det här måttet beräknas

Det här måttet beräknas med hjälp av formeln [`Page views`](page-views.md)` divided by `[`Visits`](visits.md).

## Procent över 100 %

Det här måttet innehåller ofta procenttal över 100 %. Nämnaren är hela dimensionens genomsnittliga sidvisningar per besök, och täljaren är dimensionsobjektets genomsnittliga sidvisningar per besök. Om den genomsnittliga sidvisningen per besök för hela dimensionen är lägre än den genomsnittliga sidvisningen per besök för en viss dimensionspost, kommer du att se procenttal över 100 %. Sortering av rankade rapporter efter det här måttet visar en onormal genomsnittlig sidvisning per besöksvärde, vilket vanligtvis inte är värdefullt. Adobe rekommenderar sortering efter andra mätvärden, som [Besök](visits.md), i rankade rapporter.