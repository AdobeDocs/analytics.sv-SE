---
title: Besök enstaka sidor
description: En flagga som anger att besöket bestod av en enda sida.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '143'
ht-degree: 0%

---


# Besök enstaka sidor

*Den här hjälpsidan beskriver hur&quot;Enstaka sidbesök&quot; fungerar som en dimension. Mer information finns i Mätvärden för besök[på en](../metrics/single-page-visits.md)sida.*

Dimensionen för besök på en sida visar antalet besök som bestod av en enda unik [sidobjektdimension](page.md) . Det är dimensionsformen för [enkelsidiga besöksmått](../metrics/single-page-visits.md) .

Den här dimensionen används oftast som en komponent i [segmenteringen](../c-segmentation/seg-home.md). Det används vanligtvis inte som en dimension i rapporter.

## Fyll den här dimensionen med data

Den här dimensionen fungerar som den ska för alla implementeringar. Om en rapportsvit innehåller data fungerar den här dimensionen.

## Dimensionsobjekt

Den enda dimensionsartikeln är `"Enabled"`. Om ett besök består av en enda sida ställs träffen in på det här värdet. Alla andra träffar utelämnas i den här rapporten.
