---
description: Lär dig hur du synkroniserar frihandstabeller eller datakällor med motsvarande visualisering.
keywords: Analysis Workspace;Synkronisera visualisering med datakälla
title: Hantera datakällor
feature: Visualizations
role: User, Admin
exl-id: 0500b27a-032e-4dc8-98b7-58519ef59368
source-git-commit: ca84a5f807545d7196e2e0e90d3209c32d3fd789
workflow-type: tm+mt
source-wordcount: '421'
ht-degree: 0%

---

# Hantera datakällor {#manage-data-sources}

>[!CONTEXTUALHELP]
>id="workspace_freeformtable_lockselection"
>title="Lås markering"
>abstract="Aktivera den här inställningen för att låsa visualiseringen till de valda positionerna eller de valda objekten i datakällan."

>[!CONTEXTUALHELP]
>id="workspace_freeformtable_lockselection_showtable"
>title="Visa tabell"
>abstract="Om du väljer **[!UICONTROL Show table]** genereras en ny datakälla för den aktuella visualiseringen, som är skild från den ursprungliga datakällan."

>[!CONTEXTUALHELP]
>id="workspace_freeformtable_showtable"
>title="Visa tabell"
>abstract="Välj **[!UICONTROL Show table]** om du vill generera en ny datakälla för den aktuella visualiseringen, som är skild från den ursprungliga datakällan."


Med synkronisering av visualiseringar kan du styra vilken frihandstabell eller datakälla som motsvarar en visualisering.


>[!TIP]
>
>Du kan se vilka visualiseringar som är relaterade till färgen ![StatusOrange](/help/assets/icons/StatusOrange.svg) bredvid titeln för visualiseringar. Matchande färger innebär att visualiseringar baseras på samma datakälla.
>

Du kan visa eller dölja datakällan. Du kan även låsa markeringen till markerade positioner eller markerade objekt. Dessa inställningar avgör hur visualiseringen ändras (eller inte ändras) när nya data kommer in.

![Dialogrutan Data Source med alternativen som beskrivs i nästa avsnitt.](assets/lock-selection.png)

<!--
**Tip:** You can tell which visualizations are related by the color of the dot next to the title. Matching colors mean that visualizations are based on the same data source.

Managing a data source lets you show the data source or lock the selection. These settings determine how the visualization changes (or doesn't change) when new data comes in.

1. [Create a project](/help/analyze/analysis-workspace/home.md) with a data table and a [visualization](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md).
1. In the data table, select the cells (data source) you want to associate with the visualization.
1. In the visualization, click the dot next to the title to bring up the **[!UICONTROL Data Source]** dialog. Select **[!UICONTROL Show Data Source]** or **[!UICONTROL Lock Selection]**.

   ![](assets/manage-data-source.png)

   Synchronizing a visualization to a table cell creates a new (hidden) table and color-codes the synchronized visualization with that table.

>[!BEGINSHADEBOX]

See ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Data source settings](https://video.tv.adobe.com/v/23729?quality=12&learn=on){target="_blank"} for a demo video.

>[!ENDSHADEBOX]

-->

| Alternativ | Beskrivning |
|--- |--- |
| **[!UICONTROL Data source]** | Välj den datakälla som visualiseringen baseras på i listrutan. |
| **[!UICONTROL Linked visualizations]** | Visar alla länkade visualiseringar. Gäller datakällan (friformstabell). |
| **[!UICONTROL Show data source]** | Gör att du kan visa eller dölja den datakälla (frihandstabell) som motsvarar visualiseringen. |
| **[!UICONTROL Lock Selection]** | Välj det här alternativet om du vill låsa visualiseringen ![LockClosed](/help/assets/icons/LockClosed.svg) till de data som är markerade i motsvarande datatabell. När den är aktiverad väljer du mellan:  <ul><li>**Markerade positioner**: Visualiseringen är låst för de **positioner** som är markerade i motsvarande datatabell. Dessa positioner fortsätter att visualiseras, även om de specifika objekten i de här positionerna ändras (till exempel på grund av sortering eller filtrering). Välj till exempel det här alternativet om du alltid vill visa de fem främsta kampanjnamnen som anges i datakällan i den här visualiseringen. Oavsett vilka kampanjnamn som visas.</li> <li>**Markerade objekt**: Visualiseringen är låst för de specifika **objekt** som är markerade i motsvarande datatabell. Dessa objekt fortsätter att visualiseras, även om de ändrar sin rankning bland objekt i tabellen. Välj till exempel det här alternativet om du alltid vill visa samma fem specifika kampanjnamn som finns i datakällan i den här visualiseringen. Oavsett hur kampanjnamnen rankas.</li></ul>Om visualiseringen är låst till data som inte längre är synliga i den anslutna datatabellen, kan du generera en ny tabell. Välj **[!UICONTROL Show table]** om du vill generera en ny datakälla för den aktuella visualiseringen, som är skild från den ursprungliga datakällan. |
