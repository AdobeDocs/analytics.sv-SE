---
title: Vad är Cohort Analysis och hur fungerar den?
description: Gräv djupare in i informationen om er målgrupp och dela in i relaterade grupper med Cohort Analysis. Läs om kohortanalyser i Analysis Workspace.
feature: Cohort Analysis
role: User, Admin
exl-id: 6a46e76f-671e-4b1b-933a-6c2776c72d09
source-git-commit: 1ce002a513860ce15dc8a70825d26795fd93eb1d
workflow-type: tm+mt
source-wordcount: '674'
ht-degree: 0%

---

# Översikt över kohortabellen {#cohort-table-overview}


<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_cohorttable_button"
>title="Kohortabell"
>abstract="Skapa en kohortvisualisering för att gruppera användare baserat på slutförandet av en händelse och analysera det pågående engagemanget och bortfallet över tid."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_cohorttable_panel"
>title="Kohortabell"
>abstract="Gruppera användarna efter att ha slutfört en händelse, analysera sedan deras pågående engagemang och kraschar över tid.<br/><br/>**Parametrar &#x200B;**<br/>**Inkluderingskriterier**: De komponenter som används för att definiera den inledande besökarkohorten.<br/>**Returvillkor**: Komponenterna som används för att avgöra om en besökare har returnerat."

<!-- markdownlint-enable MD034 -->


>[!BEGINSHADEBOX]

_Den här artikeln dokumenterar kohorttabellen i_ ![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _&#x200B;**Adobe Analytics**._<br/>_Se [Kohorttabell](https://experienceleague.adobe.com/sv/docs/analytics-platform/using/cja-workspace/visualizations/cohort-table/cohort-analysis) för_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _&#x200B;**Customer Journey Analytics**-versionen av den här artikeln._

>[!ENDSHADEBOX]



En *kohort* är en grupp personer som delar gemensamma egenskaper under en angiven period. En ![TextNumbered](/help/assets/icons/TextNumbered.svg) **[!UICONTROL Cohort table]**-visualisering är till exempel användbar när du vill veta hur en kohort interagerar med ett varumärke. Du kan enkelt upptäcka ändringar i trender och sedan svara på dem. (Förklaringar av [!UICONTROL Cohort Analysis] finns på webben, till exempel [Kohortanalys 101](https://en.wikipedia.org/wiki/Cohort_analysis).)

När du har skapat en kohortrapport kan du strukturera komponenterna (specifika dimensioner, mätvärden och filter) och sedan dela kohortrapporten med vem som helst. Se [Kuratera och dela](/help/analyze/analysis-workspace/curate-share/curate.md).

Exempel på vad du kan göra med en [!UICONTROL Cohort table]:

* Lansera kampanjer som är utformade för att ge önskat resultat.
* Byt marknadsföringsbudget vid exakt rätt tidpunkt i kundlivscykeln.
* Identifiera när en testversion eller ett erbjudande ska avslutas för att maximera värdet.
* Få idéer för A/B-testning inom områden som priser, uppgraderingsalternativ osv.

[!UICONTROL Cohort table] är tillgängligt för alla Customer Journey Analytics-kunder med åtkomstbehörighet till [!UICONTROL Analysis Workspace].


>[!BEGINSHADEBOX]

Se ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Kohortanalys i Analysis Workspace](https://video.tv.adobe.com/v/23990/?quality=12&learn=on){target="_blank"} för en demonstrationsvideo.

>[!ENDSHADEBOX]


>[!IMPORTANT]
>
>[!UICONTROL Cohort Analysis] stöder inte icke-filterbara mått (inklusive beräknade värden), icke-heltalsmått (till exempel Intäkter) eller förekomster. Endast mätvärden som kan användas i filter kan användas i [!UICONTROL Cohort Analysis], och de kan bara ökas med 1 åt gången.

Kohorttabeller i Customer Journey Analytics stöder dubbelbaserade (eller numeriska) mätvärden. Exempel: Purchase.Value (en dubbel) kan användas som Inkluderings-/returmått. Dessutom fördubblas också alla mätvärden som skickas till Adobe Experience Platform via Analytics Source Connector.

## Cohort table capabilities

I följande avsnitt beskrivs kohortanalysfunktioner som gör det möjligt att finjustera kontrollen över kohorterna som du bygger.

Mer information om hur du skapar en kohort och kör en [!UICONTROL Cohort Analysis]-rapport finns i [Konfigurera en kohorttabell](/help/analyze/analysis-workspace/visualizations/cohort-table/t-cohort.md).

### [!UICONTROL Retention]-tabell

En [!UICONTROL Retention]-kohorttabell returnerar personer: varje datacell visar det råa antalet och procentandelen personer i kohorten som utförde åtgärden under den tidsperioden. Du kan ta med upp till 3 mätvärden och upp till 10 filter.

![En återgivningskohortrapport som visar enheter och procent av personerna i kohorten.](assets/retention-report.png)

### [!UICONTROL Churn]-tabell

En [!UICONTROL Churn]-kohorttabell är omvänd till en kvarhållningstabell och visar de personer som inte uppfyller eller aldrig uppfyller returkriterierna för din kohort över tiden. Du kan ta med upp till 3 mätvärden och upp till 10 filter.

![En Churn-tabell som visar enheter och procentandel av personer som inte uppfyller returkriterierna för en kohort.](assets/churn-report.png)

### [!UICONTROL Rolling Calculation]

Du kan beräkna kvarhållning eller bortfall baserat på föregående kolumn, inte den inkluderade kolumnen, som kallas rullande beräkning.

![En CSS-kvarhållningsrapport som visar beräkningar baserade på en tidigare datakolumn.](assets/retention-report-rolling.png)

### [!UICONTROL Latency]-tabell

En latenstabell mäter den tid som har gått före och efter det att inkluderingshändelsen inträffade. Mätning av fördröjning är ett utmärkt verktyg för för- och efteranalys. Kolumnen **[!UICONTROL Included]** finns i mitten av tabellen och tidsperioder före och efter inkluderingshändelsen visas på båda sidor.

![En kohortrapport som visar förfluten tid före och efter en händelse.](assets/retention-report-latency.png)

### [!UICONTROL Custom dimension]-kohort

Du kan skapa kohorter baserat på en vald dimension och inte på tidsbaserade kohorter (som är standard). Använd dimensioner som [!UICONTROL City geo], [!UICONTROL Marketing channel], [!UICONTROL campaign], [!UICONTROL product], [!UICONTROL page], [!UICONTROL region] eller någon annan dimension för att visa hur kvarhållandet ändras. Baserat på de olika värdena för de här dimensionerna.

![En kohortrapport som visar en anpassad rapport med valda dimensioner är inte standardtidsbaserad kohort.](assets/retention-dimensions.png)

>[!MORELIKETHIS]
>
>[Konfigurera en kohorttabell](/help/analyze/analysis-workspace/visualizations/cohort-table/t-cohort.md).
>



<!--
A *`cohort`* is a group of people sharing common characteristics over a specified period. [!UICONTROL Cohort Analysis] is useful, for example, when you want to learn how a cohort engages with a brand. You can easily spot changes in trends, then respond accordingly. (Explanations of [!UICONTROL Cohort Analysis] are available on the web, such as at [Cohort Analysis 101](https://en.wikipedia.org/wiki/Cohort_analysis).)

After creating a cohort report, you can curate its components (specific dimensions, metrics, and segments), then share the cohort report with anyone. See [Curate and Share](/help/analyze/analysis-workspace/curate-share/curate.md).

Examples of what you can do with [!UICONTROL Cohort Analysis]:

* Launch campaigns designed to spur a desired action.
* Shift marketing budget at exactly the right time in the customer lifecycle.
* Recognize when to end a trial or an offer, in order to maximize value.
* Gain ideas for A/B testing in areas such as pricing, upgrade path, and so on.

[!UICONTROL Cohort Analysis] is available for all Adobe Analytics customers with access rights to [!UICONTROL Analysis Workspace].


>[!BEGINSHADEBOX]

See ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Cohort analysis in Analysis Workspace](https://video.tv.adobe.com/v/25965?quality=12&learn=on){target="_blank"} for a demo video.

>[!ENDSHADEBOX]

>[!IMPORTANT]
>
>[!UICONTROL Cohort Analysis] does not support non-segmentable metrics (including calculated metrics), non-integer metrics (such as Revenue), or Occurrences. 
>
>Only metrics that can be used in segments can be used in [!UICONTROL Cohort Analysis], and they can only be incremented by >1 at a time. 

## Cohort Analysis capabilities

The following sections describe Cohort Analysis features that allow for fine-tuned control over the cohorts you are building.

For more detailed information about creating a cohort and running a [!UICONTROL Cohort Analysis] report, see [Configure a Cohort Analysis report](/help/analyze/analysis-workspace/visualizations/cohort-table/t-cohort.md).

### [!UICONTROL Retention] Table

A [!UICONTROL Retention] cohort report returns visitors: each data cell shows the raw number and percentage of visitors in the cohort who did the action during that time period. You can include up to 3 metrics and up to 10 segments.

![](assets/retention-report.png)


>[!BEGINSHADEBOX]

See ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Calculate rolling retention](https://video.tv.adobe.com/v/25962?quality=12&learn=on){target="_blank"} for a demo video.

>[!ENDSHADEBOX]



### [!UICONTROL Churn] Table

A [!UICONTROL Churn] cohort is the inverse of a retention table and shows the visitors who fell out or never met the return criteria for your cohort over time. You can include up to 3 metrics and up to 10 segments.

![](assets/churn-report.png)

>[!BEGINSHADEBOX]

See ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Churn analysis](https://video.tv.adobe.com/v/25966?quality=12&learn=on){target="_blank"} for a demo video.

>[!ENDSHADEBOX]


### [!UICONTROL Rolling Calculation]

Lets you calculate retention or churn based on the previous column, not the included column.

![](assets/cohort-rolling-calculation.png)

### [!UICONTROL Latency] Table

Measures the time that has elapsed before and after the inclusion event occurred. This is an excellent tool for pre/post analysis. The **[!UICONTROL Included]** column is in the center of the table and time periods before and after the inclusion event are shown on both sides.

![](assets/cohort-latency.png)

### [!UICONTROL Custom Dimension] Cohort

Create cohorts based on a selected dimension, and not time-based cohorts, which are the default. Use dimensions such as [!UICONTROL marketing channel], [!UICONTROL campaign], [!UICONTROL product], [!UICONTROL page], [!UICONTROL region], or any other dimension in Adobe Analytics to show how retention changes based on the different values of these dimensions.

![](assets/cohort-customizable-cohort-row.png)

-->
