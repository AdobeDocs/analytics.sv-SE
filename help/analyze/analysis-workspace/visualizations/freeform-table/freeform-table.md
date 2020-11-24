---
title: Frihandstabell
description: Frihandsregister är grunden för dataanalys i Workspace
translation-type: tm+mt
source-git-commit: ae04b10edb35f15e552527948b5b7d57c175f562
workflow-type: tm+mt
source-wordcount: '649'
ht-degree: 2%

---


# Frihandstabell

I Analysis Workspace är Freeform Table grunden för interaktiv dataanalys. Du kan dra och släppa en kombination av [komponenter](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/components/analysis-workspace-components.html) i rader och kolumner för att skapa en anpassad tabell för analysen. När varje komponent släpps uppdateras tabellen omedelbart så att du snabbt kan analysera och fördjupa.

## Automatiserade tabeller

Det snabbaste sättet att skapa en tabell är att släppa komponenter direkt i ett tomt projekt, en panel eller en frihandstabell. En frihandstabell skapas automatiskt i det format som rekommenderas. [Titta på självstudiekursen](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/building-freeform-tables/auto-build-freeform-tables-in-analysis-workspace.html).

## Frihandsritbordsverktyget

Om du föredrar att lägga till flera komponenter i tabellen först och sedan återge data, kan du aktivera Frihand tabellverktyg. Med verktyget aktiverat kan du dra och släppa i många dimensioner, uppdelningar, mätvärden och segment för att skapa tabeller som besvarar mer komplexa frågor. Data uppdateras inte direkt, utan uppdateras när du klickar **[!UICONTROL Build]**. Titta på [självstudiekursen](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/building-freeform-tables/using-the-freeform-table-builder-in-analysis-workspace.html)Frihandsritbordsverktyget.

Table Builder är ett tidsbesparande alternativ när du har en komplex fråga om data och du har en uppfattning om tabellen som du vill konstruera för att besvara din fråga. Andra fördelar med tabellbyggaren är möjligheten att:

* Ordna tabellen i det format du behöver, utan att behöva vänta på att varje åtgärd ska återges.
* Utför snabbt upp till fyra nivåer av uppdelningar.
* Definiera rad- och brytningsinställningarna för varje tabellrad och dimensionskolumn.
* **[!UICONTROL Breakdown by Position]** för alla nivåer i tabellen som standard (i traditionella frihandstabeller är standardvärdet **[!UICONTROL Breakdown by Item]**.)
* Ordna statiska rader manuellt i tabellen. Om du till exempel vill att måttrader ska visas i en viss ordning.
* Förhandsgranska tabellformatet innan du återger verkliga data.

## Tabellinteraktioner

Du kan interagera med och anpassa en frihandstabell på flera olika sätt:

* **Rader**
   * Du kan anpassa fler rader till en enda skärm genom att justera projektets [visningsdensitet](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/build-workspace-project/view-density.html).
   * Varje dimensionsrad kan visa upp till 400 rader, innan sidnumreringen görs. Klicka på siffran intill &quot;Rader&quot; för att visa fler rader på en sida. Navigera till en annan sida med sidpilen i sidhuvudet.
   * Rader kan delas upp efter ytterligare komponenter. Om du vill dela upp flera rader samtidigt markerar du bara flera rader och drar sedan nästa komponent över de markerade raderna. Läs mer om [uppdelningar](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/components/dimensions/t-breakdown-fa.html).
   * Rader kan [filtreras](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/visualizations/freeform-table/pagination-filtering-sorting.html) för att visa en reducerad uppsättning med objekt. Ytterligare inställningar finns under [Radinställningar](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/visualizations/freeform-table/column-row-settings/table-settings.html).

* **Kolumner**
   * Komponenter kan staplas i kolumner för att skapa segmenterade mätvärden, tabbanalyser med mera.
   * Vyn för varje kolumn kan justeras under [kolumninställningarna](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/build-workspace-project/column-row-settings/column-settings.html).
   * Flera åtgärder är tillgängliga via [högerklicksmenyn](https://docs.adobe.com/content/help/en/analytics-learn/tutorials/analysis-workspace/building-freeform-tables/using-the-right-click-menu.html). Menyn innehåller olika åtgärder beroende på om du klickar på tabellhuvudet, raderna eller kolumnerna.

## Exportera frihandstabelldata

Data i en frihandstabell kan kopieras från Analysis Workspace på några sätt:

* Högerklicka > **[!UICONTROL Copy data to clipboard]** exporterar visade tabelldata. Om du markerar en tabell visas det här alternativet **[!UICONTROL Copy selection to clipboard]**. Snabbtangenten **Ctrl+C** kopierar även markerade data.
* Högerklicka > **[!UICONTROL Download data as CSV]** hämtar visade tabelldata som en CSV-fil. Om du markerar en tabell visas det här alternativet **[!UICONTROL Download selection as CSV]**.
* Högerklicka > **[!UICONTROL Project > Download items as CSV]** exporterar upp till 50 000 dimensionsobjekt för den valda dimensionen.

Läs mer om alla [exportalternativ](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/download-send.html) för Analysis Workspace.
