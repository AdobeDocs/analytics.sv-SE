---
description: Lär dig lägga till komponenter i ett projekt i Analysis Workspace
title: Använda komponenter i Analysis Workspace
feature: Workspace Basics
role: User, Admin
exl-id: fb56e794-67e3-4f85-960e-b90684300fa0
source-git-commit: 9fcebd7a8fb3a3d98eebef53a748c8ac585cbcd1
workflow-type: tm+mt
source-wordcount: '872'
ht-degree: 0%

---

# Använda komponenter i Analysis Workspace

Komponenterna utgör själva data i alla projekt i Analysis Workspace. Komponenterna består av mått, mått, segment och datumintervall. Du kan lägga till komponenter i ett projekt genom att dra dem till visualiseringar eller paneler.

Mer information om de typer av komponenter du kan lägga till finns i [Komponenter - översikt](/help/analyze/analysis-workspace/components/analysis-workspace-components.md).

>[!TIP]
>
>Om du vill ha mer information om de olika komponenterna väljer du ikonen Info bredvid en komponents namn i den vänstra listen i Analysis Workspace, eller läser [Handbok för analyskomponenter](/help/components/home.md).

## Börja lägga till komponenter i ett projekt

1. [Skapa ett projekt i Analysis Workspace](/help/analyze/analysis-workspace/build-workspace-project/create-projects.md) om du inte redan gjort det.

1. [Lägga till en panel](/help/analyze/analysis-workspace/c-panels/panels.md) eller [lägga till en visualisering](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel) till Analysis Workspace.

   Om du lägger till en komponent i ett tomt projekt skapas en frihandsritabellvisualisering automatiskt.

1. Välj **[!UICONTROL Components]** ikonen i den vänstra listen.

   ![](assets/build-components.png)

1. Bläddra till eller sök efter komponenten som du vill lägga till och dra den sedan till en panel eller visualisering i projektet.

1. (Valfritt) Dra en komponent till segmentets släppzon i ett panelhuvud.

   Segmenten gäller för allt innehåll på panelen.

   Mer information om hur du kan använda segmentets släppzon på en panel för att filtrera panelen finns i [Släppzon](/help/analyze/analysis-workspace/c-panels/panels.md#drop-zone) in [Paneler - översikt](/help/analyze/analysis-workspace/c-panels/panels.md).

   ![släppa ett segment i släppzonen](assets/segment-dropzone.png)

1. Mer detaljerad information finns i följande avsnitt, beroende på vilken komponenttyp du lägger till:

   * [Lägga till dimensioner i ett projekt](#add-dimensions-to-a-project)

   * [Lägga till mätvärden i ett projekt](#add-metrics-to-a-project)

   * [Lägga till segment i ett projekt](#add-segments-to-a-project)

   * [Lägga till datumintervall i ett projekt](#add-date-ranges-to-a-project)

## Lägga till dimensioner i ett projekt

[Dimensioner](/help/components/dimensions/overview.md) är variabler i Adobe Analytics som vanligtvis innehåller strängvärden. Vanliga dimensioner är [Sida](/help/components/dimensions/page.md), [Refererande domän](/help/components/dimensions/referring-domain.md), eller en [eVar](/help/components/dimensions/evar.md). I motsats till [mått](/help/components/metrics/overview.md) innehåller numeriska värden som är kopplade till en dimension. En grundläggande rapport visar rader med strängvärden (dimension) mot en kolumn med numeriska värden (metrisk).

1. Börja lägga till en dimension i ditt projekt i Analysis Workspace, enligt beskrivningen i [Börja lägga till komponenter i ett projekt](#begin-adding-components-to-a-project).

1. Välj en av följande metoder för att lägga till dimensioner och bestämma vilken typ av data du vill analysera:

   * Dra en dimension till en visualisering (till exempel en frihandstabell) i Analysis Workspace.

     ![Lägga till dimensioner i ett projekt](assets/add-dimensions.png)

   * Dra en eller flera dimensioner från den vänstra listen till segmentets släppzon för att skapa ett ad hoc-segment enligt beskrivningen i [Lägga till segment i ett projekt](#add-segments-to-a-project).

     ![släppa ett segment i släppzonen](assets/segment-dropzone.png)

1. (Valfritt) Du kan dela upp dimensioner och dimensionsobjekt i Analysis Workspace med andra komponenter.

   Mer information finns i [Dela upp dimensioner](/help/analyze/analysis-workspace/components/dimensions/t-breakdown-fa.md).

Mer information om hur du använder dimensioner i Analysis Workspace finns i [Förhandsvisa dimensioner](/help/analyze/analysis-workspace/components/dimensions/view-dimensions.md), [Dela upp dimensioner](/help/analyze/analysis-workspace/components/dimensions/t-breakdown-fa.md)och [Tidsdelningsdimensioner](/help/analyze/analysis-workspace/components/dimensions/time-parting-dimensions.md).

## Lägga till mätvärden i ett projekt

[Mått](/help/analyze/analysis-workspace/components/apply-create-metrics.md) kan du kvantifiera datapunkter i Analysis Workspace. De används oftast som kolumner i en visualisering och är knutna till dimensioner.

Så här lägger du till en mätmetod i ett projekt i Analysis Workspace:

1. Börja lägga till en mätmetod i ditt projekt i Analysis Workspace, enligt beskrivningen i [Börja lägga till komponenter i ett projekt](#begin-adding-components-to-a-project).

1. Välj en av följande metoder för att lägga till ett mått i Analysis Workspace:

   * Dra ett mätvärde till släppzonen för mätvärden i en tom Freeform-tabell om du vill se mätningen under projektets datumperiod.

     ![Lägga till ett mått i ett projekt](assets/add-metrics.png)

   * Dra ett mätvärde när det finns en dimension för att se mätvärdet jämfört med varje dimensionsobjekt.

   * Dra ett mätresultat över ett befintligt måtthuvud om du vill ersätta det.

   * Dra ett mätvärde bredvid ett huvud om du vill visa båda mätvärdena sida vid sida.

Mer information om hur du använder mätvärden i Analysis Workspace finns i [Mått](/help/analyze/analysis-workspace/components/apply-create-metrics.md).

## Lägga till segment i ett projekt

[Segment](/help/components/segmentation/seg-overview.md) gör att du kan identifiera undergrupper av besökare baserat på egenskaper eller specifika interaktioner.

Du kan använda segment i Analysis Workspace på något av följande sätt:

### Lägga till segment i en panel

När du lägger till segment på en panel används segmenten på allt innehåll på panelen.

Mer information om hur du kan använda segmentets släppzon på en panel för att filtrera panelen finns i [Släppzon](/help/analyze/analysis-workspace/c-panels/panels.md#drop-zone) in [Paneler - översikt](/help/analyze/analysis-workspace/c-panels/panels.md).

### Lägga till segment i en kolumn i en frihandstabell

När du lägger till segment i en kolumn i en frihandstabell används segmenten på allt innehåll i tabellkolumnen.

### Använd segment när du skapar beräknade värden

I verktyget Beräknade mätvärden kan du använda segment i måttdefinitionen.

Mer information finns i [Segmenterade mätvärden](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/metrics-with-segments.md).

## Lägga till datumintervall i ett projekt

[Datumintervall](/help/analyze/analysis-workspace/components/calendar-date-ranges/custom-date-ranges.md) fastställa tidsramen för rapporteringen i Analysis Workspace och kan tillämpas på en eller flera paneler i ett projekt.

Varje panel innehåller som standard ett datumintervall. Det finns flera sätt att uppdatera ett datumintervall för en panel. Ett sätt att uppdatera ett datumintervall för en panel i Analysis Workspace är att dra en datumintervallkomponent från den vänstra listen:

1. Börja lägga till ett datumintervall i ditt projekt i Analysis Workspace, enligt beskrivningen i [Börja lägga till komponenter i ett projekt](#begin-adding-components-to-a-project).

1. Dra ett datumintervall från den vänstra listen till det aktuella datumintervallet i panelens övre högra del.

   ![släppa ett datumintervall](assets/daterange-drop.png)

Mer information om hur du använder kalendrar och datumintervall i Analysis Workspace finns i [Översikt över kalender- och datumintervall](/help/analyze/analysis-workspace/components/calendar-date-ranges/calendar.md).
