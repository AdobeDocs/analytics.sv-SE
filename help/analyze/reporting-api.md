---
description: Resurser och länkar för Reporting API.
title: API för Analytics-rapportering
uuid: 68ec3490-6e47-4606-860d-dd5e89c574a1
feature: API
role: Developer
exl-id: 003a8b83-6ef0-4313-903a-b76078558d55
source-git-commit: 8f25dfefbc6fba1fb525d2e9e0fce654e21ef362
workflow-type: tm+mt
source-wordcount: '132'
ht-degree: 12%

---

# API för Analytics-rapportering

Dokumentationen för Adobe Analytics API:er är aktiverad [Adobe Developer](https://developer.adobe.com/analytics-apis/docs/2.0/).

## Jämförelse av API:er i Analytics

| **API-typ** | **Fullt bearbetad** | **Realtid** | **Livesream** | **Data Warehouse** |
| --- | --- | --- | --- | --- |
| **Beskrivning** | Fullständigt bearbetade, slutförda data som är tillgängliga i alla Analytics-gränssnitt. | Delvis bearbetade, begränsade mätvärden är tillgängliga inom några sekunder efter insamlingen. | Delvis bearbetade träffdata är tillgängliga inom några sekunder efter insamlingen. | Fullständigt bearbetade, slutförda data som används för att dra igång stora dataexporter. |
| [**Latens**](/help/technotes/latency.md) | 30-90 minuter | Sekunder - 10 minuter | Sekunder - 10 minuter | 90+ minuter |
| **Slutförd bearbetning** | Fullständig | Delvis | Delvis | Fullständig |
| **Rapporteringsgränssnitt** | Analysis Workspace, Reports &amp; Analytics, Report Builder, API | Real-Time Report in Reports &amp; Analytics, Report Builder, 1.4 API | Endast API | data warehouse, API |
| **Datagranularitet** | Sammanfattad | Sammanfattad | Träffnivå | Sammanfattad |
| **Bearbetning av besökarprofiler** | Ja | Nej | Nej | Ja |
| **Segmentstöd** | Ja | Nej | Nej | Delvis |
