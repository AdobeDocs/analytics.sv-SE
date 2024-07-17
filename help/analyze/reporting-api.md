---
description: Resurser och länkar för Reporting API.
title: API för analysrapportering
uuid: 68ec3490-6e47-4606-860d-dd5e89c574a1
feature: API
role: Developer
exl-id: 003a8b83-6ef0-4313-903a-b76078558d55
source-git-commit: d173a6c6c9751a86f4218ec842da17da14f8485b
workflow-type: tm+mt
source-wordcount: '131'
ht-degree: 5%

---

# API för analysrapportering

Dokumentation för Adobe Analytics API:er finns på [Adobe Developer](https://developer.adobe.com/analytics-apis/docs/2.0/).

## Jämförelse av API:er i Analytics

| **API-typ** | **Fullt bearbetad** | **Realtid** | **Livesream** | **Data Warehouse** |
| --- | --- | --- | --- | --- |
| **Beskrivning** | Fullständigt bearbetade, slutförda data som är tillgängliga i alla Analytics-gränssnitt. | Delvis bearbetade, begränsade mätvärden är tillgängliga inom några sekunder efter insamlingen. | Delvis bearbetade träffdata är tillgängliga inom några sekunder efter insamlingen. | Fullständigt bearbetade, slutförda data som används för att dra igång stora dataexporter. |
| [**Latens**](/help/technotes/latency.md) | 30-90 minuter | Sekunder - 10 minuter | Sekunder - 10 minuter | 90+ minuter |
| **Bearbetning slutförd** | Fullständig | Delvis | Delvis | Fullständig |
| **Rapporteringsgränssnitt** | Analysis Workspace, Report Builder, API | Realtidsrapport i Report Builder, 1.4 API | Endast API | Data Warehouse, API |
| **Datagranularitet** | Sammanfattad | Sammanfattad | Träffnivå | Sammanfattad |
| **Bearbetning av besökarprofiler** | Ja | Nej | Nej | Ja |
| **Segmentstöd** | Ja | Nej | Nej | Delvis |
