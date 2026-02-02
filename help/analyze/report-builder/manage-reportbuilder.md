---
title: Hantera datablock i Report Builder
description: Lär dig hur du hanterar datablock i Report Builder.
role: User
feature: Report Builder
type: Documentation
solution: Analytics
exl-id: 63e169b3-7e13-405e-83a4-17f2a9917ed2
source-git-commit: c3fe537967473754a3b5fe88c7b383647b2c742e
workflow-type: tm+mt
source-wordcount: '492'
ht-degree: 0%

---

# Hantera datablock

Du kan visa och hantera alla datablock i en arbetsbok med [!UICONTROL Data block manager]. [!UICONTROL Data block manager] innehåller sök-, filter- och sorteringsfunktioner som gör att du kan hitta specifika datablock. När du har markerat ett eller flera datablock kan du redigera, ta bort eller uppdatera de markerade datablocken.

## Visa datablock

Om du vill visa en tabell med alla datablock i en arbetsbok väljer du ![TableManage](/help/assets/icons/TableManage.svg) **[!UICONTROL Manage]**.

![Hantera-alternativet om du vill visa en lista över alla datablock.](./assets/image53.png){zoomable="yes"}

**[!UICONTROL Data block manager]** visar en tabell med alla datablock i en arbetsbok.

![Listan med alla datablock i en arbetsbok.](./assets/image52.png){zoomable="yes"}

Du kan använda ![ColumnSetting](/help/assets/icons/ColumnSetting.svg) för att välja vilka kolumner du vill visa.

## Sortera datablock

Du kan sortera datablockstabellen efter en kolumn som visas. Du kan till exempel sortera datablock efter rapportsviter, segment, datumintervall och andra variabler.

Om du vill sortera datablockstabellen väljer du en kolumnrubrik. Markera samma kolumnrubrik om du vill kasta om sorteringsordningen.


## Sök i datablock

Använd fältet ![Sök](/help/assets/icons/Search.svg) **[!UICONTROL _Sök_]** för att hitta något i datablockstabellen. Du kan till exempel söka efter mätvärden i datablocken eller rapportsviten. Du kan också söka efter datum i datumintervallet, ändringsdatumet eller sista körningsdatumkolumnen.


## Redigera datablock

Du kan redigera rapportsviter och datumintervall för datablock. Eller segmenten som tillämpas på datablock.

Du kan till exempel ersätta ett befintligt segment med ett nytt segment i ett eller flera datablock.

1. Markera de datablock som du vill uppdatera. Du kan markera kryssrutan på den översta nivån om du vill markera alla datablock, eller markera enskilda datablock.

   ![Ikonen för redigering av penna](./assets/image56.png){zoomable="yes"}

1. Välj ![Redigera](/help/assets/icons/Edit.svg) för att visa fönstret **[!UICONTROL Quick edit]**.

   ![Snabbredigeringsfönstret](./assets/image58.png){zoomable="yes"}

1. Välj en länk för att uppdatera rapportsviter, datumintervall eller segment. I **[!UICONTROL Quick Edit]** - **[!UICONTROL Segments]** kan du lägga till, ta bort eller uppdatera segment för de markerade datablocken.

   ![Fältet Lägg till segment i snabbredigeringsfönstret](./assets/image59.png){zoomable="yes"}

## Uppdatera datablock

Välj ![Uppdatera](/help/assets/icons/Refresh.svg) om du vill uppdatera datablockstabellen.

Kontrollera om ett datablock har uppdaterats genom att visa ikonen för uppdateringsstatus:

- Ett uppdaterat datablock visar ![CheckmarkCircleGreen](/help/assets/icons/CheckmarkCircleGreen.svg).

- Ett datablock som inte kunde uppdateras visar en ![AlertRed](/help/assets/icons/AlertRed.svg).


## Ta bort datablock

Så här tar du bort ett eller flera datablock:

1. Markera ett eller flera datablock.
1. Välj ![Ta bort](/help/assets/icons/Delete.svg).
1. Välj **[!UICONTROL Delete]** i dialogrutan **[!UICONTROL Delete data block]** eller **[!UICONTROL Cancel]** om du vill avbryta borttagningen.

## Gruppera datablock

Du kan gruppera datablock med hjälp av den nedrullningsbara menyn **[!UICONTROL Group by]** eller välja en kolumnrubrik.

Om du vill sortera datablock efter kolumn markerar du kolumnrubriken. Om du vill gruppera datablock efter grupper väljer du ett gruppnamn i listrutan **[!UICONTROL Group by]**. På skärmbilden nedan visas datablock grupperade efter rapportsviten.

Du kan använda gruppering för att snabbt markera datablock som du vill ändra ett vanligt element för, som segment.

![Datablockhanteraren visar listan Gruppera efter ark.](./assets/group-data-blocks.png){zoomable="yes"}



<!--

# Manage Data Blocks in Report Builder

You can view and manage all data blocks in a workbook using the Data Block Manager. The Data Block Manager provides search, filter, and sort capabilities that allow you to quickly locate specific data blocks. After selecting one or more data blocks, you can edit, delete, or refresh the selected data blocks.

![The Data block manager screen.](./assets/image52.png)

## View Data Blocks

Click **Manage** to view a list of all data blocks in a workbook.

![The Manage option to view a list of all data blocks.](./assets/image53.png)

The Data Block Manager lists all data blocks present in a workbook. 

## Sort the Data Blocks list

You can sort the data block list by a displayed column. For example, you can sort the data block list by report suites, segments, date range, and other variables.

To sort the data block list, click a column heading.

![Sorting the data blocks.](./assets/image54.png)

## Search the Data Block list

Use the Search field to locate anything in the data block table. For example, you could search for metrics contained in the data blocks or report suite. You can also search for dates appearing in the date range, date modified, or last run date columns.

![Using the Search field to locate anything in the data block table.](./assets/image55.png)

## Edit Data Blocks

You can edit the report suite, date range, or the segments applied to one or more data blocks.

For example, you can replace an existing segment with a new segment in one or more data blocks.

1. Select the data blocks that you want to update. You can select the top-level check box to select all data blocks or you can select individual data blocks.

   ![The pencil edit icon](./assets/image56.png)

1. Click the edit icon to display the Quick edit window.

   ![The Quick edit window](./assets/image58.png)

1. Select a segment link to update report suites, date ranges, or segments.

   ![The Add Segment field in the Quick edit window](./assets/image59.png)

## Refresh Data Blocks

Click the refresh icon to refresh the data blocks in the list.

<img src="./assets/refresh-icon.png" width="15%" alt="Refresh icon"/>

To verify if a data block is refreshed, view the refresh status icon. 

A successfully refreshed data block displays a checkmark in a green circle: <img src="./assets/refresh-success.png" width="5%" alt="Green circle with check mark icon"/>. 

A data block that has failed to refresh displays a warning icon: <img src="./assets/refresh-failure.png" width="5%" alt="Red triangle with exclamation mark icon"/>.This makes it easy to identify if any data blocks have errors.


![Data block manager showing refresh status for each data block listed.](./assets/image512.png)

## Delete a Data Block

1. Select a data block in the Data Block manager. 
1. Click the trash can icon to delete the selected data block.

## Group Data Blocks

You can group data blocks using the **Group by** drop-down menu or you can click a column title. To sort data blocks by column, click the column title. To group data blocks by groups, select a group name from the **Group by** drop-down menu. For example, the screenshot below shows data blocks grouped by Sheet. It shows data blocks grouped by Sheet1 and Sheet2.  This is useful, for example, in the segment-replacing use case. If you have multiple segments applied to each data block, it is helpful to create a group containing all the data blocks that you want to replace. Then you can easily select and edit them all at once.

![Data block manager showing the Group by Sheet list.](./assets/group-data-blocks.png)

## Modify the Data Block Manager view

You can modify which columns are visible in the Data Block Manager window.


Click the column list <img src="./assets/image515.png" width="3%" alt="Column list icon"/> icon to select which columns are listed in the Data Block Manager. Select a column name to display the column. Deselect the column name to remove the column from view.

![Data block manager showing the column list](./assets/image516.png)

-->