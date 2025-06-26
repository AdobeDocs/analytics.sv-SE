---
description: Se och hantera schemalagda rapporter i hela organisationen.
title: Schemalagd projektledare
feature: Admin Tools
exl-id: 8bc8d983-f680-48fa-8483-694c87a9ae4c
source-git-commit: d4d0eeac4f1f29e4c68e80b6fa0fe987a1fb32b9
workflow-type: tm+mt
source-wordcount: '734'
ht-degree: 0%

---

# Schemalagda projekt

Schemalagda Analysis Workspace-projekt kan hanteras i Adobe Analytics med **[!UICONTROL Components]** > **[!UICONTROL Scheduled projects]**.

I **[!UICONTROL Scheduled Projects]** kan du redigera och ta bort återkommande projektscheman.  I [schemalagda projektlistan](#scheduled-project-list) visas de objekt som en viss användare har skapat. Om användarkontot är inaktiverat i programmet stoppas alla schemalagda leveranser.

![Gränssnitt för schemalagda projekt](assets/scheduled-projects.png)

## Schemalagd projektlista

Listan ➊ med schemalagda projekt visar kolumner för:

| Kolumn | Beskrivning |
| --- | --- |
| ![SelectBox](/help/assets/icons/SelectBox.svg) | När ett eller flera schemalagda projekt har valts visas ett blått åtgärdsfält längst ned i gränssnittet för schemalagda projekt. Mer information finns i [Åtgärder](#actions). |
| ![Stjärna](/help/assets/icons/Star.svg) | Välj om du vill gynna ![Star](/help/assets/icons/Star.svg) eller ![StarOutline](/help/assets/icons/StarOutline.svg) i ett schemalagt projekt. |
| **[!UICONTROL Schedule ID]** | Ett ID som huvudsakligen används för felsökning. |
| **[!UICONTROL Name]** | Projektets namn.<br/>Välj ![InfoOutline](/help/assets/icons/InfoOutline.svg) om du vill visa mer information om det schemalagda projektet.<br/>Välj ![Mer](/help/assets/icons/More.svg) om du vill öppna en snabbmeny. På den här menyn kan du:<ul><li>![Ta bort](/help/assets/icons/Delete.svg) **[!UICONTROL Delete]** ett schemalagt projekt.</li><li>![Etiketter](/help/assets/icons/Labels.svg) **[!UICONTROL Tag]** ett planerat projekt.</li><li>![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) **[!UICONTROL Approve]** ett schemalagt projekt.</li><li>![FileCSV](/help/assets/icons/FileCSV.svg) **[!UICONTROL Export CSV]**: Exportera ett planerat projekt till en CSV-fil.</li></ul> |
| **[!UICONTROL Owner]** | Personen som skapade och äger projektet. |
| **[!UICONTROL Tags]** | (valfritt) Taggning är ett bra sätt att ordna projekt. Alla användare kan skapa taggar och använda en eller flera taggar i ett projekt. Men du kan bara se taggar för de projekt som du äger eller som har delats med dig. |
| **[!UICONTROL Delivered to]** | Mottagarna av det här schemalagda projektet. |
| **[!UICONTROL Expiration date]** | Du kan ange ett förfallodatum till upp till ett år, oavsett hur ofta schemat används. |
| **[!UICONTROL Frequency]** | Hur ofta du vill att schemaprojektet ska skickas till en eller flera mottagare. |
| **[!UICONTROL Execution Time]** | Vid vilken tidpunkt på dagen det här schemalagda projektet skickas. |
| **[!UICONTROL Number of Queries]** | Antalet frågor mot det här projektet. |
| **[!UICONTROL Longest Date Range]** | Det längsta datumintervallet som har definierats för det schemalagda projektet. Det här värdet kan vara relevant för att undersöka prestandaproblem. Mer information finns i [Rapportera aktivitetshanteraren](/help/admin/admin/reporting-activity-manager/reporting-activity-overview.md). |
| **[!UICONTROL Number of queries]** | Antalet frågor som har körts för det schemalagda projektet. Det här värdet kan vara relevant för att undersöka prestandaproblem. Mer information finns i [Rapportera aktivitetshanteraren](/help/admin/admin/reporting-activity-manager/reporting-activity-overview.md). |


Du kan använda ![ColumnSetting](/help/assets/icons/ColumnSetting.svg) för att konfigurera vilka kolumner som ska visas.

Sök efter ett schemalagt projekt med ![Sök](/help/assets/icons/Search.svg). Du kan också se om några filter har tillämpats från filterpanelen. Om du vill ta bort ett filter väljer du ![CrossSize75](/help/assets/icons/CrossSize75.svg) för ett filter. Om du vill ta bort alla filter väljer du **[!UICONTROL Clear all]**.

Om du vill redigera ett schemalagt projekt markerar du titeln på det schemalagda projektet. Använd dialogrutan **[!UICONTROL Edit scheduled project]** för att uppdatera schemainformationen. Mer information finns i [Skicka filer till andra](../analyze/analysis-workspace/curate-share/t-schedule-report.md).

![Redigera schemalagt projekt](assets/edit-scheduled-project.png)

Välj **[!UICONTROL Update]** om du vill uppdatera schemat.




## Åtgärder

Följande är vanliga åtgärder i hanteraren för schemalagda projekt. Du kan välja åtgärder från snabbmenyn eller från det blå åtgärdsfältet när du väljer ett eller flera schemalagda projekt.

| Ikon | Åtgärd | Beskrivning |
|:---:|---|---|
| ![Stäng](/help/assets/icons/Close.svg) | **[!UICONTROL *x *selected]** | Välj det här alternativet om du vill avmarkera dina valda schemalagda projekt. |
| ![Ta bort](/help/assets/icons/Delete.svg) | **[!UICONTROL Delete]** | Ta bort de valda schemalagda projekten för projektet. Projekten tas inte bort. |
| ![Etiketter](/help/assets/icons/Labels.svg) | **[!UICONTROL Tag]** | Tagga de valda schemalagda projekten. I **[!UICONTROL Tag Scheduled projects]** markerar du taggar och väljer **[!UICONTROL Save]** att spara. |
| ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | **[!UICONTROL Approve]** | Godkänn de valda schemalagda projekten. |
| ![FileCSV](/help/assets/icons/FileCSV.svg) | **[!UICONTROL Export to CSV]** | Exportera de markerade schemalagda projekten till en fil med namnet `Export Scheduled Projects List.csv`. |


## Filter

Du kan filtrera listan [Schemalagda projekt](#scheduled-project-list) med filterpanelen ➌. Om du vill visa eller dölja filterpanelen använder du ![Filter](/help/assets/icons/Filter.svg).

Filterpanelen består av följande avsnitt.

### Taggar

| Taggar | Beskrivning |
|---|---|
| ![Taggar](/help/components/assets/scheduledprojects-filter-tags.png){width="300"} | I avsnittet **[!UICONTROL Tags]** kan du filtrera efter taggar. <ul><li>Du använder ![Sök](/help/assets/icons/Search.svg) **[!UICONTROL Search Tags]** för att söka efter taggar som du vill använda för att filtrera.</li><li>Du kan markera flera taggar. Vilka märkord som är tillgängliga beror på vilka markeringar du har gjort i andra avsnitt på filterpanelen.</li><li>Siffrorna anger:<ul><li>7︎⃣: Antalet schemalagda projekt som är associerade med den specifika taggen.</li></ul></li></ul> |


### Ägare

| Ägare | Beskrivning |
|---|---|
| ![Ägare](/help/components/assets/scheduledprojects-filter-owners.png){width="300"} | I avsnittet **[!UICONTROL Owner]** kan du filtrera efter ägare. <ul><li>Du använder ![Sök](/help/assets/icons/Search.svg) *Sökägare* för att söka efter ägare som du vill använda för att filtrera.</li><li>Du kan välja mer än en ägare. Vilka ägare som är tillgängliga beror på vad som har gjorts i andra avsnitt på filterpanelen.</li><li>Siffrorna anger:<ul><li>4︎⃣: Antalet schemalagda projekt som är associerade med den specifika ägaren.</li></ul></li></ul> |


### Andra filter

| Andra filter | Beskrivning |
|---|---|
| ![Andra filter](/help/components/assets/scheduledprojects-filter-otherfilters.png){width="300"} | I avsnittet **[!UICONTROL Other filters]** kan du filtrera på andra fördefinierade filter.<ul><li>Du kan välja ett eller flera av följande alternativ:<ul><li> **[!UICONTROL Expired]**: Filtrera på inaktuella schemalagda projekt.</li><li>**[!UICONTROL Failed]**: Filtrera på schemalagda projekt som schemat har misslyckats för.</li></ul>Vad du kan välja beror på din roll och dina behörigheter.</li><li>Du kan markera mer än ett annat filter. Vilka andra filter som är tillgängliga beror på vilka markeringar du har gjort i andra avsnitt på filterpanelen.</li><li>Siffrorna anger:<ul><li>4︎⃣: Antalet schemalagda projekt som är associerade med det specifika andra filtret.</li></ul></li></ul> |


<!--
# Scheduled projects

Scheduled Analysis Workspace projects can be managed under **Analytics > Components > Scheduled Projects**.

When you manage scheduled projects, you can edit and delete recurring project schedules:

*  Change the file type (.csv or PDF)
*  Update the project description
*  Add or remove recipients
*  Change the frequency

To modify a scheduled project

1.  Select **Analytics > Components > Scheduled Projects**.
1.  Search for a schedule in the search bar or by using the filter options in the left rail. You can filter by [!UICONTROL Tags], [!UICONTROL Owners], [!UICONTROL Favorites], and more.

![Screenshot showing the scheduled projects list with the column displaying title, owner, tags, delivered to, and other columns described in the Available columns section.](assets/scheduled-project-manager2.png)

## Available columns

| Field | Description |
| --- | --- |
| [!UICONTROL Favorites] | Selecting the star icon makes this schedule a favorite. |
| [!UICONTROL Schedule ID] | This ID is used mainly for debugging purposes. |
| [!UICONTROL Title and description] | Title and description of this project. |
| [!UICONTROL Owner] | The person who created and owns the project. |
| [!UICONTROL Tags] | (optional) Tagging is a good way to organize projects. All users can create tags and apply one or more tags to a project. However, you can see tags only for those projects that you own or that have been shared with you.  |
| [!UICONTROL Delivered to] | The recipient(s) of this scheduled project. |
| [!UICONTROL Expiration date] | For any scheduled project frequency, you can set the expiration date for up to one year in the future. |
| [!UICONTROL Frequency] | How often you want to have this schedule project sent to the recipient(s). |
| [!UICONTROL Execution time] | At what time of day this scheduled project gets sent. |
| [!UICONTROL Number of queries] | The number of queries against this project. | 

## Common actions

The following are common actions in the Scheduled Projects manager:

|Action|Description|
|---|---|
|**[!UICONTROL Edit]**|Select the title of the schedule to update its delivery settings.|
|**[!UICONTROL Delete]**|Select the scheduled project in the list and then click Delete from the menu. This will delete the selected schedule for the project; the project itself will not be deleted.|
|**[!UICONTROL Tag]**|Select the scheduled project in the list and then choose "Tag" or "Approve" to organize your schedules and make them easier to search for.|
|**[!UICONTROL View failed schedules]**|Navigate to the left rail > Other filters > Failed to see schedules that have failed.|
|**[!UICONTROL View expired schedules]**|Navigate to the left rail > Other filters > Expired to see schedules that have expired. Click the title of the schedule to setup a new delivery schedule.|
|**[!UICONTROL View schedule ID]**|Navigate to column options in the top right and add the Schedule ID column to the table. The scheduled ID is often useful for debugging.|

The Scheduled Projects manager shows the items that a specific user created. If the user account is disabled in the application, all scheduled deliveries stop. Scheduled project ownership can be transferred to a new user under **Admin** > **Analytics Users & Assets** > **Transfer Assets**.
-->