---
description: Lär dig hur du använder segmenthanteraren för att hantera segment, till exempel dela, filtrera, tagga, godkänna, kopiera, ta bort segment och markera segment som favoriter.
title: Hantera segment
feature: Segmentation
exl-id: be182a55-23cb-415f-a7d0-3c1efeead1a1
source-git-commit: ca84a5f807545d7196e2e0e90d3209c32d3fd789
workflow-type: tm+mt
source-wordcount: '526'
ht-degree: 0%

---

# Hantera segment


Du kan [dela](t-seg-share.md), [segment](t-seg-filter.md), [tagg](seg-tag.md), [godkänna](seg-approve.md), byta namn på, [kopiera](seg-copy.md), ta bort, exportera segment och markera segment som [favorit](t-seg-favorite.md) från ett centralt [!UICONTROL Segment]-hanteringsgränssnitt. Så här hanterar du segment:

* Välj **[!UICONTROL Components]** i huvudgränssnittet och välj sedan **[!UICONTROL Segments]**.


>[!NOTE]
>
>Snabbsegmenten som du skapar i ett visst Workspace-projekt visas inte i hanteraren för [!UICONTROL Segment], såvida du inte har gjort segmentet tillgängligt för alla dina projekt.
>

## Segmenthanterare

Segmenthanteraren har följande gränssnittselement:

![Segmentgränssnitt](assets/segments-manager.png)

### Segmentlista

Segmentlistan ➊ visar alla segment som du äger, de segment som har omfattats av alla dina projekt och de segment som har delats med dig. Listan innehåller följande kolumner:

| Kolumn | Beskrivning |
| --- | --- |
| ![StarOutline](/help/assets/icons/StarOutline.svg) | Välj om du vill gynna ![Star](/help/assets/icons/Star.svg) eller ![StarOutline](/help/assets/icons/StarOutline.svg) ett segment. Se [Markera segment som favorit](t-seg-favorite.md) |
| **[!UICONTROL Title and description]** | Om du vill redigera segmentet markerar du titellänken, som öppnar [segmentverktyget](seg-build.md). Ett delat segment anges med ![Dela](/help/assets/icons/ShareAlt.svg). |
| **[!UICONTROL Report suitew]** | Rapportsviten som det här segmentet gäller för. |
| **[!UICONTROL Owner]** | Segmentets ägare. Som användare ser du bara de segment som du äger eller de anteckningar som delas med dig. |
| **[!UICONTROL Tags]** | Taggarna för detta segment. |
| **[!UICONTROL Shared with]** | Hur många individer eller grupper du har delat segmentet med. Välj det här alternativet om du vill öppna dialogrutan **[!UICONTROL Share Component]**. Mer information finns i [Dela segment](t-seg-share.md). |
| **[!UICONTROL Published]** | Anger om [segmentet publiceras](seg-publish.md) till Experience Cloud. |
| **[!UICONTROL Date modified]** | Datum och tid då segmentet senast ändrades. |

Använd ![ColumnSetting](/help/assets/icons/ColumnSetting.svg) för att ange vilka kolumner du vill visa.

### Åtgärdsfält

Du kan vidta åtgärder för segment med åtgärdsfältet ➋. Åtgärdsfältet innehåller följande åtgärder:

| Åtgärd | Beskrivning |
|---|---|
| ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL Add]** | Lägg till ett annat segment med hjälp av [segmentverktyget](seg-build.md). |
| ![Sök](/help/assets/icons/Search.svg) [!UICONTROL *Sök efter titel*] | Om inget segment är markerat i listan söker du efter segment med det här sökfältet. |
| ![Etikett](/help/assets/icons/Label.svg) **[!UICONTROL Tag]** | Tagga de markerade segmenten. I dialogrutan **[!UICONTROL Tag Segment]** markerar eller avmarkerar du taggarna för de markerade segmenten. Välj **[!UICONTROL Save]** om du vill spara taggarna för de valda segmenten. Mer information finns i [Tagga segment](seg-tag.md). |
| ![Dela](/help/assets/icons/ShareAlt.svg) **[!UICONTROL Share]** | Dela de markerade segmenten. I dialogrutan **[!UICONTROL Share Segment]** kan du ![&#x200B; söka &#x200B;](/help/assets/icons/Search.svg) *söka efter enskilda personer eller grupper* eller välja **[!UICONTROL Organization]** eller **[!UICONTROL Groups]**. Välj **[!UICONTROL Save]** om du vill spara delningsinformation för de valda segmenten. Mer information finns i [Dela segment](t-seg-share.md). |
| ![Ta bort](/help/assets/icons/Delete.svg) **[!UICONTROL Delete]** | Ta bort markerade segment. Du uppmanas att bekräfta åtgärden. |
| ![Redigera](/help/assets/icons/Edit.svg) **[!UICONTROL Rename]** | Byt namn på ett enskilt markerat segment. När du har markerat det här alternativet kan du byta namn på segmentet. |
| ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) **[!UICONTROL Approve]** | Godkänn de markerade segmenten. Mer information finns i [Godkänn segment](seg-approve.md). |
| ![Kopiera](/help/assets/icons/Copy.svg) **[!UICONTROL Copy]** | Kopiera det markerade segmentet. Nya segment skapas med samma namn och suffix `(Copy)`. |
| ![FileCSV](/help/assets/icons/FileCSV.svg) **[!UICONTROL Export to CSV]** | Exportera segmenten till en `Segments List.csv`-fil. |

### Aktivt filterfält

Filterfältet ➌ visar de aktiva segment som används från filterpanelen till listan med segment (om det finns några). Du kan snabbt ta bort ett filter med ![CrossSize75](/help/assets/icons/CrossSize75.svg). Om fler än ett filter har angetts kan du ta bort alla filter med **[!UICONTROL Remove all]**.

### Panelen Filter

Du kan filtrera listan med segment med hjälp av den vänstra panelen ![Filter](/help/assets/icons/Filter.svg) **[!UICONTROL Filter]** ➍ . Filterpanelen visar typen av filter och antalet segment som använder det specifika filtret. Välj ![Filter](/help/assets/icons/Filter.svg) för att växla visningen av panelen Filter.

Mer information finns i [Filtrera listan med segment](t-seg-filter.md).


<!--

The Segment manager offers many ways of curating segments, such as sharing, filtering, tagging, approving, copying, deleting, and marking as favorites.

The Analytics Segment manager shows you all the segments you own and that have been shared with you. Admin-level users can see all segments in the organization. This overview presents the user interface and the capabilities of the Segment manager. 

![Segments manager](assets/segments-manager.png)

## Access the Segment manager

1. In Adobe Analytics, select the **[!UICONTROL Components]** tab, then select **[!UICONTROL Segments]**.

   Or 

   In an existing report, select the Segments icon ![](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Segmentation_18_N.svg) in the left navigation, then select **[!UICONTROL Manage]**.

## Available actions in the Segment manager

In the Segment manager, you can:

* [Filter segments](/help/components/segmentation/segmentation-workflow/t-seg-filter.md)

* [Mark segments as favorites](/help/components/segmentation/segmentation-workflow/t-seg-favorite.md)

* [Approve segments](/help/components/segmentation/segmentation-workflow/seg-approve.md)

* [Tag segments](/help/components/segmentation/segmentation-workflow/seg-tag.md)

* [Share segments](/help/components/segmentation/segmentation-workflow/t-seg-share.md)

* Export a segment to a CSV file.

* [Copy segments](/help/components/segmentation/segmentation-workflow/seg-copy.md)

* [Delete segments](/help/components/segmentation/segmentation-workflow/seg-delete.md)

## Configure columns

You can configure the information displayed for each segment in the Segment manager by configuring the columns that are displayed.

To configure the visible columns in the Segment manager:

1. In Adobe Analytics, select the **[!UICONTROL Components]** tab, then select **[!UICONTROL Segments]**. 

1. In the Segment manager, select the **Customize columns** icon ![Customize columns icon](assets/customize-columns-icon.png), then select the columns that you want to be displayed in the Segment manager.

   The following columns are available:

   | Column title | Description  |
   |---|---|
   | Title and description | These values are provided in the Segment builder. To edit the title and description, select the title link to open the Segment builder.  |
   | Favorites  | Displays star icons next to each segment, allowing you to mark segments as favorites. For more information, see [Mark segments as favorites](/help/components/segmentation/segmentation-workflow/t-seg-favorite.md). |
   | Report suites  | This column indicates in which report suite the segment was last saved.  |
   | Owner  | Indicates who owns the segment. As a non-Admin, you can see only segments you own or those that were shared with you.  |
   | Tags (not checked in column selector, hence column not appearing)  | Tags that were applied to the segment, either by you or by people who shared the segment with you.  |
   | Shared with  | Lists individuals or groups (Admin only) or All (Admin only) that you shared the segment with. <p>When a segment is being shared by you or with you, a share icon displays next to the segment name.</p>|
   | Date modified  | Shows the date that the segment was last modified.  |
   | Used in | Shows where segments are currently being used, and how many times they are being used in each area. <p>For example, if the segment is being used in 40 projects and 2 alerts, then the value of this column shows as [!UICONTROL **42 components**].</p> <p>Select the value in this column to see the breakdown of where the segments are being used (for example, [!UICONTROL **Projects (40)**], [!UICONTROL **Alerts (2)**]). Furthermore, you can view the list of items where the segments are being used. For example, so see the list of projects where they are being used, select the [!UICONTROL **Projects (40)**] link.</p><p>Each of the following areas shows the number of instances of segments being used in that area:</p>  <ul><li>[!UICONTROL **Projects**]<p>Contains segments that were [created in the segment builder](/help/components/segmentation/segmentation-workflow/seg-build.md) and are available for all projects.</p></li><li>[!UICONTROL **Ad hoc components**]<p>Contains segments that were [created as quick segments](/help/analyze/analysis-workspace/components/segments/quick-segments.md) and are available only within a single project.</p></li><li>[!UICONTROL **Scheduled projects**]</li><li>[!UICONTROL **Mobile Scorecards**]</li><li>[!UICONTROL **Annotations**]</li><li>[!UICONTROL **Alerts**]</li><li>[!UICONTROL **Calculated metrics**]</li><li>[!UICONTROL **Report Builder**]<p>Selecting this option downloads a CSV file, with the following columns of data:</p><ul><li>Report Builder Name</li><li>Last accessed</li><li>Last accessed IMS User ID</li><li>Last accessed user name</li></ul><p>When viewing information for Report Builder, usage information is available starting in September 2024.</p></li></ul><p>This information can help you determine whether a component is valuable to users in your organization, where it is used, and if it needs to be deleted or modified.</p><p>Consider the following when viewing this column:</p><ul><li>This information is available only to system administrators.</li><li>The [!UICONTROL **Used in**] column does not display by default. [Configure columns](#configure-columns) to display it.</li><li>If a segment includes another segment in its definition, any use of that segment is not shown in the [!UICONTROL **Used in**] column. If a segment is included in the definition of another type of component (such as a calculated metric), then usage is shown in the [!UICONTROL **Used in**] column.</li><li>This information does not include usage from the API or Data Warehouse.</li><li>If there is no data in this column for a given component but it has a [!UICONTROL **Last used**] date, the component might have been used in an analysis without being saved.</li><li>Usage information is available starting in September 2023.</li></ul><p>You can use the [Data Dictionary](/help/analyze/analysis-workspace/components/data-dictionary/data-dictionary-overview.md) along with this information to help you keep track of and better understand how components are being used in your organization.</p>  |
   | Last used | Shows the date when the segment was last used in any of the following component types: <ul><li>Alerts</li><li>Calculated metrics</li><li>Projects</li><li>Scheduled projects</li><li>Segments</li></ul> <p>This information can help you determine whether a component is valuable to users in your organization, where it is used, and if it needs to be deleted or modified.</p><p>Consider the following when viewing this column:</p><ul><li>This information does not include usage from the API, Report Builder, or Data Warehouse.</li><li>For some components, this column might not contain data if the component was last used prior to September 2023.</li><li>This information is available only to system administrators.</li></ul><p>You can use the [Data Dictionary](/help/analyze/analysis-workspace/components/data-dictionary/data-dictionary-overview.md) along with this information to help you keep track of and better understand how components are being used in your organization. |
   
   {style="table-layout:auto"}

## How-To Video {#section_B3C5DA22DC5248DBA17C56E03DA2D4F2}

This [Adobe Analytics video](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/components/segmentation/segment-management-and-sharing.html) gives a short overview of how to use the Segment manager.

-->