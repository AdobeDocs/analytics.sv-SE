---
title: Panelen Mediegenomsnitt för miniatyrmålgrupp
description: Lär dig hur du använder och tolkar panelen Media Average Minute Audience i Analysis Workspace.
feature: Panels
role: User, Admin
exl-id: be8371ee-8bc6-4a99-8527-dd94eab8a7f9
source-git-commit: c9299befa63868ce0450af9c63132738474e2371
workflow-type: tm+mt
source-wordcount: '1777'
ht-degree: 0%

---

# Mediemedelets minutmålspanel {#media-average-minute-audience-panel}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_mediaminuteaverageaudience_button"
>title="Genomsnittlig minutmålgrupp för media"
>abstract="Skapa en panel för att analysera den genomsnittliga minuten-publiken för visst innehåll, eller under en viss tidsperiod."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_mediaaverageminuteaudience_panel"
>title="Genomsnittlig minutmålgrupp för media"
>abstract="Visar prestandan för visst medieinnehåll eller för en anpassad tidsperiod.<br/><br/>**Allmänna parametrar &#x200B;**<br/>**Beräkna mätvärden för**: Välj det mätvärde som ska användas för panelen. Välj **Specifikt innehåll** om du vill analysera den genomsnittliga minuten-publiken för specifikt innehåll eller händelse utifrån innehållets längd. **Välj Anpassad tidsperiod** om du vill analysera hur den genomsnittliga minuten publiken ändras under en anpassad vald tidsperiod.<br/>**Rapporteringsdimension**: Välj att rapportera med **videonamn** för dimensionen **Innehåll-ID**. Endast tillgängligt när du har valt Specifikt innehåll som mätvärde.<br/>**Kornighet**: Välj granularitet för rapporten. Endast tillgängligt när du har valt Anpassad tidsperiod som mått.<br/>**Filtrera innehåll efter (valfritt)**: Välj ett specifikt program, årstid, avsnitt eller välj en anpassad dimension för att filtrera innehållet.<br/><br/>**Avancerade inställningar &#x200B;**<br/>**Tabellinställningar**: Välj om du vill visa beräkningsvärden i tabellen.<br/>**Tidsåtgång för mått**: Välj vilken tid du vill använda för beräkning av specifikt innehåll. Endast tillgängligt när du har valt Specifikt innehåll som mätvärde."

<!-- markdownlint-enable MD034 -->

>[!BEGINSHADEBOX]

_I den här artikeln beskrivs den genomsnittliga minuten-målgruppspanelen för media i_ ![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _&#x200B;**Adobe Analytics**&#x200B;_.<br/>_Se [Målgruppspanel i genomsnitt](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-workspace/panels/average-minute-audience-panel) för_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _&#x200B;**Customer Journey Analytics**-versionen av den här artikeln._

>[!ENDSHADEBOX]

>[!NOTE]
>
>Panelen **[!UICONTROL Media average minute audience]** är bara tillgänglig för kunder som har köpt Streaming Media Collection för Adobe Analytics.
>
>Kontakta din Adobe-säljare eller Adobe-kontogrupp om du vill ha mer information.
>

I Analysis Workspace kan den genomsnittliga minuten av publiken ge information om

* hur lång tid som har ägnats åt att visa en viss medieström delat med innehållets längd, eller
* den tid som du har tittat på under en anpassad tidsperiod med vald granularitet.

Med den genomsnittliga minuten-panelen för media kan du förstå hur mycket innehåll som används i genomsnitt genom att jämföra program av alla storlekar och genrer. Du kan till exempel förstå den genomsnittliga förbrukningen när du jämför en 30-minuters webbplats med en 3-timmars sportevenemang.

Dessutom kan du använda panelen för genomsnittlig minutpublik i mediemiljö för att jämföra eller lägga till den digitala genomsnittliga minuten-målgruppen med linjära minutvärden för tv-genomsnitt.

Målgruppspanelen för media i genomsnitt ger följande fördelar jämfört med måttet för genomsnittlig minutpublik:

* Stöder anpassade tidsperioder

* Tillåter att tidsklassificeringen uppdateras efter att vyer har bearbetats (om tidsklassificeringen inte fanns eller behöver korrigeras)

  Om du gör den här uppdateringen när du använder måttet finns inte tidsklassificeringen (om klassificeringen inte fanns). Eller så är tidsklassificeringen inaktuell (om klassificeringen fanns men var felaktig).

## Använd

Så här använder du en **[!UICONTROL Media average minute audience]**-panel:

1. Skapa en **[!UICONTROL Media average minute audience]**-panel. Mer information om hur du skapar en panel finns i [Skapa en panel](panels.md#create-a-panel).

1. Se till att du väljer en datavy för panelen som har konfigurerade komponenter från den direktuppspelande mediesamlingen.

1. Ange [indata](#panel-input) för panelen.

1. Observera [utdata](#panel-output) för panelen.

### Panelindata

Använd de indatainställningar som beskrivs i det här avsnittet för att konfigurera målgruppspanelen för genomsnittlig minuts i media.

1. Konfigurera följande indatainställningar:

   | Inställning | Beskrivning |
   |---------|------------|
   | **Panelens datumintervall** | Panelens datumintervall är som standard [!UICONTROL **Den här månaden**]. Du kan redigera den för att visa en enstaka dag eller flera månader i taget. <br></br> Den här visualiseringen är begränsad till 1 440 datarader (till exempel 24 timmar vid granularitet på minutnivå). Om ett datumintervall och en granularitetskombination resulterar i mer än 1 440 rader uppdateras granulariteten automatiskt för att passa det fullständiga datumintervallet. |
   | [!UICONTROL **Släpp ett segment här (eller någon annan komponent)**] | Precis som andra paneler filtrerar den här inställningen dina markeringar baserat på segment som du har skapat. Den här inställningen är ett bra sätt att se på specifika plattformar, liveströmmar eller andra vanliga mediesegment. |
   | [!UICONTROL **Beräkna mått för**] | Välj om du vill se den genomsnittliga minutmålgruppen för [**[!UICONTROL Specific content]**](#specific-content). Eller om du vill se den genomsnittliga minuten-publiken för en [**[!UICONTROL Custom time period]**](#custom-time-period).<br/><br/>Välj [!UICONTROL **Anpassad tidsperiod**]: <ul><li>Om längden inte är tillgänglig, eller </li><li>om du vill visa den genomsnittliga minutmålgruppen för en tidsserie med flera innehållsdelar, eller</li><li>för innehåll utan angiven varaktighet (som under en liveström eller händelse)</li></ul></li></li></ul> <p>Den här inställningen ändrar arbetsflödet och rapportutdata.</p> |

1. Fortsätt med [specifikt innehåll](#specific-content) eller [anpassad tidsperiod](#custom-time-period), beroende på vilket alternativ du väljer i listrutan [!UICONTROL **Beräkna mått för**].

#### Specifikt innehåll

1. Om du valde [!UICONTROL **specifikt innehåll**] i listrutan [!UICONTROL **Beräkna mått för**] när [panelindata](#panel-inputs) konfigureras anger du följande konfigurationsalternativ:

   | Inställning | Beskrivning |
   |---------|------------|
   | [!UICONTROL **Rapporteringsdimension**] | När du väljer specifikt innehåll kan du välja rapportutdata och använda antingen video-ID- eller innehålls-ID-fälten för att visa innehållet och dess associerade genomsnittliga minutmålgrupp. |
   | [!UICONTROL **Filtrera innehåll efter (valfritt)**] | Välj hur du vill filtrera det specifika innehållet, beroende på vilken vy du vill ha eller hur data är strukturerade. <ul>[!UICONTROL **Visa, säsong, avsnitt**]: Visar tillgängliga bildspel i listrutan, som du kan filtrera med hjälp av en sökning (eller genom att dra och släppa bildspelsnamnet från den vänstra kolumnen). Du kan avsluta markeringen där för att se alla årstiderna i programmet eller filtrera efter enskilda årstider och sedan efter enskilda avsnitt. Den här inställningen visar data för dessa program, säsonger eller avsnitt för den valda tidsperioden.</li><li>[!UICONTROL **Anpassad dimension**]: Om ditt visningsnamn finns under en anpassad dimension kan du hitta det antingen genom att söka i listrutan för dimension (valfritt) eller genom att använda den vänstra kolumnsökningen. Dimensionsobjektet fylls automatiskt baserat på det urvalet och behandlas som ett avsnitt.</li><li>[!UICONTROL **Inget**]: Visar alla videonamn som har genomsnittliga minutdata för det valda urvalet. (Det här alternativet är markerat som standard.)</li></ul> |

1. Fortsätt med [Avancerade inställningar för specifikt innehåll](#specific-content-advanced-settings) om du vill konfigurera avancerade inställningar.

#### Avancerade inställningar för specifikt innehåll

1. Välj [!UICONTROL **Specifikt innehåll**] i listrutan [!UICONTROL **Beräkna mått för**] och välj [!UICONTROL **Visa avancerade inställningar**]. Ange sedan följande konfigurationsalternativ:

   | Alternativ | Beskrivning |
   |---------|------------|
   | **[!UICONTROL Table settings]** | Standardalternativet **[!UICONTROL Show calculation values in table]** visar täljaren och nämnaren för den genomsnittliga minutmålgruppen som de föregående kolumnerna i tabellen. Om du avmarkerar det här alternativet tas de två kolumnerna bort. Den genomsnittliga minuten målgruppskolumnen finns kvar i tabellen bredvid videons namn eller innehålls-ID. |
   | **[!UICONTROL Time spent metric]** | Du kan välja standardalternativet **[!UICONTROL Content Time Spent]**, som endast inkluderar innehållstid. Du kan också välja att använda **[!UICONTROL Media Time Spent]**, som inkluderar innehåll och annonstid tillsammans som täljarberäkning för den genomsnittliga minuten-målgruppen. |

1. Välj [!UICONTROL **Build**] om du vill skapa målgruppspanelen för medieminister.

1. Fortsätt med [Panelutdata](#panel-output) om du vill ha information om hur du använder den genomsnittliga minutpanelen för mediefiler.

#### Anpassad tidsperiod

1. Om du valde [!UICONTROL **Anpassad tidsperiod**] i listrutan [!UICONTROL **Beräkna mått för**] när [panelindata](#panel-inputs) konfigureras anger du följande konfigurationsalternativ:

   | Alternativ | Beskrivning |
   |---------|------------|
   | **[!UICONTROL Granularity]** | Standardgranulariteten är [!UICONTROL **5 minuter**], men du kan välja vilken granularitet som helst som används som nämnare för tidsserien under den valda tidsperioden. Om du till exempel väljer 12:00 till 12:30 pm med en 5-minuters granularitet returneras den genomsnittliga minuten-publiken över hela halvtimmen samt sex rader med den genomsnittliga minuten-publiken för varje 5-minutersperiod. Dessa rader används som datapunkter för tidsseriediagrammet. |
   | [!UICONTROL **Filtrera innehåll efter (valfritt)**] | Välj hur du vill filtrera det specifika innehållet, beroende på vilken vy du vill ha eller hur data är strukturerade. <ul>[!UICONTROL **Visa, säsong, avsnitt**]: Visar tillgängliga bildspel i listrutan, som du kan filtrera med hjälp av en sökning (eller genom att dra och släppa bildspelsnamnet från den vänstra kolumnen). Du kan avsluta markeringen där för att se alla årstiderna i programmet eller filtrera efter enskilda årstider och sedan efter enskilda avsnitt. Den här inställningen visar data för dessa program, säsonger eller avsnitt för den valda tidsperioden.</li><li>[!UICONTROL **Anpassad dimension**]: Om ditt visningsnamn finns under en anpassad dimension kan du hitta det antingen genom att söka i listrutan för dimension (valfritt) eller genom att använda den vänstra kolumnsökningen. Dimensionsobjektet fylls automatiskt baserat på det urvalet och behandlas som ett avsnitt.</li><li>[!UICONTROL **Inget**]: Visar alla videonamn som har genomsnittliga minutdata för det valda urvalet. (Det här alternativet är markerat som standard.)</li></ul> |

1. Fortsätt med [Avancerade inställningar för anpassad tidsperiod](#custom-time-period-advanced-settings) om du vill konfigurera avancerade inställningar.

#### Avancerade inställningar för anpassad tidsperiod

1. Välj [!UICONTROL **Anpassad tidsperiod**] i listrutan [!UICONTROL **Beräkna mått för**] och välj [!UICONTROL **Visa avancerade inställningar**]. Ange sedan följande konfigurationsalternativ:

   | Alternativ | Beskrivning |
   |---------|------------|
   | **[!UICONTROL Table settings]** | Standardinställningen visar beräkningsvärdena i tabellen, som visar täljaren och nämnaren för den genomsnittliga minutmålgruppen som de föregående kolumnerna i tabellen. Om du avmarkerar det här alternativet tas de två kolumnerna bort, så att bara den genomsnittliga minuten-målgruppen visas intill tidsperioden. |

1. Välj [!UICONTROL **Build**] om du vill skapa målgruppspanelen för medieminister.

1. Fortsätt med [Panelutdata](#panel-output) om du vill ha information om hur du använder den genomsnittliga minutpanelen för mediefiler.

### Panelutdata

Utdata från panelen varierar beroende på om du väljer [!UICONTROL **Specifikt innehåll**] eller [!UICONTROL **Anpassad tidsperiod**] i listrutan [!UICONTROL **Beräkna mått för**] när [panelindata ](#panel-inputs) konfigureras.

#### Specifikt innehåll

Den genomsnittliga minuten-panelen för media returnerar följande:

* Total genomsnittlig minutmålstid för hela urvalet
* Filter och genomsnittlig minimal publik för de enskilda videoklippen, som visas i en tabell
* Innehållstid och videolängd (längd) om den avancerade inställningen har valts

Om du vill redigera och återskapa panelen väljer du ![Redigera](/help/assets/icons/Edit.svg) i det övre högra hörnet.

![Standardvy](assets/specific-content-panel-output.png)

#### Datakälla för specifikt innehåll

I den genomsnittliga minuspennan i mediemiljön används endast den genomsnittliga minuspoängen för att samla in data. Det går inte att använda uppdelningar eller andra mätvärden i panelen.

| Mått | Beskrivning |
|--------|-------------|
| **[!UICONTROL Average minute audience]** | Den tid som har använts för att visa medieströmmen dividerat med videolängden (längden) som levereras via klassificeringar. |

#### Anpassad tidsperiod {#custom-time-period-output}

Den genomsnittliga minuten-panelen för media returnerar följande:

* Total genomsnittlig minutmålgrupp för hela urvalet

* Maximal och minimal genomsnittlig minutpublik

* Diagrammet för linjeserien visar den genomsnittliga minuten-publiken för hela markeringen.

* En tabell som visar filtren och den genomsnittliga minuten-publiken för detaljerna, samt hur lång tid och granularitet som använts för varje tidsperiod

  Den här tabellen visas bara om alternativet under de avancerade inställningarna [!UICONTROL **Visa beräkningsvärden i tabellen**] har valts.

Om du vill redigera och återskapa panelen när som helst väljer du ![Redigera den genomsnittliga minuten-målpanelen](/help/assets/icons/Edit.svg) i det övre högra hörnet.


#### Datakälla för anpassad tidsperiod

I den genomsnittliga minuspennan i mediemiljön används endast den genomsnittliga minuspoängen för att samla in data. Det går inte att använda uppdelningar eller andra mätvärden i panelen.

| Mått | Beskrivning |
|---|---|
| **[!UICONTROL Average Minute Audience]** | Den tid det tar att visa medieströmmen dividerat med det totala urvalet eller den valda granulariteten i minuter. |


>[!MORELIKETHIS]
>
> [Skapa en panel](/help/analyze/analysis-workspace/c-panels/panels.md#create-a-panel)
> &#x200B;> [Panelen för samtidiga visningsprogram för media](media-concurrent-viewers.md)
> &#x200B;> [Medieuppspelningstid för panelen ](media-playback-time-spent.md)
>


<!--

# Media average minute audience panel

>[!NOTE]
>
>The Media average minute audience panel is available only to customers who have purchased the Streaming Media Collection Add-on. 
>
>Contact your Adobe Sales Representative or Adobe Account Team to purchase the Streaming Media Collection Add-on. 

In Analysis Workspace, average minute audience is the time spent viewing your media stream divided by the duration of the content or the total selection of the period and selected granularity.

The Media average minute audience panel enables you to better understand average consumption of your content by comparing programs of any length or genre. For example, you can understand average consumption when comparing a 30-minute sitcom with a 3-hour sporting event.

In addition, you can use the Media average minute audience panel to compare or append this digital average minute audience to linear TV average minute metrics. 

The Media average minute audience panel provides the following benefits over the Average Minute Audience metric:

* Supports custom time periods

* Allows for updating the duration classification after views are processed (if it was not present or if it needs to be corrected)

  If you did this when using the metric, it either won't exist (if the classification wasn't present) or it will be out of date (if the classification was present but incorrect).

## Access the Media average minute audience panel

1. In Analysis Workspace, go to a report suite that has streaming media components enabled. 

1. In the left nav, select the **Panels** icon.

   ![Panels icon in left nav](assets/panels-icon.png)

1. Drag the [!UICONTROL **Media average minute audience**] panel onto the canvas in Analysis Workspace.

1. To configure the panel, continue with [Panel inputs](#panel-inputs).

## Panel inputs {#Input}

Use the input settings described in this section to configure the Media average minute audience panel.

1. Begin creating a Media average minute audience panel, as described in [Access the Media average minute audience panel](#access-the-media-average-minute-audience-panel).

1. Configure the following input settings:

   | Setting | Description |
   |---------|------------|
   | **Panel date range** | The panel date range default is [!UICONTROL **This month**]. You can edit it to view a single day or many months at a time. <br></br> This visualization is limited to 1440 rows of data (for example, 24-hours at minute-level granularity). If a date range and granularity combination results in more than 1440 rows, the granularity is automatically updated to accommodate the full date range. |
   | [!UICONTROL **Drop a segment here (or any other component)**] | Like other panels, this setting filters your selections based on segments you've created. This is a great way to look at specific platforms, live streams, or other common media segments. |
   | [!UICONTROL **Calculate metric for**] | Choose whether you want to see the average minute audience for a specific piece of content, or if you want to see the average minute audience for a custom period of time:<ul><li>**Specific content:** This is available only if the duration has been updated using Classifications. If the duration is unavailable, or if you want to view the average minute audience for a time series with multiple pieces of content or content without a specific assigned duration (like during a live stream or event), then you should select [!UICONTROL **Custom time period**]. (Durations can be set using Classifications either before or after processing time.)</li><li>**Custom time period:** This is available regardless of whether the durations is made available using Classifications.</li></ul> <p>This setting changes the workflow and report output.</p>  |

1. Continue with [Specific content](#specific-content) or [Custom time period](#custom-time-period), depending on the option you chose in the [!UICONTROL **Calculate metric for**] drop-down menu.

### Specific content

1. If you selected [!UICONTROL **Specific content**] in the [!UICONTROL **Calculate metric for**] drop-down menu when [configuring panel inputs](#panel-inputs), specify the following configuration options:

   | Setting | Description |
   |---------|------------|
   | [!UICONTROL **Reporting dimension**] | When you choose specific content, you can select the report output to use either the video name or content ID fields to show the content and its associated average minute audience for the time period selected. |
   | [!UICONTROL **Filter content by (optional)**] | Choose how to filter the specific content, depending on the view you want or the way your data is structured. <ul>[!UICONTROL **Show, season, episode**]: Displays your available shows in the drop-down, which you can filter using a search (or by dragging and dropping the show name from the left column). You can end your selection there to see all the seasons of your show, or you can filter by individual seasons and then by individual episodes. This setting shows the data for those shows, seasons, or episodes for the selected time period.</li><li>[!UICONTROL **Custom dimension**]: If your show name is under a custom dimension, you can find it either by searching in the dimension (optional) drop down or by using the left column search. The dimension item automatically populates based on that selection and is treated as an episode.</li><li>[!UICONTROL **None**]: Shows all the video names that have average minute audience data for the selection you've chosen. (This options is selected by default.)</li></ul>  |

1. Continue with [Specific content advanced settings](#specific-content-advanced-settings) to configure advanced settings. 

### Specific content advanced settings

1. With [!UICONTROL **Specific content**] selected in the [!UICONTROL **Calculate metric for**] drop-down menu, select [!UICONTROL **Show advanced settings**], then specify the following configuration options:

   | Setting | Description |
   |---------|------------|
   | Table settings | The default setting shows the calculation values in the table, which shows the numerator and denominator of the average minute audience as the preceding columns in the table. Deselecting this option removes those two columns, leaving only the average minute audience next to the video name or content ID. |
   | Time spent metric | You can choose the default content time spent, which includes only content time, or you can choose to use the media time spent, which includes content and ad time together as the numerator calculation for the average minute audience. |

1. Select [!UICONTROL **Build**] to finish creating the Media average minute audience panel.

1. Continue with [Panel output](#panel-output) for information about how to use the Media average minute audience panel.

### Custom time period

1. If you selected [!UICONTROL **Custom time period**] in the [!UICONTROL **Calculate metric for**] drop-down menu when [configuring panel inputs](#panel-inputs), specify the following configuration options:

   | Setting | Description |
   |---------|------------|
   | Granularity | The default granularity is [!UICONTROL **5-Minute**], but you can choose any of the granularities that are used as the denominator for the time series within your overall time period selection made in the calendar selection. For example, selecting 12:00 pm to 12:30 pm with a 5-minute granularity returns the average minute audience over the full half hour as well as six rows with the average minute audience for each 5-minute period. These rows are used as the datapoints for the time series chart. |
   | [!UICONTROL **Filter content by (optional)**] | Choose how to filter the specific content, depending on the view you want or the way your data is structured. <ul>[!UICONTROL **Show, season, episode**]: Displays your available shows in the drop-down, which you can filter using a search (or by dragging and dropping the show name from the left column). You can end your selection there to see all the seasons of your show, or you can filter by individual seasons and then by individual episodes. This setting shows the data for those shows, seasons, or episodes for the selected time period.</li><li>[!UICONTROL **Custom dimension**]: If your show name is under a custom dimension, you can find it either by searching in the dimension (optional) drop down or by using the left column search. The dimension item automatically populates based on that selection and is treated as an episode.</li><li>[!UICONTROL **None**]: Shows all the video names that have average minute audience data for the selection you've chosen. (This options is selected by default.)</li></ul>  |

1. Continue with [Custom time period advanced settings](#custom-time-period-advanced-settings) to configure advanced settings. 

### Custom time period advanced settings

1. With [!UICONTROL **Custom time period**] selected in the [!UICONTROL **Calculate metric for**] drop-down menu, select [!UICONTROL **Show advanced settings**], then specify the following configuration option:

   | Setting | Description |
   |---------|------------|
   | Table settings | The default setting displays the calculation values in the table, which displays the numerator and denominator of the average minute audience as the preceding columns in the table. Deselecting this option removes those two columns leaving only the average minute audience next to the time period. |

1. Select [!UICONTROL **Build**] to finish creating the Media average minute audience panel.

1. Continue with [Panel output](#panel-output) for information about how to use the Media average minute audience panel.

## Panel output

The panel output differs depending on whether you chose [!UICONTROL **Specific content**] or [!UICONTROL **Custom time period**] in the [!UICONTROL **Calculate metric for**] drop-down menu when [configuring panel inputs](#panel-inputs).

### Specific content

The Media average minute audience panel returns the following:

* Total average minute audience for your entire selection
* Filters and average minute audience for the individual videos displayed in a table 
* Content time spent and video length (duration) if that advanced setting was selected

To edit and rebuild the panel at any time, select the Edit (pencil) icon in the top right.

![Default view](assets/specific-content-panel-output.png)

### Specific content data source

The Media average minute audience panel uses only the Average Minute Audience metric to gather data. Breakdowns or other metrics cannot be used in the panel.

| Metric | Description |
|--------|-------------|
| Average Minute Audience | The time spent viewing your media stream divided by the video length (duration) supplied via Classifications. |

### Custom time period {#custom-time-period-output}

The Media average minute audience panel returns the following:

* The total average minute audience for your entire selection

* The maximum and minimum average minute audience

* The line series graph showing the average minute audience over the entire selection.

* A table that shows the filters and average minute audience for the granularities, as well as the content time spent and granularity for each time period 

  This table displays only if the option under advanced settings called [!UICONTROL **Show calculation values in table**] is selected.

To edit and rebuild the panel at any time, select the Edit (pencil) icon in the top right.

![concurrent viewers output](assets/custom-time-period-panel-output.png)

### Custom time period data source

The Media average minute audience panel uses only the Average Minute Audience metric to gather data. Breakdowns or other metrics cannot be used in the panel.

|Metric|Description|
|---|---|
|Average Minute Audience| The time spent viewing your media stream divided by the total selection or selected granularity in minutes.|

-->