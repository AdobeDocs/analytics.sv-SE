---
title: Visa anteckningar
description: Lär dig hur du visar anteckningar i Analysis Workspace.
role: User, Admin
feature: Annotations
exl-id: 52b179fd-d9a4-4119-a3c6-f6a36f24f8ea
source-git-commit: bf8bc40e3ec325e8e70081955fb533eee66a1734
workflow-type: tm+mt
source-wordcount: '217'
ht-degree: 1%

---

# Visa anteckningar

Anteckningarna visas något annorlunda beroende på var de visas och om de sträcker sig över en dag eller ett datumintervall.

## Visa anteckningar i Workspace

| Visualisering<br/>Typ | Beskrivning |
| --- | --- |
| **Rad &#x200B;**<br/>**En dag** | När du väljer ![Anteckna](/help/assets/icons/Annotate.svg) i en radvisualisering visas ett popup-fönster med anteckningsinformationen.<br/>![Anteckning en dag](assets/annotation-single-day.png)<br/>Om du vill redigera anteckningen i [Anteckningsverktyget](create-annotations.md#annotation-builder) väljer du ![Redigera](/help/assets/icons/Edit.svg). Om du vill ta bort anteckningen väljer du ![Ta bort](/help/assets/icons/Delete.svg). |
| **Rad &#x200B;**<br/>**Datumintervall** | När du väljer ![AnnotateRange](/help/assets/icons/AnnotateRange.svg) visas ett popup-fönster med anteckningsinformationen och en rad längst ned som anger datumintervallet.<br/>![Anteckningsintervall](assets/annotation-range.png)Om du vill redigera anteckningen i [Anteckningsverktyget](create-annotations.md#annotation-builder) väljer du ![Redigera](/help/assets/icons/Edit.svg). Om du vill ta bort anteckningen väljer du ![Ta bort](/help/assets/icons/Delete.svg). |
| **Frihandstabell** | I en Freeform-tabell kan du komma åt alla anteckningar från anteckningsknappen längst upp till höger i visualiseringen. Välj ![Anteckna](/help/assets/icons/Annotate.svg) om du vill se en (rullningslista) med alla anteckningar.<br/>![Anteckningstabell](assets/annotations-table.png)<br/>För varje anteckning kan du välja ![Redigera](/help/assets/icons/Edit.svg) om du vill redigera anteckningen i [Anteckningsverktyget](create-annotations.md#annotation-builder) och ![Ta bort](/help/assets/icons/Delete.svg) om du vill ta bort anteckningen. |

{style="table-layout:auto"}

## Visa anteckningar i en PDF

När du laddar ned ditt projekt som PDF, eller skickar ditt projekt som PDF, sammanfattas anteckningarna i PDF i sammanfattningsavsnittet Anteckningar.

![Markerad vy av en PDF-fil med förklaringar till anteckningar.](assets/annotations-pdf.png)


<!--
# View annotations

Annotations manifest slightly differently, depending on whether they span a single day or a date range.

## View annotations in Line charts or Tables

| Date | Appearance |
| --- | --- |
| **Single day** |   ![](assets/single-day.png)<p>When you hover over the annotation, you can see its details, you can edit it by selecting the pen icon, or you can delete it:<p> ![](assets/hover.png) |
| **Date range** |  The icon changes and when you hover over it, the date range appears.<p>![](assets/multi-day.png)<p>When you select it in the line chart, the annotation metadata appear, and you can edit or delete it:![](assets/multi-hover.png)<p>In a table, an icon appears on every date in the date range.<p>![](assets/multi-day-table.png)|
| **Overlapping annotations** | On days that have more than one annotation tied to them, the icon appears in a grey color.<p>![](assets/grey.png)<p>When you hover over the grey icon, all overlapping annotations appear:<p>![](assets/overlap.png) |

{style="table-layout:auto"}

## View annotations in a .pdf file

Since you cannot hover over icons in a .pdf file, this file (after export) provides notes of explanations at the bottom of a panel. Here is an example:

![](assets/ann-pdf.png)

## View annotations with non-trended data

Sometimes annotation are shown with non-trended data, but tied to a specific dimension. In that case, they appear only in a summary annotation in the bottom right corner. Here is an example:

![](assets/non-date.png)

The summary chart appears in all visualization types in the corner, not just in non-trended freeform tables and summary numbers. It also appears in visualizations like [!UICONTROL Donut], [!UICONTROL Flow],[!UICONTROL Fallout],[!UICONTROL Cohort], and so on.

![](assets/ann-summary.png)

-->