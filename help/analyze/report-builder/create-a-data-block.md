---
title: Skapa ett datablock i Report Builder
description: Lär dig hur du skapar ett datablock.
role: User
feature: Report Builder
type: Documentation
solution: Analytics
exl-id: fd3ff12a-14de-46f6-ab89-a0152fb11b0d
source-git-commit: ff1722416fe5062d16c12185d17271ebc2d6b624
workflow-type: tm+mt
source-wordcount: '731'
ht-degree: 0%

---

# Skapa ett datablock

Ett *datablock* är den datatabell som skapas av en enskild databegäran. En Report Builder-arbetsbok kan innehålla flera datablock. När du skapar ett datablock konfigurerar du först datablocket och skapar sedan datablocket.

## Konfigurera datablocket

Konfigurera de inledande datablocksparametrarna för datablockplatsen, rapportsviten och datumintervallet.

1. Välj ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL Create]**.

   ![Skärmbild som visar alternativet Skapa datablock](./assets/create-data-block.png){zoomable="yes"}


1. Ange **[!UICONTROL Data block location]**.

   Platsalternativet för datablocket anger den plats i kalkylbladet där Report Builder lägger till data i ditt kalkylblad.

   Om du vill ange platsen för datablocket markerar du en enskild cell i kalkylbladet eller anger en celladress, till exempel `a3`, `\\\$a3`, `a\\\$3` eller `sheet1!a2`. Den angivna cellen blir det övre vänstra hörnet i datablocket när data hämtas.

   Använd ![DataBlockSelector](/help/assets/icons/DataBlockSelector.svg) om du vill välja en plats för ett datablock från den markerade cellen i kalkylbladet.

1. Välj **[!UICONTROL Report suites]**.

   Med alternativet Rapportsviter kan du välja en rapportserie i en nedrullningsbar meny eller referera till en rapportsvit från en cellplats.

   Välj ![DataViewSelector](/help/assets/icons/DataViewSelector.svg) om du vill skapa en rapportserie från en cell.

1. Ange **[!UICONTROL Date range]**.

   Med alternativet **[!UICONTROL Date range]** kan du välja ett datumintervall. Datumintervall kan vara fasta eller rullande.

   Välj **[!UICONTROL Calendar]** om du vill välja ett dataintervall med ![Kalender](/help/assets/icons/Calendar.svg) eller ange ett datumintervall manuellt. Du kan också välja en förinställning i listrutan **[!UICONTROL _Sökförinställningar_]** .

   Välj **[!UICONTROL From cell]** om du vill definiera start- och slutdata baserat på en cell i det aktuella bladet.

   Mer information om alternativ för datumintervall finns i [Markera ett datumintervall](select-date-range.md).

1. Välj **[!UICONTROL Next]**.

   ![Skärmbild som visar datumintervallalternativet och den aktiva knappen Nästa.](./assets/choose_date_data_view3.png)

   När du har konfigurerat datablocket kan du välja mått, mätvärden och segment för att skapa datablocket. Flikarna **[!UICONTROL Dimensions]**, **[!UICONTROL Metrics]** och **[!UICONTROL Segments]** visas ovanför rutan **[!UICONTROL Table]**.

## Bygg datablocket

Om du vill skapa datablocket väljer du rapportkomponenter och anpassar sedan layouten.

1. Lägg till **[!UICONTROL Dimensions]**-, **[!UICONTROL Metrics]**- och **[!UICONTROL Segments]**-komponenter.

   Bläddra i komponentlistorna eller använd fältet ![Sök](/help/assets/icons/Search.svg) **[!UICONTROL _Sök efter komponenter_]** för att söka efter komponenter. Dra och släpp komponenter i rutan [!UICONTROL Table] eller dubbelmarkera ett komponentnamn i listan för att lägga till komponenten i rutan [!UICONTROL Table].

   Dubbelmarkera en komponent om du vill lägga till komponenten i ett standardavsnitt i tabellen.

   - Dimension-komponenter läggs till i avsnittet ![TableSelectRow](/help/assets/icons/TableSelectRow.svg) **[!UICONTROL Row]** eller i avsnittet ![TableSelectColumn](/help/assets/icons/TableSelectColumn.svg) **[!UICONTROL Column]** om du redan har en dimension i kolumnerna.
   - Datumkomponenter läggs till i avsnittet ![TableSelectColumn](/help/assets/icons/TableSelectColumn.svg) **[!UICONTROL Column]**.
   - Segmentkomponenter läggs till i avsnittet ![Segmentering](/help/assets/icons/Segmentation.svg) **[!UICONTROL Segments]** .
   - Mätkomponenter läggs till i avsnittet ![Event](/help/assets/icons/Event.svg) **[!UICONTROL Values]** .

1. Ordna objekten i tabellrutan för att anpassa layouten för ditt datablock.

   Dra och släpp komponenter i varje lista i tabellrutan om du vill ändra ordning på komponenterna eller markera ![MoreSmall](/help/assets/icons/MoreSmall.svg) och välj ![ArrowUp](/help/assets/icons/ArrowUp.svg) Move up, ![ArrowDown](/help/assets/icons/ArrowDown.svg) Move down, med mera för att flytta komponenterna i en lista.

   När du lägger till komponenter i tabellen visas en förhandsvisning av datablocket på datablockets plats i kalkylbladet. Layouten för förhandsgranskningen av datablocket uppdateras automatiskt när du lägger till, flyttar eller tar bort objekt i tabellen.

   ![Skärmbild som visar de tillagda komponenterna och det uppdaterade kalkylbladet.](./assets/image10.png)


1. Du kan även ange **[!UICONTROL Start date]** som en dimension för att identifiera startdatumet för ditt datablock. Det kan vara bra att lägga till startdata som en dimension om du har en regelbundet schemalagd rapport med ett löpande datumintervall. Eller om du har ett okonventionellt datumintervall och du måste vara explicit angående startdatumet.

   ![Skärmbild som visar startdatumet i listan över dimensioner.](./assets/start-date-dimension.png)

1. Du kan även visa eller dölja rad- och kolumnrubriker. Så här gör du:

   1. Välj ikonen **[!UICONTROL Table]** ![Inställningar](/help/assets/icons/Setting.svg).

      ![Skärmbild med alternativet Tabellinställningar.](./assets/table-settings.png)

   1. Markera eller avmarkera alternativet för **[!UICONTROL Display row and column headers]**. Rubrikerna visas som standard.

1. Du kan även dölja eller visa dimensionsetiketter och metriska rubriker. Så här gör du:

   1. Välj ![MoreSmall](/help/assets/icons/MoreSmall.svg) på dimensionsetiketten eller kolumnrubriken för att visa snabbmenyn.

      ![Ellipsikonen i avsnittet Rad.](./assets/row-heading.png)

   1. Välj ![VisibilityOff](/help/assets/icons/VisibilityOff.svg) **[!UICONTROL Hide]** eller ![Visibility](/help/assets/icons/Visibility.svg) **[!UICONTROL Show]** för att växla dimensionsetikett eller kolumnrubrik. Alla etiketter visas som standard.

1. Välj **[!UICONTROL Finish]** för att slutföra konfigurationen av ditt datablock.

1. Ett bearbetningsmeddelande **[!UICONTROL #BUSY]** visas när analysdata hämtas.

   ![Bearbetningsmeddelandet.](./assets/image11.png)

1. Report Builder hämtar data och visar det ifyllda datablocket i kalkylbladet.

   ![Det slutförda datablocket.](./assets/image12.png)


>[!MORELIKETHIS]
>
>[Välja en rapportsvit](select-report-suite.md)
>[Välj ett datumintervall ](select-date-range.md)
>[Filterdimensioner ](filter-dimensions.md)
>[Arbeta med segment ](work-with-segments.md)
>


<!--

A *data block* is the table of data created by a single data request. A Report Builder workbook can contain multiple data blocks. When you create a data block, first configure the data block and then build the data block.

## Configure the data block

Configure the initial data block parameters for the data block location, report suite, and a date range.

1. Click **[!UICONTROL Create]**.

    ![Screenshot showing the Create data block option.](./assets/create_db.png)

1. Set the **[!UICONTROL Data block location]**.

    The data block location option defines the worksheet location where report builder adds the data to your worksheet.

    To specify the data block location, select a single cell in the worksheet and click the icon next to **[!UICONTROL Data block location]**: 
    
    You can also enter a cell address such as a3, \\\$a3, a\\\$3 or sheet1!a2. The cell specified marks the upper-left corner of the data block when the data is retrieved.

1. Choose a **Report Suite**.

    The report suites option allows you to choose a report suite from a drop-down menu or to reference a report suite from a cell location.

1. Set the **[!UICONTROL Date range]**.

    The Date range option allows you to choose a date range. Date ranges may be fixed or rolling. For information about data range options, see [Select a Date Range](select-date-range.md).

1. Click **[!UICONTROL Next]**.

    ![Screenshot showing the date range option and the active Next button.](./assets/choose_date_report_suite.png)

    After you configure the data block, you can select dimensions, metrics, and segments to build your data block. The Dimensions, Metrics, and Filters tabs are displayed above the Table builder pane.

## Build the data block

To build the data block, select report components, and then customize the layout.

1. Add Dimensions, Metrics, and Segments.

    Scroll the component lists or use the **[!UICONTROL Search]** field to locate components. Drag and drop components to the Table pane or double-click a component name in the list to automatically add the component to the Table pane.

    Double-click a component to add it to a default section of the table.

    - Dimension components are added to the Row section or to the Column section if you have a dimension already in the columns.
    - Date components are added to the Column section.
    - Segment components are added to the Segments section.

    **Start date as a Dimension**

    Set the **[!UICONTROL Start date]** as a dimension to clearly identify the start date of your data block. This is helpful if you have a regularly scheduled report that has a rolling date range or if you have an unconventional date range and you need to be clear on the start date.

    ![Screenshot showing the Start date in the list of dimensions.](./assets/start-date-dimension.png){width="30%"}

1. Arrange the items in the Table pane to customize the layout of your data block.

    Drag and drop components in the Table pane to reorder components or right-click a component name and select from the options menu.

    When you add components to the table, a preview of the data block is displayed at the Data block location in the worksheet. The layout of the data block preview automatically updates as you add, move, or remove items in the table.

    ![Screenshot showing the added components and updated worksheet.](./assets/image10.png)

    **Display or hide row and column headers**

1. Click the **[!UICONTROL Table settings]** icon.

    ![Screenshot showing the Table settings option.](./assets/table-settings.png){width="35%"}

1. Check or uncheck the option to Display row and column headers. The headers are displayed by default.

    **Hide or show dimension labels and metric headers**

1. Click the ellipsis icon on either the dimensions or the column headers to display the settings.

    ![The ellipsis icon in the Row section.](./assets/row-heading.png){width="35%"}

1. Click Hide or Show to toggle the dimension labels or column headers. All labels are displayed by default.

1. Click **[!UICONTROL Finish]**.

    A processing message is displayed while the analytics data is retrieved.

    Report Builder retrieves the data and displays the completed data block in the worksheet.

    ![The completed data block.](./assets/image12.png)

-->