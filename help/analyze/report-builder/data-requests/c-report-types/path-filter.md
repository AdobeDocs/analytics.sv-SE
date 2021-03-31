---
description: Beskriver stegen som ingår i att tillämpa filter på en målningsrapport.
title: Filtrera en sökvägsrapport med frågeguiden
uuid: 9b22d5b5-7ae8-49a2-90ae-0c1075562bbe
feature: Report Builder
role: Affärsledare, administratör
translation-type: tm+mt
source-git-commit: 894ee7a8f761f7aa2590e06708be82e7ecfa3f6d
workflow-type: tm+mt
source-wordcount: '319'
ht-degree: 6%

---


# Filtrera en sökvägsrapport med frågeguiden

Beskriver stegen som ingår i att tillämpa filter på en målningsrapport.

I det här exemplet används platsavsnittssökvägar.

1. Öppna begärandeguiden genom att klicka på **[!UICONTROL Create]** i Adobe Report Builder.
1. Välj rätt rapportsvit.
1. I trädvyn till vänster väljer du **[!UICONTROL Paths]** > **[!UICONTROL Site Sections]** > **[!UICONTROL Site Section Paths]**.

   ![](assets/site_section_path_1.png)

1. Ange lämpligt datum/datum.
1. Klicka på **[!UICONTROL Next]**.
1. Klicka på länken **[!UICONTROL Top 1-10 (pattern applied)]** under **[!UICONTROL Row Labels]** i steg 2 av guiden. I en banrapport används ett mönster som standard.

   ![](assets/site_section_path_2.png)

1. Välj alternativet **[!UICONTROL Filter]**.

   ![](assets/filter_option.png)

1. I dialogrutan **[!UICONTROL Define 'Site Section Paths' Path Pattern]** kan du ange
   1. den första rapportens inledande rankning.
   1. antalet poster som du vill visa i den här rapporten.
1. Klicka på **[!UICONTROL Edit]** för att definiera ett sökvägsmönster.
1. Om du vill ha ett eget mönster drar och släpper du **[!UICONTROL Pattern Objects]** från listan till vänster i **[!UICONTROL Pattern Build Canvas]** till höger.

   ![](assets/custom_pattern.png)

1. Du kan också välja ett fördefinierat mönster i listrutan **[!UICONTROL Select a Pattern]** och ändra det. Här är de tillgängliga mönstren:

   ![](assets/select_a_pattern.png)

   Vissa av dessa mönster är specifika för Report builder: Inmatningsbanans mönster för nästa objekt, Avsluta banans mönster för föregående objekt, mönstret för nästa objekt.
1. Om du vill redigera ett fördefinierat mönster
   1. Markera den. Välj till exempel **[!UICONTROL Exited Site Pattern]**: ![](assets/exited_site_pattern.png)

   1. Nu bör du definiera sökvägen till webbplatsavsnittet som användaren följer innan han/hon avslutar. Klicka på **[!UICONTROL Specific Item(s): 0 selected]**. Du kan definiera den här sökvägen genom att välja från ett cellintervall (om du redigerar en befintlig begäran) eller genom att välja från en lista med avsnitt.
   1. Om du vill välja från ett cellintervall från en tidigare begäran markerar du **[!UICONTROL From range of cells]** och klickar på cellväljarikonen. Välj sedan cellerna från rapporten. ![](assets/choose_site_section_paths.png)

   1. Om du vill välja från en lista med webbplatsavsnitt väljer du **[!UICONTROL From list]** och klickar på **[!UICONTROL Add]**.
   1. Flytta element från kolumnen **[!UICONTROL Available Elements]** till kolumnen **[!UICONTROL Selected Elements]** genom att markera dem och klicka på den orangefärgade pilen. Klicka på **[!UICONTROL OK]**. ![](assets/move_site_section_elements.png)

   1. Klicka på **[!UICONTROL Save]** om du vill spara mönstret du nyss skapade.
   1. Klicka på **[!UICONTROL OK]** tre gånger och sedan på **[!UICONTROL Finish]**. Den filtrerade sökvägsbegäran genereras nu.
