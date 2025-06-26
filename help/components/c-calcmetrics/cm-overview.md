---
description: Beräknade och avancerade beräknade värden är anpassade mått som du kan skapa utifrån befintliga mätvärden.
keywords: Beräknade mått;Avancerade beräknade värden
title: Beräknade och avancerade beräknade värden
feature: Calculated Metrics
exl-id: 9bf8239f-cf74-4feb-85e5-d47805e90afb
source-git-commit: d85e6990998e3c153ef969d8dc7f3a4835f683bf
workflow-type: tm+mt
source-wordcount: '272'
ht-degree: 0%

---

# Översikt över beräknade mätvärden

Beräknade och anpassade mätvärden som ni kan skapa utifrån befintliga mätvärden.

Beräknade mätvärden är ett mycket flexibelt sätt att skapa, hantera och strukturera mätvärden. Med beräknade mätvärden kan du som marknadsförare, produktchefer och analytiker ställa frågor om data utan att behöva ändra implementeringen av [!DNL Analytics].

Beräknade mått är tillgängliga i varje [!DNL Analytics]-paket, men Adobe Analytics Foundation Pack för Experience Cloud är begränsat till grundläggande beräknade mått, inklusive [formattyper (decimal, time, percent, currency)](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/cm-build-metrics.md), [allokeringsändringar (standard, linjär, deltagande osv.)](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/m-metric-type-alloc.md), [metriska typer (standard, total)](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/m-metric-type-alloc.md) och [grundläggande operatorer](c-workflow/cm-workflow/c-build-metrics/cm-build-metrics.md#operators) (lägg till, subtrahera, multiplicera och dividera).


Mer information finns i [Adobe Analytics produktbeskrivning](https://helpx.adobe.com/se/legal/product-descriptions/adobe-analytics.html).

<!--
Here is a comparison of calculated metrics and advanced calculated metrics capabilities: 

| [Format types (decimal, time, percent, currency)](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/cm-build-metrics.md)  | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg)  | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg)  |
| [Attribution changes (default, linear, participation, etc.)](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/m-metric-type-alloc.md)  | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg)  | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg)  |
| [Metric types (standard, total)](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/m-metric-type-alloc.md)  | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg)  | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg)  |
|  Basic operators (add, subtract, multiply, divide)  | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg)  | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg)  |
| [Apply segments](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/metrics-with-segments.md)  | ![StopCircle](/help/assets/icons/StopCircle.svg)  | Yes  |
| [Basic functions (count, abs value, mean, etc)](/help/components/c-calcmetrics/cm-reference/cm-functions.md)  | No  | Yes  |
| [Advanced functions (regression, if/then, t-score, etc)](/help/components/c-calcmetrics/cm-reference/cm-adv-functions.md)  | No  | Yes  |

-->

## Funktioner {#section_A0A5C275B68A4D628950BBB0B1EE631F}

Du kan

* [Skapa mått](/help/components/c-calcmetrics/c-workflow/cm-workflow/cm-workflow.md) över [!UICONTROL Analysis Workspace], [!UICONTROL Report Builder], [!UICONTROL Anomaly Detection] och [!UICONTROL Contribution Analysis].
* [Skapa segmenterade mätvärden](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/metrics-with-segments.md) som härleds vid rapportkörningen, utan att implementeringen behöver ändras. Du kan till exempel skapa ett mått för *nya besökare* med ett antal personer som det här är den första sessionen för.

* [Dela mått](/help/components/c-calcmetrics/c-workflow/cm-workflow/cm-sharing.md) mellan rapportsviter. Det innebär att alla nya mätvärden gäller för alla rapportsviter i samma inloggningsföretag.

* [Inkludera statistiska funktioner](/help/components/c-calcmetrics/cm-reference/cm-adv-functions.md) som hjälper dig att beskriva dina data bättre. Du kan till exempel räkna antalet objekt i en rapport eller lägga till antalet standardavvikelser för varje objekt.

## Begränsningar

Vissa [!DNL Analytics]-funktioner tillåter inte användning av beräknade värden:

* [!UICONTROL Fallout] i [!UICONTROL Analysis Workspace]
* [!UICONTROL Cohort Analysis] i Analysis Workspace
* [!UICONTROL Data Warehouse]
* [!UICONTROL Segments]
* [!DNL Analytics] för [!DNL Target]


>[!BEGINSHADEBOX]

Se ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Beräknade mätvärden](https://video.tv.adobe.com/v/25407?quality=12&learn=on){target="_blank"} för en demonstrationsvideo.

>[!ENDSHADEBOX]

>[!BEGINSHADEBOX]

Se ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Segmenterade beräknade mätvärden i segment](https://video.tv.adobe.com/v/25409?quality=12&learn=on){target="_blank"} för en demonstrationsvideo.

>[!ENDSHADEBOX]

<!--

Here is a short overview of the [!UICONTROL Calculated metrics] tools: 

|Tool|Capabilities|
|--- |--- |
| [Calculated metric builder](c-workflow/cm-workflow/c-build-metrics/cm-build-metrics.md)| The capabilities are: <ul><li>Create calculated and advanced calculated metrics using advancmd allocation models.</li><li>Add segments inline to metric formulas</li><li>Compare segments in the same report. For example, compare local visitors vs. international visitors.</li><li>Use statistical functions</li><li>Provide detailed metric descriptions (show what it does, where to use it, where NOT to use it)</li><li>Copy definitions into new metrics</li><li>Provide an inline metric preview</li><li>Set metric polarity, which indicates whether it's good or bad if a given custom event (metric) goes up</li><li>Tag metrics</li></ul>|
|Calculated Metric Manager|<ul><li>Share metrics with others</li<li>Approve and curate metrics</li><li>Organize (tag) your metrics so people can find them</li><li>Delete metrics</li><li>Rename metrics</li></ul>|
|Metric Selector rail|Lets you search for and add/apply metrics to the report. You can also change the  sort order (options are: alphabetical, recommended, frequently used, recently used.) In addition, you can filter on Report Suites to show only metrics created in a specific report suite.  To access this Metric Selector, click the Metrics icon  to the left of a report. |
|API for Calculated Metrics|Part of the Adobe Analytics 2.0 API set.|

-->

>[!MORELIKETHIS]
>
>[Skapa mått](/help/components/c-calcmetrics/c-workflow/cm-workflow/cm-workflow.md)
>&#x200B;>[Bygg mått ](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/cm-build-metrics.md)
>&#x200B;>[Använd funktioner ](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/cm-using-functions.md)
>
