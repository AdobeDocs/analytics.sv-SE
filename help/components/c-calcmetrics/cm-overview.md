---
description: Beräknade och avancerade beräknade värden är anpassade mått som du kan skapa utifrån befintliga mätvärden.
keywords: Beräknade mått;Avancerade beräknade värden
title: Beräknade och avancerade beräknade värden
feature: Calculated Metrics
exl-id: 9bf8239f-cf74-4feb-85e5-d47805e90afb
source-git-commit: 9714863374052e257e1d6349c442fc74182a0a2f
workflow-type: tm+mt
source-wordcount: '349'
ht-degree: 4%

---

# Beräknade och avancerade beräknade mätvärden

Beräknade och avancerade beräknade värden är anpassade mätvärden som du kan skapa utifrån befintliga mätvärden.

Våra verktyg för beräknade värden är ett mycket flexibelt sätt att bygga, hantera och strukturera mätvärden. De gör att du som marknadsförare, produktchefer och analytiker kan ställa frågor om data utan att behöva ändra din [!DNL Analytics]-implementering. De anpassade mätvärden som är tillgängliga i varje [!DNL Analytics]-paket är:

* Adobe [!DNL Analytics] Foundation: Beräknat
* [Adobe Analytics Select](https://www.adobe.com/se/data-analytics-cloud/analytics/select.html): Beräknat + avancerat beräknat
* [Adobe Analytics Prime](https://www.adobe.com/se/data-analytics-cloud/analytics/prime.html): Beräknat + avancerat beräknat
* [Adobe Analytics Ultimate](https://www.adobe.com/se/data-analytics-cloud/analytics/ultimate.html): Beräknat + avancerat beräknat

Här är en jämförelse av beräknade värden och avancerade beräknade mätvärden:

| Alternativ för verktyget Builder | Beräknade mått | Avancerade beräknade värden |
|---|---|---|
| [Formattyper (decimal, tid, procent, valuta)](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/cm-build-metrics.md) | Ja | Ja |
| [Attributändringar (standard, linjär, deltagande osv.)](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/m-metric-type-alloc.md) | Ja | Ja |
| [Måtttyper (standard, summa)](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/m-metric-type-alloc.md) | Ja | Ja |
| Grundläggande operatorer (lägg till, subtrahera, multiplicera, dividera) | Ja | Ja |
| [Använd segment](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/metrics-with-segments.md) | Nej | Ja |
| [Grundfunktioner (antal, abs-värde, medelvärde osv.)](/help/components/c-calcmetrics/cm-reference/cm-functions.md) | Nej | Ja |
| [Avancerade funktioner (regression, if/then, t-score etc)](/help/components/c-calcmetrics/cm-reference/cm-adv-functions.md) | Nej | Ja |

## Funktioner {#section_A0A5C275B68A4D628950BBB0B1EE631F}

Du kan

* Skapa mätvärden för [!UICONTROL Analysis Workspace], [!UICONTROL Report Builder], [!UICONTROL Anomaly Detection] och [!UICONTROL Contribution Analysis].
* Skapa segmenterade mätvärden som genereras vid rapportkörning, utan att behöva ändra implementeringen. Dessa kan ses historiskt eftersom de baseras på segment.

>[!BEGINSHADEBOX]

Se ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Beräknade mätvärden](https://video.tv.adobe.com/v/25407?quality=12&learn=on){target="_blank"} för en demonstrationsvideo.

>[!ENDSHADEBOX]

* Dela mätvärden mellan olika rapportsviter. Det innebär att alla nya mätvärden gäller för alla rapportsviter i samma inloggningsföretag.
* (Endast avancerade beräknade mätvärden) Segment på mätvärden. Du kan t.ex. skapa ett mått för&quot;Nya besökare&quot; med antalet personer som detta är den första sessionen för.

* (Endast avancerade beräknade mätvärden) Lägg in statistiska funktioner som hjälper dig att beskriva dina data bättre. Du kan till exempel räkna antalet objekt i en rapport eller lägga till antalet standardavvikelser för varje objekt.


## Begränsningar

Vissa [!DNL Analytics]-funktioner gör att du kan använda händelser men inte beräknade värden:

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