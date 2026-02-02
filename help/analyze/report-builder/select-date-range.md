---
title: Markera ett dataintervall i Report Builder
description: Lär dig hur du väljer ett datumintervall i Report Builder.
role: User
feature: Report Builder
type: Documentation
solution: Analytics
exl-id: 610ce2c8-8ff6-4434-912f-3015cc56a51e
source-git-commit: c3fe537967473754a3b5fe88c7b383647b2c742e
workflow-type: tm+mt
source-wordcount: '780'
ht-degree: 1%

---

# Välj ett datumintervall

Så här ändrar du datumintervallet för ett befintligt datablock:

- Välj **[!UICONTROL Edit a data block]**, eller
- Markera länken **[!UICONTROL Date range]** i **[!UICONTROL Quick edit]**.

Använd följande alternativ för att ändra ett datumintervall för ett datablock.

## Kalender

Med alternativet **[!UICONTROL Calendar]** kan du skapa statiska eller rullande datum med följande alternativ:

### Datumintervall

Datumintervallfältet visar det aktuella datumintervallet för begäran om datablock. Du kan ange datum direkt eller använda ![Kalender](/help/assets/icons/Calendar.svg) för att ange ett datumintervall.

![Kalender för datumintervall](assets/date-range-calendar.png){zoomable="yes"}

### Förinställningar

Använd listrutan med förinställningar för att välja en förinställning. Du kan också ange text för att söka efter förinställningar.

![Förinställningar för datumintervall](assets/date-range-presets.png){zoomable="yes"}

Den förinställda listrutan innehåller en standarduppsättning med förinställda datumintervall och datumintervallkomponenter för en rapportserie som du har sparat eller en rapportserie som delats med dig.

### Rullande datum

Så här definierar du rullande datum:

![Amerikanska rullande datum](assets/date-range-rolling-date.png){zoomable="yes"}

1. Välj **[!UICONTROL Use rolling dates]** för att definiera logiken för en definition av rullande datum. Du kan markera texten inom hakparenteser (till exempel **[!UICONTROL fixed start - rolling daily]**) för att utöka panelen och ange information för **[!UICONTROL Start]** och **[!UICONTROL End]**.

1. Välj **[!UICONTROL Start of]**, **[!UICONTROL End of]** eller **[!UICONTROL Fixed day]**.

   - När du har valt **[!UICONTROL Start of]** eller **[!UICONTROL End of]** kan du skapa ett fullständigt uttryck. Till exempel: **[!UICONTROL End of]** **[!UICONTROL current year]** **[!UICONTROL plus]** `1` **[!UICONTROL day]**. Välj lämpligt värde för varje enskild del av uttrycket.

      - Välj ett värde för aktuell. Exempel: **[!UICONTROL current year]**.
      - Välj ett värde för en valfri ytterligare beräkning. Exempel: **[!UICONTROL plus]**.
      - När du har angett ytterligare en beräkning anger du ett värde. Exempel: `1`.
      - När du har angett ytterligare en beräkning väljer du den tidsperiod som ska användas för beräkningen. Exempel: **[!UICONTROL day]**.

   - När du har valt **[!UICONTROL Fixed Day]** anger du en fast dag eller använder väljaren för att välja en dag.

1. Välj **[!UICONTROL hide]** om du vill dölja informationen för beräkning av rullande datum.


### Anpassade uttryck

Med alternativet för anpassade uttryck kan du ändra datumintervallet genom att skapa ett anpassat uttryck eller genom att ange en aritmetisk formel.

![Anpassat uttryck för datumintervall](assets/date-range-custom-expression.png){zoomable="yes"}

1. Välj **[!UICONTROL Use rolling dates]**.

1. Välj **[!UICONTROL Use custom expression]**.

   När du väljer **[!UICONTROL Use custom expression]** inaktiveras standardkontrollerna för rullande datumintervall.

1. Ange ett [anpassat uttryck](#create-a-custom-expression).

1. Använd **[!UICONTROL Date preview]** för att verifiera det resulterande datumintervallet.

#### Skapa ett anpassat uttryck

1. Ange en [datumreferens](#date-references).

1. Lägg till en valfri [datumoperator](#date-operators) om du vill flytta datumet till föregående eller kommande datum.

Du kan ange ett anpassat uttryck som innehåller flera operatorer, till exempel `tm-11m-1d`.

#### Datumreferenser

I följande tabell visas exempel på datumreferenser.

| Datumreferens | Typ | Beskrivning |
|----------------|--------------|----------------------------|
| `1/1/10` | Statiskt datum | Anges i ISO-datumformat |
| `td` | Rullningsdatum | Början av aktuell dag |
| `tw` | Rullningsdatum | Början av aktuell vecka |
| `tm` | Rullningsdatum | Månadens början |
| `tq` | Rullningsdatum | Början av aktuellt kvartal |
| `ty` | Rullningsdatum | Början av aktuellt år |

#### Datumoperatorer

I följande tabell visas exempel på operatorer för datum.

| Datumoperator | Enhet | Beskrivning |
|----------------|---------|--------------------|
| `+6d` | Dag | Lägg till 6 dagar i datumreferensen |
| `+1w` | Vecka | Lägg till en hel vecka i datumreferensen |
| `-2m` | Månad | Subtrahera 2 hela månader till datumreferensen |
| `-4q` | Kvartal | Subtrahera 4 kvartal till datumreferensen |
| -`1y` | År | Ta bort ett år från datumreferensen |

#### Datumuttryck

I följande tabell visas exempel på datumuttryck.

| Datumuttryck | Betydelse |
|-----------------|--------------------------------------|
| `td` | Idag |
| `td-1w` | Första dagen i förra veckan |
| `tm-1d` | Sista dagen i föregående månad |
| `td-52w` | Samma dag, för 52 veckor sedan |
| `tm-11m-1d` | Sista dagen i samma månad förra året |
| `"2020-09-06"` | Specifikt datum, 9 september 2020 |



## Datumintervall från cell

Datumintervallet kan anges i kalkylbladsceller. Använd alternativet **[!UICONTROL Date range from cell]** för att välja datablockets start- och slutdatum från markerade celler. När du väljer alternativet **[!UICONTROL From cell]** visar panelen **[!UICONTROL From]**- och **[!UICONTROL To]**-fält där du kan ange en cellplats eller använda ![DataBlockSelector](/help/assets/icons/DataBlockSelector.svg) för att välja den markerade cellen.

![Välj från cellark1!H4 till ark1!I4](./assets/date-range-from-cell.png){zoomable="yes"}


## Exkludera idag

Välj **[!UICONTROL Exclude today]** om du vill exkludera idag från ett valt datumintervall. Den aktuella dagen exkluderas från alla lägen som används för att definiera ett datumintervall: kalender, rullande datum eller anpassade uttryck.


## Giltiga datumintervall

I följande lista beskrivs giltiga datumintervallformat.

- Start- och slutdatum måste ha följande format: ÅÅÅ-MM-DD

- Startdatumet måste vara tidigare än eller lika med slutdatumet. Båda datumen kan anges till framtiden.

- När du använder rullande datum måste startdatumet vara idag eller tidigare. Startdagen måste vara tidigare om **[!UICONTROL Exclude today]** har valts.

- Du kan skapa en statisk datumintervalluppsättning för framtiden. Du kan till exempel behöva ange ett framtida datum för lanseringen av en marknadsföringskampanj nästa vecka. Med det här alternativet skapas en arbetsboksövervakning för en kampanj i förväg.

## Ändra datumintervall

Du kan redigera datumintervallet för ett befintligt datablock.

1. Markera en cell i datablocket.

- Välj **[!UICONTROL Edit data block]** på panelen **[!UICONTROL Commands]** eller
- Markera länken **[!UICONTROL Date range]** på panelen **[!UICONTROL Quick edit]**.

1. Ändra datumintervallet med något av de tillgängliga datumalternativen.

1. Välj **[!UICONTROL Apply]**.

Report Builder använder det nya datumintervallet för alla datablock i markeringen.

<!--
To change the date range of an existing data block, select Edit a data block or use the QUICK EDIT panel.

Use the following options to change a date range for a data block.

**Calendar**

 The Calendar allows you to create static or rolling dates using the following options:

- Date range field
- Calendar
- Preset drop-down menu
- Rolling date mode
- Customize expressions


**From cell**

The **[!UICONTROL From cell]** option allows you to reference dates entered in worksheet cells.

You have the option to exclude today on any selected date range.

 ![Report Builder Quick edit pane with calendar selected and Exclude today selected.](./assets/image17.png)

## Use the Calendar

When you use the **Calendar**, the date range field displays the current date range for the data block request. You can enter dates directly into the date range field or use a data range selection option.

### Date range field

To enter dates directly into the date range field

1. Click the date range field next to the calendar icon.

1. Enter start and end dates for your date range.

### Calendar

To select dates using the calendar

1. Click the calendar icon to display a monthly calendar.

1. Click a start date.

1. Click an end date.

To set a date range in reverse, click the end date first and then click the start date.

![Report Builder date range pane showing the calendar and the end date and the start date selected.](./assets/image18.png)

### Preset drop down menu

The preset drop-down menu includes a standard set of preset date ranges and date range components for a report suite that you saved or a report suite that was shared with you.

### Rolling dates

The rolling dates option allows you to select a date range using rolling dates.

1. Select **Use rolling dates**.

1. Select a rolling expression for your start and or end date.

    ![Report Builder date range pane showing Use rolling dates selected and the rolling expression.](./assets/image19.png)

    **Start of** — Allows you to select the beginning of a day, week, month, quarter, or year.

    **End of** — Allows you to select the end of a day, week, month, quarter, or year.

    **Fixed day** — Allows you to fix a start or end date while the other date is rolling.

1. Choose day, week, month, quarter, or year as the rolling period.

    ![Report Builder date range pane showing the current day selected.](./assets/image20.png)

1. Add or subtract days, weeks, months, quarters, or years from your rolling date.

    ![Report Builder date range pane showing the current day plus 14 days selected.](./assets/image21.png)

1. Click Next to define the data range.

    Use the date preview to confirm the resulting date range is the desired range.

### Custom expressions

The custom expression option allows you to change the date range by building a custom expression or you can enter an arithmetic formula.

1. Select **Use rolling dates**.

1. Select **Use custom expression**.

    When you select the **Use custom expression** option, the standard rolling date range controls are disabled.

    ![Select Use custom expression showing tm-1m to td-1d.](./assets/custom_expression.png)

1. Enter a custom expression.

    For a sample list of custom expressions, see **Date expressions**.

1. Use the date preview to verify the resulting date range is the desired range.

#### Create a custom expression

1. Enter a **Date reference**.

1. Add **Date operators** to move the date to the past or future.

You can enter a custom date expression that includes multiple operators, such as ```tm-11m-1d```.

#### Date references

The following table lists date reference examples.

| Date Reference | Type         | Description                |
|----------------|--------------|----------------------------|
| 1/1/10         | Static Date  | Entered in ISO Date format |
| td             | Rolling Date | Start of current day       |
| tw             | Rolling Date | Start of current week      |
| tm             | Rolling Date | Start of current month     |
| tq             | Rolling Date | Start of current quarter   |
| ty             | Rolling Date | Start of current year      |

#### Date operators

The following table lists date operator examples.

| Date Operators | Unit    | Description   |
|----------------|---------|--------------------|
| +6d            | Day     | Add 6 days to the Date Reference |
| +1w            | Week    | Add one full week to the Date Reference |
| -2m            | Month   | Subtract 2 full months to the Date Reference |
| -4q            | Quarter | Subtract 4 quarters to the Date Reference |
| -1y            | Year    | Subtract one year to the Date Reference |

#### Date expressions

The following table lists date expression examples.

| Date Expression | Meaning                              |
|-----------------|--------------------------------------|
| td-1w           | First day of last week               |
| tm-1d           | Last day of previous month           |
| td-52w          | Same day, 52 weeks ago               |
| tm-11m-1d       | Last day of the same month last year |
| "2020-09-06"    | Sept 9th, 2020                       |

## Date range from cell

The date range can be specified in worksheet cells. Use the **Date range from cell** option to choose the data block start and end date from selected cells. When you select the **From cell** option, the panel displays **From** and **To** fields where you can enter a cell location.

![Select From cell Sheet1!H4 to Sheet1!I4](./assets/image23.png)

## Exclude today

Choose the **Exclude today** option to exclude today from a selected date range. Choosing to include today may pull incomplete data for today.

When selected, the **Exclude today** option excludes the current day from all date range modes including calendar, rolling dates, or custom expressions.

## Valid date ranges

The following list describe valid date range formats.

- The start and end dates must be in the following format: YYYY-MM-DD

- The start date must be earlier to or equal to the end date. Both dates can be set to the future.

- When using rolling dates, the start date must be today or in the past. It must be in the past if **Exclude today** is checked.

- You can create a static date range set for the future. For example, you may need to set a future date for a marketing campaign launch next week. This option creates a workbook monitoring for a campaign ahead of time.

## Change the date range

You can edit the date range of an existing data block by selecting Edit data block in the COMMANDS panel or by selecting the date range link in the QUICK EDIT panel.

**Edit data block** — Allows you to edit multiple data block parameters, including date range, for a single data block.

**Quick Edit: Date range** — Allows you to edit the date range of one or more data blocks.

To edit the date range from the QUICK EDIT panel

1. Select cells within one or more data blocks in a worksheet.

1. Click the **Date range** link in the QUICK EDIT panel.

1. Select the date range using any of the date selection options.

1. Click **Apply**.


Report Builder applies the new date range to all data blocks in the selection.
-->