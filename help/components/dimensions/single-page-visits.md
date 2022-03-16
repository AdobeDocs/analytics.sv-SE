---
title: Enkelsidiga besök (dimensioner)
description: En flagga som anger att besöket bestod av en enda sida.
feature: Dimensions
exl-id: f7b58941-add4-4e7b-8645-a64280fd9dcb
source-git-commit: 10ff98f7ca4697afe5c2dae66be415c0d68c4aac
workflow-type: tm+mt
source-wordcount: '144'
ht-degree: 0%

---

# Besök enstaka sidor

*Den här hjälpsidan beskriver hur&quot;Enstaka sidbesök&quot; fungerar som en dimension. Se [Besök enstaka sidor](../metrics/single-page-visits.md) för mer information.*

Dimensionen för besök på en sida visar antalet besök som bestod av en enda unik [Sida](page.md) dimensionsobjekt. Det är dimensionsformen för [Besök enstaka sidor](../metrics/single-page-visits.md) mätvärden.

Den här dimensionen används oftast som en komponent i [segmentering](../segmentation/seg-home.md). Det används vanligtvis inte som en dimension i rapporter.

## Fyll den här dimensionen med data

Den här dimensionen fungerar som den ska för alla implementeringar. Om en rapportsvit innehåller data fungerar den här dimensionen.

## Dimensioner

Den enda dimensionsartikeln är `"Enabled"`. Om ett besök består av en enda sida ställs träffen in på det här värdet. Alla andra träffar utelämnas i den här rapporten.
