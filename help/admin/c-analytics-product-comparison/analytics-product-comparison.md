---
description: Systemkrav och en jämförelse av Analysis Workspace, rapporter och analyser, Ad Hoc Analysis, Report Builder, Data warehouse och Data Workbench
title: Produktjämförelse och krav för analyser
translation-type: tm+mt
source-git-commit: 8a48a5bd9e7ef38ffc90ecb9c640166bb3ac4405
workflow-type: tm+mt
source-wordcount: '432'
ht-degree: 39%

---


# Produktjämförelse och krav för analyser

Den här sidan innehåller en jämförelse av olika Adobe Analytics-produkter: Analysis Workspace, Reports &amp; Analytics, Report Builder, Data warehouse, Data Workbench, Data Feeds och Analytics API 2.0.

Information om vilken Adobe Analytics-produkt du ska använda finns [här](/help/admin/c-analytics-product-comparison/which-analytics-tool.md).

| Produkt- och hjälplänk | [Analysis Workspace](/help/analyze/analysis-workspace/home.md) | [Rapporter och analyser](/help/analyze/reports-analytics/getting-started.md) | [Report Builder](/help/analyze/report-builder/home.md) | [Data Warehouse](/help/export/data-warehouse/data-warehouse.md) | [Data Workbench](https://docs.adobe.com/content/help/en/data-workbench/using/home.html) | [Datafeeds](/help/export/analytics-data-feed/data-feed-overview.md) | [Analytics API 2.0](https://www.adobe.io/apis/experiencecloud/analytics/docs.html) |
|---|---|---|---|---|---|---|---|
| **Åtkomstmetod** | [Webbläsare](/help/admin/sys-reqs.md) | [Webbläsare](/help/admin/sys-reqs.md) | [MS Excel för Windows](/help/analyze/report-builder/setup/system-requirements.md) | Konfigurera via webbläsaren. [Läs mer](/help/admin/sys-reqs.md) | [Windows 64 bitar](https://docs.adobe.com/content/help/en/data-workbench/using/install/c-data-workbench-client-install.html) | Konfigurera via webbläsaren. [Läs mer](/help/export/analytics-data-feed/data-feed-overview.md) | RESTful API tools. Logga in med inloggningsuppgifter för Adobe. [Läs mer](https://www.adobe.io/apis/experiencecloud/analytics/docs.html) |
| **Datagranularitet** | Sammanställd | Sammanställd | Sammanställd | Sammanställd | Träff | Träff | Sammanställd |
| **Experience Cloud-ID (ECID) tillgängligt** | Nej | Nej | Nej | Ja | Ja | Ja | Nej |
| **Tidsstämpel tillgänglig** | Nej | Nej | Nej | Nej | Ja | Ja | Nej |
| **Bearbetningsnivå** | Fullt bearbetad | Fullständigt bearbetad, med separat [realtidsrapport](/help/components/c-real-time-reporting/realtime.md) | Fullständigt bearbetad, med separat [realtidsrapport](/help/components/c-real-time-reporting/realtime.md) | Fullt bearbetad | Fullt bearbetad | Fullt bearbetad | Fullt bearbetad |
| **Administratörsrobotfilterdata ingår** <br> [Läs mer](/help/admin/admin/bot-removal/bot-removal.md) | Nej | Ja - separat robotrapport | Ja - separat robotrapport | Nej | Nej | Nej | Nej |
| **Låg trafik (Uniques-gränsen överskrids) visas** <br> [Läs mer](/help/technotes/low-traffic.md) | Ja | Ja | Ja | Nej | Nej | Nej | Ja |
| **Synlig radgräns (före sidnumrering)** | 400 | 200 | 50000 | Obegränsad | Obegränsad | Obegränsad | 50000 |
| **Flera rapportsviter** | [Ja](/help/analyze/analysis-workspace/build-workspace-project/multiple-report-suites.md) | Ja, med begränsningar | Ja | Nej | Ja | Nej | Ja |
| **Antal uppdelningar** | Obegränsad | Upp till 2 | Upp till 2 | Obegränsad | Obegränsad | Obegränsad | Obegränsat, kör över flera frågor |
| **Segmentering** <br> [Läs mer](/help/components/segmentation/segmentation-workflow/seg-workflow.md) | Ja | Ja | Ja | Ja, med [begränsningar](/help/components/segmentation/seg-reference/seg-compatibility.md) | Ja | Nej | Ja |
| **Beräknade värden** <br> [Läs mer](/help/components/c-calcmetrics/cm-overview.md) | Ja, med [Attribution IQ](/help/analyze/analysis-workspace/attribution/overview.md) | Ja | Ja | Nej | Ja | Nej | Ja, med [Attribution IQ](/help/analyze/analysis-workspace/attribution/overview.md) |
| **Marknadsföringskanaler** <br> [Läs mer](/help/components/c-marketing-channels/c-getting-started-mchannel.md) | Ja | Ja | Ja | Ja | Ja | Ja - [va_finder, va_close](/help/export/analytics-data-feed/c-df-contents/datafeeds-reference.md) | Ja |
| **Kohortanalys** | [Ja](/help/analyze/analysis-workspace/visualizations/cohort-table/cohort-analysis.md) | Nej | Nej | Nej | Ja | Nej | Nej |
| **Attribuering** | Ja, med [Attribution IQ](/help/analyze/analysis-workspace/attribution/overview.md) | Begränsad | Begränsad | Nej | Ja | Nej | Ja, med [Attribution IQ](/help/analyze/analysis-workspace/attribution/overview.md) |
| **Funktioner i Virtual Analyst** <br> [Läs mer](/help/analyze/analysis-workspace/virtual-analyst/overview.md) | Ja | Nej | Nej | Nej | Nej | Nej | Ja |
| **Kuration** <br> [Läs mer](/help/analyze/analysis-workspace/curate-share/curate.md) | Ja - projekt och VRS | Nej | Nej | Nej | Nej | Nej | Ja - endast VRS |
| **Projektdelning** <br> [Läs mer](/help/analyze/analysis-workspace/curate-share/share-projects.md) | Ja, med projektroller | Ja | Ja | Nej | Ja | Nej | Nej |
| **Schemalagd leverans** | Ja | Ja | Ja | Ja | Nej | Ja | Nej |
| **Leveransmål** | E-post | E-post | E-post, FTP, SFTP, [publicera till Microsoft PowerBI](/help/analyze/report-builder/c-publish-power-bi/power-bi.md) | E-post, FTP. Kontakta kundtjänst för ytterligare destinationssupport som SFTP, Azure Blob, Amazon S3 | - | FTP, SFTP, Azure Blob, Amazon S3 | - |
| **Tidsbearbetning för VRS-rapport** <br> [Läs mer](/help/components/vrs/vrs-report-time-processing.md) | Ja | Nej | Nej | Nej | Nej | Nej | Ja |
