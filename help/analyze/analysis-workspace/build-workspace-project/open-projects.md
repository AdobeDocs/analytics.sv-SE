---
title: Öppna projekt
description: Lär dig hur du öppnar projekt
feature: Workspace Basics
role: User, Admin
source-git-commit: 8f7c6a0d1477b599b05aeb7b74c4ee96531d294d
workflow-type: tm+mt
source-wordcount: '229'
ht-degree: 0%

---

# Öppna projekt

Du kan öppna ett projekt direkt från sidan [Projekt](/help/analyze/analysis-workspace/build-workspace-project/freeform-overview.md). Leta efter ditt projekt i listan. Använd [search](/help/analyze/analysis-workspace/build-workspace-project/freeform-overview.md#search) eller [segmentpanelen](/help/analyze/analysis-workspace/build-workspace-project/freeform-overview.md#segment-panel) för att begränsa listan.

* Välj projekttitel för att öppna projektet i Analysis Workspace.

Du kan också öppna ett projekt medan du arbetar i ett annat projekt.

* Välj **[!UICONTROL Open]** på menyn **[!UICONTROL Project]**. En dialogruta visas som liknar sidan [Projekt](/help/analyze/analysis-workspace/build-workspace-project/freeform-overview.md).  Använd [search](/help/analyze/analysis-workspace/build-workspace-project/freeform-overview.md#search) eller [segmentpanelen](/help/analyze/analysis-workspace/build-workspace-project/freeform-overview.md#segment-panel) för att begränsa listan.
* Välj projekttitel för att öppna projektet i Analysis Workspace.

Om du inte kan hitta projektet och vill starta ett nytt projekt väljer du **[!UICONTROL Create new]**.

## Öppna föregående version

Så här öppnar du en tidigare sparad version av ett projekt:

1. Välj **[!UICONTROL Open previous version]** på menyn **[!UICONTROL Project]**.

   ![Listan med tidigare sparade projektversioner och alternativ för att visa alla versioner eller endast versioner med anteckningar.](assets/open-previously-saved.png)

1. Granska listan över tidigare versioner i dialogrutan **[!UICONTROL Previously saved versions]**. Du kan växla mellan **[!UICONTROL All versions]** och **[!UICONTROL Only versions with notes]**.

   För varje version visar listan en tidsstämpel, redigeraren och sparade anteckningar.


1. Välj en tidigare version och klicka på **[!UICONTROL Load]**.
Den föregående versionen läses sedan in med ett meddelande. Den tidigare versionen blir inte den aktuella sparade versionen av ditt projekt förrän du klickar på **[!UICONTROL Save]**. Om du navigerar bort från den inlästa versionen visas den senast sparade versionen när du vill öppna en tidigare version en gång till.


<!-- 
## Incompatible data view

When you open a project, you might see an **[!UICONTROL Incompatible data view]** warning dialog. This dialog explains that certain components within the project are not enabled in the selected data view for one of the panels in the project. 

![Incompatible](assets/incompatible-data-view.png)

To fix this warning, you can:

* **[!UICONTROL Change the data view]**. Select a proper data view from **[!UICONTROL Change data view:]** ![Data](/help/assets/icons/Data.svg). If the selected data view is valid, your project opens in Analysis Workspace.
* **[!UICONTROL Return to landing page]**. Your selected project is not opened and you can select another project.
* **[!UICONTROL Continue anyway]**. Your project opens in Analysis Workspace, but shows errors in some of the visualization and the incompatible data views have an alert ![Alert](/help/assets/icons/Alert.svg) before the name of the data view.


-->