---
description: Lär dig grunderna i hur du arbetar i ett Workspace-projekt.
keywords: Analysis Workspace
title: Projektöversikt
feature: Workspace Basics
role: User, Admin
exl-id: 75c551de-297e-4c45-95e6-77472be6628a
source-git-commit: f6bfded8b3a8346b912f34cf2f3ba9a4958eefa7
workflow-type: tm+mt
source-wordcount: '1430'
ht-degree: 1%

---

# Projektöversikt

Med Workspace-projekt kan ni kombinera datakomponenter, tabeller och visualiseringar för att skapa analyser och dela dem med vem som helst i organisationen. Innan du startar ditt första projekt bör du lära dig hur du får tillgång till, navigerar och hanterar dina projekt.

Här är en video om hur du bygger ett Workspace-projekt:

>[!VIDEO](https://video.tv.adobe.com/v/334076/?quality=12)

## Projektlista {#project-list}

När du först går till **[!UICONTROL Analytics]** > **[!UICONTROL Workspace]** visas alla projekt som du äger eller har delats med på sidan. Den här sidan är också landningssidan för Adobe Analytics, såvida du inte tidigare har angett en anpassad landningssida.

Sidan Projekt innehåller följande information:

| Element | Beskrivning |
|---|---|
| [Redigera inställningar](/help/analyze/analysis-workspace/user-preferences.md) | Hantera inställningar för Analysis Workspace och dess tillhörande komponenter för alla nya projekt eller paneler som du skapar. |
| [Skapa mapp](/help/analyze/analysis-workspace/build-workspace-project/workspace-folders/create-folders.md) | Lägg till en ny mapp eller undermapp i listan över projekt och mappar. |
| [Skapa projekt](/help/analyze/analysis-workspace/build-workspace-project/create-projects.md) | Starta ett nytt projekt från grunden eller från en rapport. |
| Visa mer | Det här valet visar alternativ för att skapa ett tomt projekt eller ett mobilstyrkort, [visa självstudiekurser](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/analysis-workspace/analysis-workspace-basics/analysis-workspace-introduction) eller [visa versionsinformation](/help/release-notes/latest.md). |
| ![Visa filter](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Filter_18_N.svg) | Visa eller dölj filter. Du kan filtrera på taggar, rapportsviten, ägare, typ (projekt, mapp, mobilstyrkort) och andra filter. |
| ![Sök](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Search_18_N.svg) | Använd sökfältet för att söka efter mappar, Workspace-projekt eller mobila styrkort. |
| Visa mappar och projekt | Välj om du vill visa mappstrukturen för projekt. Mer information finns i [Om mappar i Analytics](/help/analyze/analysis-workspace/build-workspace-project/workspace-folders/about-folders.md). |
| ![Anpassa tabell](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ColumnSettings_18_N.svg) | Med den här ikonen kan du anpassa kolumnerna som visas för varje projekt i projektlistan. |

I projektlistan kan följande kolumner visas:

| Kolumn | Beskrivning |
|---|---|
| [!UICONTROL Name] | Namn på Workspace-projektet. Välj ![Info](https://spectrum.adobe.com/static/icons/workflow_18/Smock_InfoOutline_18_N.svg) om du vill visa ett popup-fönster med mer information om ett projekt eller en mapp. Välj ![Mer](https://spectrum.adobe.com/static/icons/workflow_18/Smock_More_18_N.svg) om du vill visa tillgängliga åtgärder. Mer information finns i [Hantera projekt](#manage-projects). |
| [!UICONTROL Type] | Anger om posten är ett Workspace-projekt, en mapp eller ett [Mobile-styrkort](https://experienceleague.adobe.com/en/docs/analytics/analyze/mobapp/home). |
| [!UICONTROL Tags] | Taggar som tillämpades på projektet. |
| [!UICONTROL Scheduled] | Anger om projekt har schemalagts att skickas med e-post till mottagare. Se [Schemalägg projekt](/help/analyze/analysis-workspace/curate-share/t-schedule-report.md). |
| Delad länk (alla) | Projekt kan delas med alla, även med personer som inte har tillgång till Analysis Workspace. I den här kolumnen visas om projekt har delats på det här sättet. Mer information finns i [Dela ett projekt med vem som helst (ingen inloggning krävs)](/help/analyze/analysis-workspace/curate-share/share-projects.md#share-public-link) i [Dela projekt](/help/analyze/analysis-workspace/curate-share/share-projects.md). |
| [Projektroll](https://experienceleague.adobe.com/en/docs/analytics/analyze/analysis-workspace/curate-share/share-projects) | Anger din roll för projektet - ägare, redigera, duplicera, visa. |
| [!UICONTROL Report suite] | Rapportsviten som projektet är kopplat till. |
| [!UICONTROL Owner] | Den person som skapade det här projektet (antingen du eller någon som delade projektet med dig). |
| [!UICONTROL Shared with] | Användare som projektet har delats med. |
| [!UICONTROL Last Modified] | Datum och tid när projektet senast ändrades. |
| [!UICONTROL Last Opened] | Datum och tid när projektet senast öppnades. |
| [!UICONTROL Last Used] | Datum och tid då projektet senast användes. |
| [!UICONTROL Project ID] | ID för projektet. |
| [!UICONTROL Longest Date Range] | Det längsta datumintervallet för projektet. |
| [!UICONTROL Number of Queries] | Det totala antalet frågor i projektet. |
| [!UICONTROL Location] | Mappen där projektet finns. |

### Hantera projekt

Om du vill hantera projekt väljer du ett eller flera projekt i projektlistan.

I det blå åtgärdsfältet kan du välja följande åtgärder:

| Åtgärd | Beskrivning |
|---|---|
| ![Ta bort](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Delete_18_N.svg) Ta bort | När du väljer det här alternativet uppmanas du att bekräfta borttagningen av ett Workspace-projekt eller ett Mobile-styrkort. Bekräfta genom att välja **[!UICONTROL OK]**. |
| ![Dela](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Share_18_N.svg) Dela | Med den här åtgärden kan du dela ditt projekt. Se [Dela projekt](../curate-share/share-projects.md). |
| ![Byt namn](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) Byt namn | Öppnar en dialogruta för **[!UICONTROL Rename: *namn *]**där du kan byta namn på projektet. Välj **[!UICONTROL Save]**om du vill spara det nya namnet för projektet. |
| ![Kopiera](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Copy_18_N.svg) Kopiera | Kopierar omedelbart det markerade projektet till ett nytt projekt med namnet *ursprungligt namn* (kopia). |
| ![Fäst](https://spectrum.adobe.com/static/icons/workflow_18/Smock_PinOff_18_N.svg) | Fäster projektet direkt överst i listan. Lägger till indikatorn ![Fäst](https://spectrum.adobe.com/static/icons/workflow_18/Smock_PinOff_18_N.svg). |
| ![Tagg](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Label_18_N.svg) | Öppnar dialogrutan **[!UICONTROL Tag Project]**. Du kan markera en befintlig tagg eller lägga till nya taggar. Välj **[!UICONTROL Save]** om du vill spara taggarna för projektet. |
| ![(Un-)Godkänn ](https://spectrum.adobe.com/static/icons/workflow_18/Smock_CheckmarkCircle_18_N.svg) Godkänn eller Avgodkänn | Godkänner eller avgodkänner projektet. |
| ![Exportera CSV](https://spectrum.adobe.com/static/icons/workflow_18/Smock_FileCSV_18_N.svg) Exportera CSV | Hämtar omedelbart en fil som innehåller en kommaavgränsad värdelista över projekten. |
| ![Flytta till](https://spectrum.adobe.com/static/icons/workflow_18/Smock_FolderAddTo_18_N.svg) Flytta till | Med den här åtgärden kan du flytta projektet till en mapp. I dialogrutan **[!UICONTROL Select Folder]** väljer du en mapp i listan **[!UICONTROL Folder]** och sedan **[!UICONTROL Move]**. |


## Menyrad {#menu-bar}

I ett projekt innehåller menyn alternativ för att hantera ditt projekt, lägga till komponenter, söka efter hjälp och mycket mer. Du kan även komma åt de olika menyalternativen via [kortkommandon](https://experienceleague.adobe.com/en/docs/analytics/analyze/analysis-workspace/build-workspace-project/fa-shortcut-keys).


| Menyalternativ | Beskrivning |
|---|---|
| Projekt | Den här menyn innehåller vanliga åtgärder för projekthantering, bland annat Ny, Öppna, Spara som och [Spara som företagsrapport](/help/analyze/analysis-workspace/build-workspace-project/starter-projects.md). Du kan även uppdatera hela projektet för att hämta de senaste data och definitionerna genom att klicka på Uppdatera projekt. Med alternativen för [Hämta CSV och PDF](https://experienceleague.adobe.com/en/docs/analytics/analyze/analysis-workspace/curate-share/download-send) kan du exportera data från Workspace. [Projektinformation och inställningar](https://experienceleague.adobe.com/en/docs/analytics/analyze/analysis-workspace/build-workspace-project/freeform-overview) innehåller många alternativ för att hantera ditt projekt. |
| Redigera | Ångra eller gör om den senaste åtgärden. Rensa alla återställer projektet till en tom startpunkt. |
| Infoga | Infoga nya paneler eller visualiseringar från den här menyn. Du kan även infoga nya paneler och visualiseringar från den vänstra listen. |
| [Komponenter](https://experienceleague.adobe.com/en/docs/analytics/analyze/analysis-workspace/components/analysis-workspace-components) | Skapa nya segment, beräknade värden, datumintervall eller aviseringskomponenter från projektet. Du kan också skapa nya komponenter från den vänstra listen. Om komponentdefinitionerna nyligen har ändrats hämtar Uppdatera komponenter de senaste definitionerna. |
| [Dela](https://experienceleague.adobe.com/en/docs/analytics/analyze/analysis-workspace/curate-share/send-schedule-files) | Kuratera, dela och schemalägg PDF/CSV-projekt till mottagare i organisationen. |
| Hjälp | Få tillgång till hjälpdokumentation, videoklipp och Analytics [Experience League-communityn](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics/ct-p/adobe-analytics-community). Hantera synligheten för Workspace-tips och [felsökaren](https://developer.adobe.com/analytics-apis/docs/2.0/). Hitta information om Workspace och faktorer som påverkar projektet [prestanda](https://experienceleague.adobe.com/en/docs/analytics/analyze/analysis-workspace/workspace-faq/optimizing-performance). |
| Dela-knapp eller ägare | Om du arbetar i en egen eller Redigera för projektet ger knappen Dela i det övre högra hörnet tillgång till ett klick för att hantera projektmottagarna. Om du har en duplicerad roll eller en vy-roll för projektet visas projektägarens namn. |

### Projektinformation och inställningar {#info-settings}

**[!UICONTROL Workspace]** > **[!UICONTROL Project]** > **[!UICONTROL Project Info & settings]** innehåller information på projektnivå om det aktuella projektet.

![Projektinformation](assets/projectinfo.png)

Inställningarna inkluderar:

| Inställning | Beskrivning |
|---|---|
| Projektnamn | Namnet på projektet. Du kan dubbelklicka på namnet för att redigera det. |
| Ägare | Projektägarnamn |
| Senast ändrad | Datum för senaste ändring av projektet. |
| Taggar | Visar alla taggar som har använts i ett projekt för enklare kategorisering. |
| Beskrivning | En beskrivning är användbar för att förtydliga syftet med ett projekt. Du kan dubbelklicka på beskrivningen för att redigera den. |
| Antal upprepande instanser | Anger om upprepade instanser räknas i rapporter. Den här inställningen (när den är aktiverad) hanterar flera på varandra följande sidvyer till samma sida som flera sidvyer. När du avaktiverar det räknas de som en enda sidvy (den här inställningen påverkar bara vissa mått, t.ex. enkelsidiga besök). **Obs!**: Den här inställningen gäller inte för visualiseringar av flöde och utfall. |
| [Visa anteckningar](/help/analyze/analysis-workspace/components/annotations/overview.md) | Ange om anteckningar ska visas i projektet eller inte. |
| [Projektfärgpalett](https://experienceleague.adobe.com/en/docs/analytics/analyze/analysis-workspace/build-workspace-project/color-palettes) | Du kan ändra den kategoriska färgpalett som används i Workspace genom att välja bland färdiga paletter som har optimerats för färgblindhet, eller genom att ange en anpassad palett. Den här funktionen påverkar många saker i Workspace, bland annat de flesta visualiseringar. |
| [Visa densitet](https://experienceleague.adobe.com/en/docs/analytics/analyze/analysis-workspace/build-workspace-project/view-density) | Gör att du kan se mer data på skärmen genom att minska den lodräta utfyllnaden av den vänstra listen, frihandstabeller och kohorttabeller. |

## Vänster räl {#left-rail}

I ett projekt finns olika ikoner i den vänstra listen, och de representerar viktiga verktyg för att bygga ditt projekt:

| Ikon | Funktionalitet |
|---|---|
| ![panelikon](https://spectrum.adobe.com/static/icons/workflow_18/Smock_WebPage_18_N.svg) | [Paneler](/help/analyze/analysis-workspace/c-panels/panels.md) |
| ![visualiseringsikon](https://spectrum.adobe.com/static/icons/workflow_18/Smock_GraphBarVertical_18_N.svg) | [Visualiseringar](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md) |
| ![komponentikon](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Curate_18_N.svg) | [Komponenter](/help/analyze/analysis-workspace/components/analysis-workspace-components.md) |
| ![ikon för dataordlista](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Bookmark_18_N.svg) | [Dataordlista](/help/analyze/analysis-workspace/components/data-dictionary/data-dictionary-overview.md) |
| ![verktygsikon](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ViewList_18_N.svg) | [Innehållsförteckning](/help/analyze/analysis-workspace/build-workspace-project/project-table-of-contents.md) |

Komponenter (mått, mått, segment, datumintervall) i den vänstra listen relaterar till den aktiva panelens datavy. En blå ram identifierar den aktiva panelen och den aktiva rapportsviten visas högst upp i komponentspåret.


## Högerklicka på menyn

Här är en video om hur du använder högerklicksmenyn i Analysis Workspace:

>[!VIDEO](https://video.tv.adobe.com/v/23981/?quality=12)

## Projektarbetsyta {#canvas}

Projektarbetsytan är där du sammanför paneler, tabeller, visualiseringar och komponenter för att bygga din analys. Ett projekt kan innehålla många paneler, och varje panel kan innehålla många tabeller och visualiseringar.

Paneler är användbara när du vill ordna dina projekt efter tidsperioder, rapportsviter eller användningsfall för analyser. Den aktiva panelen har en färgad ram runt sig och avgör vilka komponenter som är tillgängliga i den vänstra listen.

Beroende på vilken startpunkt du väljer för dina projekt har du antingen en [friformstabell](https://experienceleague.adobe.com/en/docs/analytics/analyze/analysis-workspace/visualizations/freeform-table/freeform-table) eller en [tom panel](https://experienceleague.adobe.com/en/docs/analytics/analyze/analysis-workspace/panels/blank-panel) på arbetsytan som du vill börja med. Det snabbaste sättet att börja analysera är att markera en eller flera komponenter och helt enkelt dra och släppa dem på arbetsytan i projektet. En datatabell återges automatiskt åt dig. [Lär dig mer](https://experienceleague.adobe.com/en/docs/analytics/analyze/analysis-workspace/visualizations/freeform-table/freeform-table) om de olika alternativen för att skapa en tabell, eller använd den [självstudiekursen](https://experienceleague.adobe.com/en/docs/analytics/analyze/analysis-workspace/home) för mer information om hur du skapar ditt första projekt.

![](assets/canvas.png)
