---
title: Arbeta med segment i Report Builder
description: Lär dig använda segment i Report Builder.
role: User
feature: Report Builder
type: Documentation
solution: Analytics
exl-id: 2691fde0-59c6-45a7-80a5-8e5e221adce2
source-git-commit: c3fe537967473754a3b5fe88c7b383647b2c742e
workflow-type: tm+mt
source-wordcount: '575'
ht-degree: 0%

---

# Arbeta med segment

Du kan tillämpa segment när du skapar ett nytt datablock eller när du väljer **[!UICONTROL Edit data block]** på panelen **[!UICONTROL Commands]**.

## Använda segment i ett datablock

Om du vill tillämpa ett segment på hela datablocket dubbelmarkerar du ett segment eller drar och släpper segment från komponentlistan till segmentavsnittet i tabellen.

## Tillämpa filter på enskilda mätvärden

Så här använder du filter med segment för enskilda mätvärden:

* Dra och släpp ett eller flera segment från **[!UICONTROL Segments]** till ett mätvärde i tabellen.

* Alternativt:

   1. Välj ![MoreSmall](/help/assets/icons/MoreSmall.svg) för ett specifikt mått i rutan **[!UICONTROL Table]** och välj sedan **[!UICONTROL Filter metric]**.

      ![segmentflik som visar mått.](./assets/filter-metric.png){zoomable="yes"}

   1. Välj ett eller flera segment i listrutan **[!UICONTROL Segments]**. Segmenten läggs till i listan **[!UICONTROL Segments applied]**.

      ![Segment tillämpade](assets/segments-applied.png)
   1. Välj ![CrossSize75](/help/assets/icons/CrossSize75.svg) om du vill ta bort ett segment från listan **[!UICONTROL Segment applied]**. Eller välj **[!UICONTROL Clear all]** om du vill ta bort alla segment från listan **[!UICONTROL Segment applied]**.
   1. Välj **[!UICONTROL Apply]**.

Om du vill visa använda filter håller du pekaren över eller väljer ett mått i tabellrutan. Mätvärden med tillämpade segment visar en segmentikon.


## Snabbredigeringssegment

Du kan använda panelen **[!UICONTROL Quick edit]** för att lägga till, ta bort eller ersätta segment för befintliga datablock.

När du markerar ett cellintervall i kalkylbladet visas en sammanfattningslista med de segment som används av datablocken i markeringen på länken **[!UICONTROL Segments]** på panelen **[!UICONTROL Quick edit]**.

Så här redigerar du segment med panelen **[!UICONTROL Quick edit]**:

1. Markera ett cellintervall från ett eller flera datablock.

1. Klicka på länken **[!UICONTROL Segments]** för att öppna panelen **[!UICONTROL Quick edit]** **[!UICONTROL Segments]**.


### Lägga till eller ta bort segment

Du kan lägga till eller ta bort segment med alternativen Lägg till/ta bort.

1. Välj fliken **[!UICONTROL Add/Remove]** på panelen **[!UICONTROL Quick edit]** **[!UICONTROL Segments]**.


   1. Välj ett eller flera segment i listrutan **[!UICONTROL Segments]**. Segmenten läggs till i listan **[!UICONTROL Segments applied]**.
   1. Välj ![CrossSize75](/help/assets/icons/CrossSize75.svg) om du vill ta bort ett segment från listan **[!UICONTROL Segment applied]**.
   1. Välj **[!UICONTROL Apply]**.

Report Builder visar ett meddelande som bekräftar de använda segmentändringarna.

### Ersätt segment

Du kan ersätta ett befintligt segment med ett annat segment om du vill ändra hur data segmenteras.

1. Välj fliken **[!UICONTROL Replace]** på panelen **[!UICONTROL Quick edit]** **[!UICONTROL Segments]**.

1. Använd sökfältet **Söklista** för att hitta specifika segment.

1. Markera ett eller flera segment som du vill ersätta.

1. Sök efter ett eller flera segment i listrutan Ersätt med om du vill lägga till segmentet i listan **[!UICONTROL Replace with]**.

1. Välj **[!UICONTROL Apply]**.

Report Builder uppdaterar segmentlistan så att den återspeglar ersättningen.

## Definiera datablocksegment från celler

Datablocken kan referera till segment från en cell. Flera datablock kan referera till samma cell för segment, vilket gör att du enkelt kan byta segment för flera datablock samtidigt.

Så här använder du segment från en cell:

1. [Skapa ett nytt datablock](create-a-data-block.md#create-a-data-block) eller redigera ett befintligt datablock.
1. Välj fliken **[!UICONTROL Segments]** för att definiera segment.
1. Välj ![DataViewSelector](/help/assets/icons/DataViewSelector.svg).

   ![Markera segment i cell](assets/select-segment-from-cell.png){zoomable="yes"}

1. Markera cellen som du vill att datablocken ska referera till ett segment från.

1. Dubbelmarkera om du vill lägga till ett segment i cellen. Du kan också dra och släppa ett eller flera segment i avsnittet **[!UICONTROL Segments included]**.

1. Välj **[!UICONTROL Apply]** om du vill skapa referenscellen.

1. På fliken **Segment** lägger du till det nyligen skapade referenscellsegmentet i ditt datablock.

   ![fliken Segment med segmentet Sheet1!J1(Alla data) som har lagts till i tabellen.](assets/segment-from-cell-applied.png){zoomable="yes"}

1. Välj **[!UICONTROL Finish]**.

Om du vill använda referenscellen som ett segment i andra datablock använder du cellreferensen som ett av segmenten i listan **[!UICONTROL Segments]** på fliken **[!UICONTROL Table]**.

### Använd en referenscell för att ändra datablocksegment

1. Markera referenscellen i kalkylbladet.

1. Markera länken under **[!UICONTROL Segments from cell]** på menyn **[!UICONTROL Quick Edit]**.

   ![segment från cellänk som visar Sheet1!J1 (alla data)](assets/select-segment-from-cell-in-sheet.png){zoomable="yes"}

1. Välj segmentet i listrutan.

1. Välj **[!UICONTROL Apply]**.

<!--
You can apply segments when you create a new data block or when you select the **Edit data block** option from the COMMANDS panel.

## Apply segments to a data block

To apply a segment to the entire data block, double-click a segment or drag and drop filters from the components list into the Segments section of the Table.

## Apply segments to individual metrics

To apply segments to individual metrics, drag and drop a segment onto a metric in the table. You can also click the **...** icon to the right of a metric in the Table pane and then select **[!UICONTROL Segment metric]**. To view applied segments, hover over or select a metric in the Table pane. Metrics with applied segments display a filter icon.

![Segments tab displaying metrics.](./assets/filter_by.png)

## Quick edit segments

You can use the Quick edit panel to add, remove, or replace segments for existing data blocks.

When you select a range of cells in the spreadsheet, the **[!UICONTROL Segments]** link in the Quick edit panel displays a summary list of the segments used by the data blocks in that selection.

To edit segments using the Quick edit panel

1. Select a range of cells from one or multiple data blocks.

    ![Quick Edit segment panel showing segment options for report suites, date range, and segments.](./assets/select_multiple_dbs.png)

1. Click the link underneath **[!UICONTROL Segments]** to launch the Quick edit - Filters panel.

    ![the Segments panel showing the Add Segments field and Segments Applied lists.](./assets/quick_edit_filters.png)

### Add or remove a segment

You can add or remove segments using the Add/Remove options.

1. Select the **[!UICONTROL Add/Remove]** tab in the Quick edit-segments panel.

    All segments applied to the selected data blocks are listed in the Quick Edit-segments panel. Segments applied to all data blocks in the selection are listed under the **[!UICONTROL Applied to all selected data blocks]** heading. Segments applied to some but not all data blocks are listed under the **[!UICONTROL Applied to 1 or more selected data blocks]** heading.

    When multiple segments are present in the selected data blocks, you can search for specific segments using the **[!UICONTROL Add Filter]** search field.

    ![The Add Segments field.](./assets/add_filter.png)

1. Add segments by selecting segments from the **[!UICONTROL Add segment]** drop down menu.

    The list of searchable segments includes all segments accessible to the report suites that are present in one or more of the selected data blocks as well as all the segments that are available globally in the organization.

    Adding a segment applies the segment to all data blocks in the selection.

1. To remove segments, click the delete icon **x** to the right of segments in the **[!UICONTROL Segments applied]** list.

1. Click **[!UICONTROL Apply]** to save changes and return to the hub panel.

    Report Builder displays a message to confirm the applied segment changes.

### Replace a segment

You can replace an existing segment with another segment to change how the data is segmented.

1. Select the **[!UICONTROL Replace]** tab in the Quick edit-segment panel.

    ![Select the Replace tab.](./assets/replace_filter.png)

1. Use the **[!UICONTROL Search list]** search field to locate specific segments.

1. Choose one or more segments that you want to replace.

1. Search for one or more segments in the Replace with field.

    Selecting a filter adds it to the **[!UICONTROL Replace with]**... list.

1. Click **[!UICONTROL Apply]**.

    Report Builder updates the list of segments to reflect the replacement.

### Define data block segments from cell

Data blocks can reference segments from a cell. Multiple data blocks can reference the same cell for segments, allowing you to easily switch segments for multiple data blocks at a time.

To apply segments from a cell

1. Navigate to Step 2 in either the data block creation or editing process. See [Create a Data Block](./create-a-data-block.md).
1. Click the **[!UICONTROL Segments]** tab to define filters.
1. Click **[!UICONTROL Create segment from cell]**.

    ![Create segment from cell icon.](./assets/create-filter-from-cell.png)

1. Select the cell from which you want the data blocks to reference a segment.
   
1. Add the segment choice you wish to add to the cell by either double clicking the segment, or by dragging and dropping it into the **[!UICONTROL Segments Included]** section. 
   
   Note: Only one choice may be selected for the given cell at one time.

    ![The Add segment from cell window showing the Filters included.](./assets/select-filters.png)

1. Click **[!UICONTROL Apply]** to create the reference cell.

1. From the **[!UICONTROL Segments]** tab, add the newly created reference cell segments to your data block.

    ![Segments tab showing Sheet1!J1(All Data) segment added to the table.](./assets/reference-cell-filter.png)

1. Click **[!UICONTROL Finish]**.

    Now this cell can be referenced by other data blocks in their segments. To apply the reference cell as a segment to other data blocks, simply add the cell reference to their segments from the Segments tab. 

#### Use the reference cell to change data block segments

1. Select the reference cell in your spreadsheet.

1. Click the link under **[!UICONTROL Segments from Cell]** in the Quick Edit menu.

    ![Segments from cell link showing Sheet1!J1 (All Data)](./assets/filters-from-cell-link.png)

1. Select your segment from the drop-down menu.

    ![Segments drop down menu](./assets/filter-drop-down.png)

1. Click **[!UICONTROL Apply]**.
-->