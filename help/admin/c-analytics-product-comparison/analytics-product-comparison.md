---
description: Systemkrav och en jämförelse mellan Analysis Workspace, rapporter och Analytics, Ad Hoc Analysis, Report Builder, Data warehouse och Data Workbench
title: Produktjämförelse och krav för analyser
translation-type: tm+mt
source-git-commit: cb3948f03e65edf18b7f3c54c891b77629b41dc0
workflow-type: tm+mt
source-wordcount: '609'
ht-degree: 34%

---


# Produktjämförelse och krav för analyser

Systemkrav och en jämförelse mellan Analysis Workspace, Reports &amp; Analytics, Report Builder, Data warehouse, Data Workbench, Analytics API 2.0, Data Feeds och Customer Journey Analytics.

Information om vilken Adobe Analytics-produkt du ska använda finns [här](/help/admin/c-analytics-product-comparison/which-analytics-tool.md).

| Produkt- och hjälplänk | [Analysis Workspace](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/home.html) | [Rapporter och Analytics](https://docs.adobe.com/content/help/en/analytics/analyze/reports-analytics/getting-started.html) | [Report Builder](https://docs.adobe.com/content/help/en/analytics/analyze/report-builder/home.html) | [Data Warehouse](https://docs.adobe.com/content/help/en/analytics/export/data-warehouse/data-warehouse.html) | [Data Workbench](https://docs.adobe.com/content/help/en/data-workbench/using/home.html) | Analytics API 2.0 | Datafeeds | Customer Journey Analytics |
|---|---|---|---|---|---|---|
| **Åtkomstmetod** | Webbläsarlösning för att skapa stabila, anpassade analysprojekt och demokratisera insikter. | Webbläsarlösning för digital analys. | Webbläsarlösning som genererar rapporter i CSV-format. Kan generera filer i Tableu-format. | Flerkanalsanalysverktyg för avancerad analys, som anpassad attribueringsmodellering, prediktiv analys och 360 kundanalyser. |  |  |  |
| **Rapportuppdelningar** | Obegränsad | Upp till två korrelationer | Upp till två korrelationer | Utför helt utökade, obegränsade uppdelningar, uppdelade efter segment. | Obegränsad |  |  |  |
| **Segmentjämförelser** | Obegränsad | Upp till 2 segment | Obegränsad (dataförfrågningsstackning) | 1 segment. Stöder flera (staplade) segment. | Obegränsad |  |  |  |
| **Utdatagräns** | 400 | 200 | 50,000 | Obegränsad | Anpassningsbar |  |  |  |
| **Unika värdegränser** (inom eVar-/prop-rapporter) | 500 K-2 MM | 500 K-2 MM | 500 K-2 MM | Obegränsad | Anpassningsbar |  |  |  |
| **Tratt/bana** | Ja: [Utfall](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/visualizations/fallout/fallout-flow.html)/[flöde](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/visualizations/flow/flow.html) | [Ja](https://docs.adobe.com/content/help/en/analytics/analyze/reports-analytics/reports.html) | Ja | Nej | Ja |  |  |  |
| **Avancerad kundreseanalys** | Yes: [Customer Journey Analytics](https://docs.adobe.com/content/help/en/analytics-platform/using/cja-landing.html) | Nej | Nej | Nej | Ja |  |  |  |
| **Kohortanalys** | [Ja](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/visualizations/cohort-table/cohort-analysis.html) | Nej | Nej | Nej | Ja |  |  |  |
| **Avancerad attribuering** | Ja: [Attributions-IQ](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/attribution-iq.html) | Begränsad - första/sista/linjär | Begränsad - första/sista/linjär | Begränsad - första/sista/linjär | Ja |  |  |  |
| **Förbättrade visualiseringsalternativ** | [Ja](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.html) | Nej | Ja | Nej | Ja |  |  |  |
| **Anpassningsbar layout** | [Ja](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/home.html) | Ja - [instrumentpaneler](https://docs.adobe.com/content/help/en/analytics/analyze/reports-analytics/dashboard.html) | [Ja](https://docs.adobe.com/content/help/en/analytics/analyze/report-builder/layout/configure-the-custom-layout.html) | Sortera resultaten efter uppdelning eller efter mått. | Ja |  |  |  |
| **Projektkurering** (förenkla rapporter för icke-analytiker) | [Ja](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/curate-share/curate.html) | Nej | Ja | Nej | Ja |  |  |  |
| **Projektdelning** | [Ja: alla/alla användare](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/curate-share/curate.html) | [Ja: alla/alla användare](https://docs.adobe.com/content/help/en/analytics/analyze/reports-analytics/scheduling.html) | Ja: alla/alla användare | Nej | Ja |  |  |  |
| **Schemalagd rapportleverans** | [Ja](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/curate-share/schedule-projects.html) | [Ja](https://docs.adobe.com/content/help/en/analytics/analyze/reports-analytics/scheduling.html) | [Ja](https://docs.adobe.com/content/help/en/analytics/analyze/report-builder/t-schedule-a-data-request.html) | Ja | Ja |  |  |  |
| **Systemkrav** | <br>[Mer webbläsare..](https://docs.adobe.com/content/help/sv-SE/analytics/admin/sys-reqs.html) | <br>[Mer webbläsare..](https://docs.adobe.com/content/help/sv-SE/analytics/admin/sys-reqs.html) | Windows, MS<br>[ExcelMore...](https://docs.adobe.com/content/help/en/analytics/analyze/report-builder/report-builder-setup/system-requirements.html) | Webbläsare och program för att öppna CSV-filer som MS Excel. Kan generera filer i Tableu-format. | Windows 64-bitars, bra grafikkort för OpenGL 3.2 [Mer...](https://docs.adobe.com/content/help/en/data-workbench/using/install/c-data-workbench-client-install.html) |  |  |  |
| **Kompatibilitet med Virtual Report Suite (tidsbearbetning av rapport)** | Ja | Ja | Ja | Nej | Ja? |  |  |  |
| **Flera rapportsviter** | Ja | Nej | Nej | Nej | Ja? |  |  |  |
| **Beräknade mätvärden** | Ja | Ja | Ja | Ja | Ja |  |  |  |
| **Kompatibilitet med marknadsföringskanaler** | Ja | Ja | Ja | ? | ? |  |  |  |
| **Detaljnivå** |  |  |  |  |  |  |  |  |
| **Avvikelseidentifiering** | Ja | Nej |  |  |  |  |  |  |
| **Bidragsanalys** | Ja | Nej | Nej | Nej | Ja |  |  |  |
| **Segmenttyper** |  |  |  |  |  |  |  |  |