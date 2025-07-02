---
description: Lär dig hur du bryter ned dimensioner och dimensionsobjekt i Analysis Workspace.
keywords: Analysis Workspace
title: Bryt ned dimensioner
feature: Dimensions
role: User, Admin
exl-id: 0d26c920-d0d9-4650-9cf0-b67dbc4629e1
source-git-commit: ff38740116ac6f12033ebdc17cffa3250a30f3f7
workflow-type: tm+mt
source-wordcount: '547'
ht-degree: 0%

---

# Dela upp dimensioner

Ni kan dela upp era data i Analysis Workspace på ett obegränsat sätt för just era behov; skapa frågor med hjälp av relevanta mått, dimensioner, segment, tidslinjer och andra analysvärden.

1. I en [friformstabell](/help/analyze/analysis-workspace/visualizations/freeform-table/freeform-table.md) väljer du **[!UICONTROL Breakdown]** ![SparronRight](/help/assets/icons/ChevronRight.svg) på snabbmenyn för en eller flera markerade rader.

   ![Stegresultat som visar Skapa avisering från markering.](assets/breakdown.png)

1. På undermenyn väljer du **[!UICONTROL Dimensions]**, **[!UICONTROL Metrics]**, **[!UICONTROL Segments]** eller **[!UICONTROL Date ranges]** och sedan ett alternativ. Eller sök bara efter en komponent i fältet **[!UICONTROL *Sök *]**.

Du kan dela upp mätvärden efter dimensionsobjekt eller målgruppssegment under valda tidsperioder. Du kan även gå ned mer i detalj.

>[!NOTE]
>
>Antalet uppdelningar i tabellen är begränsat till 200. Den här gränsen ökar vid export av uppdelningar.

## Uppdelning efter position

Som standard är uppdelningar fasta på statiska radobjekt. Tänk dig att du har delat upp de tre viktigaste sidobjekten (startsida, sökresultat, utcheckning) efter marknadsföringskanal. Sedan lämnar du projektet och återvänder två veckor senare. När du öppnar projektet igen har de tre översta sidorna ändrats, och nu är startsidan, sökresultaten och utcheckningen de 4-6 översta sidorna istället. Som standard visas dina Marketing Channel-indelningar fortfarande under Hemsida, Sökresultat och Utcheckning, även om de nu finns på raderna 4-6.

**Uppdelning efter position** delar däremot alltid upp de tre översta objekten, oavsett vilka de är. När du öppnar ditt projekt på nytt är Marketing Channel-uppdelningarna kopplade till de tre översta sidorna i tabellen. Och inte till startsidan, sökresultat och utcheckning, som nu finns på raderna 4-6. Se [Radinställningar](/help/analyze/analysis-workspace/visualizations/freeform-table/column-row-settings/table-settings.md) om hur du konfigurerar den här inställningen.



## Tillämpa attribueringsmodeller på uppdelningar

Alla uppdelningar i en tabell kan också ha en attribueringsmodell. Den här attribueringsmodellen kan vara densamma eller en annan än den överordnade kolumnen. Du kan till exempel analysera linjära beställningar i dimensionen marknadsföringskanaler, men använda U-formade beställningar på specifika spårningskoder i en kanal. Om du vill redigera attribueringsmodellen som används för en nedbrytning håller du pekaren över uppdelningsmodellen och väljer **[!UICONTROL Edit]**.

![Jämförelse av orderattribut som visar brytningsinställningarna](assets/breakdown-attribution.png)

Detta är det förväntade beteendet när du tillämpar attribueringsmodeller på uppdelningar eller redigerar dem:

* Om du tillämpar en attribuering när det inte finns några andra attribut gäller attribueringen för hela kolumnträdet.

* Om du lägger till en uppdelning efter att en attribuering har tillämpats, används standardvärdet för den angivna uppdelning som lades till (om den dimensionen har ett standardvärde). I annat fall används den uppdelning som görs från den överordnade kolumnen. Vissa dimensioner har en standardallokering. Tidsdimensioner och Referens använder till exempel samma beröring. Produktdimensionen använder Senaste beröring. Andra dimensioner saknar standardvärde och använder den överordnade kolumnallokeringen.

* Om det redan finns attribut i kolumnträdet påverkas bara den du redigerar om du ändrar attributet.

>[!BEGINSHADEBOX]

Se ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Dimension i Analysis Workspace](https://video.tv.adobe.com/v/23971?quality=12&learn=on){target="_blank"} för en demonstrationsvideo.


>[!ENDSHADEBOX]


>[!BEGINSHADEBOX]

Se ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Dimension-uppdelningar](https://video.tv.adobe.com/v/23969?quality=12&learn=on){target="_blank"} för en demonstrationsvideo.


>[!ENDSHADEBOX]


>[!BEGINSHADEBOX]

Se ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Lägga till mått och mätvärden](https://video.tv.adobe.com/v/30606?quality=12&learn=on){target="_blank"} för en demonstrationsvideo.


>[!ENDSHADEBOX]


>[!BEGINSHADEBOX]

Se ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Arbeta med dimensioner i en frihandstabell](https://video.tv.adobe.com/v/40179?quality=12&learn=on){target="_blank"} för en demonstrationsvideo.


>[!ENDSHADEBOX]


>[!BEGINSHADEBOX]

Se ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Dimension-nedbrytning efter position](https://video.tv.adobe.com/v/24033){target="_blank"} för en demonstrationsvideo.


>[!ENDSHADEBOX]



<!--
# Break down dimensions

Break down dimensions and dimension items in Analysis Workspace.

Break down your data in unlimited ways for your specific needs; build queries using relevant metrics, dimensions, segments, time lines, and other analysis breakdown values.

1. [Create a project](/help/analyze/analysis-workspace/home.md) with a data table.
1. In the data table, right-click a line item and select **[!UICONTROL Breakdown]** > *`<item>`*.

   ![Step Result](assets/fa_data_table_actions.png)

   You can break down metrics by dimension items or audience segments across selected time periods. You can also drill down further to a more granular level.

   >[!NOTE]
   >
   >The number of breakdowns to show in the table is limited to 200. This limit will increase for exporting breakdowns.

## Apply attribution models to breakdowns

Any breakdown within a table can also have any attribution model applied to it. This attribution model can be the same or different from the parent column. For example, you can analyze linear Orders on your Marketing Channels dimension but apply U-Shaped Orders to the specific tracking codes within a Channel. To edit the attribution model applied to a breakdown, hover over the breakdown model and click **[!UICONTROL Edit]**:

![Breakdown settings](assets/breakdown_settings.png)

This is the expected behavior when applying attribution models to breakdowns or editing them:

* If you apply an attribution when no other attributions exist, then the attribution applies to the entire column tree.

* If you add a breakdown after an attribution has been applied, it will use the default for the given breakdown that was added, if that dimension has a default. Otherwise it will use the breakdown from the parent column. Some dimensions have a default allocation.  For example, [!UICONTROL Time] dimensions and [!UICONTROL Referrer] use [!UICONTROL Same Touch]. The [!UICONTROL Product] dimension uses [!UICONTROL Last Touch]. Other dimensions don't have a default, and will use the parent column allocation.

* If there are already attributions in the column tree, changing the attribution only impacts the one you are editing.

## Videos


>[!BEGINSHADEBOX]

See ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Adding dimensions and metrics to your project in Analysis Workspace](https://video.tv.adobe.com/v/30606?quality=12&learn=on){target="_blank"} for a demo video.

>[!ENDSHADEBOX]



>[!BEGINSHADEBOX]

See ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Working with dimensions in a Freeform Table](https://video.tv.adobe.com/v/40179?quality=12&learn=on){target="_blank"} for a demo video.

>[!ENDSHADEBOX]


>[!BEGINSHADEBOX]

See ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [dimension breakdowns by position](https://video.tv.adobe.com/v/24033?quality=12&learn=on){target="_blank"} for a demo video.

>[!ENDSHADEBOX]


-->