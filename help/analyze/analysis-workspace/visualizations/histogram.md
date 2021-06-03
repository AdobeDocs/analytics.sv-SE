---
description: Ett histogram är en ny visualiseringstyp i Analysis Workspace.
title: Histogram
uuid: 8a6bd2c4-da15-4f64-b889-ab9add685046
feature: Visualiseringar
role: Business Practitioner, Administrator
exl-id: f3dd7507-db2c-495c-b6b9-6c770c7c7ddc
source-git-commit: f669af03a502d8a24cea3047b96ec7cba7c59e6f
workflow-type: tm+mt
source-wordcount: '359'
ht-degree: 1%

---

# Histogram

Ett histogram liknar ett stapeldiagram, men det grupperar nummer i intervall (intervall). Analytics automatiserar&quot;paketeringen&quot; av tal i intervall, men du kan ändra inställningarna i [Avancerade inställningar](#section_09D774C584864D4CA6B5672DC2927477).

## Skapa ett histogram {#section_74647707CC984A1CB6D3097F43A30B45}

Så här skapar du ett histogram:

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
| Inventeringsmetod | Här kan du välja mellan [Besökare](/help/components/metrics/unique-visitors.md), [Besök](/help/components/metrics/visits.md) eller [Träfftyp](/help/components/dimensions/hit-type.md). Exempel: sidvisningar per besök eller sidvisningar per besökare eller sidvisningar per träff. För Träff används&quot;Förekomster&quot; som y-axelmått i en friformstabell. |

<!--Russ or Meike - Check Hit Type link above. -->

**Exempel**:

* Startar Bucket: 1. Mätbuffertar: 5. Måttpytsstorlek: 2 resulterar i detta histogram: 1-2, 3-4, 5-6, 7-8, 9-10.
* Startar Bucket: 0; Mätbuffertar: 3. Måttpytsstorlek: 5 kommer att resultera i detta histogram: 0-4, 5-9, 10-14

## Visa och redigera histogramdata {#section_B2CD7CDF0F6B432F928103AE7AAA3617}

Om du vill visa eller ändra datakällan för histogramdiagrammet klickar du på punkten bredvid histogramhuvudet och går till **[!UICONTROL Data Source Settings]** > **[!UICONTROL Show Data Source]**.

![](assets/manage-data-source.png)

Färdiga segment som visas i tabellen är interna segment och visas inte i segmentväljaren. Klicka på ikonen&quot;i&quot; bredvid segmentnamnet och klicka sedan på **[!UICONTROL Make public]** för att göra segmentet offentligt.

![](assets/prebuilt_segments.png)

Om du vill utforska fler sätt att hantera frihandsdatatabeller och andra visualiseringar, till exempel att göra datauppdelningar, går du [hit](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.html).
