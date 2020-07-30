---
description: Systemkrav och en jämförelse mellan Analysis Workspace, rapporter och Analytics, Ad Hoc Analysis, Report Builder, Data warehouse och Data Workbench
title: Produktjämförelse och krav för analyser
translation-type: tm+mt
source-git-commit: 54d6b4c2993c5b0391b9243c76661db1da4087b8
workflow-type: tm+mt
source-wordcount: '714'
ht-degree: 35%

---


# Produktjämförelse och krav för analyser

Den här sidan innehåller en jämförelse av olika Adobe Analytics-produkter: Analysis Workspace, Reports &amp; Analytics, Report Builder, Data warehouse, Data Workbench, Data Feeds och Analytics API 2.0.

Information om vilken Adobe Analytics-produkt du ska använda finns [här](/help/admin/c-analytics-product-comparison/which-analytics-tool.md).

| Produkt- och hjälplänk | [Analysis Workspace](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/home.html) | [Rapporter och Analytics](https://docs.adobe.com/content/help/en/analytics/analyze/reports-analytics/getting-started.html) | [Report Builder](https://docs.adobe.com/content/help/en/analytics/analyze/report-builder/home.html) | [Data Warehouse](https://docs.adobe.com/content/help/en/analytics/export/data-warehouse/data-warehouse.html) | [Data Workbench](https://docs.adobe.com/content/help/en/data-workbench/using/home.html) | [Datafeeds](https://docs.adobe.com/content/help/en/analytics/export/analytics-data-feed/data-feed-overview.html) | [Analytics API 2.0](https://www.adobe.io/apis/experiencecloud/analytics/docs.html) |
|---|---|---|---|---|---|---|---|
| **Åtkomstmetod** | [Webbläsare](https://docs.adobe.com/content/help/sv-SE/analytics/admin/sys-reqs.html) | [Webbläsare](https://docs.adobe.com/content/help/sv-SE/analytics/admin/sys-reqs.html) | [MS Excel för Windows](https://docs.adobe.com/content/help/en/analytics/analyze/report-builder/report-builder-setup/system-requirements.html) | Konfigurera via webbläsaren. [Läs mer](https://docs.adobe.com/content/help/sv-SE/analytics/admin/sys-reqs.html) | [Windows 64 bitar](https://docs.adobe.com/content/help/en/data-workbench/using/install/c-data-workbench-client-install.html) | Konfigurera via webbläsaren. [Läs mer](https://docs.adobe.com/content/help/en/analytics/export/analytics-data-feed/data-feed-overview.html) | RESTful API tools. Logga in med inloggningsuppgifter för Adobe. [Läs mer](https://www.adobe.io/apis/experiencecloud/analytics/docs.html) |
| **Datagranularitet** | Sammanställd | Sammanställd | Sammanställd | Sammanställd | Träff | Träff | Sammanställd |
| **Expierence Cloud ID (ECID) är tillgängligt** | Nej | Nej | Nej | Ja | Ja | Ja | Nej |
| **Tidsstämpel tillgänglig** | Nej | Nej | Nej | Nej | Ja | Ja | Nej |
| **Bearbetningsnivå** | Fullt bearbetad | Fullständigt bearbetad, med separat [realtidsrapport](https://docs.adobe.com/content/help/en/analytics/components/real-time-reporting/realtime.html) | Fullständigt bearbetad, med separat [realtidsrapport](https://docs.adobe.com/content/help/en/analytics/components/real-time-reporting/realtime.html) | Fullt bearbetad | Fullt bearbetad | Fullt bearbetad | Fullt bearbetad |
| **Administratörsfilterdata ingår** <br>[Läs mer](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/bot-removal/bot-removal.html) | Nej | Ja - separat robotrapport | Ja - separat robotrapport | Nej | Nej | Nej | Nej |
| **Låg trafik (Uniques-** överstigna) visas <br>[Läs mer](https://docs.adobe.com/content/help/en/analytics/technotes/low-traffic.html) | Ja | Ja | Ja | Nej | Nej | Nej | Ja |
| **Synlig radgräns (före sidnumrering)** | 400 | 200 | 50000 | Obegränsad | Obegränsad | Obegränsad | 50000 |
| **Flera rapportsviter** | [Ja](https://docs.adobe.com/content/help/sv-SE/analytics/analyze/analysis-workspace/build-workspace-project/multiple-report-suites.html) | Ja, med begränsningar | Ja | Nej | Ja | Nej | Ja |
| **Antal uppdelningar** | Obegränsad | Upp till 2 | Upp till 2 | Obegränsad | Obegränsad | Obegränsad | Obegränsat, kör över flera frågor |
| **Segmentering** <br>[Läs mer](https://docs.adobe.com/content/help/en/analytics/components/segmentation/segmentation-workflow/seg-workflow.html) | Ja | Ja | Ja | Ja, med [begränsningar](https://docs.adobe.com/content/help/en/analytics/components/segmentation/segment-reference/seg-compatibility.html) | Ja | Nej | Ja |
| **Beräknade mätvärden** <br>[Läs mer](https://docs.adobe.com/content/help/sv-SE/analytics/components/calculated-metrics/cm-overview.html) | Ja, med [Attribution IQ](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/attribution/overview.html) | Ja | Ja | Nej | Ja | Nej | Ja, med [Attribution IQ](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/attribution/overview.html) |
| **Marknadsföringskanaler** <br>[Läs mer](https://docs.adobe.com/content/help/en/analytics/components/marketing-channels/c-getting-started-mchannel.html) | Ja | Ja | Ja | Ja | Ja | Ja - [va_finder, va_close](https://docs.adobe.com/content/help/en/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-reference.html) | Ja |
| **Kohortanalys** | [Ja](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/visualizations/cohort-table/cohort-analysis.html) | Nej | Nej | Nej | Ja | Nej | Nej |
| **Attribuering** | Ja, med [Attribution IQ](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/attribution/overview.html) | Begränsad | Begränsad | Nej | Ja | Nej | Ja, med [Attribution IQ](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/attribution/overview.html) |
| **Funktioner** i Virtual Analyst <br>[Läs mer](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/virtual-analyst/overview.html) | Ja | Nej | Nej | Nej | Nej | Nej | Ja |
| **Kurva** <br>[Läs mer](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/curate-share/curate.html) | Ja - projekt och VRS | Nej | Nej | Nej | Nej | Nej | Ja - endast VRS |
| **Projektdelning** <br>[Läs mer](https://docs.adobe.com/content/help/sv-SE/analytics/analyze/analysis-workspace/curate-share/share-projects.translate.html) | Ja, med projektroller | Ja | Ja | Nej | Ja | Nej | Nej |
| **Schemalagd leverans** | Ja | Ja | Ja | Ja | Nej | Ja | Nej |
| **Leveransmål** | E-post | E-post | E-post, FTP, SFTP, [publicera till Microsoft PowerBI](https://docs.adobe.com/content/help/en/analytics/analyze/report-builder/publish-powerbi/power-bi.html) | E-post, FTP. Kontakta kundtjänst för ytterligare destinationssupport som SFTP, Azure Blob, Amazon S3 | - | FTP, SFTP, Azure Blob, Amazon S3 | - |
| **Tidsbearbetning** för VRS-rapport <br>[Läs mer](https://docs.adobe.com/content/help/en/analytics/components/virtual-report-suites/vrs-report-time-processing.html) | Ja | Nej | Nej | Nej | Nej | Nej | Ja |
