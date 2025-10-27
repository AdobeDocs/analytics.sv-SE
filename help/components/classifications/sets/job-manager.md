---
title: Klassificeringsjobbshanteraren
description: Lär dig hur du visar aktuella och slutförda klassificeringsjobb som genereras från klassificeringsuppsättningar.
exl-id: 0470e131-79c6-4906-85f0-530d360ac227
feature: Classifications
source-git-commit: 2ced7cd61c4119347be2ef0fba9b8d60ee6c4df2
workflow-type: tm+mt
source-wordcount: '565'
ht-degree: 0%

---

# Visa och agera på klassificeringsjobb

Klassificeringsjobbhanteraren visar aktuella och slutförda klassificeringsjobb som genereras för klassificeringsuppsättningar. Du kan också använda hanteraren för att hämta klassificeringsdata eller mallar för ett visst jobb.

Så här visar och agerar du på klassificeringsjobb:


1. Välj **[!UICONTROL Components]** i Adobe Analytics övre menyrad och välj sedan **[!UICONTROL Classification sets]**.
1. I **[!UICONTROL Classification Sets]** väljer du fliken **[!UICONTROL Jobs]**.

## Hanterare för klassificeringsjobb

Hanteraren **[!UICONTROL Classification Sets - Jobs]** har följande gränssnittselement:

![Klassificeringsuppsättningar - Jobbhanteraren](manage/assets/classifications-sets-jobs.png)



### Lista över klassificeringsjobb

**[!UICONTROL Classification Jobs]**-listan ➊ visar klassificeringsjobb. Listan innehåller följande kolumner:

| Kolumn | Beskrivning |
|---|---|
| **[!UICONTROL Job Id]** | Identifieraren för klassificeringsjobbet. |
| **[!UICONTROL Classification Set]** | Klassificeringsuppsättningen som är associerad med klassificeringsjobbet. |
| **[!UICONTROL Size]** | Storleken på filen som exporterades eller importerades som en del av klassificeringsjobbet. |
| **[!UICONTROL Status]** | Klassificeringsjobbets status. Möjliga värden är: **[!UICONTROL Created]**, **[!UICONTROL Queued]**, **[!UICONTROL Validated]**, **[!UICONTROL Failed validation]**, **[!UICONTROL Processing]**, **[!UICONTROL Done processing]**, **[!UICONTROL Failed processing]**, **[!UICONTROL Completed]** eller **[!UICONTROL Progress]**. Om den visas för du markören över aviseringen ![Varning](/help/assets/icons/Alert.svg) för att visa ytterligare information. |
| **[!UICONTROL File Name]** | Identifierar namnet eller funktionaliteten som används för att importera eller exportera filen som en del av klassificeringsjobbet. Möjliga värden är: <ul><li>*inget värde*</li><li>Namnet på filen som bearbetas som en del av klassificeringsjobbet.</li><li>**[!UICONTROL SAINT Export]**: Jobbet är en export från det [gamla klassificeringsgränssnittet](/help/components/classifications/importer/c-working-with-saint.md).</li><li>**[!UICONTROL export for _klassificeringsuppsättningen _vid_timestamp_]**: Jobbet är en hämtning från gränssnittet [schema](manage/schema.md#download).</li></ul> |
| **[!UICONTROL Job Type]** | Typ av klassificeringsjobb. Möjliga värden är: **[!UICONTROL Import]** eller **[!UICONTROL Export]**. |
| **[!UICONTROL Source]** | Källan till klassificeringsjobbet. Möjliga värden är: **[!UICONTROL Web API]**, **[!UICONTROL Direct API Upload]**, **[!UICONTROL Adobe]**, **[!UICONTROL SAINT]** eller **[!UICONTROL Unknown]**. |
| **[!UICONTROL Modified Lines]** | Antalet ändrade rader som klassificeringsjobbet ändrade. |
| **[!UICONTROL Total Lines]** | Antalet rader som klassificeringsjobbet bearbetade. |
| **[!UICONTROL Completion Time]** | Slutförandetiden för klassificeringsjobbet. |
| **[!UICONTROL File Download]** | Använd ![Hämta](/help/assets/icons/Download.svg) för att hämta filen (mallen eller data) som är associerad med klassificeringsjobbet. |

Om du vill ändra storlek på en kolumn i listan över klassificeringsjobb kan du:

* Håll pekaren över kolumnavgränsaren och dra kolumnavgränsaren till önskad kolumnbredd.
* Välj ![SparrNed](/help/assets/icons/ChevronDown.svg) och välj **[!UICONTROL Resize column]**. Med en lodrät linje med storleksknappen kan du ändra storlek på kolumnen till det önskade med.

Sortera en kolumn i listan över klassificeringsjobb

* Välj ![SparrNed](/help/assets/icons/ChevronDown.svg) och välj **[!UICONTROL Sort Ascending]** eller **[!UICONTROL Sort Descending]**. En pil ( ↑ ↓) visar vilken kolumn och hur kolumnen sorteras.


### Sökning och knappar

I området ➋ ovanför listan över klassificeringsjobb kan du:

* Sök i ![Sök](/help/assets/icons/Search.svg) efter klassificeringsjobb. Resultat visas i listan över klassificeringsjobb. Välj ![CrossSize200](/help/assets/icons/CrossSize200.svg) för att rensa sökningen.
* Ta bort alla filter som används i listan över klassificeringsjobb. Välj ![CrossSize100](/help/assets/icons/CrossSize100.svg) om du vill ta bort ett filter.
* Välj ![MoreCircle](/help/assets/icons/MoreCircle.svg) om du vill läsa in ytterligare 1 000 klassificeringsjobb. Inledningsvis visas upp till 1 000 klassificeringsjobb i listan över klassificeringsuppsättningar.
* Definiera kolumnerna i listan med klassificeringsuppsättningar. Välj ![Kolumninställning](/help/assets/icons/ColumnSetting.svg) och markera de kolumner som ska visas under **[!UICONTROL Customize table]** i dialogrutan **[!UICONTROL Select columns to show]**. Välj **[!UICONTROL Apply]** om du vill använda kolumninställningarna.



### Panelen Filter

Välj ![Filter](/help/assets/icons/Filter.svg) om du vill visa filterpanelen ➌ som gör att du kan filtrera listan med klassificeringsjobb. Du kan filtrera på:

* **[!UICONTROL Classification Set]**. Välj en eller flera klassificeringsuppsättningar för att filtrera listan över klassificeringsjobb.
* **[!UICONTROL Completion Time]**. Välj ett av de möjliga värdena för att filtrera listan över klassificeringsjobb när de är klara.
* **[!UICONTROL Status]**. Välj ett av de möjliga värdena för att filtrera listan över klassificeringsjobb efter status.
* **[!UICONTROL Job Type]**. Välj ett av de möjliga värdena för att filtrera listan över klassificeringsjobb på jobbtyp.
* **[!UICONTROL Source]**. Välj ett av de möjliga värdena för att filtrera listan över klassificeringsjobb på källan.


Välj ![Filter](/help/assets/icons/Filter.svg) **[!UICONTROL Hide filters]** om du vill dölja filterpanelen.

Observera att de filter som visas på filterpanelen återspeglar alternativen för de klassificeringsjobb som är förinlästa.


<!--

**[!UICONTROL Components]** > **[!UICONTROL Classification sets]** > **[!UICONTROL Jobs]**

You cannot create jobs from this interface. Create jobs by uploading data to a classification set (either manually or through a configured external location), requesting a download file, or requesting a template file.

## Filter classification sets

The left side of the Classification set job manager provides filter settings to locate the desired job. Clicking the filter icon toggles the filter settings visibility. You can filter Classification sets by **[!UICONTROL Classification set]**, **[!UICONTROL Completion time]**, **[!UICONTROL Status]**, **[!UICONTROL Job Type]**, or **[!UICONTROL Source]**.

![Classification set job filters](../assets/classification-set-job-filters.png)

Additional filter options are available above the Classification set job manager columns:

* **[!UICONTROL Search by title]**: Search for jobs by filename.
* **[!UICONTROL Load more]**: The Classification set job manager initially displays up to 1000 jobs. If more jobs exist, click this button to load 1000 more jobs.
* **Show/Hide columns**: Toggle visibility for any column besides [!UICONTROL Filename] and [!UICONTROL Completion time].

## Classification set job manager columns

The following columns are available in the Classification set job manager:

* **[!UICONTROL Filename]**: The name of the upload or download file.
* **[!UICONTROL Classification set]**: The name of the Classification set that the file applies to. You can click the Classification set name to reach the Classification set's [Settings](manage/settings.md).
* **[!UICONTROL Size]**: The size of the file.
* **[!UICONTROL Status]**: The status of the job processing the file.
  * **[!UICONTROL Created]**: The job was submitted.
  * **[!UICONTROL Queued]**: The file is ready to be processed, and is waiting for a classification server to process the file.
  * **[!UICONTROL Validated]**: The file is valid and is waiting to be processed.
  * **[!UICONTROL Failed validation]**: The file is formatted incorrectly or otherwise invalid. The file does not go through processing.
  * **[!UICONTROL Processing]**: The file is actively being processed by Adobe.
  * **[!UICONTROL Failed processing]**: The file failed processing.
  * **[!UICONTROL Complete]**: Processing is complete. Classification data is visible in reporting.
  * **[!UICONTROL Failed]**: Generic failure not related to validation or processing.
* **[!UICONTROL Job type]**: The type of job.
* **[!UICONTROL Source]**: The job source.
* **[!UICONTROL File download]**: Only applies to download jobs, such as downloading classification data or downloading templates. When a download is ready, this column provides a download link.
* **[!UICONTROL Modified lines]**: The number of modified lines.
* **[!UICONTROL Completed lines]**: The number of completed lines.
* **[!UICONTROL Completion time]**: The date and time that the job completed (or failed).
-->