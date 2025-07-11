---
description: Lär dig hur du använder ett histogram, som liknar ett stapeldiagram, men grupperar nummer i intervall (intervall).
title: Histogram
uuid: 8a6bd2c4-da15-4f64-b889-ab9add685046
feature: Visualizations
role: User, Admin
exl-id: f3dd7507-db2c-495c-b6b9-6c770c7c7ddc
source-git-commit: 978bd8642011dd2c8e43564c90303f194689a64e
workflow-type: tm+mt
source-wordcount: '326'
ht-degree: 2%

---

# Histogram {#histogram}

>[!CONTEXTUALHELP]
>id="workspace_histogram_button"
>title="Histogram"
>abstract="Skapa en histogramvisualisering som representerar fördelningen av numeriska data i grupper av intervall."


>[!BEGINSHADEBOX]

_I den här artikeln dokumenteras histogramvisualiseringen i_ ![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _&#x200B;**Adobe Analytics**._<br/>_Se [Histogram](https://experienceleague.adobe.com/sv/docs/analytics-platform/using/cja-workspace/visualizations/histogram) för_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _&#x200B;**Customer Journey Analytics**-versionen av den här artikeln._

>[!ENDSHADEBOX]


Visualiseringen av ![histogrammet](/help/assets/icons/Histogram.svg) **[!UICONTROL Histogram]** liknar en [!UICONTROL Bar]-visualisering, men grupperar nummer i intervall (bucket). Analytics automatiserar&quot;paketeringen&quot; av tal i intervall, men du kan ändra inställningarna i [Avancerade inställningar](#advanced-settings).

## Använd

Skapa ett histogram:

1. Lägg till en ![histogram](/help/assets/icons/Histogram.svg) **[!UICONTROL Histogram]**-visualisering. Se [Lägga till en visualisering på en panel](freeform-analysis-visualizations.md#add-visualizations-to-a-panel).
1. Dra ett mätvärde från komponentlistan **[!UICONTROL Metrics]** eller välj ett mätvärde i listrutan [!UICONTROL *Lägg till ett mätvärde*] .
1. (valfritt) Välj **[!UICONTROL Show advanced settings]**. Se [Avancerade inställningar](#advanced-settings).
1. Välj **[!UICONTROL Build]**.

>[!NOTE]
>
>Histogram stöder endast standardvärden, inte beräknade värden.

I exemplet nedan används ett histogram för att bucket-sessioner för antalet personer. Histogrammet visar att de flesta personer har mellan 16 och 21 sessioner för det valda datumintervallet.

![](assets/histogram.png)

## Avancerade inställningar

Som en del av visualiseringen är specifika histograminställningar tillgängliga.

| Histograminställningar | Beskrivning |
|---|---|
| **[!UICONTROL Starting bucket]** | Anger vilken bucket histogrammet börjar med. &quot;1&quot; är standardvärdet. Du kan ange startnummer från 0 till oändlighet (inga negativa tal). |
| **[!UICONTROL Metric buckets]** | Gör att du kan öka/minska antalet dataintervall (bucket). Det högsta antalet bucklor är 50. |
| **[!UICONTROL Metric bucket size]** | Gör att du kan ange storleken för varje bucket. Du kan till exempel ändra bucketstorleken från en sidvy till två sidvyer. |
| **[!UICONTROL Counting method]** | Välj från **[!UICONTROL Person]**, **[!UICONTROL Session]** eller **[!UICONTROL Event]**. Exempel: sidvisningar per session, sidvisningar per person eller sidvisningar per händelse. |

<!--Russ or Meike - Check Hit Type link above. -->

**Exempel**:

| Startar bucket | Måttbucklar | Storlek på måttpyts | Resultat |
|:----:|:--:|:--:|:--|
| 1 | 5 | 2 | ![Histogram, med startintervall 1, metriska bucket 5, metrisk bucketstorlek 2](assets/histogram-1-5-2.png) |
| 0 | 3 | 5 | ![Histogram, med startintervall 0, metriska intervall 3, metrisk bucket 5](assets/histogram-0-3-5.png) |

>[!MORELIKETHIS]
>
>[Lägg till en visualisering på en panel](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel)
>&#x200B;>[Visualiseringsinställningar](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md#settings)
>&#x200B;>[Snabbmenyn Visualisering ](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md#context-menu)
>&#x200B;>[Identifiera oväntade datavärden med histogram ](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/using-histograms-to-identify-unexpected-data-values/ba-p/596168)

