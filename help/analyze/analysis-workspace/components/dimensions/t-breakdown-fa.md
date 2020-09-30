---
description: Dela upp dimensioner och dimensionsobjekt i Analysis Workspace.
keywords: Analysis Workspace
title: Dela upp dimensioner
topic: Reports and analytics
uuid: 0b888e26-f201-4405-99f9-755b3ee6cd18
translation-type: tm+mt
source-git-commit: 56ca9fa36db9d7dd126808280ba17f29f4b787d9
workflow-type: tm+mt
source-wordcount: '224'
ht-degree: 14%

---


# Dela upp dimensioner

Dela upp dimensioner och dimensionsobjekt i Analysis Workspace.

Analysera data på obegränsade sätt efter just era behov och bygg frågor med hjälp av relevanta mätvärden, mått, segment, tidslinjer och andra analysvärden.

1. [Skapa ett projekt](/help/analyze/analysis-workspace/build-workspace-project/t-freeform-project.md) med en datatabell.
1. Högerklicka på ett radobjekt i datatabellen och välj **[!UICONTROL Breakdown]** > *`<item>`*.

   ![Stegresultat](assets/fa_data_table_actions.png)

   Du kan dela upp mätvärden efter dimensionsobjekt eller målgruppssegment under valda tidsperioder. Du kan även gå ned mer i detalj.

   >[!NOTE]
   >
   >Antalet uppdelningar i tabellen är begränsat till 200. Den här gränsen kommer att öka för export av uppdelningar.

[Lägga till Dimensioner och statistik i ditt projekt i Analysis Workspace](https://docs.adobe.com/content/help/en/analytics-learn/tutorials/analysis-workspace/metrics/adding-dimensions-and-metrics-to-your-project-in-analysis-workspace.html) (11:39)

[Arbeta med Dimensioner i en frihandstabell](https://docs.adobe.com/content/help/en/analytics-learn/tutorials/analysis-workspace/building-freeform-tables/working-with-dimensions-in-a-freeform-table.html) (15:35)

## Tillämpa attribueringsmodeller på uppdelningar

Alla uppdelningar i en tabell kan också ha en attribueringsmodell. Den här attribueringsmodellen kan vara densamma eller en annan än den överordnade kolumnen. Du kan till exempel analysera linjära beställningar i dimensionen marknadsföringskanaler, men använda U-formade beställningar på specifika spårningskoder i en kanal. Om du vill redigera attribueringsmodellen som används för en uppdelning håller du muspekaren över uppdelningsmodellen och klickar på **[!UICONTROL Edit]**:

![Brytningsinställningar](assets/breakdown_settings.png)
