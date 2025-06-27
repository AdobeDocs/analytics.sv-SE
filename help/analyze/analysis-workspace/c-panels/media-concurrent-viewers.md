---
title: Media Concurrent Viewers Panel
description: Lär dig hur du använder och tolkar panelen Media Concurrent Viewer i Analysis Workspace.
feature: Panels
role: User, Admin
exl-id: 29575b51-e319-4156-9834-aa0b671afb31
source-git-commit: 978bd8642011dd2c8e43564c90303f194689a64e
workflow-type: tm+mt
source-wordcount: '1194'
ht-degree: 0%

---


# Panelen Medievisningsprogram för samtidig användning {#media-concurrent-viewers-panel}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_mediaconcurrentviewers_button"
>title="Medievisningsprogram för samtidig användning"
>abstract="Skapa en panel för att analysera den genomsnittliga minuten-publiken för visst innehåll, eller under en viss tidsperiod."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_mediaconcurrentviewers_panel"
>title="Medievisningsprogram för samtidig användning"
>abstract="Analysera samtidiga visningsprogram över tid, visa samtidighet vid toppmöten eller dela upp och jämföra.<br/><br>**Kornighet**: Välj en tidsperiod om du vill visa samtidiga visningsprogram efter.<br/>**Panelsammanfattningsnummer**:<br/>Alternativ för att visa sammanfattningsnummer med datum- och tidsinformation för varje rad. Maximal visar detaljer för maximal samtidighet. Minimivärdet visar information om dalvärdet.<br/>**Serieuppdelning (valfritt)**: Dela upp visualisering efter segment, dimensioner, dimensionsobjekt eller datumintervall. Visa upp till 10 rader i taget. Uppdelningarna begränsas till en enda nivå."

<!-- markdownlint-enable MD034 -->


>[!BEGINSHADEBOX]

_Den här artikeln visar panelen Medievisningsprogram för samtidig användning i_ ![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _&#x200B;**Adobe Analytics Analytics**._<br/>_Se [Panelen för visningsprogram för samtidiga media](https://experienceleague.adobe.com/sv/docs/analytics/analyze/analysis-workspace/panels/media-concurrent-viewers) för_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _&#x200B;**Customer Journey Analytics**-versionen av den här artikeln._

>[!ENDSHADEBOX]


>[!NOTE]
>
>Den genomsnittliga minuten-panelen för media är endast tillgänglig för kunder som har köpt tillägget Streaming Media Collection för Adobe Analytics.
>
>Kontakta din Adobe-säljare eller Adobe-kontogrupp om du vill ha mer information.
>

Panelen **[!UICONTROL Media concurrent viewers]** gör det möjligt att analysera samtidiga visningsprogram över tid, med information om maximal samtidighet och möjlighet att dela upp och jämföra.

Ni kan analysera samtidiga visningsprogram för att förstå var maximal samtidighet inträffade eller var bortfall inträffade för att ge värdefull insikt i innehållets och visningsprogrammets kvalitet. Och för att hjälpa till med felsökning eller planering av volym eller skala.

I Analysis Workspace är indikatorn för Concurrent viewers antalet unika personer som visar medieströmmarna vid en viss tidpunkt, oavsett antalet sessioner.


>[!BEGINSHADEBOX]

En demonstrationsvideo finns i ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Panelen Medievisningsprogram för samtidig användning](https://video.tv.adobe.com/v/330177?quality=12&learn=on){target="_blank"} .

>[!ENDSHADEBOX]



## Använd

Så här använder du en **[!UICONTROL Media concurrent viewers]**-panel:

1. Skapa en **[!UICONTROL Media concurrent viewers]**-panel. Mer information om hur du skapar en panel finns i [Skapa en panel](panels.md#create-a-panel).

1. Se till att du väljer en datavy för panelen som har konfigurerade komponenter från den direktuppspelande mediesamlingen.

1. Ange [indata](#panel-input) för panelen.

1. Observera [utdata](#panel-output) för panelen.

### Panelindata

Du kan konfigurera panelen för visningsprogram för parallella media med följande indatainställningar:

| Inställning | Beskrivning |
|---|---|
| **[!UICONTROL Panel date range]** | Panelens datumintervall är som standard Idag.  Du kan redigera den för att visa en enstaka dag eller flera månader i taget. <br> <br>Den här visualiseringen är begränsad till 1 440 datarader (till exempel 24 timmar vid granularitet på minutnivå).  Om ett datumintervall och en granularitetskombination resulterar i mer än 1 440 rader uppdateras granulariteten automatiskt för att passa det fullständiga datumintervallet. |
| **[!UICONTROL Granularity]** | Granularitetsstandardvärdet är Minut.<br>Den här visualiseringen är begränsad till 1 440 datarader (till exempel 24 timmar vid granularitet på minutnivå).  Om ett datumintervall och en granularitetskombination resulterar i mer än 1 440 rader uppdateras granulariteten automatiskt för att passa det fullständiga datumintervallet. |
| **[!UICONTROL Panel summary numbers]** | Det finns en sammanfattning av datum- och tidsinformation för samtidiga visningsprogram. Maximal visar detaljer för maximal samtidighet. **[!UICONTROL Minimum]** visar information om dalvärdet.  Som standard visas bara Maximum, men du kan ändra den till Minimum eller både Maximum och Minimum.<br><br>Om du använder uppdelningar visas ett summeringsnummer för varje. |
| **[!UICONTROL Series breakdown]** | Du kan även dela upp visualiseringen med filter, dimensioner, dimensionsobjekt eller datumintervall.<br>Du kan visa upp till 10 rader i taget. Uppdelningarna begränsas till en enda nivå.<br>När du drar en dimension markeras de översta dimensionsobjekten automatiskt baserat på det valda panelens datumintervall.<br>Om du vill jämföra datumintervall drar du 2 eller fler datumintervall till serieuppdelningsfiltret. |

Här är ett exempel på panelen som konfigurerats för **[!UICONTROL Minute]** granularitet, med **[!UICONTROL Maximum only]** sammanfattningsnummer. Och bruten av **[!UICONTROL Other]**, **[!UICONTROL Table]**, **[!UICONTROL Mobile Phone]**, **[!UICONTROL Gaming Console]**, **[!UICONTROL Media Player]**, **[!UICONTROL Set-top Box]**, **[!UICONTROL Television]**.

![Serieuppdelningsvyn i Media Concurrent Viewer med 7 av 10 dimensioner, segment eller datumintervall.](assets/concurrent-viewers-series-breakdown.png)

### Panelutdata

Panelen Media Concurrent Viewer returnerar ett linjediagram och sammanfattningsnummer som innehåller information om maximalt och/eller lägsta antal samtidiga visningsprogram.  Längst upp på panelen finns en sammanfattningsrad som påminner om de panelinställningar du har valt.

Välj när som helst ![Redigera medievyn för samtidig användning](/help/assets/icons/Edit.svg) för att redigera och återskapa panelen.

Om du väljer en seriebrytning visas en rad i linjediagrammet och ett sammanfattningsnummer för varje rad:

![Media Concurrent Viewer-utdata.](assets/concurrent-viewers-output.png)

### Datakälla

Det enda mätvärdet som kan användas på den här panelen är **[!UICONTROL Concurrent viewers]**:

| Mått | Beskrivning |
|---|---|
| **[!UICONTROL Concurrent viewers]** | Antalet unika personer som visar medieströmmarna vid en viss tidpunkt, oavsett antalet sessioner. |

Det finns ingen friformstabell i den här vyn.  Om du vill visa datakällan kan du hämta datakällan från snabbmenyn för visualisering av linjediagram och välja **[!UICONTROL Download data as CSV]**.  Serieuppdelningar ingår.

![Alternativen för Concurrent viewers-utdata med&quot;Download data as CSV&quot; markerat.](assets/concurrent-viewers-download-csv.png)

## Vanliga frågor

| Fråga | Svar |
|---|---|
| Var är friformsregistret? Hur ser jag datakällan? | Frihandsregistret är inte tillgängligt i den här vyn.  Du kan hämta datakällan från snabbmenyn för linjediagram och välja **[!UICONTROL Download data as CSV]**. |
| Varför ändrades min granularitet? | Den här visualiseringen är begränsad till 1 440 datarader (till exempel 24 timmar vid granularitet på minutnivå).  Om ett datumintervall och en granularitetskombination resulterar i mer än 1 440 rader uppdateras granulariteten automatiskt för att passa det fullständiga datumintervallet.<br><br>När du ändrar från ett större datumintervall till ett mindre uppdateras granulariteten till den lägsta detaljnivån som tillåts när datumintervallet ändras. Om du vill visa en högre granularitet redigerar du panelen och återskapar den. |
| Hur jämför jag videonamn, filter, innehållstyper och annat? | Om du vill jämföra dessa objekt i en enda visualisering drar du filter, dimensioner eller specifika dimensionsobjekt i serieuppdelningsfiltret.<br><br>Vyn är begränsad till tio uppdelningar.  Om du vill visa mer än 10 måste du använda flera paneler. |
| Hur jämför jag datumintervall? | Om du vill jämföra datumintervall i en enda visualisering använder du serieuppdelningarna genom att dra två eller flera datumintervall.  Datumintervallen åsidosätter panelens datumintervall. |
| Hur ändrar jag visualiseringstypen? | På den här panelen kan du endast använda linjevisualisering för tidsserien. |
| Kan jag köra avvikelseidentifiering? | Nej.  Anomalsidentifiering är inte tillgängligt för den här panelen. |
| Varför använda unika personer istället för aktiva sessioner? | Genom att använda unika personer kan du ta bort oönskade toppar vid visningsgränserna (där sessionerna avslutas och börjar samtidigt). |
| Vad innebär det att ha samtidiga visningsprogram med högre granularitet än en minut? | Med en granularitet som är större än en minut är samtidiga visningsprogram summan av unika samtidiga visningsprogram för alla minuter inom det tidsintervallet.  På timnivå är till exempel samtidiga visningsprogram summan av unika samtidiga visningsprogram för alla minuter inom timmen. |
| Visar arbetsytan samma information som rapporten Samtidiga visningsprogram? | Nej.  I Analysis Workspace definieras mätvärdet för Concurrent viewers som antalet unika personer som visar medieströmmen vid en viss tidpunkt. Oavsett antalet sessioner.<br><br>Det här måttet skiljer sig från Concurrent Viewer-rapportering i avsnittet Rapporter, där Concurrent Active Sessions används. Med unika personkonton kan du ta bort oönskade toppar vid visningsgränserna (där sessionerna avslutas och börjar samtidigt). |

<!-- For more information about Media Concurrent Viewers, visit [MA doc page]( https://url). -->


>[!MORELIKETHIS]
>
>[Skapa en panel](/help/analyze/analysis-workspace/c-panels/panels.md#create-a-panel)
>&#x200B;>[Medieuppspelningstid för panelen ](media-playback-time-spent.md)
>&#x200B;>[Medie - genomsnittlig minutmålspanel](average-minute-audience-panel.md)
>
<!--
# Media Concurrent Viewers panel

Customers who have purchased the Streaming Media Collection Add-on can analyze concurrent viewers to understand where peak concurrency occurred or where drop-offs happened to provide valuable insight into the quality of content and viewer engagement, and to help with troubleshooting or planning for volume or scale.

In Analysis Workspace, Concurrent Viewers is the number of unique visitors viewing your media stream(s) at a specific point in time, regardless of the number of sessions.

The Media Concurrent Viewers panel enables analysis of concurrent viewers over time, with details on peak concurrency and the ability to break down and compare.  To access the Media Concurrent Viewers panel, navigate to a report suite with streaming media components enabled. Then, click the panel icon on the far-left and drag the panel into your Analysis Workspace project.

Here is a video overview of this panel:

>[!VIDEO](https://video.tv.adobe.com/v/330177/?quality=12)

## Panel Inputs {#Input}

You can configure the Media Concurrent Viewers panel using these input settings:

|Setting|Description|
|---|---|
|Panel date range|The panel date range default is Today.  You may edit it to view a single day or many months at a time. <br> <br>This visualization is limited to 1440 rows of data (for example, 24-hours at minute-level granularity).  If a date range and granularity combination results in more than 1440 rows, the granularity is automatically updated to accommodate the full date range.|
|Granularity|The granularity default is Minute. <br> <br>This visualization is limited to 1440 rows of data (for example, 24-hours at minute-level granularity).  If a date range and granularity combination results in more than 1440 rows, the granularity is automatically updated to accommodate the full date range.|
|Panel summary numbers| To see date or time details for concurrent viewers, a summary number is available. The Maximum shows details for peak concurrency. The Minimum shows details for the trough.  The panel default shows Maximum only, but you can change it to show Minimum or both Maximum and Minimum.<br><br>If you are using breakdowns, a summary number is displayed for each.|
|Series breakdown| Optionally, you can break down your visualization by segments, dimensions, dimension items, or date ranges. <br><br>- You may view up to 10 lines at a time. Breakdowns are limited to a single level.<br><br>- When dragging a dimension, the top dimension items will be automatically selected based on the selected panel date range.<br><br>- To compare date ranges, drag 2 or more date ranges into the series breakdown filter.|

### Default view

![Default view](assets/concurrent-viewers-default.png)


### Series breakdown view

![series breakdown view](assets/concurrent-viewers-series-breakdown.png)

## Panel Output {#Output}

The Media Concurrent Viewers panel returns a line chart and summary numbers to include details for the maximum and/or minimum concurrent viewers.  At the top of the panel, a summary line is provided to remind you of the panel settings you selected.

At any time, you can edit and rebuild the panel by clicking the edit pencil on the top right.

If you selected series breakdown, a line on the line chart and a summary number is displayed for each:

![concurrent viewers output](assets/concurrent-viewers-output.png)

### Data Source

The only metric that can be used in this panel is Concurrent Viewers:

|Metric|Description|
|---|---|
|Concurrent Viewers| Number of unique visitors viewing your media stream(s) at a specific point in time, regardless of the number of sessions.<br><br>This is different than Concurrent Viewer reporting in the Reports section, which uses Concurrent Active Sessions.  Using unique visitors accounts for removal of unwanted 'spikes' at show boundaries (where sessions are ending and starting at the same time).|

A Freeform table is not available in this view.  In order to view the data source, you may right-click on the line chart and download as a .csv file.  Series breakdowns will be included.


![concurrent viewers output](assets/concurrent-viewers-download-csv.png)

## FAQs {#FAQ}

|Question|Answer|
|---|---|
|Where is the Freeform table? How can I see the data source?| The Freeform table is not available in this view.  You can download the data source by right-clicking on the line chart and downloading the CSV file.|
|Why did my granularity change?|This visualization is limited to 1440 rows of data (for example, 24-hours at minute-level granularity).  If a date range and granularity combination results in more than 1440 rows, the granularity will be automatically updated to accommodate the full date range.<br><br>When changing from a larger date range to a smaller one, the granularity will be updated to the lowest detail allowable once the date range is changed. To view a higher granularity, edit the panel and rebuild.|
|How do I compare video names, segments, content types, etc?|To compare these in a single visualization, drag segments, dimensions, or specific dimension items in the series breakdown filter.<br><br>The view is limited to 10 breakdowns.  To view more than 10, you must use multiple panels.|
|How do I compare date ranges?|To compare date ranges in a single visualization, use the series breakdowns by dragging 2 or more date ranges.  These date ranges will override the panel date range.|
|How do I change the visualization type?|This panel only allows for the line visualization for the time series.|
|Can I run anomaly detection?|No.  Anomaly detection is not available for this panel.|
|Why use unique visitors instead of active sessions?|Using unique visitors enables removal of unwanted spikes at show boundaries (where sessions are ending and starting at the same time).|
|What does it mean to have concurrent viewers at higher granularity than minute?|With a granularity larger than a minute, concurrent viewers is the sum of unique concurrent viewers for all minutes within that time range.  For example, at hour-level granularity concurrent viewers is the sum of unique concurrent viewers for all minutes within the hour.|
|Does the workspace panel show the same information as the Concurrent Viewers Report?|No.  In Analysis Workspace, Concurrent viewers is defined as the number of unique visitors viewing your media stream at a specific point in time, regardless of the number of sessions.<br><br>This is different than Concurrent Viewer reporting in the Reports section, which uses Concurrent Active Sessions.  Using unique visitors accounts for removal of unwanted spikes at show boundaries—where sessions are ending and starting at the same time.|

-->
