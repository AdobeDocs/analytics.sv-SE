---
description: Använd segment i Analysis Workspace.
title: Segment
uuid: 677f6030-5b3e-4dfa-bb79-9f27f3382fb1
feature: Workspace Basics
role: User, Admin
exl-id: 67112e13-4d0a-4d77-be50-496c3d28779c
source-git-commit: 65c955e25714591b8c4b2359969717d13626b322
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Segment {#topic_DC2917A2E8FD4B62816572F3F6EDA58A}

Du kan skapa olika typer av segment i Workspace, beroende på hur komplexa de behöver vara, om de bara ska gälla för det här projektet osv. Här följer en sammanfattning av segmenttyper:

| Segmenttyp | Skapad var? | Tillämpligt var? | När ska användas |
| --- | --- | --- | --- |
| Komponentlistsegment | [Segment Builder](/help/components/segmentation/segmentation-workflow/seg-build.md) | Global/offentlig | För komplexa segment, sekventiella segment |
| Snabbsegment | [Bygg snabbt segment](/help/analyze/analysis-workspace/components/segments/quick-segments.md) | Projektnivå, men kan göra offentlig | Flexibilitet och kontroll för att lägga till/redigera regler, namn och flera regler |
| Ad hoc-segment: |  |  |  |
| - Ad hoc Workspace-projektsegment | [Dra och släpp i segmentsläppzonen i ett projekt](/help/analyze/analysis-workspace/components/segments/ad-hoc-segments.md) | Projektnivå, men kan göra offentlig | Enkelradiga segment som standard |
| - Beräknat metrisk baserat segment | [Bygg beräknade mätvärden](https://experienceleague.adobe.com/docs/analytics/components/calculated-metrics/calcmetric-workflow/metrics-with-segments.html) | Till individuellt beräknat mått | Använd segment i måttdefinitionen |
| - VRS-baserat segment | [Virtuell Report Suite Builder](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-workflow/vrs-create.html) | Till enskild virtuell rapportsvit | Använd segment i VRS-definitionen |

Mer information om segmentering i Adobe Analytics finns [här](/help/components/segmentation/seg-overview.md).

## Skapa segment {#section_693CFADA668B4542B982446C2B4CF0F5}

Du kan skapa olika typer av segment i Analysis Workspace:

* [Snabbsegment](/help/analyze/analysis-workspace/components/segments/quick-segments.md)
* [Ad hoc-segment](/help/analyze/analysis-workspace/components/segments/ad-hoc-segments.md)
* Vanliga segment i komponentlistan som slutar i segmentbiblioteket (se nedan)

### Skapa komponentlistsegment {#section_3B07D458C43E42FDAF242BB3ACAF3E90}

Segmentspåret under menyn Komponenter visar både segment och segmentmallar, enligt följande ikoner:

![](assets/segment_icons.png)

[Använda segment i Analysis Workspace](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/applying-segments/using-segments-in-analysis-workspace.html) (6:46)

### Andra metoder för att använda segment {#section_10FF2E309BA84618990EA5B473015894}

>[!VIDEO](https://video.tv.adobe.com/v/30994/?quality=12)

Det finns flera andra metoder för att tillämpa segment i frihandsprojekt.

| Åtgärd | Beskrivning |
|--- |--- |
| Skapa segment från markering | Skapa ett textbundet segment. Det här segmentet gäller bara det öppna projektet och sparas inte som ett Analytics-segment. 1. Markera rader.  2. Högerklicka på markeringen.  3. Klicka på *Skapa segment från markering*. |
| Komponenter > Nytt segment | Visar segmentbyggaren. Mer information om segmentering finns i [Segmentbyggare](https://experienceleague.adobe.com/docs/analytics/components/segmentation/segmentation-workflow/seg-build.html). |
| Dela > Dela projekt eller Dela > Kuratera projektdata | I [Curate and Share](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/curate.html#concept_4A9726927E7C44AFA260E2BB2721AFC6) kan du lära dig hur segment som du tillämpar på projektet är tillgängliga i en delad analys för mottagaren. |
| Använd segment som Dimensioner | Video: [Använda segment som Dimensioner i Analysis Workspace](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/applying-segments/using-segments-as-dimensions-in-analysis-workspace.html?lang=en) |

## Segment IQ

Segmentanalys omfattar följande funktioner:

* [Segmentjämförelsepanel:](/help/analyze/analysis-workspace/c-panels/c-segment-comparison/segment-comparison.md) Kärnfunktionen i segmentanalys. Dra två segment till panelen och visa en omfattande rapport som visar statistiskt signifikanta skillnader och överlappning mellan de två målgrupperna.
* [Jämföra segment i utfall:](/help/analyze/analysis-workspace/visualizations/fallout/compare-segments-fallout.md) Se hur olika målgrupper skiljer sig från varandra i samband med en utfallsvisualisering.
