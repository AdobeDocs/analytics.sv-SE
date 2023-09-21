---
title: Vecka
description: Veckan som måttet inträffade på.
feature: Dimensions
exl-id: 944ec843-998c-473f-b8e6-16cf126745b4
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '141'
ht-degree: 0%

---

# Vecka

Veckan [dimension](overview.md) rapporterar veckan att ett givet mätvärde inträffade. Den första dimensionsuppgiften är den första veckan i datumintervallet och den sista dimensionsuppgiften är den sista veckan i datumintervallet. Denna dimension är viktig för trendrapporter, eftersom den gör att ni kan se mätvärden över tid.

## Fyll den här dimensionen med data

Den här dimensionen fungerar som den ska för alla implementeringar. Om en rapportsvit innehåller data fungerar den här dimensionen.

## Dimensioner

I Analysis Workspace omfattar dimensionsobjekten datumet (månad, dag och år) för den första dagen i veckan.

I Data Warehouse innehåller dimensionsobjekten numrerade veckor baserat på begärans datumintervall. Den första hela veckan är till exempel `"Week 1"`. Om en begäran innehåller en partiell vecka grupperas data i dimensionsposten `"Week 0"`.
