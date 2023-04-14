---
title: Frihandstabell
description: Frihandsregister är grunden för dataanalys i Workspace
feature: Freeform Tables
role: User, Admin
exl-id: 7a0432f9-2cab-47be-bbd6-ede96cb840a3
source-git-commit: ef2b452a0dcb2659b49fc0507b096952a89ea2f4
workflow-type: tm+mt
source-wordcount: '607'
ht-degree: 0%

---

# Frihandstabell

I Analysis Workspace är Freeform Table grunden för interaktiv dataanalys. Du kan dra och släppa en kombination av [komponenter](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/components/analysis-workspace-components.html) till rader och kolumner för att skapa en anpassad tabell för din analys. När varje komponent släpps uppdateras tabellen omedelbart, så att du snabbt kan analysera och fördjupa den.

## Bygg en enkel friformstabell

Du börjar med en tom friformstabell.

![Tom tabell för frihandsfigur](assets/freeform-table-1.png)

Om du släpper **[!UICONTROL ** Besök **]** på **[!UICONTROL ** Släpp ett mätresultat här (eller någon annan komponent)**]**, fylls friformstabellen automatiskt i med besök per dag för den kalenderperiod du har valt.

![Besök friformstabell](assets/freeform-table-2.png)

Om du sedan släpper **[!UICONTROL ** Sida **]** dimension som ska ersätta **[!UICONTROL ** Dag **]** dimensionskolumnen återspeglar friformstabellen automatiskt besöken för varje sida.

![Besök efter sidfriformstabell](assets/freeform-table-3.png)

Du kan sedan dela upp, till exempel **[!UICONTROL ** kategori:5 **]** genom att släppa **[!UICONTROL ** Marknadsföringskanal **]** dimension på **[!UICONTROL ** kategori:5 **]** rad.

![Besöksfördelning efter sidfriformstabell](assets/freeform-table-4.png)


## Automatiserade tabeller

Så som visas ovan är det snabbaste sättet att skapa en tabell att släppa komponenter direkt i ett tomt projekt, en tom panel eller en frihandstabell. En frihandstabell skapas automatiskt i det format som rekommenderas. [Se självstudiekursen](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/building-freeform-tables/auto-build-freeform-tables-in-analysis-workspace.html).

![](assets/automated-table.png)

## Frihandsritbordsverktyget

Om du föredrar att lägga till flera komponenter i tabellen först och sedan återge data, kan du aktivera Frihand tabellverktyg. Med verktyget aktiverat kan du dra och släppa i många dimensioner, uppdelningar, mätvärden och segment för att skapa tabeller som besvarar mer komplexa frågor. Data uppdateras inte direkt, utan uppdateras när du klickar på **[!UICONTROL Build]**.

![](assets/table-builder.png)

## Tabellinteraktioner

Du kan interagera med och anpassa en frihandstabell på flera olika sätt:

* **Rader**
   * Du kan anpassa fler rader till en enda skärm genom att justera projektets [visningsdensitet](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/view-density.html).
   * Varje dimensionsrad kan visa upp till 400 rader, innan sidnumreringen görs. Klicka på siffran intill &quot;Rader&quot; för att visa fler rader på en sida. Navigera till en annan sida med sidpilen i sidhuvudet.
   * Rader kan delas upp efter ytterligare komponenter. Om du vill dela upp flera rader samtidigt markerar du bara flera rader och drar sedan nästa komponent över de markerade raderna. Läs mer om [uppdelningar](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/components/dimensions/t-breakdown-fa.html).
   * Rader kan [filtrerad](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/freeform-table/filter-and-sort.html) för att visa en reducerad uppsättning objekt. Ytterligare inställningar finns under [Radinställningar](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/freeform-table/column-row-settings/table-settings.html).

* **Kolumner**
   * Komponenter kan staplas i kolumner för att skapa segmenterade mätvärden, tabbanalyser med mera.
   * Vyn för varje kolumn kan justeras under [kolumninställningar](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/column-row-settings/column-settings.html).
   * Flera åtgärder är tillgängliga via [högerklicksmeny](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/building-freeform-tables/using-the-right-click-menu.html). Menyn innehåller olika åtgärder beroende på om du klickar på tabellhuvudet, raderna eller kolumnerna.

## Exportera frihandstabelldata

Läs mer om alla data [exportalternativ](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/download-send.html) för Analysis Workspace.

* Högerklicka > **[!UICONTROL Copy data to clipboard]** exporterar visade tabelldata. Om en tabellmarkering görs kommer det här alternativet att ange **[!UICONTROL Copy selection to clipboard]**. The **Ctrl+C** hotkey kopierar även markerade data.
* Högerklicka > **[!UICONTROL Download data as CSV]** hämtar visade tabelldata som en CSV-fil. Om en tabellmarkering görs kommer det här alternativet att ange **[!UICONTROL Download selection as CSV]**.
* Högerklicka > **[!UICONTROL Project > Download items as CSV]** exporterar upp till 50 000 dimensionsobjekt för den valda dimensionen.

Läs mer om alla data [exportalternativ](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/download-send.html) för Analysis Workspace.

![](assets/export-options.png)

## Videor

Översikt över tabellbyggaren i frihand:

>[!VIDEO](https://video.tv.adobe.com/v/31318/?quality=12)

Frihandstabellfilter:

>[!VIDEO](https://video.tv.adobe.com/v/23232/?quality=12)

Totalvärden för friformsregister:

>[!VIDEO](https://video.tv.adobe.com/v/29273/?quality=12)
