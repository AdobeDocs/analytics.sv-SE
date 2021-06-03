---
description: 'Ni kan använda AAM Audience-dimensioner i hela Analytics. De integrerade segmenten är nya analysdimensioner som kallas publikens ID och publikens namn, och kan användas precis som andra dimensioner som samlas in med Analytics. I Dataflöden lagras publikens ID:n i kolumnen"mc_audiences". Dessa dimensioner är för närvarande inte tillgängliga i Data Workbench eller livream. Några exempel på hur publikens dimensioner kan utnyttjas är '
solution: Experience Cloud
title: Använd målgruppsdata i Analytics
uuid: 203925fb-f070-441c-813a-43099cb9b2b9
exl-id: c1c0a9de-4051-4073-82c1-5615b0f01fa9
source-git-commit: f669af03a502d8a24cea3047b96ec7cba7c59e6f
workflow-type: tm+mt
source-wordcount: '594'
ht-degree: 3%

---

# Använd målgruppsdata i Analytics

Ni kan använda AAM Audience-dimensioner i hela Analytics. De integrerade segmenten är nya analysdimensioner som kallas publikens ID och publikens namn, och kan användas precis som andra dimensioner som samlas in med Analytics. I Dataflöden lagras publikens ID:n i kolumnen&quot;mc_audiences&quot;. Dessa dimensioner är för närvarande inte tillgängliga i Data Workbench eller livream. Några exempel på hur publikens dimensioner kan utnyttjas är:

## Analysis Workspace {#section_C70837499BEA4DED885B3486C9E02C68}

I Analysis Workspace visas AAM som två dimensioner.

1. Gå till **[!UICONTROL Workspace]**.
1. Välj dimensionerna **[!UICONTROL Audience ID]** eller **[!UICONTROL Audience Name]** i listan **[!UICONTROL Dimensions]**. Namnet är en användarvänlig klassificering av ID:t.

   ![](assets/aw-mcaudiences.png)

## Segmentjämförelse {#section_E72B80B6470C42D4B9B19BE90E6070A2}

[Segmentjämförelse ](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/segment-comparison/segment-comparison.html) visar de mest statistiskt signifikanta skillnaderna mellan två segment. Målgruppsdata kan användas i segmentjämförelsen på två sätt: 1) som de två segment som ska jämföras och 2) som objekt i tabellen&quot;Objekt på den översta Dimensionen&quot;.

1. Gå till **[!UICONTROL Workspace]** och välj panelen **[!UICONTROL Segment Comparison]** i den vänstra listen.

1. Sök efter [!UICONTROL Audiences Name] på **[!UICONTROL Component]**-menyn.

1. Öppna [!UICONTROL Audiences Name]så att relaterade dimensionsobjekt visas.
1. Dra de målgrupper du vill jämföra till segmentjämförelseverktyget.
1. (Valfritt): Du kan även infoga andra dimensionsobjekt eller segment, upp till 2 kan jämföras.
1. Klicka på **[!UICONTROL Build]**.

   Måtten för publikens ID och namn visas automatiskt i tabellen&quot;Objekt i den översta Dimensionen&quot;, eftersom de är ytterligare profildata för de två segment som jämförs.

   ![](assets/aud-segcompare.png)

## Kundresa (flöde) i Analysis Workspace {#section_FC30E5795C9D4539838E30FE11FAEA6E}

AAM segmentdata överförs till Analytics från en träffsäker nivå och representerar målgruppsmedlemskapet för en besökare vid den tidpunkten. Det innebär att en besökare kan hamna i ett segment (t.ex. &quot;Kännedom&quot;), kan senare kvalificera sig för ett mer kvalificerat segment (t.ex. &quot;Övervägande&quot;). Du kan använda [Flöde](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/fallout/fallout-flow.html) i Analysis Workspace för att visualisera den resa en besökare tar mellan olika målgrupper.

1. Gå till **[!UICONTROL Workspace]** och välj visualiseringen **[!UICONTROL Flow]** i den vänstra listen.

1. Dra [!UICONTROL Audience Name]-dimensionen till Flow-verktyget.
1. Klicka på **[!UICONTROL Build]**.
1. (Valfritt): Dra en annan dimension till Flödesvisualiseringen för att skapa ett [interdimensionellt flöde](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/flow/multi-dimensional-flow.html).

![](assets/flow-aamaudiences.png)

Publiker kan också användas i [bortfallsvisualiseringar](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/fallout/fallout-flow.html).

## Visualisering av Venner i Analysis Workspace {#section_E78AB764FB5047148B51DC1526B0DF89}

[Vennvisualiseringar ](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/venn.html) visar överlappningen mellan upp till 3 segment.

1. Gå till **[!UICONTROL Workspace]** och välj visualiseringen **[!UICONTROL Venn]** i den vänstra listen.

1. Sök efter [!UICONTROL Audience Name] på komponentmenyn.
1. Öppna [!UICONTROL Audience Name] så att relaterade dimensionsobjekt visas.
1. Dra de målgrupper du vill jämföra till Venn-byggaren.
1. (Valfritt): Du kan även infoga andra dimensionsobjekt eller segment. upp till 3 kan jämföras.
1. Klicka på **[!UICONTROL Build]**.

![](assets/venn-viz.png)

## Segment Builder {#section_2AA81852A1404AB894472CA8959461B6}

Du kan inkludera publikens dimensioner i [Segment Builder](/help/components/segmentation/segmentation-workflow/seg-build.md), tillsammans med den beteendeinformation som samlas in i Analytics.

1. Gå till **[!UICONTROL Components]** > **[!UICONTROL Segments]**.
1. Klicka på **[!UICONTROL Add]** för att skapa ett nytt segment.
1. När du har namngett segmentet drar du [!UICONTROL Audience Name]-dimensionen till panelen Definitioner.
1. (Valfritt): Lägg till andra villkor till segmentet.
1. Spara segmentet.

   ![](assets/aud-segbuilder.png)

## Rapporter och analyser och Report Builder {#section_04E8FD30F73344D7937AD3C6CD19E34A}

1. Om du vill visa analysrapporten går du till **[!UICONTROL Reports]** > **[!UICONTROL Visitor Profile]** > **[!UICONTROL Audience ID Reports]**.
1. Från den här mappen kan du komma åt både Audience ID och Audience Name.

   ![](assets/mc-audiences.png)
