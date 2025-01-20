---
description: Ett histogram är en ny visualiseringstyp i Analysis Workspace.
title: Histogram
uuid: 8a6bd2c4-da15-4f64-b889-ab9add685046
feature: Visualizations
role: User, Admin
exl-id: f3dd7507-db2c-495c-b6b9-6c770c7c7ddc
source-git-commit: fe1d4a87157a125f6065a6d827e4266d4ddefd4e
workflow-type: tm+mt
source-wordcount: '427'
ht-degree: 0%

---

# Histogram {#histogram}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_histogram_button"
>title="Histogram"
>abstract="Skapa en histogramvisualisering som representerar fördelningen av numeriska data i grupper av intervall."

<!-- markdownlint-enable MD034 -->


>[!BEGINSHADEBOX]

_I den här artikeln dokumenteras histogramvisualiseringen i_ ![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _**Adobe Analytics**._<br/>_Se [Histogram](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-workspace/visualizations/histogram) för_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _**Customer Journey Analytics**-versionen av den här artikeln._

>[!ENDSHADEBOX]


Ett histogram liknar ett stapeldiagram, men det grupperar nummer i intervall (intervall). Analytics automatiserar&quot;paketeringen&quot; av tal i intervall, men du kan ändra inställningarna i [Avancerade inställningar](#section_09D774C584864D4CA6B5672DC2927477).

Här är en video om hur du använder histogram:

>[!VIDEO](https://video.tv.adobe.com/v/23725/?quality=12)

## Skapa ett histogram {#section_74647707CC984A1CB6D3097F43A30B45}

Skapa ett histogram:

1. Klicka på **[!UICONTROL Visualizations]** i den vänstra listen.
1. Dra **[!UICONTROL Histogram]** till panelen.
1. Välj ett mått som du vill dra till histogramvisualiseringen och klicka på **[!UICONTROL Build]**.

![](assets/histogram.png)

>[!NOTE]
>
>Histogram stöder endast standardvärden, inte beräknade värden.

Här har vi använt måtten för sidvisningar per unika besökare. Den första (vänster) markeringen motsvarar en sidvy per unik besökare, den andra markeringen motsvarar två sidvisningar osv.

![](assets/histogram2.png)

## Avancerade inställningar {#section_09D774C584864D4CA6B5672DC2927477}

Om du vill justera histograminställningarna klickar du på inställningsikonen (&quot;kugghjulet&quot;) i det övre högra hörnet. Här är de inställningar du kan ändra:

| Histograminställningar | Vad det gör |
|---|---|
| Startar Bucket | Anger vilken bucket histogrammet börjar med. &quot;1&quot; är standardvärdet. Du kan ange startnummer från 0 till oändlighet (inga negativa tal). |
| Mätbuffertar | Gör att du kan öka/minska antalet dataintervall (bucket). Det högsta antalet bucklor är 50. |
| Storlek på mätpyts | Gör att du kan ange storleken för varje bucket. Du kan till exempel ändra bucketstorleken från en sidvy till två sidvyer. |
| Inventeringsmetod | Gör att du kan välja mellan [besökare](/help/components/metrics/unique-visitors.md), [besök](/help/components/metrics/visits.md) eller [träfftyp](/help/components/dimensions/hit-type.md). Exempel: sidvisningar per besök eller sidvisningar per besökare eller sidvisningar per träff. För Träff används&quot;Förekomster&quot; som y-axelmått i en friformstabell. |

<!--Russ or Meike - Check Hit Type link above. -->

**Exempel**:

* Startpyts: 1; Måttfel: 5; Måttpytsstorlek: 2 resulterar i detta histogram: 1-2, 3-4, 5-6, 7-8, 9-10.
* Startpyts: 0; Måttfel: 3; Måttpytsstorlek: 5 ger detta histogram: 0-4, 5-9, 10-14

## Visa och redigera histogramdata {#section_B2CD7CDF0F6B432F928103AE7AAA3617}

Om du vill visa eller ändra datakällan för histogramdiagrammet klickar du på punkten bredvid histogramhuvudet för att gå till **[!UICONTROL Data Source Settings]** > **[!UICONTROL Show Data Source]**.

![](assets/manage-data-source.png)

Färdiga segment som visas i tabellen är interna segment och visas inte i segmentväljaren. Klicka på ikonen i bredvid segmentnamnet och klicka sedan på **[!UICONTROL Make public]** för att göra segmentet offentligt.

![](assets/prebuilt_segments.png)

Om du vill utforska fler sätt att hantera frihandsdatatabeller och andra visualiseringar, som att göra datauppdelningar, går du [här](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.html).
