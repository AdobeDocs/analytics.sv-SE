---
title: Beräknade mätsummor
description: Läs om beräknade mätvärden i Analysis Workspace
feature: Calculated Metrics
exl-id: 3e4429de-3e0c-49a5-b32c-3a4d24a29816
source-git-commit: be5a73347d417c8dc6667d4059e7d46ef5f0f5cd
workflow-type: tm+mt
source-wordcount: '143'
ht-degree: 0%

---

# Beräknade mätvärden i Analysis Workspace

När du visar data i Analysis Workspace visas i de flesta fall beräknade mätvärden. I vissa fall går det inte att ange en summa, till exempel när raderna i rapporten har blandat format (t.ex. decimal och valuta).

När summorna visas beräknas de ofta på serversidan, vilket innebär att den totala mängden avduplicerade mått, som besök eller besökare. Under vissa omständigheter genereras beräknade värden på klientsidan genom summering över tabellraderna, vilket innebär att summan inte avduplicerar mått som besök eller besökare. Detta inträffar:

* När [statiska rader](/help/analyze/analysis-workspace/visualizations/freeform-table/column-row-settings/manual-vs-dynamic-rows.md) används i frihandstabeller och **[!UICONTROL Show as sum of current rows]** (standard) är valt.
* I [Visualisering av ring](/help/analyze/analysis-workspace/visualizations/donut.md)så att siffrorna blir upp till 100 %.

Mer information om totalsummor i Analysis Workspace finns på [Summor för arbetsyta](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/freeform-table/workspace-totals.html#static-row-total).
