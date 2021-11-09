---
description: Använd segment i Analysis Workspace.
title: Segment
uuid: 677f6030-5b3e-4dfa-bb79-9f27f3382fb1
feature: Workspace Basics
role: User, Admin
exl-id: 67112e13-4d0a-4d77-be50-496c3d28779c
source-git-commit: 86766c4452a571a7c7b36ad6693a1a1e0bc2deea
workflow-type: tm+mt
source-wordcount: '510'
ht-degree: 0%

---


# Segment {#topic_DC2917A2E8FD4B62816572F3F6EDA58A}

Du kan skapa olika typer av segment i Workspace, beroende på hur komplexa de behöver vara, om de bara ska gälla för det här projektet osv. Här följer en sammanfattning av segmenttyper:

| Segmenttyp | Skapad var? | Tillämpligt var? | När ska användas |
| --- | --- | --- | --- |
| Segment i komponentlista | Klicka på +, vilket tar dig till [Segment Builder](/help/components/segmentation/segmentation-workflow/seg-build.md) | Alla arbetsyteprojekt | För mer komplexa segment, sekventiella segment |
| Snabbsegment | [Bygg snabbt segment](/help/analyze/analysis-workspace/components/segments/quick-segments.md) | Endast projekt, men du kan spara och lägga till i segmentlistan. | Flexibilitet att lägga till/redigera en eller flera regler |
| Ad hoc-segment: |  |  |  |
| - Ad hoc Workspace-projektsegment | [Dra och släpp i segmentsläppzonen i ett projekt](/help/analyze/analysis-workspace/components/segments/ad-hoc-segments.md) | Endast projekt, men du kan spara och lägga till i segmentlistan. | För segment med en regel |
| - Beräknat metrisk baserat segment | [Bygg beräknade mätvärden](https://experienceleague.adobe.com/docs/analytics/components/calculated-metrics/calcmetric-workflow/metrics-with-segments.html) | Till individuellt beräknat mått | Använd segment i måttdefinitionen |
| - VRS-baserat segment | [Virtuell Report Suite Builder](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-workflow/vrs-create.html) | Till enskild virtuell rapportsvit | Använd segment i VRS-definitionen |

## Videor

Använda segment i Analysis Workspace:

>[!VIDEO](https://video.tv.adobe.com/v/23977/?quality=12)

Hitta och skapa segment:

>[!VIDEO](https://video.tv.adobe.com/v/334092/?quality=12)

Rullande datumintervall i segment:

>[!VIDEO](https://video.tv.adobe.com/v/25403/?quality=12)

## Skapa segment {#section_693CFADA668B4542B982446C2B4CF0F5}

Du kan skapa olika typer av segment i Analysis Workspace:

* [Snabbsegment](/help/analyze/analysis-workspace/components/segments/quick-segments.md)
* [Ad hoc-segment](/help/analyze/analysis-workspace/components/segments/ad-hoc-segments.md)
* Vanliga segment för komponentlistor som du skapar i segmentbyggaren och som hamnar i segmentbiblioteket (se nedan)

### Skapa segment för komponentlistor {#section_3B07D458C43E42FDAF242BB3ACAF3E90}

Segmentspåret under komponentmenyn visas
* Segment som du eller ditt företag har skapat
* Segmentmallar, enligt Adobe-ikonen:

![](assets/segment_icons.png)

Om du vill skapa ett segment av den här typen har du två alternativ. Bägge tar dig till [Segment Builder](/help/components/segmentation/segmentation-workflow/seg-build.md) i Adobe Analytics, där du hittar mer information.

* Klicka på plustecknet (+) bredvid den vänstra listen [!UICONTROL Segments]:

![](assets/create-seg.png)

eller

* Gå till [!UICONTROL Components] > [!UICONTROL Segments]och sedan klicka [!UICONTROL + Add].


### Andra metoder för att använda segment {#section_10FF2E309BA84618990EA5B473015894}

>[!VIDEO](https://video.tv.adobe.com/v/30994/?quality=12)

Det finns flera andra metoder för att tillämpa segment i frihandsprojekt.

| Åtgärd | Beskrivning |
|--- |--- |
| Skapa segment från markering | Skapa ett textbundet segment. Det här segmentet gäller bara det öppna projektet och sparas inte som ett Analytics-segment. 1. Markera rader.  2. Högerklicka på markeringen.  3. Klicka *Skapa segment från markering*. |
| Komponenter > Nytt segment | Visar segmentbyggaren. Se [Segment Builder](https://experienceleague.adobe.com/docs/analytics/components/segmentation/segmentation-workflow/seg-build.html) för mer information om segmentering. |
| Dela > Dela projekt eller Dela > Kuratera projektdata | I [Kuratera och dela](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/curate.html#concept_4A9726927E7C44AFA260E2BB2721AFC6), får du lära dig hur segment som du tillämpar på projektet är tillgängliga i en delad analys för mottagaren. |
| Använd segment som Dimensioner | Video: [Använda segment som Dimensioner i Analysis Workspace](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/applying-segments/using-segments-as-dimensions-in-analysis-workspace.html?lang=en) |

## Segment IQ

Segmentanalys (även kallad segmentjämförelse) omfattar följande funktioner:

* [Panelen Segmentjämförelse:](/help/analyze/analysis-workspace/c-panels/c-segment-comparison/segment-comparison.md) Kärnfunktionen i segmentanalys. Dra två segment till panelen och visa en omfattande rapport som visar statistiskt signifikanta skillnader och överlappning mellan de två målgrupperna.
* [Jämföra segment i utfall:](/help/analyze/analysis-workspace/visualizations/fallout/compare-segments-fallout.md) Se hur olika målgrupper jämför med varandra i samband med en utfallsvisualisering.

## Mer info

Mer information om segmentering i Adobe Analytics finns på [här](/help/components/segmentation/seg-overview.md).