---
description: Systemkrav och en jämförelse av Analysis Workspace, Report Builder, Data Warehouse och Data Workbench
title: Produktjämförelse och krav för analyser
exl-id: 5adc6c10-cbbb-48d5-a7ab-367cbaff5e8a
feature: Analytics Basics
source-git-commit: 16046af6b7a78bdc4bfaf7e5ec7d05c55f2ebc01
workflow-type: tm+mt
source-wordcount: '340'
ht-degree: 17%

---

# Produktjämförelse och krav för analyser

Den här sidan innehåller en jämförelse av olika Adobe Analytics-produkter: Analysis Workspace, Report Builder, Data Warehouse, Data Feeds och Analytics API 2.0.

Mer information om vilken Adobe Analytics-produkt som ska användas finns i [Vilket Adobe Analytics-verktyg ska jag använda?](/help/analyze/get-started/which-analytics-tool.md).

| Produkt- och hjälplänk | [Analysis Workspace](/help/analyze/analysis-workspace/home.md) | [Report Builder](/help/analyze/report-builder/report-buider-overview.md) | [Data Warehouse](/help/export/data-warehouse/data-warehouse.md) | [Datafeeds](/help/export/analytics-data-feed/data-feed-overview.md) | [Analytics API 2.0](https://www.adobe.io/apis/experiencecloud/analytics/docs.html) |
|---|---|---|---|---|---|
| **Åtkomstmetod** | [Webbläsare](/help/analyze/get-started/sys-reqs.md) | [MS Excel för Windows](/help/analyze/legacy-report-builder/setup/system-requirements.md) | Konfigurera via webbläsaren. [Läs mer](/help/analyze/get-started/sys-reqs.md) | Konfigurera via webbläsaren. [Läs mer](/help/export/analytics-data-feed/data-feed-overview.md) | RESTful API tools. Logga in med Adobe Developer inloggningsuppgifter. [Läs mer](https://developer.adobe.com/analytics-apis/docs/2.0/) |
| **Datagranularitet** | Sammanställd | Sammanställd | Sammanställd | Träff | Sammanställd |
| **Experience Cloud-ID (ECID) tillgängligt** | Nej | Nej | Ja | Ja | Nej |
| **Tidsstämpel tillgänglig** | Nej | Nej | Nej | Ja | Nej |
| **Bearbetningsnivå** | Fullt bearbetad | Fullständigt bearbetad, med separat [realtidsrapport](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/realtime/realtime.md) | Fullt bearbetad | Fullt bearbetad | Fullt bearbetad |
| **Administratörsfilterdata ingår** <br> [Läs mer](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/bot-removal.md) | Nej | Ja - separat robotrapport | Nej | Nej | Nej |
| **Låg trafik (Uniques-gräns) visas** <br> [Läs mer](/help/technotes/low-traffic.md) | Ja | Ja | Nej | Nej | Ja |
| **Synlig radgräns (före sidnumrering)** | 400 | 50000 | Obegränsad | Obegränsad | 50000 |
| **Flera rapportsviter** | [Ja](/help/analyze/analysis-workspace/build-workspace-project/multiple-report-suites.md) | Ja | Nej | Ja | Nej | Ja |
| **Antal uppdelningar** | Obegränsad | Upp till 2 | Obegränsad | Obegränsad | Obegränsat, kör över flera frågor |
| **Segmentering** <br> [Läs mer](/help/components/segmentation/segmentation-workflow/seg-workflow.md) | Ja | Ja | Ja, med [begränsningar](/help/components/segmentation/seg-reference/seg-compatibility.md) | Nej | Ja |
| **Beräknade mått** <br> [Läs mer](/help/components/c-calcmetrics/cm-overview.md) | Ja, med [Attribution](/help/analyze/analysis-workspace/attribution/overview.md) | Ja, med attribuering | Ja | Nej | Ja, med [Attribution](/help/analyze/analysis-workspace/attribution/overview.md) |
| **Marknadsföringskanaler** <br> [Läs mer](/help/components/c-marketing-channels/c-getting-started-mchannel.md) | Ja | Ja | Ja | Ja - [va_finder, va_close](/help/export/analytics-data-feed/c-df-contents/datafeeds-reference.md) | Ja |
| **Kohortanalys** | [Ja](/help/analyze/analysis-workspace/visualizations/cohort-table/cohort-analysis.md) | Ja | Nej | Nej | Nej |
| **Attribution** | Ja, med [Attribution](/help/analyze/analysis-workspace/attribution/overview.md) | Begränsad | Nej | Nej | Ja, med [Attribution](/help/analyze/analysis-workspace/attribution/overview.md) | Nej |
| **Kuration** <br> [Läs mer](/help/analyze/analysis-workspace/curate-share/curate.md) | Ja - Project och Virtual Report Suite | Nej | Nej | Nej | Ja - endast Virtual Report Suite |
| **Projektdelning** <br> [Läs mer](/help/analyze/analysis-workspace/curate-share/share-projects.md) | Ja, med projektroller | Ja | Nej | Nej | Nej |
| **Schemalagd leverans** | Ja | Ja | Ja | Ja | Nej |
| **Leveransmål** | E-post | E-post, FTP, SFTP, [publicera till Microsoft PowerBI](/help/analyze/legacy-report-builder/c-publish-power-bi/power-bi.md) | Amazon S3, Google Cloud Platform, Azure SAS, Azure RBAC och e-post | Amazon S3, Azure RBAC, Azure SAS och Google Cloud Platform | - |
| **Tidsbearbetning för virtuell rapportsserie** <br> [Läs mer](/help/components/vrs/vrs-report-time-processing.md) | Ja | Nej | Nej | Nej | Ja |
