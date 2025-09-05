---
title: Beräknade mätsummor
description: Läs om beräknade mätvärden i Analysis Workspace
feature: Calculated Metrics
exl-id: 3e4429de-3e0c-49a5-b32c-3a4d24a29816
source-git-commit: 325a42c080290509309e90c9127138800d5ac496
workflow-type: tm+mt
source-wordcount: '139'
ht-degree: 0%

---

# Beräknade mätsummor

När du visar data i Analysis Workspace visas i de flesta fall beräknade mätvärden. I vissa fall går det inte att ange en summa, till exempel när raderna i rapporten har blandat format (t.ex. decimal och valuta).

När summorna visas beräknas de ofta på serversidan, vilket innebär att den totala mängden avduplicerade mått, som besök eller besökare. Under vissa omständigheter genereras beräknade värden på klientsidan genom summering över tabellraderna, vilket innebär att summan inte avduplicerar mått som besök eller besökare. Detta inträffar:

* När [statiska rader](/help/analyze/analysis-workspace/visualizations/freeform-table/column-row-settings/manual-vs-dynamic-rows.md) används i frihandstabeller och alternativet **[!UICONTROL Show as sum of current rows]** (standard) är markerat.
* I [Donutvisualisering](/help/analyze/analysis-workspace/visualizations/donut.md), så att tal blir upp till 100 %.

Mer information om totalsummor i Analysis Workspace finns på [Workspace totals](/help/analyze/analysis-workspace/visualizations/freeform-table/workspace-totals.md#static-row-total).
