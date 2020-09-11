---
title: Frihandstabell
description: Läs mer om frihandsritningar och frihandsritningstabeller
translation-type: tm+mt
source-git-commit: 677539632878655a6e573176321b59b531e1ab2c
workflow-type: tm+mt
source-wordcount: '535'
ht-degree: 4%

---


# Frihandstabell

I Analysis Workspace är en frihandstabell inte bara en datatabell, utan även en interaktiv visualisering. Du kan dra och släppa en kombination av [komponenter](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/components/analysis-workspace-components.html) i rader och kolumner för att skapa en anpassad tabell för analysen. När varje komponent släpps uppdateras tabellen omedelbart så att du kan göra en snabb analys.

Du kan anpassa tabellen på flera olika sätt:

* **Rader**
   * Varje dimensionsrad kan visa upp till 400 rader, innan sidnumreringen görs. Du kan anpassa fler rader till en enda skärm genom att justera projektets [visningsdensitet](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/build-workspace-project/view-density.html).
   * Rader kan delas upp efter ytterligare komponenter. Om du vill dela upp flera rader samtidigt markerar du bara flera rader och drar sedan nästa komponent över de markerade raderna. Läs mer om [uppdelningar](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/components/dimensions/t-breakdown-fa.html).
   * Rader kan [filtreras](https://docs.adobe.com/content/help/sv-SE/analytics/analyze/analysis-workspace/build-workspace-project/pagination-filtering-sorting.html) för att visa en reducerad uppsättning med objekt. Ytterligare inställningar finns under [Radinställningar](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/build-workspace-project/column-row-settings/table-settings.html).

* **Kolumner**
   * Komponenter kan staplas i kolumner för att skapa segmenterade mätvärden, tabbanalyser med mera.
   * Vyn för varje kolumn kan justeras under [kolumninställningarna](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/build-workspace-project/column-row-settings/column-settings.html).
   * Flera åtgärder är tillgängliga via [högerklicksmenyn](https://docs.adobe.com/content/help/en/analytics-learn/tutorials/analysis-workspace/building-freeform-tables/using-the-right-click-menu.html). Menyn innehåller olika åtgärder beroende på om du klickar på tabellhuvudet, raderna eller kolumnerna.

## Bygg frihandstabell

Om du föredrar att lägga till flera komponenter i tabellen först och sedan återge data, kan du aktivera Frihand tabellverktyg. Med verktyget aktiverat kan du dra och släppa i många dimensioner, uppdelningar, mätvärden och segment för att skapa tabeller som besvarar mer komplexa frågor. Data uppdateras inte direkt, utan uppdateras när du klickar **[!UICONTROL Build]**.

Table Builder är ett tidsbesparande alternativ när du har en komplex fråga om data och du har en uppfattning om tabellen som du vill konstruera för att besvara din fråga. Andra fördelar med tabellbyggaren är möjligheten att:

* Ordna tabellen i det format du behöver, utan att behöva vänta på att varje åtgärd ska återges.
* Utför snabbt upp till fyra nivåer av uppdelningar.
* Definiera rad- och brytningsinställningarna för varje tabellrad och dimensionskolumn.
* **[!UICONTROL Breakdown by Position]** för alla nivåer i tabellen som standard (i traditionella frihandstabeller är standardvärdet **[!UICONTROL Breakdown by Item]**.)
* Ordna statiska rader manuellt i tabellen. Om du till exempel vill att måttrader ska visas i en viss ordning.
* Förhandsgranska tabellformatet innan du återger verkliga data.

Se hur Frihand tabellbyggaren fungerar [här](https://youtu.be/GUMWiJAmMGI).

## Exportera frihandstabelldata

Data i en frihandstabell kan kopieras från Analysis Workspace på några sätt:

* Högerklicka på tabellrubriken och välj **[!UICONTROL Copy to Clipboard]**. Den fullständiga (synliga) tabellen exporteras.
* Markera specifika celler i tabellen, högerklicka och markera **[!UICONTROL Copy to Clipboard]** eller använd snabbtangenten Ctrl + C.
* **[!UICONTROL Project > Download CSV]**. Då exporteras alla synliga tabeller i projektet som en CSV-fil.
