---
description: Beräknade och avancerade beräknade värden är anpassade mått som du kan skapa utifrån befintliga mätvärden.
keywords: Beräknade mått;Avancerade beräknade värden
title: Beräknade och avancerade beräknade värden
feature: Calculated Metrics
exl-id: 9bf8239f-cf74-4feb-85e5-d47805e90afb
source-git-commit: 08e29da4847e8ef70bd4435949e26265d770f557
workflow-type: tm+mt
source-wordcount: '534'
ht-degree: 2%

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


>[!BEGINSHADEBOX]

Se ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Segmenterade beräknade mätvärden i segment](https://video.tv.adobe.com/v/25409?quality=12&learn=on){target="_blank"} för en demonstrationsvideo.

>[!ENDSHADEBOX]


## Begränsningar {#section_CB878B02451541D68A68B508D4DBD19A}

Vissa [!DNL Analytics]-funktioner gör att du kan använda händelser men inte beräknade värden:

* [!UICONTROL Fallout] i [!UICONTROL Analysis Workspace]
* [!UICONTROL Cohort Analysis] i Analysis Workspace
* [!UICONTROL Data Warehouse]
* [!UICONTROL Segments]
* [!DNL Analytics] för [!DNL Target]

## verktyg {#section_D65E9C067E9C45E1A50DD30F50561BB2}

Här är en kort översikt över verktygen i [!UICONTROL Calculated metrics]:

| Verktyg | Funktioner |
|--- |--- |
| Beräknad metrisk Builder | <ul><li>Skapa beräknade och avancerade beräknade värden med avancerade allokeringsmodeller.</li><li>Lägga till segment textbundet i mätformler</li><li>Jämför segment i samma rapport. Exempel: jämför lokala besökare med internationella besökare.</li><li>Använd statistiska funktioner</li><li>Tillhandahålla detaljerade måttbeskrivningar (visa vad den gör, var den ska användas, var den inte ska användas)</li><li>Kopiera definitioner till nya mätvärden</li><li>Ange en intern förhandsvisning av mätvärden</li><li>Ange måttpolaritet, vilket anger om det är bra eller dåligt om en viss anpassad händelse (metrisk) inträffar</li><li>Taggarstatistik</li></ul> |
| Beräknad måtthanterare | <ul><li>Dela mått med andra&lt;/li<li>Godkänn och strukturera mätvärden</li><li>Ordna (tagga) mätvärden så att andra kan hitta dem</li><li>Ta bort mått</li><li>Ändra namn på mått</li></ul> |
| Mätväljarskenor | Gör att du kan söka efter och lägga till/använda mått i rapporten. Du kan också ändra sorteringsordningen (alternativen är: alfabetisk, rekommenderad, ofta använd, nyligen använd). Dessutom kan du filtrera rapportsviterna så att endast mätvärden som har skapats i en viss rapportserie visas.  Om du vill komma åt den här mätväljaren klickar du på mätikonen till vänster om en rapport. |
| API för beräknade värden | Ingår i Adobe Analytics 2.0 API. |
