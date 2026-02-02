---
title: Report Builder Hub
description: Läs om Report Builder nav.
role: User
feature: Report Builder
type: Documentation
solution: Analytics
exl-id: e18381ea-b7d4-4d7a-9ded-23b2d06fa204
source-git-commit: ff1722416fe5062d16c12185d17271ebc2d6b624
workflow-type: tm+mt
source-wordcount: '489'
ht-degree: 1%

---

# Report Builder nav


Report Builder-navet är den högra rutan som visas i Excel-arbetsboken när du väljer ![AdobeLogoRedonWhite](/help/assets/icons/AdobeLogoRedOnWhite.svg) **[!UICONTROL Report Builder]** i menyfliksområdet i Excel.

Använd Report Builder nav för att skapa, uppdatera, ta bort och hantera datablock.

Report Builder-hubben innehåller knapparna ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL Create]**, ![&#x200B; TableManage](/help/assets/icons/TableManage.svg) **[!UICONTROL Manage]** och ![Calendar](/help/assets/icons/Calendar.svg) **[!UICONTROL Schedule]** , **[!UICONTROL Commands]**-panelen och **[!UICONTROL Quick edit]**-panelen.

![Report Builder-nav](assets/hub51.png){zoomable="yes"}


Välj

* ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL Create]** för att [skapa nya datablock](create-a-data-block.md).
* ![TableManage](/help/assets/icons/TableManage.svg) **[!UICONTROL Manage]** för att [hantera befintliga datablock](manage-reportbuilder.md).
* ![Kalender](/help/assets/icons/Calendar.svg) **[!UICONTROL Schedule]** för att [hantera scheman för att skicka din arbetsbok via e-post](schedule-reportbuilder.md).

## Panelen Kommandon

Använd panelen **[!UICONTROL Commands]** för att komma åt kommandon som är kompatibla med de markerade cellerna eller en tidigare åtgärd.

| Kommandon | Tillgängligt när.. | Syfte |
|------|------------------|--------|
| ![Redigera](/help/assets/icons/Edit.svg) **[!UICONTROL Edit data block]** | Det markerade cellområdet eller cellområdet ingår endast i ett datablock. | Används för att redigera ett datablock. |
| ![Uppdatera](/help/assets/icons/Refresh.svg) **[!UICONTROL Refresh data block]** | Markeringen innehåller minst ett datablock. Kommandot uppdaterar bara datablocken i markeringen. | Används för att uppdatera ett eller flera datablock. |
| ![DocumentRefresh](/help/assets/icons/DocumentRefresh.svg) **[!UICONTROL Refresh all data blocks]** | Arbetsboken innehåller ett eller flera datablock. | Används för att uppdatera alla datablock i arbetsboken |
| ![Skicka](/help/assets/icons/Send.svg) **[!UICONTROL Send workbook]** | Arbetsboken innehåller ett eller flera datablock. | Används för att [skicka arbetsboken som en fil via e-post](schedule-reportbuilder.md). |
| ![Kopiera](/help/assets/icons/Copy.svg) **[!UICONTROL Copy data block]** | Det markerade cellområdet eller cellområdet ingår i ett eller flera datablock. | Används för att kopiera ett datablock. |
| ![Klipp ut](/help/assets/icons/Cut.svg) **[!UICONTROL Cut data block]** | Det markerade cellområdet eller cellområdet ingår i ett eller flera datablock. | använda för att klippa ut ett datablock. |
| ![Ta bort](/help/assets/icons/Delete.svg) **[!UICONTROL Delete data block]** | Det markerade cellområdet eller cellområdet ingår endast i ett datablock. | Används för att ta bort ett datablock |

## Snabbredigeringspanel

När du markerar ett eller flera datablock i ett kalkylblad visas panelen **[!UICONTROL Quick edit]** i Report Builder. Du kan använda panelen **[!UICONTROL Quick edit]** om du vill ändra parametrar i ett eller flera datablock samtidigt.

De ändringar du gör när du använder **[!UICONTROL Quick Edit]**-avsnitten gäller alla markerade datablock.

### Rapportsviter

Datablocken hämtar data från ett valt rapportpaket. Om flera datablock är markerade i ett kalkylblad och de inte hämtar data från samma rapportserie, visas länken **Rapportsviter** **[!UICONTROL _Flera_]**.

När du ändrar rapportsviten antar alla datablock i urvalet den nya rapportsviten. Komponenterna i datablocket matchas mot den nya rapportsviten baserat på ID. Om en komponent inte hittas i ett datablock tas komponenten bort och ersätts med **[!UICONTROL Invalid value]**, annars visas en ![AlertRed](/help/assets/icons/AlertRed.svg) för den specifika komponenten.

Om du vill ändra rapportsviten väljer du en ny rapportserie i listrutan **[!UICONTROL Report suite]**.


### Datumintervall

**Datumintervallet** visar datumintervallet för de markerade datablocken. Om flera datablock har markerats med flera datumintervall visas **[!UICONTROL Date range]**-länken **[!UICONTROL _Flera_]**.

### Segment

Länken **Segment** visar en sammanfattningslista över de segment som används av de markerade datablocken. Om flera datablock har markerats med flera segment visas länken **Segment** **[!UICONTROL _Flera_]**.

>[!MORELIKETHIS]
>
>[Välja en rapportsvit](select-report-suite.md)
>[Välj ett datumintervall &#x200B;](select-date-range.md)
>[Arbeta med filter](work-with-segments.md)
>

<!--

Use the Report Builder hub to create, update, delete, and manage data blocks.

The Report Builder hub contains the Create, Manage, and Schedule buttons, the COMMANDS panel, and The QUICK EDIT panel.

<img src="./assets/hub51.png" alt="Report Builder Hub"/>


## Create, Manage, and Schedule buttons

Use the Create, Manage, and Schedule buttons to create new data blocks, manage existing data blocks, or schedule datablocks.

## COMMANDS panel

Use the COMMANDS panel to access commands that are compatible with the selected cells or a previous action.

### Commands

| Commands displayed      | Available when…   | Purpose          |
|------|------------------|--------|
| Edit data block | The selected cell or cells range is part of one data block only. | Used to edit a data block |
| Refresh data block | The selection contains at least one data block. The command refreshes only the data blocks in the selection. | Used to refresh one or more data blocks |
| Refresh all data blocks | The workbook contains one or more data blocks. | Used to refresh ALL data blocks in the workbook |
| Send workbook |   |  Send a workbook on a schedule. |
| Copy data block   | The selected cell or cell range is part of one or more data blocks. | Used to copy a data block   |
| Cut data block |   | Used to cut a data block |
| Delete data block | The selected cell or cells range is part of one data block only. | Used to delete a data block |

## QUICK EDIT panel

When you select one or more data blocks in a spreadsheet, Report Builder displays the QUICK EDIT panel. You can use the QUICK EDIT panel to change parameters in a single data block or to change parameters in multiple data blocks at the same time.

![The Quick Edit panel in Report Builder](./assets/hub2.png)

The changes made using the Quick Edit sections apply to all selected data blocks.

### Report suites

Data blocks pull data from a selected report suite. If multiple data blocks are selected in a worksheet and they don't pull data from the same report suite, the **Report Suites** link displays *Multiple*.

When you change the report suite, all data blocks in the selection adopt the new report suite. Components in the data block are matched to the new report suite based on ID, for example, matching ```evars```). If a component isn't found in a data block, a warning message is displayed and the component is removed from the data block.

To change the report suite, select a new report suite from the drop-down menu.

![The Report Builder Hub showing the report suite drop-down menu.](./assets/image16.png)

### Date range

**[!UICONTROL Date range]** shows the date range for the selected data blocks. If multiple data blocks are selected with multiple date ranges, the **[!UICONTROL Date range]** link displays *Multiple*. [Learn more](/help/analyze/report-builder/select-date-range.md)

### Segments

The **Segments** link displays a summary list of the segments used by the selected data blocks. If multiple data blocks are selected with multiple segments applied, the **Segments** link displays *Multiple*. [Learn more](/help/analyze/report-builder/work-with-segments.md)

-->