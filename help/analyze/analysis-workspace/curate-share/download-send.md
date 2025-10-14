---
description: Läs om de olika möjligheterna att hämta data från ditt Analysis Workspace-projekt.
title: Hämta projekt och data
feature: Curate and Share
role: User, Admin
exl-id: 085013dc-8263-4fc8-9492-99f0ecadf14b
source-git-commit: 281dbf68c7a3f1afc35d775c731904bd9c413d6a
workflow-type: tm+mt
source-wordcount: '1091'
ht-degree: 0%

---


# Hämta projekt och data

Du kan hämta Analysis Workspace-projekt och data till din lokala enhet. Den här hämtningen kan vara kopierade data, en CSV-fil (kommaavgränsade data) eller ett PDF-dokument (portabla dokumentformat).

* Välj alternativet PDF om du vill att visualiseringar ska ingå i den hämtade filen.
* Välj CSV och kopierade dataalternativ om du bara behöver textdata.

Ytterligare metoder för att exportera Adobe Analytics-data beskrivs i [exportguiden](/help/export/home.md).

## Hämta ett projekt som en PDF- eller CSV-fil {#download-project}

![Listrutan Projekt med alternativen Hämta CSV och Hämta PDF markerade.](assets/download-project.png)

### Hämta ett projekt som en PDF-fil

Tänk på följande när du hämtar ett projekt som PDF:

* Lämna inte projektet förrän projektet har laddats ned till din arbetsstation. Nedladdningen kan ta flera minuter eftersom projektet körs på Adobe-servrar igen för att PDF ska kunna återge. Du kan fortsätta att ändra projektet medan hämtningen återger. Om det tar längre tid än fem minuter att återge en PDF uppmanas du att [skicka PDF](../curate-share/send-schedule-files.md) via e-post i stället.
* Hämtningar återges som en sida utan sidnumrering.
* PDF innehåller det som visas på webbläsarsidan i Analysis Workspace. Om du vill undvika trunkerat innehåll väljer du ![Ändra storlek](/help/assets/icons/Resize.svg) för att automatiskt ändra storlek på visualiseringar eller paneler i anpassad storlek.
* [Det går att klicka på hyperlänkar](/help/analyze/analysis-workspace/visualizations/freeform-table/freeform-table-hyperlinks.md) i frihandstabeller i den hämtade PDF-filen.

Så här hämtar du ett projekt som en PDF-fil:

1. Välj **[!UICONTROL Project]** > **[!UICONTROL Download PDF]**.

   Ett grönt fält visas med följande meddelande: ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) **[!UICONTROL Your download has been requested. Please wait.]**

1. När nedladdningen är klar visas ett grönt fält med följande meddelande: ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) **[!UICONTROL *Projektets namn *PDF är klart.]**

1. Välj **[!UICONTROL Download]** i det gröna fältet.

   Beroende på inställningarna i webbläsaren hämtas PDF automatiskt till den mapp som du tidigare konfigurerat, eller så uppmanas du att välja en mapp där PDF ska hämtas.

   Filnamnet består av *projektnamn* - *rapportsvitens namn* - *datum*. Exempel: `Example Project - Omni-Channel - Luma - Jun 30, 2025.pdf`.

### Hämta ett projekt som en CSV-fil

1. Välj **[!UICONTROL Project]** > **[!UICONTROL Download CSV]**.

   Beroende på inställningarna i webbläsaren hämtas CSV-filen automatiskt till en mapp som du tidigare konfigurerat, eller så uppmanas du att välja en mapp där CSV-filen ska hämtas.

   Filnamnet består av *projektnamn* - *rapportsvitens namn* - *datum*. Exempel: `Example Project - Omni-Channel - Luma - Jun 30, 2025.csv`.

## Kopiera data inom en visualisering till Urklipp {#copy-data}

Med alternativet **[!UICONTROL Copy to clipboard]** på snabbmenyn kan du snabbt kopiera data från Analysis Workspace och klistra in data i ett verktyg från tredje part.

* Om du vill att tabelldata som visas ska kopieras markerar du tabellrubriken och väljer **Kopiera data till Urklipp** på snabbmenyn.
* Om du vill att en delmängd av data ska kopieras markerar du den i tabellen och väljer **Kopiera markering till Urklipp** på snabbmenyn.

>[!TIP]
>
>Du kan använda snabbtangenten **_cmd + c_** (macOS) eller **_ctrl + c_** (Windows) för att kopiera ditt val till Urklipp. Använd sedan **_cmd + v_** (macOS) eller **_ctrl + v_** (Windows) för att klistra in data.


![Alternativet Kopiera markering till Urklipp. &#x200B;](assets/copy-clipboard.png){zoomable="yes"}

## Hämta data i en visualisering som en CSV-fil {#download-data}

Med alternativen för att hämta som CSV på snabbmenyn kan du hämta en datatabell eller datakällan för en visualisering som en CSV-fil.

Så här gör du:

* Välj **[!UICONTROL Download data as CSV]** på snabbmenyn i en tabell eller visualisering. Detta hämtar visade data i tabellen eller den underliggande datakällan för en visualisering som en CSV-fil.

<!-- Only relevant as soon as CJA supports Map visualization 
  >[!NOTE]
  >
  >  Note: the Map visualization does not support this option.
-->

* Välj **[!UICONTROL Download selection as CSV]** på snabbmenyn i en tabell. Endast markeringen laddas ned med det här alternativet, i motsats till den fullständiga tabellen som visas.

![Alternativet Hämta data som CSV.](assets/download-data-as-csv.png)

## Hämta objekt som en CSV-fil {#download-items}

Om du vill analysera fler än de 400 synliga dataraderna i en tabell väljer du **Hämta objekt som CSV (_Dimension name_)** på snabbmenyn för tabellhuvudet eller på en rad. Med det här alternativet exporteras upp till 50 000 dimensionsobjekt (baserat på tabellsortering) för den valda dimensionen med sorteringsalternativ och filter. Om du väljer det här alternativet överst i tabellen exporteras den första dimensionen i tabellen.

![Alternativet Hämta objekt som CSV (sida).](assets/download-items-as-csv.png)

Inga begränsningar används i frihandstabellen. För att få optimala prestanda bör du använda det här alternativet i tabeller med färre än 20 kolumner.

>[!TIP]
>
> Om din dimension överstiger 50 000 objekt hämtar du filen med olika sorteringsvärden eller använder ett segment. Du kan t.ex. sortera efter besök i en nedladdning och sedan stigande efter besök i en andra nedladdning. Det här tipset kan hjälpa dig att hämta objekt med längre svans.

Du kan utföra flera uppgifter samtidigt i projektet och till och med navigera till ett nytt Workspace-projekt på samma flik medan hämtningen pågår. Hämtningen pausas om du öppnar en ny flik i webbläsaren. Hämtningen avbryts om du lämnar Workspace helt eller stänger webbläsarfliken.


### Nedladdad objektfil {#items-file}

Följande funktioner i en frihandstabell används i den hämtade filen:

* Alla panelsegment används som filter.
* Uppdelningar **ovanför** den valda dimensionen i tabellen används som filter ovanför varje kolumn.
* Uppdelningar **nedanför** av den valda dimensionen i tabellen tas bort.

![Den hämtade CSV-filen som öppnats i Excel.](assets/download-items-file.png)

### Hämta meddelanden {#notifications}

När filen laddas ned visas följande meddelanden:

* Ett blått **[!UICONTROL _tabellnamn _-_Dimension _.csv har begärts._x _% slutfört]**&#x200B;anger förloppet. Om du vill avbryta hämtningen väljer du **[!UICONTROL Cancel download]**. Välj ![CrossSize100](/help/assets/icons/CrossSize100.svg) om du vill stänga meddelandet, som inte avbryter hämtningen.
* Ett grönt **[!UICONTROL _tabellnamn _-_Dimension _.csv har hämtats]**&#x200B;meddelande om slutförd filhämtning. Filen hämtas till den nedladdningsmapp som är konfigurerad för webbläsaren.

Om du begär mer än en nedladdning åt gången får du ett meddelande om att varje ytterligare nedladdning är i kö tills den tidigare nedladdningen är klar.


## Vanliga frågor och svar {#faq}

| Fråga | Svar |
| --- | --- |
| Varför består min nedladdade PDF av bara en sida? | Funktionen [Hämta PDF](#download-as-csv-or-pdf) numrerar inte hämtade PDF-filer. |
| Kan jag exportera mer än 50 000 objekt med alternativet **[!UICONTROL Download items as CSV]**? | Varje nedladdning kan innehålla upp till 50 000 dimensionsobjekt, men du kan ändra sorteringsordningen i tabellen för att hämta längre slutobjekt eller använda ett filter för att hämta mer specifika objekt. |
| Vad gör **[!UICONTROL Copy visualization]**? | Till skillnad från [!UICONTROL **Kopiera data till Urklipp**] eller [!UICONTROL **Kopiera markering till Urklipp**] är snabbmenyalternativet **[!UICONTROL Copy visualization]** inte ett exportalternativ. Med det här alternativet kan du [kopiera en visualisering](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md#context-menu) eller [kopiera en panel](/help/analyze/analysis-workspace/c-panels/panels.md#context-menu) från en plats i Workspace till en annan. Exempel: från en panel till en annan i samma projekt, eller från ett projekt till ett annat projekt. |



<!--

# Download 

There are several ways to export data from Analysis Workspace. The method you choose depends on what set of data you want to analyze and who needs to access it.

Exported data can be in the form of copied data, CSV, or PDF. A PDF is typically preferred if you want visualizations included in the file. CSV and copied data is preferred if you simply want plain-text data.

## Download a project as CSV or PDF {#download-project}

Consider the following when downloading projects:

* When downloading projects as a CSV or PDF, the project can be saved or unsaved when you request a project download. However, only saved projects can be [scheduled](/help/analyze/analysis-workspace/curate-share/t-schedule-report.md). 

* When downloading projects as a PDF:
  * Downloads can take several minutes to export because the project is re-run on Adobe servers before rendering in PDF format. We recommend not leaving the project until the PDF downloads in your browser. However, you can continue to make changes to the project while you wait. If a PDF takes longer than 5 minutes to render, you will be prompted to email it instead.
  * Downloads are rendered as a single page with no pagination applied.
  * PDF renderings contain what is on the page in Workspace. If a project has custom-sized visualizations and panels, you need to change them to be auto-sized (button in top-right corner) so that there will be no truncated content.
  * Any [hyperlinks](/help/analyze/analysis-workspace/visualizations/freeform-table/freeform-table-hyperlinks.md) that exist within freeform tables are not functional in the downloaded PDF. 

To download a project as a CSV or PDF file:

1. Do either of the following, depending on what format you want to download the project in:

   * **PDF:** Select **[!UICONTROL Project]** > **[!UICONTROL Download PDF]**.

     Choose this option if you want the downloaded file to contain all the displayed (visible) tables and visualizations in the project.

   * **CSV:** Select **[!UICONTROL Project]** > **[!UICONTROL Download CSV]**. 

     Choose this option if you want plain-text data.

   ![](assets/download-project.png)

1. (Conditional) If you chose to download a PDF, a message is shown after the project is ready to be downloaded. Click [!UICONTROL **Download**].
1. Click the **[!UICONTROL Download this file]** icon and save the file to a folder of your choice.

## Copy data to clipboard (hotkey: cmd + c) {#copy-data}

The right-click option **[!UICONTROL Copy to clipboard]** lets you quickly copy data from Workspace and paste it in a third-party tool. 

* If you want the displayed table copied, right-click the table header and choose **Copy data to clipboard**. 
* If you want a subset of data copied, make a selection in the table and then right-click > **Copy selection to clipboard**.

>[!TIP]
>
>You can use the hotkey `Ctrl+C` to copy your selection to the clipboard, then use `Ctrl+V` to paste it into a third-party tool.

![](assets/copy-selection.png)

## Download data as CSV {#download-data}

The right-click option **[!UICONTROL Download data as CSV]** allows you to download a table of data or the data source of any visualization as a CSV.

* From the header of any table or visualization, right-click and choose **[!UICONTROL Download data as CSV]**. This downloads the displayed data in the table or the underlying data source for a visualization as a CSV. 

  >[!NOTE]
  >
  >  Note: the Map visualization does not support this option.

* Within a table, right-click and choose **[!UICONTROL Download selection as CSV]**. Only the selection is downloaded with this option, as opposed to the full, displayed table.

![](assets/download-data-viz.png)

## Download items as CSV {#download-items}

If you want to analyze more than the visible 400 rows of data in a table, right-click the table header or any row and select **Download items as CSV (_Dimension name_)**. This option exports up to 50,000 dimension items (based on the table sort) for the selected dimension, with filters and segments applied. If you chose this option from the top of the table, the first dimension in the table will be exported. While no limits are enforced in the freeform table, it is recommended that the Download items option be used in tables with less than 20 columns to ensure optimal performance.

>[!TIP]
>
> If your dimension exceeds 50,000 items, download the file with different sort metrics applied or apply a filter. For example, sort descending by Visits in one download and then ascending by Visits in a second download. This tip can help you retrieve longer-tail items.

You can multi-task within the project and even navigate to a new Workspace project in the same tab while the download is in progress. The download pauses if you open a new browser tab. The download is canceled if you leave Workspace completely or close the browser tab.

![](assets/download-items.png)

### Downloaded items file 

Features of the table will be applied to the downloaded file as follows:

* All panel segments are applied as filters.
* Breakdowns **above** the selected dimension in the table are applied as filters above each column. 
* Breakdowns **below** the selected dimension in the table are removed.

In the example above, Page items are downloaded with the panel segment (New Visitors Customers) and components above (Marketing Channel = Email) applied as filters, and the components below (Mobile Device Type) removed from the downloaded CSV.

![](assets/downloaded-file.png)

### Download notifications

As the file downloads, you will see an informational notification with the progress. At any time, you can cancel the download by clicking **[!UICONTROL Cancel download]**. Closing the toast **will not** cancel the download. 

Once the file completes, you will see a completion notification and the file will download to your browser.

If you request more than one download at a time, you will receive a notification that each additional download will be queued until the prior download completes.

![](assets/toast.png)

## FAQ {#faq}

| Question | Answer |
| --- | --- |
| Why is my downloaded PDF one page? | Workspace does not paginate downloaded PDFs at this time. |
| Can I export more than 50,000 items with the "Download items as CSV" option? | While each download can contain up to 50,000 dimension items, you can change the sort of your table to retrieve longer tail items, or apply a filter to download more specific items. |
| What does **[!UICONTROL Copy visualization]** do? | Unlike [!UICONTROL **Copy data to clipboard**] or [!UICONTROL **Copy selection to clipboard**], the **[!UICONTROL Copy visualization]** right-click option is not an export option. It allows you to copy a visualization or panel from one place in Workspace to another. For example, from one panel to another in the same project, or from one project to another project. [Intra-linking video](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/visualizations/intra-linking-in-analysis-workspace.html?lang=sv-SE) |

-->