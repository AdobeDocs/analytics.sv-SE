---
description: 'null'
title: Kör bidragsanalys
uuid: 5282a5f9-0771-4974-93cb-335204bde114
translation-type: tm+mt
source-git-commit: ad9a7729924636055e456d0fd7ab928be227034d

---


# Kör bidragsanalys

Bidragsanalys är en intensiv maskininlärningsprocess som utformats för att identifiera medverkande till en iakttagen avvikelse i Adobe Analytics. Avsikten är att hjälpa användaren att hitta fokusområden eller möjligheter till ytterligare analys mycket snabbare än vad som annars skulle vara möjligt.

## Kör bidragsanalys {#section_7D2C5E48A5664727941DF4C90976D9DC}

Det finns två sätt att anropa bidragsanalys i ett projekt:

* I en frihandstabell med daglig kornighet högerklickar du på en rad och väljer **[!UICONTROL Run Contribution Analysis]**. Du kan till och med köra det på rader som inte visar några avvikelser.

   >[!NOTE]
   >
   >Vi stöder för närvarande endast bidragsanalys med daglig granularitet.

   ![](assets/run_ca.png)

* Håll pekaren över en avvikande datapunkt i ett linjediagram. Klicka på **[!UICONTROL Analyze]** länken som visas.

   ![](assets/contribution-analysis.png)

1. (Valfritt) När du har klickat **[!UICONTROL Run Contribution Analysis]** i antingen linjediagrammet eller en tabell kan du begränsa omfattningen av (och därmed snabba upp) analysen genom att [utesluta dimensioner](/help/analyze/analysis-workspace/virtual-analyst/contribution-analysis/run-contribution-analysis.md#section_F6932F4BF74544B5872164E7B1E0C6FC).

1. Vänta medan din bidragsanalys läses in. Detta kan ta lång tid, beroende på rapportsvitens storlek och antalet dimensioner. Bidragsanalys utför analyser på de 50 000 främsta objekten per dimension.
1. Analysis Workspace läser sedan in en ny Contribute Analysis-panel direkt i det här projektet. Du kommer att märka en mängd välbekanta paneler om du har använt bidragsanalys i rapporter och analyser tidigare:

   * En visualisering som visar antalet **besök** den dagen.
   * En månatlig **besöks trendlinje** för kontext.
   * **De vanligaste objekten** som bidrog till avvikelsen, sorterade efter [bidragspoängen](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/virtual-analyst/contribution-analysis/ca-tokens.html), plus måttet i fråga och ett unikt besökarmått som sätter måttet i rätt kontext ur ett storleksperspektiv.

   * Tabellen [Generated Segments](https://docs.adobe.com/content/help/en/analytics/components/segmentation/segmentation-workflow/seg-build.html) (Top Item Clusters) identifierar associationer av de främsta objekten baserat på bidragsresultat, avvikelser och den totala procentandelen som bidrar till det avvikande måttet. Detta registreras sedan som ett målgruppssegment (bidragssegment 1, bidragssegment 2 osv.). Om du klickar på knappen &quot;i&quot; (info) får du en översikt över varje segment, inklusive vilka av de viktigaste objekten som den består av:

      ![](assets/auto_segment.png)

1. Eftersom bidragsanalysen nu ingår i Analysis Workspace kan du utnyttja ett antal funktioner i en tabells högerklicksmeny för att göra analysen ännu mer meningsfull, till exempel:

   * [Bryter ned varje dimensionsobjekt med en annan dimension.](/help/analyze/analysis-workspace/components/dimensions/t-breakdown-fa.md)
   * [Trending one or more rows.](/help/analyze/analysis-workspace/home.md#section_34930C967C104C2B9092BA8DCF2BF81A)
   * [Lägga till nya visualiseringar.](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md)
   * [Skapa aviseringar.](/help/components/c-alerts/intellligent-alerts.md)
   * [Skapa eller jämföra segment.](/help/analyze/analysis-workspace/c-panels/c-segment-comparison/segment-comparison.md)

>[!NOTE] Vi belyser den avvikelse som analyseras med en blå prick i bidragsanalysen och de intelligenta aviseringsprojekt som är kopplade till den. Detta ger en tydligare indikation på den avvikelse som analyseras.

## Uteslut dimensioner från bidragsanalys {#section_F6932F4BF74544B5872164E7B1E0C6FC}

Det kan finnas tillfällen när du vill utesluta vissa dimensioner från bidragsanalysen. Du kanske inte bryr dig om webbläsar- eller maskinvarurelaterade dimensioner alls och du vill snabba upp analysen genom att ta bort dem.

1. När du har klickat **[!UICONTROL Run Contribution Analysis]** (eller **[!UICONTROL Analyze]** i ett linjediagram) visas **[!UICONTROL Excluded Dimensions]** panelen.

1. Bara dra oönskade mått till **[!UICONTROL Excluded Dimensions]** panelen och spara sedan listan genom att klicka på **[!UICONTROL Set as Default]**. Du kan också klicka **[!UICONTROL Clear All]** för att börja om med att välja dimensioner som ska uteslutas.

   ![](assets/exclude_dimensions.png)

1. När du har lagt till dimensioner som ska uteslutas (eller valt att inte göra det) klickar du **[!UICONTROL Run Contribution Analysis]** igen.
1. Om du någon gång behöver revidera listan över undantagna dimensioner dubbelklickar du bara på Dimensioner så visas listan över undantagna dimensioner:

   ![](assets/excluded-dimensions.png)

1. Ta bara bort oönskade dimensioner genom att klicka på x:et bredvid dem och spara sedan listan genom att klicka **[!UICONTROL Set as Default]**.

