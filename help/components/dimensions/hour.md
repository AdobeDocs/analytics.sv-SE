---
title: Timme
description: Den timme som mätvärdet inträffade på.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '107'
ht-degree: 0%

---


# Timme

Dimensionen Timme anger timmen då ett givet mätresultat inträffade (avrundat nedåt). Den första dimensionsartikeln är den första timmen i datumintervallet, och den sista dimensionsartikeln är den sista timmen i datumintervallet. Denna dimension är värdefull för trendrapporter eftersom den gör att du kan se mätvärden över tid.

## Fyll den här dimensionen med data

Den här dimensionen fungerar som den ska för alla implementeringar. Om en rapportsvit innehåller data fungerar den här dimensionen.

## Dimensionsobjekt

Dimensionsobjekten inkluderar en given timme inom rapportens datumintervall tillsammans med dess datum. Den är formaterad som `HH:HH YYYY-MM-DD`.
