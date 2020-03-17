---
description: 'Ni kan använda AAM Audience-dimensionerna i hela Analytics. De integrerade segmenten är nya analysdimensioner som kallas publikens ID och publikens namn, och kan användas precis som andra dimensioner som samlas in med Analytics. I Dataflöden lagras publikens ID:n i kolumnen"mc_audiences". Dessa dimensioner är för närvarande inte tillgängliga i Data Workbench eller LiveStream. Några exempel på hur publikens dimensioner kan utnyttjas är '
solution: Experience Cloud
title: Använd målgruppsdata i Analytics
uuid: 203925fb-f070-441c-813a-43099cb9b2b9
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Använd målgruppsdata i Analytics

Ni kan använda AAM Audience-dimensionerna i hela Analytics. De integrerade segmenten är nya analysdimensioner som kallas publikens ID och publikens namn, och kan användas precis som andra dimensioner som samlas in med Analytics. I Dataflöden lagras publikens ID:n i kolumnen&quot;mc_audiences&quot;. Dessa dimensioner är för närvarande inte tillgängliga i Data Workbench eller LiveStream. Några exempel på hur publikens dimensioner kan utnyttjas är:

## Analysis Workspace {#section_C70837499BEA4DED885B3486C9E02C68}

I Analysis Workspace visas AAM-segmenten som två dimensioner.

1. Gå till **[!UICONTROL Workspace]**.
1. Välj dimensioner **[!UICONTROL Dimensions]** eller **[!UICONTROL Audience ID]** i listan över **[!UICONTROL Audience Name]**. Namnet är en användarvänlig klassificering av ID:t.

   ![](assets/aw-mcaudiences.png)

## Segmentjämförelse {#section_E72B80B6470C42D4B9B19BE90E6070A2}

[Segmentjämförelsen](https://marketing.adobe.com/resources/help/en_US/analytics/analysis-workspace/segment-comparison.html) visar de mest statistiskt signifikanta skillnaderna mellan två segment. Målgruppsdata kan användas i segmentjämförelsen på två sätt: 1) som de två segment som jämförs och 2) som objekt i tabellen&quot;Top Dimension Items&quot;.

1. Gå till **[!UICONTROL Workspace]** och välj **[!UICONTROL Segment Comparison]** panelen i den vänstra listen.

1. Sök [!UICONTROL Audiences Name] på **[!UICONTROL Component]** menyn.

1. Öppna [!UICONTROL Audiences Name]så att relaterade dimensionsobjekt visas.
1. Dra de målgrupper du vill jämföra till segmentjämförelseverktyget.
1. (Valfritt): Du kan även infoga andra dimensionsobjekt eller segment, upp till 2 kan jämföras.
1. Klicka på **[!UICONTROL Build]**.

   Måtten för publikens ID och namn visas automatiskt i tabellen&quot;Top Dimension Items&quot; eftersom de är ytterligare profildata för de två segment som jämförs.

   ![](assets/aud-segcompare.png)

## Kundresa (flöde) på analysarbetsytan {#section_FC30E5795C9D4539838E30FE11FAEA6E}

AAM-segmentdata överförs till Analytics från en träffsäker nivå och representerar målgruppsmedlemskapet för en besökare vid den tidpunkten. Det innebär att en besökare kan hamna i ett segment (t.ex. &quot;Kännedom&quot;), kan senare kvalificera sig för ett mer kvalificerat segment (t.ex. &quot;Övervägande&quot;). Du kan använda [Flow](https://marketing.adobe.com/resources/help/en_US/analytics/analysis-workspace/flow.html) i Analysis Workspace för att visualisera den resa en besökare tar mellan olika målgrupper.

1. Gå till **[!UICONTROL Workspace]** och välj **[!UICONTROL Flow]** visualisering från den vänstra listen.

1. Dra [!UICONTROL Audience Name] dimensionen till Flow Builder.
1. Klicka på **[!UICONTROL Build]**.
1. (Valfritt): Dra andra dimensioner till Flödesvisualiseringen för att skapa ett [interdimensionellt flöde](https://marketing.adobe.com/resources/help/en_US/analytics/analysis-workspace/multi-dimensional-flow.html).

![](assets/flow-aamaudiences.png)

Publiken kan också användas i [bortfallsvisualiseringar](https://marketing.adobe.com/resources/help/en_US/analytics/analysis-workspace/fallout_flow.html).

## Visualisering av Venner i analysarbetsytan {#section_E78AB764FB5047148B51DC1526B0DF89}

[Vennvisualiseringar](https://marketing.adobe.com/resources/help/en_US/analytics/analysis-workspace/venn.html) visar överlappningen mellan upp till 3 segment.

1. Gå till **[!UICONTROL Workspace]** och välj **[!UICONTROL Venn]** visualisering från den vänstra listen.

1. Sök efter [!UICONTROL Audience Name] på komponentmenyn.
1. Öppna [!UICONTROL Audience Name] så att relaterade dimensionsobjekt visas.
1. Dra de målgrupper du vill jämföra till Venn-byggaren.
1. (Valfritt): Du kan även infoga andra dimensionsobjekt eller segment. upp till 3 kan jämföras.
1. Klicka på **[!UICONTROL Build]**.

![](assets/venn-viz.png)

## Segment Builder {#section_2AA81852A1404AB894472CA8959461B6}

Ni kan införliva målgruppsdimensionerna i [segmentbyggaren](https://marketing.adobe.com/resources/help/en_US/analytics/segment/seg_build.html)för Analytics, tillsammans med den beteendeinformation som samlas in i Analytics.

1. Gå till **[!UICONTROL Components]** > **[!UICONTROL Segments]** .
1. Klicka **[!UICONTROL Add]** för att skapa ett nytt segment.
1. När du har namngett segmentet drar du [!UICONTROL Audience Name] dimensionen till panelen Definitioner.
1. (Valfritt): Lägg till andra villkor till segmentet.
1. Spara segmentet.

   ![](assets/aud-segbuilder.png)

## Rapporter och analyser och Report Builder {#section_04E8FD30F73344D7937AD3C6CD19E34A}

1. Om du vill visa Analytics-rapporten går du till **[!UICONTROL Reports]** > **[!UICONTROL Visitor Profile]** > **[!UICONTROL Audience ID Reports]** .
1. Från den här mappen kan du komma åt både Audience ID och Audience Name.

   ![](assets/mc-audiences.png)

