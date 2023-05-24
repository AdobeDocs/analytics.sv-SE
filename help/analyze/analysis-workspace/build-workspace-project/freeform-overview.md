---
description: Lär dig grunderna i hur du arbetar i ett Workspace-projekt.
keywords: Analysis Workspace
title: Översikt över projekt
feature: Workspace Basics
role: User, Admin
exl-id: 75c551de-297e-4c45-95e6-77472be6628a
source-git-commit: 602f837689186f232c4c0f8baebbcf911446bc99
workflow-type: tm+mt
source-wordcount: '1523'
ht-degree: 2%

---

# Översikt över projekt

Med arbetsyteprojekt kan du kombinera datakomponenter, tabeller och visualiseringar för att skapa analyser och dela dem med vem som helst i organisationen. Innan du startar ditt första projekt bör du lära dig hur du får tillgång till, navigerar och hanterar dina projekt.

Här är en video om hur du skapar ett Workspace-projekt:

>[!VIDEO](https://video.tv.adobe.com/v/334076/?quality=12)

## Projektlista {#project-list}

När du först besöker **[!UICONTROL Analytics]** > **[!UICONTROL Workspace]** visas alla projekt som du äger eller har delat med dig. Detta är också landningssidan för Adobe Analytics, såvida du inte tidigare har angett en anpassad landningssida.

![](assets/sample-project.png)

Sidan Projekt innehåller följande information:

>[!NOTE]
>
>Vissa kolumner visas inte som standard. Om du vill anpassa kolumnerna som visas klickar du på **Anpassa tabell** icon ![Anpassa tabell](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ColumnSettings_18_N.svg).


| Element | Beskrivning |
|---|---|
| [Redigera inställningar](/help/analyze/analysis-workspace/user-preferences.md) | Hantera inställningar för Analysis Workspace och dess tillhörande komponenter för alla nya projekt eller paneler som du skapar. |
| [Skapa mapp](/help/analyze/analysis-workspace/build-workspace-project/workspace-folders/create-folders.md) | Lägg till en ny mapp eller undermapp i listan över projekt och mappar. |
| [Skapa projekt](/help/analyze/analysis-workspace/build-workspace-project/create-projects.md) | Starta ett nytt projekt från grunden eller från en rapport. |
| Visa mer | Visar alternativ för att skapa ett tomt projekt eller ett mobilstyrkort, [visa självstudiekurser](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/analysis-workspace-basics/analysis-workspace-introduction.html), eller [visa versionsinformation](/help/release-notes/latest.md). |
| Visa mappar och projekt | Välj om du vill visa mappstrukturen för projekt. Mer information finns i [Om mappar i Analytics](/help/analyze/analysis-workspace/build-workspace-project/workspace-folders/about-folders.md). |
| Anpassa tabell (ikon) | Här kan du anpassa informationen som visas för varje projekt på sidan Projekt. |
| Namn | Namn på Workspace-projektet. |
| Typ | Anger om det här är ett arbetsyteprojekt, en mapp eller en [Mobile Scorecard](https://experienceleague.adobe.com/docs/analytics/analyze/mobapp/home.html). |
| Taggar | Taggar som tillämpades på projektet. |
| Schemalagd | Anger om projekt har schemalagts att skickas med e-post till mottagare enligt ett schema. Se [Schemalägg projekt](/help/analyze/analysis-workspace/curate-share/t-schedule-report.md). |
| Delad länk (alla) | Projekt kan delas med vem som helst - även med personer som inte har tillgång till Analysis Workspace. I den här kolumnen visas om projekt har delats på det här sättet. Se [Dela ett projekt med vem som helst (ingen inloggning krävs)](/help/analyze/analysis-workspace/curate-share/share-projects.md#share-public-link) in [Dela projekt](/help/analyze/analysis-workspace/curate-share/share-projects.md) för mer information. |
| Rapportsvit | Rapportsviten som projektet är kopplat till. |
| [Projektroll](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/share-projects.html) | Anger din roll för projektet - ägare, redigera, duplicera, visa. |
| Ägare | Den person som skapade det här projektet (antingen du eller någon som delade projektet med dig). |
| Delas med | Användare som projektet har delats med. |
| Senast ändrad | Datum och tid när projektet senast ändrades. |
| Senast öppnad | Datum och tid när projektet senast öppnades. |
| Projekt-ID | ID för projektet. |
| Senaste datumintervall | Det längsta datumintervallet för projektet. |
| Antal frågor | Det totala antalet frågor i projektet. |
| Plats | Mappen där projektet finns. |

## Menyrad {#menu-bar}

I ett projekt innehåller menyn alternativ för att hantera ditt projekt, lägga till komponenter, söka efter hjälp och mycket mer. Alla menyalternativ kan också nås via tangentbordet [genvägar](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/fa-shortcut-keys.html).

![](assets/menu.png)

| Menyalternativ | Beskrivning |
|---|---|
| Projekt | Innehåller vanliga åtgärder för projekthantering, inklusive Nytt, Öppna, Spara som och [Spara som företagsrapport](/help/analyze/analysis-workspace/build-workspace-project/starter-projects.md). Du kan även uppdatera hela projektet för att hämta de senaste data och definitionerna genom att klicka på Uppdatera projekt. [Hämta CSV och PDF](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/download-send.html) kan du exportera data från arbetsytan. [Projektinformation och inställningar](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/freeform-overview.html?#info-settings) har många alternativ för att hantera ditt projekt. |
| Redigera | Ångra eller gör om den senaste åtgärden. Rensa alla återställer projektet till en tom startpunkt. |
| Infoga | Infoga nya paneler eller visualiseringar från den här menyn. Du kan även infoga nya paneler och visualiseringar från den vänstra listen. |
| [Komponenter](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/components/analysis-workspace-components.html) | Skapa nya segment, beräknade värden, datumintervall eller aviseringskomponenter från projektet. Du kan också skapa nya komponenter från den vänstra listen. Om komponentdefinitionerna nyligen har ändrats hämtas de senaste definitionerna av Uppdatera komponenter. |
| [Dela](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/send-schedule-files.html) | Kuratera, dela och schemalägg PDF/CSV-projekt till mottagare i organisationen. |
| Hjälp om  | Få tillgång till hjälpdokumentation, videor och analyser [Experience League community](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics/ct-p/adobe-analytics-community). Hantera synligheten för arbetsytetips och [debugger](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/reporting-tricks.md). Hitta information om arbetsytan och faktorer som påverkar projektet [prestanda](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/workspace-faq/optimizing-performance.html). |
| Dela-knapp eller ägare | Om du är i en egen eller Redigera för projektet ger knappen Dela i det övre högra hörnet tillgång till ett klick för att hantera projektmottagarna. Om du har en dubblett- eller vyroll för projektet visas projektägarens namn. |

### Projektinformation och inställningar {#info-settings}

**[!UICONTROL Workspace]** > **[!UICONTROL Project]** > **[!UICONTROL Project Info & Settings]** innehåller information på projektnivå om det aktiva projektet.

![](assets/projectinfo.png)

Inställningarna inkluderar:

| Inställning | Beskrivning |
|---|---|
| Projektnamn | Namnet på projektet. Du kan dubbelklicka på namnet för att redigera det. |
| Skapad av | Projektägarnamn |
| Senast ändrad | Datum för senaste ändring av projektet. |
| Taggar | Visar alla taggar som har använts i ett projekt för enklare kategorisering. |
| Beskrivning | En beskrivning är användbar för att förtydliga syftet med ett projekt. Du kan dubbelklicka på beskrivningen för att redigera den. |
| Räkna upprepade instanser i projekt | Anger om upprepade instanser räknas i rapporter. Den här inställningen (när den är aktiverad) hanterar flera på varandra följande sidvyer till samma sida som flera sidvyer. När du avaktiverar det räknas de som en enda sidvy (detta påverkar bara vissa mått, t.ex. enkelsidiga besök). **Anteckning**: Den här inställningen gäller inte för Flow- eller Fallout-visualiseringar. |
| [Projektets färgpalett](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/color-palettes.html) | Du kan ändra den kategoriserade färgpaletten som används i Workspace genom att välja bland färdiga paletter som har optimerats för färgblindhet, eller genom att ange en anpassad palett. Den här funktionen påverkar många saker i Workspace, bland annat de flesta visualiseringar. |
| [Visa densitet](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/view-density.html) | Gör att du kan se mer data på skärmen genom att minska den lodräta utfyllnaden av den vänstra listen, frihandstabeller och kohorttabeller. |

## Vänster räl {#left-rail}

Inom ett projekt [paneler](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/panels.html), tabeller, [visualiseringar](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.html)och [komponenter](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/components/analysis-workspace-components.html) är åtkomliga från den vänstra listen. Detta är era projektbyggstenar.

Du kan även komma åt visualiseringar och paneler via [Tom panel](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/blank-panel.html) också.

Komponenter (Dimensioner, Metrisk, Segment, Datumintervall) i det vänstra fältet relaterar till rapportsviten för den aktiva panelen. Den aktiva panelen har en blå ram runt sig och den aktiva rapportsviten visas högst upp i komponentspåret.

![](assets/left-rail.png)

## Högerklicka på menyn

Här är en video om hur du använder högerklicksmenyn i Analysis Workspace:

>[!VIDEO](https://video.tv.adobe.com/v/23981/?quality=12)

## Projektarbetsyta {#canvas}

Projektarbetsytan är där du sammanför paneler, tabeller, visualiseringar och komponenter för att bygga din analys. Ett projekt kan innehålla många paneler, och varje panel kan innehålla många tabeller och visualiseringar.

Paneler är användbara när du vill ordna dina projekt efter tidsperioder, rapportsviter eller användningsfall för analyser. Den aktiva panelen har en blå ram runt sig och avgör vilka komponenter som är tillgängliga i den vänstra listen.

Beroende på vilken startpunkt du väljer för dina projekt har du antingen en [frihandsritbord](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/freeform-table/freeform-table.html) eller en [tom panel](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/blank-panel.html) på arbetsytan till att börja med. Det snabbaste sättet att börja analysera är att markera en eller flera komponenter och helt enkelt dra och släppa dem på arbetsytan i projektet. En datatabell återges automatiskt åt dig. [Läs mer](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/freeform-table/freeform-table.html) om de olika alternativen för att skapa en tabell eller utnyttja [självstudiekurs](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?#training-tutorial) för mer vägledning om hur du skapar ditt första projekt.

![](assets/canvas.png)

## Projektledare {#manager}

Analysis Workspace-projekt kan hanteras under **[!UICONTROL Analytics]> [!UICONTROL Components] >[!UICONTROL Projects]**. Projekthanteraren visar de objekt som en viss användare har skapat.

Projektägarskap kan överföras till en ny användare under [!UICONTROL Admin] > [!UICONTROL Analytics Users & Assets] > [!UICONTROL Transfer Assets].

I Projects Manager kan du lägga till, tagga, dela, duplicera/kopiera och mycket mer. Sök efter ett projekt i sökfältet eller med filteralternativen i den vänstra listen. Du kan filtrera efter tagg, ägare, projekttyp med mera.

![](assets/project-manager.png)

Följande är vanliga åtgärder i Projects Manager och kan utföras på ett eller flera projekt samtidigt:

| Åtgärd | Beskrivning |
|---|---|
| Lägg till | Skapa ett nytt projekt från grunden eller börja från ett [rapport](/help/analyze/analysis-workspace/build-workspace-project/starter-projects.md). |
| Tagga eller godkänn | Välj &quot;Tagga&quot; eller &quot;Godkänn&quot; för att ordna dina projekt och göra dem enklare att söka efter. |
| [Dela](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/share-projects.html) | Gör ett projekt tillgängligt för andra Analysis Workspace-användare i organisationen. |
| Ta bort | Ta bort projektet. |
| Byt namn | Redigera namnet på projektet. |
| Kopiera | Skapa en kopia av projektet. Detta skapar ett nytt projekt- och projekt-ID. Alla aktier eller tidsplaner som är knutna till det ursprungliga projektet kopieras inte. |
| Exportera till CSV | Ladda ned projektet som en CSV-fil som innehåller oformaterad text. |
