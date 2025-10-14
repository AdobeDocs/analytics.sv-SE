---
description: Använd linjevisualisering för att visualisera trendbaserade (tidsbaserade) datauppsättningar.
title: Linje
uuid: 0508ff29-43fe-4f3a-a5f7-051869271b55
feature: Visualizations
role: User, Admin
exl-id: d177b39f-add7-4011-977a-1bdf3a9368cb
source-git-commit: 9035ea758a5e84812460c042685eae954303cc8a
workflow-type: tm+mt
source-wordcount: '509'
ht-degree: 0%

---

# Linje {#line}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_line_button"
>title="Linje"
>abstract="Skapa en linjevisualisering som visar hur värden ändras under en tidsperiod. En radvisualisering kan bara användas när tid används som dimension."

<!-- markdownlint-enable MD034 -->


>[!BEGINSHADEBOX]

_I den här artikeln dokumenteras linjevisualisering i_ ![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _**Adobe Analytics**._<br/>_Se [Line](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-workspace/visualizations/line) för_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _**Customer Journey Analytics**-versionen av den här artikeln._

>[!ENDSHADEBOX]

Visualiseringen ![GraphTrend](/help/assets/icons/GraphTrend.svg) **[!UICONTROL Line]** representerar mätvärden som använder en rad för att visa hur värden ändras under en tidsperiod. En radvisualisering kan bara användas när tid används som dimension.

![Radvisualisering](assets/line-viz.png)


## Inställningar

Som en del av [visualiseringsinställningarna](freeform-analysis-visualizations.md#settings) finns specifika radinställningar tillgängliga.

| Inställning | Beskrivning |
|---|---|
| **[!UICONTROL Granularity]** | Välj i listrutan för granularitet om du vill ändra en anpassad visualisering från dag till vecka till månad, osv. Granulariteten uppdateras också i datakälltabellen. |
| **[!UICONTROL Show min]** <br/>**[!UICONTROL Show max]** | Du kan täcka över en etikett för minsta och högsta värde för att markera minimi- och maximivärdena i ett mätresultat. min/max-värdena härleds från de synliga datapunkterna i visualiseringen, inte från hela uppsättningen värden inom en dimension.<br/>![En övertäckning med etiketten för minsta och högsta värde.](assets/min-max-labels.png) |
| **[!UICONTROL Show trendline]** | Du kan välja att lägga till en regression eller en glidande medeltrendlinje i linjeserien. Trendlinjer hjälper till att beskriva ett tydligare mönster i data. Välj en modell i listan när det är markerat. I [Modeller](#models) finns en översikt och en beskrivning av tillgängliga modeller.<br/>![Linjär trendlinje](assets/show-linear-trendline.png).<p>**TIP** Vi rekommenderar att trendlinjer tillämpas på data som inte innehåller dagens (partiella data) eller framtida datum. Idag eller i framtiden skevas trendlinjen. Om du behöver ta med framtida datum tar du dock bort nollor från data för att undvika skevning för dessa dagar. Gå till visualiseringens datakälltabell, välj måttkolumnen och aktivera **[!UICONTROL Column Settings]** > **[!UICONTROL Interpret zero as no value]**.</p> |

### Models

Alla trendlinjer för regressionsmodellen passas in med vanliga minsta fyrkanter:

| Modell | Beskrivning |
| --- | --- |
| **[!UICONTROL Linear]** | Skapa en rät linje som passar bäst för enkla linjära datauppsättningar och är användbar när data ökar eller minskar med en konstant hastighet. Ekvation: `y = a + b * x` |
| **[!UICONTROL Logarithmic]** | Skapa en kurvformad linje som passar bäst och är användbar när förändringshastigheten i data ökar eller minskar snabbt och sedan Nivåer ut. En logaritmisk trendlinje kan använda negativa och positiva värden. Ekvation: `y = a + b * log(x)` |
| **[!UICONTROL Exponential]** | Skapa en böjd linje och är användbar när data ökar eller minskar med ständigt ökande hastigheter. Det här alternativet ska inte användas om dina data innehåller noll eller negativa värden. Ekvation: `y = a + e^(b * x)` |
| **[!UICONTROL Power]** | Skapa en böjd linje och är användbart för datauppsättningar som jämför mått som ökar med en viss hastighet. Det här alternativet ska inte användas om dina data innehåller noll eller negativa värden. Ekvation: `y = a * x^b` |
| **[!UICONTROL Quadratic]** | Söker efter den bästa passningen för en datauppsättning som är formad som en parabola (konkav upp eller ned). Ekvation: `y = a + b * x + c * x^2` |
| **[!UICONTROL Moving average]** | Skapa en mjuk trendlinje baserad på en uppsättning medelvärden. Ett glidande medelvärde kallas även för ett glidande medelvärde och använder ett visst antal datapunkter (som bestäms av din [!UICONTROL Granularity]-markering), jämför dem och använder medelvärdet som en punkt på raden. Exempel är ett glidande genomsnitt på sju dagar eller ett rörligt genomsnitt på fyra veckor. |

>[!MORELIKETHIS]
>
>[Lägg till en visualisering på en panel](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel)
>>[Visualiseringsinställningar](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md#settings)
>>[Snabbmenyn Visualisering ](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md#context-menu)
>

