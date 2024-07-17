---
title: Enkelsidiga besök (dimensioner)
description: En flagga som anger att besöket bestod av en enda sida.
feature: Dimensions
exl-id: f7b58941-add4-4e7b-8645-a64280fd9dcb
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '144'
ht-degree: 0%

---

# Besök enstaka sidor

*Den här hjälpsidan beskriver hur Enkelsidiga besök fungerar som en [dimension](overview.md). Mer information finns i måtten för [besök på en sida](../metrics/single-page-visits.md).*

Dimensionen för besök på en sida rapporterar antalet besök som bestod av ett enda unikt [Page](page.md)-dimensionsobjekt. Det är dimensionsformen för måttet [Enkelsidiga besök](../metrics/single-page-visits.md).

Den här dimensionen används oftast som en komponent i [segmentering](../segmentation/seg-home.md). Det används vanligtvis inte som en dimension i rapporter.

## Fyll den här dimensionen med data

Den här dimensionen fungerar som den ska för alla implementeringar. Om en rapportsvit innehåller data fungerar den här dimensionen.

## Dimensioner

Den enda dimensionsobjektet är `"Enabled"`. Om ett besök består av en enda sida ställs träffen in på det här värdet. Alla andra träffar utelämnas i den här rapporten.
