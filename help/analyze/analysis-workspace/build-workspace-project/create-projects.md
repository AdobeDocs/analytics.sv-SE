---
description: Lär dig grunderna i att skapa projekt i Analysis Workspace
title: Skapa projekt
feature: Workspace Basics
role: User, Admin
exl-id: 24193013-1361-43fc-b129-c44f207d9101
source-git-commit: 273fea86cde8880d9c9e03ac9c6a99b75f70f6cd
workflow-type: tm+mt
source-wordcount: '768'
ht-degree: 0%

---

# Skapa projekt i Analysis Workspace

[Projekt](/help/analyze/analysis-workspace/build-workspace-project/freeform-overview.md) i Analysis Workspace kan ni visa affärskritiska analyser som kan delas med intressenter både inom och utanför organisationen.

Allmän information om hur du kommer igång med Analysis Workspace finns i [Analysis Workspace - översikt](/help/analyze/analysis-workspace/home.md).

I följande avsnitt beskrivs hur du skapar ett projekt och börjar lägga till de viktigaste byggstenarna för ett Analysis Workspace-projekt: paneler, visualiseringar och komponenter.

## Skapa ett projekt från ett tomt projekt eller en rapport

1. I Adobe Analytics: [!UICONTROL **Arbetsyta**].

1. Välj om du vill skapa ett tomt projekt eller om du vill skapa ett projekt från en rapport:

   +++Skapa ett tomt projekt

   1. På [!UICONTROL **Arbetsyta**] väljer du [!UICONTROL **Projekt**] på sidans vänstra sida och sedan väljer [!UICONTROL **Skapa projekt**].

   1. Välj om du vill skapa ett tomt projekt eller ett tomt mobilstyrkort

      * **Tomt projekt** om du planerar att dela analysen från webbläsaren
      * [**Tomt mobilstyrkort**](/help/analyze/mobile-app/curator.md) om du tänker dela med dig av dina analyser från mobilappen Adobe Analytics dashboards.

   1. Välj [!UICONTROL **Skapa**].

+++

   +++Skapa ett projekt från en rapport

   1. På [!UICONTROL **Arbetsyta**] väljer du [!UICONTROL **Rapporter**] till vänster på sidan.

   1. Sök efter eller navigera till rapporten som du vill använda och markera den när den visas.

      En uppsättning standardrapporter är tillgängliga som standard. Dessutom kan din organisation ha skapat anpassade rapporter som du kan välja bland.

   1. Välj [!UICONTROL **Projekt**] > [!UICONTROL **Spara**] för att spara rapporten som ett nytt projekt.

      Mer information om rapporter finns i&quot;Navigera på fliken Rapporter&quot; i [Adobe Analytics landningssida](/help/analyze/landing.md).

+++

1. Därefter måste du lägga till paneler, visualiseringar och komponenter i projektet. Lägg först till paneler i ditt projekt i Analysis Workspace, enligt beskrivningen i [Lägga till paneler i projektet](#add-panels-to-the-project). Du kan sedan lägga till visualiseringar i alla paneler. Slutligen kan du lägga till komponenter till valfria paneler eller visualiseringar.

## Lägga till paneler i projektet {#panels}

[Panel](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/panels.html) är grunden till alla projekt i Analysis Workspace. Paneler används för att ordna innehållet (visualiseringar och komponenter) i ett projekt.

Många av panelerna i Analysis Workspace genererar en komplett uppsättning analyser baserade på några få indata från användarna.

Så här lägger du till en panel:

1. Välj [!UICONTROL **Panel**] ikonen i den vänstra listen.

   ![](assets/build-panels.png)

1. Sök efter panelen som du vill lägga till. När den visas i den vänstra listen drar du den till ditt projekt.

1. Lägg till visualiseringar i panelen enligt beskrivningen i [Lägg till visualiseringar i projektet](#add-visualizations-to-the-project).

   Du kan också lägga till komponenter direkt på en panel enligt beskrivningen i [Lägga till komponenter i projektet](#add-components-to-the-project).

## Lägg till visualiseringar i projektet

[Visualiseringar](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.html) (t.ex. en frihandstabell, ett stapeldiagram eller ett linjediagram) kan användas för att visuellt ge liv åt data.

>[!TIP]
>
>Frihandstabeller är den vanligaste typen av visualisering och är grunden för interaktiv dataanalys. Mer information om hur du arbetar med frihandstabeller i Analysis Workspace finns i [Frihandsregister](/help/analyze/analysis-workspace/visualizations/freeform-table/freeform-table.md).

Lägga till en visualisering:

1. Välj **[!UICONTROL Visualizations]** ikonen i den vänstra listen.

   ![](assets/build-visualizations.png)

1. Sök efter den visualisering som du vill lägga till. När den visas i den vänstra listen drar du den till en panel i projektet.

1. Lägga till komponenter i visualiseringen enligt beskrivningen i [Lägga till komponenter i projektet](#add-components-to-the-project).

## Lägga till komponenter i projektet

[Komponenter](/help/analyze/analysis-workspace/components/analysis-workspace-components.md) sammanställa faktiska data för alla slags projekt. Du kan lägga till komponenter till visualiseringar eller till paneler.

>[!TIP]
>
>Om du vill ha information om de olika komponenterna väljer du ikonen Info bredvid en komponents namn i den vänstra listen. Du kan också se ikonen [Handbok för analyskomponenter](/help/components/home.md).

Här följer grundläggande information om hur du lägger till en komponent i ett projekt i Analysis Workspace. Mer information om hur du lägger till olika typer av komponenter (mått, mått, segment och datumintervall) finns i [Använda komponenter i Analysis Workspace](/help/analyze/analysis-workspace/components/use-components-in-workspace.md).

Så här lägger du till en komponent i ett projekt i Analysis Workspace:

1. Välj **[!UICONTROL Components]** ikonen i den vänstra listen.

   ![](assets/build-components.png)

1. Bläddra till eller sök efter komponenten som du vill lägga till och dra den sedan till en panel eller visualisering i projektet.

   Du kan till exempel dra ett segment till segmentets släppzon i ett panelhuvud.

   ![släppa ett segment i släppzonen](assets/segment-dropzone.png)

   Mer information om hur du lägger till komponenter i projekt finns i [Använda komponenter i Analysis Workspace](/help/analyze/analysis-workspace/components/use-components-in-workspace.md).

1. (Valfritt) Dela projektet enligt beskrivningen i [Spara och dela projektet](#save-and-share-the-project).

## Spara och dela projektet

När du gör en analys i Analysis Workspace blir resultatet [automatiskt sparad](/help/analyze/analysis-workspace/build-workspace-project/save-projects.md).

När du är klar med projektet och samlar in åtgärdbara insikter är projektet klart att användas av andra. Du kan dela projektet med användare och grupper i organisationen, eller till och med med med personer utanför organisationen. Mer information om hur du delar ett projekt finns i [Dela projekt](/help/analyze/analysis-workspace/curate-share/share-projects.md).
