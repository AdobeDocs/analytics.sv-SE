---
description: Beskriver stegen som ingår i att tillämpa filter på en utfallsrapport.
title: Filtrera en utfallsrapport med frågeguiden
feature: Report Builder
role: User, Admin
exl-id: 6134d7d4-7287-4a83-92b6-d250ca15cf69
source-git-commit: 1ee50c6a2231795b2ad0015a79e09b7c1c74d850
workflow-type: tm+mt
source-wordcount: '200'
ht-degree: 8%

---

# Filtrera en utfallsrapport med frågeguiden

Beskriver stegen som ingår i att tillämpa filter på en utfallsrapport.

I det här exemplet visas Utfallsrapporten för sidan.

1. I Adobe Report Builder klickar du på **[!UICONTROL Create]** för att öppna begärandeguiden.
1. Välj rätt rapportsvit.
1. I trädvyn till vänster väljer du **[!UICONTROL Paths]** > **[!UICONTROL Page]** > **[!UICONTROL Page Fallout]**.

   ![](assets/page_fallout.png)

1. Konfigurera lämplig [datumintervall](/help/analyze/report-builder/data-requests/configuring-report-dates/custom-calendar.md).
1. Klicka på **[!UICONTROL Next]**.
1. I steg 2 i guiden, under **[!UICONTROL Row Labels]** klickar du på **[!UICONTROL Define Checkpoints]** länk. (I en bortfallsrapport måste du alltid definiera sökvägselement, till skillnad från i en sökvägsrapport, där ett mönster används i förväg.)

   ![](assets/define_checkpoints.png)

1. Välj **[!UICONTROL Filter]** alternativ.

1. I **[!UICONTROL Define Site Section Fallout Checkpoints]** kan du definiera kontrollpunkter från ett cellintervall eller från en lista. Klicka sedan på **[!UICONTROL OK]**.
1. Bestäm om du vill välja från ett cellintervall eller från en lista.
1. Om du väljer från en lista klickar du på **[!UICONTROL Add]** för att markera kontrollpunkter som ska läggas till i utfallssökvägen. Du kan definiera mellan 3 och 8 kontrollpunkter. (Sök efter tillgängliga element genom att klicka på **[!UICONTROL More]**.)

   Mer information om hur du förfinar filtret finns i [Filtrera Dimensioner](/help/analyze/report-builder/layout/c-filter-dimensions/filter-dimensions.md). 1. Flytta **[!UICONTROL Available Elements]** från den vänstra kolumnen till höger genom att markera dem och klicka på den orangefärgade pilen.
1. Klicka **[!UICONTROL OK]** tre gånger och sedan klicka **[!UICONTROL Finish]**.

   Rapporten bör uppdateras nu.
