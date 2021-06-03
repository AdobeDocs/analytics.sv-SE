---
description: Dela upp dimensioner och dimensionsobjekt i Analysis Workspace.
keywords: Analysis Workspace
title: Dela upp dimensioner
uuid: 0b888e26-f201-4405-99f9-755b3ee6cd18
feature: Grundläggande om arbetsytan
role: Business Practitioner, Administrator
exl-id: 0d26c920-d0d9-4650-9cf0-b67dbc4629e1
source-git-commit: f669af03a502d8a24cea3047b96ec7cba7c59e6f
workflow-type: tm+mt
source-wordcount: '224'
ht-degree: 15%

---

# Dela upp dimensioner

Dela upp dimensioner och dimensionsobjekt i Analysis Workspace.

Analysera data på obegränsade sätt efter just era behov och bygg frågor med hjälp av relevanta mätvärden, mått, segment, tidslinjer och andra analysvärden.

1. [Skapa ett ](/help/analyze/analysis-workspace/home.md) projekt med en datatabell.
1. Högerklicka på ett radobjekt i datatabellen och välj **[!UICONTROL Breakdown]** > *`<item>`*.

   ![Stegresultat](assets/fa_data_table_actions.png)

   Du kan dela upp mätvärden efter dimensionsobjekt eller målgruppssegment under valda tidsperioder. Du kan även gå ned mer i detalj.

   >[!NOTE]
   >
   >Antalet uppdelningar i tabellen är begränsat till 200. Den här gränsen kommer att öka för export av uppdelningar.

[Lägga till Dimensioner och statistik i ditt projekt i Analysis Workspace](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/metrics/adding-dimensions-and-metrics-to-your-project-in-analysis-workspace.html)  (11:39)

[Arbeta med Dimensioner i en frihandstabell](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/building-freeform-tables/working-with-dimensions-in-a-freeform-table.html)  (15:35)

## Tillämpa attribueringsmodeller på uppdelningar

Alla uppdelningar i en tabell kan också ha en attribueringsmodell. Den här attribueringsmodellen kan vara densamma eller en annan än den överordnade kolumnen. Du kan till exempel analysera linjära beställningar i dimensionen marknadsföringskanaler, men använda U-formade beställningar på specifika spårningskoder i en kanal. Om du vill redigera attribueringsmodellen som används för en uppdelning håller du pekaren över nedbrytningsmodellen och klickar på **[!UICONTROL Edit]**:

![Brytningsinställningar](assets/breakdown_settings.png)
