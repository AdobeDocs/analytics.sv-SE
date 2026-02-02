---
title: Schemalägg arbetsböcker med Report Builder
description: Lär dig använda schemafunktionen i Report Builder.
role: User
feature: Report Builder
type: Documentation
solution: Analytics
exl-id: 40e1feb0-64bc-40e6-83cb-4a1ea7e2d0cc
source-git-commit: 8b6d8a4efec59b693a69984880d8f374ae0cfabc
workflow-type: tm+mt
source-wordcount: '757'
ht-degree: 0%

---

# Schemalägg arbetsböcker genom delning via e-post

>[!NOTE]
>
>Förutom att schemalägga arbetsböcker för delning via e-post, så som beskrivs i det här avsnittet, kan du schemalägga att arbetsböcker ska exporteras till molnmål, så som beskrivs i [Schemalägg arbetsböcker för export till molnmål](/help/analyze/report-builder/report-builder-export.md).

När du har sparat arbetsboken och slutfört analysen kan du enkelt dela arbetsboken med andra i teamet med hjälp av schemaläggningsfunktionen. Med funktionen Schemalägg kan du skapa ett schema som automatiskt uppdaterar data i arbetsboken och skickar Excel-arbetsbokens .xlsx-fil med e-post som en bifogad fil till den angivna målgruppen vid ett visst datum och en viss tidpunkt. Genom att ställa in ett schema får mottagarna regelbundna uppdateringar automatiskt. Du kan också använda schemafunktionen för att skicka ut arbetsboken en gång utan att schemalägga automatiska uppdateringar.

Du kan skapa flera scheman för en enskild arbetsbok. Du kan till exempel skicka en arbetsbok till ditt team dagligen och du kan skicka arbetsboken till din chef en gång i veckan genom att skapa två olika scheman.

Med funktionen Schemalägg kan du även konfigurera lösenordsskydd för en arbetsbok och redigera tidigare schemalagda arbetsböcker.


>[!BEGINSHADEBOX]

Se ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Schemalägg arbetsböcker](https://video.tv.adobe.com/v/3413079?quality=12&learn=on){target="_blank"} för en demonstrationsvideo.

>[!ENDSHADEBOX]


## Schemalägg en arbetsbok

Så här schemalägger du en arbetsbok:

1. Välj **[!UICONTROL Schedule]** i Report Builder-hubben om du vill skapa ett schema så att du automatiskt kan distribuera en Excel-arbetsboksfil (.xlsx) till en individ eller grupp.

   ![Välj knappen Schema för att skapa ett schema.](./assets/schedule.png){zoomable="yes"}

1. Välj **[!UICONTROL Schedule Workbook]** eller ![Lägg till](/help/assets/icons/Add.svg) om du vill skapa en ny schemalagd arbetsbok.

   ![Arbetsboksfönstret Schemalägg.](./assets/schedule-workbook.png){zoomable="yes"}

   I schemaläggningsrutan visas viss fördefinierad information om arbetsboken, t.ex. arbetsbokens namn och det senaste datumet som arbetsboken ändrades.

### Fil

I avsnittet **[!UICONTROL File]** anger du information om filtyp, namn och lösenord för att skydda filen.

![Schemaläggningsfönstret.](./assets/schedule-pane.png){zoomable="yes"}

1. Använd ![TableSelect](/help/assets/icons/TableSelect.svg) för att välja den aktuella arbetsboken, om den inte redan är markerad.

1. (Valfritt) Ange **[!UICONTROL File name]**.

   Arbetsbokens filnamn är som standard arbetsbokens namn, men du kan ändra filnamnet om du vill.

1. Välj en **[!UICONTROL File type]**.

   * **[!UICONTROL Excel]**
   * **[!UICONTROL PDF]**
   * **[!UICONTROL CSV]**

   När du väljer **[!UICONTROL CSV]** bör du tänka på att den schemalagda arbetsboken skickas som en zip-bilaga. Vissa e-postadministrationer kan blockera e-post med postbilagor. Du ser en varning i enlighet med detta.

1. (Valfritt) Välj **[!UICONTROL Append time-stamp to file name]**.

   Du kan lägga till en tidsstämpel till filnamnet för att identifiera vilket datum arbetsboken uppdaterades. En tidsstämpel är användbar för att se vilken version av en arbetsbok som skickades på ett visst datum. När du har markerat det här alternativet kan du välja mellan:

   * **[!UICONTROL ISO Date format]**, vilket resulterar i att `YYYY-MM-DD` läggs till i filnamnet.
   * **[!UICONTROL ISO Date format + time stamp]**, vilket resulterar i att `YYYY-MM-DD_HH-MM-SS` läggs till i filnamnet.

<!-- Does no longer seem to be an option? 
1. (Optional) Select **.zip compression** to compress the file and set up password protection on the file.

    When you make this selection, you're prompted to enter a password to open the file. This is helpful if you have concerns about data security and you want to password protect the workbook. Protecting the file with a password requires you to select **.zip compression**. The password must be at least 8 characters and contain a number and a special character.

    ![Enter a password in the Password protect the workbook field.](./assets/zip-compression.png){zoomable="yes"}{width="55%"}
-->

1. Ange ett lösenord i **[!UICONTROL Password protect the workbook]**. Ett giltigt lösenord måste innehålla minst 8 tecken, en siffra och ett specialtecken. Välj ![VisibilityOff](/help/assets/icons/VisibilityOff.svg) för att visa lösenordet och ![Visibility](/help/assets/icons/Visibility.svg) för att dölja lösenordet (standard).


### E-post

I avsnittet **[!UICONTROL Email]** anger du mottagare, ämne och beskrivning av e-postmeddelandet.

![Schemalägg e-postinställningar](assets/schedule-email.png){zoomable="yes"}

1. Ange **mottagare**. Du kan ange namnet på en person som är erkänd i din organisation. Eller så kan du ange en e-postadress till en person som inte finns i organisationen.

1. Ange **Ämne** för e-postmeddelandet och en beskrivning för mottagarna. Ämnet får som standard arbetsbokens filnamn, men du kan ändra ämnet om det behövs. Du kan lägga till information i beskrivningsavsnittet.

1. Du kan också ange en beskrivning i textområdet **[!UICONTROL Description]**.


### Schema

I avsnittet **[!UICONTROL Schedule]** kan du definiera schemat för att skicka e-postmeddelanden med arbetsboken till mottagarna.

![Schemadefinition](assets/schedule-enable.png){zoomable="yes"}

1. Välj **[!UICONTROL Show scheduling options]** om du vill definiera ett schema.

1. Ange ett startdatum i **[!UICONTROL Starting on]**. Du kan också välja ![Kalender](/help/assets/icons/Calendar.svg) om du vill välja ett startdatum från kalendern.

1. Ange ett slutdatum i **[!UICONTROL Ending on]**. Du kan också välja ![Kalender](/help/assets/icons/Calendar.svg) om du vill välja ett slutdatum från kalendern.

1. Välj en **[!UICONTROL Frequency]**. Beroende på vald frekvens har du ytterligare alternativ. Se tabellen nedan.

   | Frekvens | Alternativ |
   |---|---|
   | **[!UICONTROL Send hourly]** | Ange ett värde för **[!UICONTROL Send every number of hours]**. |
   | **[!UICONTROL Send daily]** | Välj en **[!UICONTROL Daily frequency]**: **[!UICONTROL Send every day]**, **[!UICONTROL Send every weekday]** eller **[!UICONTROL Custom frequency]**.<br/>Om du väljer **[!UICONTROL Custom frequency]** anger du ett värde för **[!UICONTROL Send every number of days]**. |
   | **[!UICONTROL Send weekly]** | Ange ett värde för **[!UICONTROL Send every number of weeks]**. Och välj en **[!UICONTROL Day of week]**. |
   | **[!UICONTROL Send monthly by day of the week]** | Välj **[!UICONTROL Day of week]** och **[!UICONTROL Week of month]**. |
   | **[!UICONTROL Send monthly by day of the month]** | Välj ett värde från **[!UICONTROL Send on this day of the month]**. |
   | **[!UICONTROL Send yearly by day of the month]** | Välj en **[!UICONTROL Day of week]**, markera en **[!UICONTROL Week of month]** och välj en **[!UICONTROL Monthly of year]**. |
   | **[!UICONTROL Send yearly by specific date]** | Välj en **[!UICONTROL Month of year]** och välj ett värde från **[!UICONTROL Send on this day of the month]**. |

### Skicka

Så här skickar du arbetsboken:

* Om du inte har definierat ett schema med **[!UICONTROL Show scheduling options]** väljer du **[!UICONTROL Send now]** för att skicka arbetsboken via e-post omedelbart.
* Om du har definierat ett schema med **[!UICONTROL Show scheduling options]** väljer du **[!UICONTROL Send on schedule]** om du vill skicka arbetsboken via e-post enligt det schema som du har definierat.

I båda fallen visas en bekräftelsetabell längst ned i Report Builder-navet.

Om du vill avbryta sändning av arbetsboken väljer du **[!UICONTROL Cancel]**.

## Hantera schemalagda arbetsböcker

Mer information om hur du hanterar arbetsböcker som redan är schemalagda finns i [Hantera schemalagda arbetsböcker](/help/analyze/report-builder/manage-reportbuilder.md).




<!--

## Schedule a workbook

Use the Schedule button in the Report Builder hub to quickly create a schedule so that you can automatically distribute a workbook Excel file (.xlsx) to an individual or a group.

1. Click the Schedule button in the Report Builder hub.

    ![Click the Schedule button to create a schedule.](./assets/schedule-button.png){width="55%"}

1. Click Schedule Workbook or the plus button in the upper-left to create a new scheduled workbook.

    ![The Schedule workbooks window.](./assets/schedule-workbook.png){width="55%"}

    The scheduling pane displays some pre-defined information about the workbook such as the workbook name and the last date that the workbook was modified.

    ![The scheduling pane.](./assets/schedule-pane.png){width="55%"}

1. (Optional) Enter a file name.

    The workbook file name defaults to the name of the workbook but you can change this if you want. If you\'re sending the same workbook to multiple audiences and you want to name it something a little bit more friendly for a certain audience, you can change the name.

1. (Optional) Select **Append time-stamp to file name**.

    You can append a timestamp to the file name to identify the date the workbook was updated. This is helpful to quickly see which version of a workbook was sent on a specific date. The **Filename preview** shows how the workbook file name will appear in the email when the workbook is distributed. The time-stamp format is YYYY-MM-DD.

1. (Optional) Select **.zip compression** to compress the file and set up password protection on the file.

    When you make this selection, you're prompted to enter a password to open the file. This is helpful if you have concerns about data security and you want to password protect the workbook. Protecting the file with a password requires you to select **.zip compression**. The password must be at least 8 characters and contain a number and a special character.

    ![Enter a password in the Password protect the workbook field.](./assets/zip-compression.png){width="55%"}

1. Enter **Recipients**. You can enter the name of a person that is recognized in your organization, or you can enter an email address of a person inside or outside of your organization.

1. Enter the **Subject** of the email and a description for your recipients. The subject defaults to the workbook file name but you can modify the subject if needed. You can add details in the description section.

    ![Enter a subject in the Subject field.](./assets/recipients-subject.png){width="55%"}

1. Set up the scheduling options to set the date and time that you want the workbook emailed to your recipients.

    Choose the start and end date and time frames. This can be today's date or a date in the future.

    Choose the **Frequency** from the drop-down menu. You can set the frequency to be hourly, daily, weekly, monthly, or yearly on a specific day. For example, you can set up a schedule to send the workbook on the first Sunday night of the month so that your recipients will have the email in their inbox first thing on Monday morning.

    ![Select the frequency to schedule your report.](./assets/frequency.png){width="55%"}

1. After you set the schedule, click **Send on schedule**.

    ![Click Send on schedule.](./assets/send-on-schedule.png){width="55%"}

    You see a confirmation toast at the bottom of the Report Builder hub and the scheduled workbook is listed under the Workbooks tab.

    ![Confirmation toast](./assets/confirmation-toast.png){width="55%"}

## Schedule a converted workbook {#converted}

1. Schedule a [converted](/help/analyze/report-builder/convert-workbooks.md) legacy workbook.

   A pop up appears, asking if you want to use the scheduling metada from the legacy workbook to create a new scheduled task. 

1. If you select **[!UICONTROL Use]**, Report Builder automatically fills in the legacy scheduling information. 

1. Ensure that this information is correct and schedule. 

1. If you want to send the workbook on a different schedule, schedule a completely fresh scheduled task. 


## Send the workbook one-time only

You can also send out the workbook only once.

1. Un-check **Show scheduling options** 

    ![Click Un-check Show scheduling options to send out a workbook one time.](./assets/send-now.png){width="40%"}

1. Click **Send Now**.

## Manage scheduled workbooks

For information about managing workbooks that are already scheduled, see [Manage scheduled workbooks](/help/analyze/report-builder/manage-schedules-reportbuilder.md).

-->