---
title: Besök enstaka sidor
description: En flagga som anger att besöket bestod av en enda sida.
translation-type: tm+mt
source-git-commit: 54aeaa35fea8f725c87030936fa24f415064e333
workflow-type: tm+mt
source-wordcount: '143'
ht-degree: 0%

---


# Besök enstaka sidor

*Den här hjälpsidan beskriver hur&quot;Enstaka sidbesök&quot; fungerar som en dimension. Mer information finns i Mätvärden för besök[på en](../metrics/single-page-visits.md)sida.*

Dimensionen för besök på en sida visar antalet besök som bestod av ett enda unikt [siddimensionsvärde](page.md) . Det är dimensionsformen för [enkelsidiga besöksmått](../metrics/single-page-visits.md) .

Den här dimensionen används oftast som en komponent i [segmenteringen](../c-segmentation/seg-home.md). Det används vanligtvis inte som en dimension i rapporter.

## Fyll den här dimensionen med data

Den här dimensionen fungerar som den ska för alla implementeringar. Om en rapportsvit innehåller data fungerar den här dimensionen.

## Dimensionsvärden

Det enda dimensionsvärdet är `"Enabled"`. Om ett besök består av en enda sida ställs träffen in på det här värdet. Alla andra träffar utelämnas i den här rapporten.
