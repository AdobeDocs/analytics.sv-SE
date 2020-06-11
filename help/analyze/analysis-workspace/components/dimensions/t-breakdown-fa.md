---
description: Dela upp dimensioner och dimensionsobjekt i Analysis Workspace.
keywords: Analysis Workspace
title: Dela upp dimensioner
topic: Reports and analytics
uuid: 0b888e26-f201-4405-99f9-755b3ee6cd18
translation-type: tm+mt
source-git-commit: 834783e4eae9100233afc164e2fabef96f089874
workflow-type: tm+mt
source-wordcount: '229'
ht-degree: 2%

---


# Dela upp dimensioner

Dela upp dimensioner och dimensionsobjekt i Analysis Workspace.

Anpassa era data på ett obegränsat sätt efter era specifika behov. skapa frågor med hjälp av relevanta mått, dimensioner, segment, tidslinjer och andra analysvärden.

1. [Skapa ett projekt](/help/analyze/analysis-workspace/build-workspace-project/t-freeform-project.md) med en datatabell.
1. Högerklicka på ett radobjekt i datatabellen och välj **[!UICONTROL Breakdown]** > *`<item>`*.

   ![Stegresultat](assets/fa_data_table_actions.png)

   Du kan dela upp mätvärden efter dimensionsvärden eller målgruppssegment under valda tidsperioder. Du kan även gå ned mer i detalj.

   >[!NOTE] Antalet uppdelningar i tabellen är begränsat till 200. Den här gränsen kommer att öka för export av uppdelningar.

[Dimensioner i Analysis Workspace på YouTube](https://www.youtube.com/watch?v=P9W0hhIHhCs&amp;index=12&amp;list=PL2tCx83mn7GuNnQdYGOtlyCu0V5mEZ8sS) (4:54)

[Dimension-uppdelningar på YouTube](https://www.youtube.com/watch?v=3mQ2HN7-lIc&amp;list=PL2tCx83mn7GuNnQdYGOtlyCu0V5mEZ8sS&amp;index=13) (2:02)

## Tillämpa attribueringsmodeller på uppdelningar

Alla uppdelningar i en tabell kan också ha en attribueringsmodell. Den här attribueringsmodellen kan vara densamma eller en annan än den överordnade kolumnen. Du kan till exempel analysera linjära beställningar i dimensionen marknadsföringskanaler, men använda U-formade beställningar på specifika spårningskoder i en kanal. Om du vill redigera attribueringsmodellen som används för en uppdelning håller du muspekaren över uppdelningsmodellen och klickar på **[!UICONTROL Edit]**:

![Brytningsinställningar](assets/breakdown_settings.png)
