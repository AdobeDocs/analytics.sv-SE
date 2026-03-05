---
description: Lär dig mer om mätningstyp och attribuering.
title: Mättyp och attribut
feature: Calculated Metrics
exl-id: 3fb98227-e2ef-4829-ae84-812f845470ee
source-git-commit: 665319bdfc4c1599292c2e7aea45622d77a291a7
workflow-type: tm+mt
source-wordcount: '566'
ht-degree: 0%

---

# Mättyp och attribuering {#metric-type-attribution}

Du kan konfigurera måtttypen och [attribueringsmodellen](#attribution-models) för ett mått i en beräknad måttdefinition.

1. Välj ![Inställning](/help/assets/icons/Setting.svg) i måttkomponenten.
1. I popup-dialogrutan:

   ![Mättyp och attribuering](assets/cm-type-alloc.png)

   * Ange **[!UICONTROL Metric type]**:

     | Mätningstyp | Definition |
     |---|---|
     | **[!UICONTROL Standard]** | Om en formel består av ett enda standardmått visas identiska data som den icke-beräknade metriska motsvarigheten. Standardvärden är användbara för att skapa beräknade värden som är specifika för varje enskilt radobjekt. <p>Till exempel tar ![Event](/help/assets/icons/Event.svg) **[!UICONTROL Orders]** ![Divide](/help/assets/icons/Divide.svg) ![Event](/help/assets/icons/Event.svg) **[!UICONTROL Visits]** order för det specifika radobjektet och dividerar det med antalet webbplatser för det specifika radobjektet. |
     | **[!UICONTROL Grand total]** | Använd **[!UICONTROL Grand total]** för rapporteringsperioden i alla radartiklar. Om en formel består av ett enda totalmått, visar det beräknade måttet samma totaltal för varje radartikel. Summavärden är användbara när du vill skapa beräknade värden som jämför med totaldata. <p>![Event](/help/assets/icons/Event.svg) **[!UICONTROL Orders]** ![Divide](/help/assets/icons/Divide.svg) ![Event](/help/assets/icons/Event.svg) **[!UICONTROL Total Visits]** visar till exempel andelen order mot alla besök, inte bara besöken till det specifika radobjektet. I det här exemplet anger du **[!UICONTROL Grand Total]** för måttet ![ Event](/help/assets/icons/Event.svg) **[!UICONTROL Visits]** i det beräknade måttet, som automatiskt förvandlar det till ![Event](/help/assets/icons/Event.svg) **[!UICONTROL Total Visits]**. |

   * Ange **[!UICONTROL Attribution]**.

      1. Du kan antingen:

         * Inaktivera **[!UICONTROL Use non-default attribution model]** om du vill använda standardkolumnattribueringsmodellen, som är Sista handen, med ett uppslagsfönster på 30 dagar.
         * Aktivera **[!UICONTROL Use non-default attribution model]**. I dialogrutan **[!UICONTROL Column attribution model]**

            * Välj **[!UICONTROL Model]** bland [attribueringsmodellerna](#attribution-models).
            * Välj en **[!UICONTROL Container]** bland alternativen för [container](#container).
            * Välj en **[!UICONTROL Lookback window]** bland alternativen för [uppslagsfönstret](#lookback-window). Om du väljer **[!UICONTROL Custom Time]** kan du definiera tidsperioden i **[!UICONTROL Minute(s)]** upp till **[!UICONTROL Quarter(s)]**.

      1. Välj **[!UICONTROL Apply]** om du vill använda en icke-standardattribueringsmodell. Välj Avbryt om du vill avbryta.

     Om du redan har definierat en icke-standardattribueringsmodell väljer du **[!UICONTROL Edit]** om du vill ändra urvalet.

Se [Exempel](#example) för ett exempel på hur du använder en attribueringsmodell, behållare och ett uppslagsfönster.


## Attributionsmodeller {#attribution-models}

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_nondefaultattributionmodel"
>title="Använd en attribueringsmodell som inte är standard"
>abstract="Aktivera en icke-standardattribueringsmodell för det valda måttet."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attributionmodel"
>title="Modell"
>abstract="Välj en attribueringsmodell för måttet."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_lasttouch"
>title="Senaste beröring"
>abstract="100 % av krediterna går till det sista dimensionsvärdet som en besökare kan se."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_firsttouch"
>title="Första beröring"
>abstract="100 % av krediterna går till det första dimensionsvärdet som en besökare ser."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_linear"
>title="Linjär"
>abstract="Krediten fördelas jämnt över alla dimensionsvärden."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_participation"
>title="deltagande"
>abstract="100 % tack för alla dimensionsvärden som ses av en besökare.<br/>Kolumnsummor är överskattade."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_sametouch"
>title="Samma beröring"
>abstract="Kreditering ges endast till dimensionsvärden som inträffar för samma händelse som konvertering."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_instance"
>title="Samma beröring"
>abstract="Kreditering ges endast till dimensionsvärden som inträffar för samma händelse som konvertering."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_ushaped"
>title="U Shaped"
>abstract="40 % krediterar det första dimensionsvärdet, 40 % fram till det sista, 20 % delas av mitten."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_jcurve"
>title="J-kurva"
>abstract="60 % krediterar det sista dimensionsvärdet, 20 % till det första och 20 % delas av mitten."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_jshaped"
>title="J-kurva"
>abstract="60 % krediterar det sista dimensionsvärdet, 20 % till det första och 20 % delas av mitten."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_inversej"
>title="Inverterad J"
>abstract="60 % krediterar det första dimensionsvärdet, 20 % till det sista, 20 % delas av mitten."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_reversejshaped"
>title="Inverterad J"
>abstract="60 % krediterar det första dimensionsvärdet, 20 % till det sista, 20 % delas av mitten."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_timedecay"
>title="Tidsminskning"
>abstract="Dimension-värden som ligger närmast konverteringen ger mest valuta för pengarna."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_custom"
>title="Anpassad"
>abstract="Definiera din egen positionsbaserad attribueringsvikt."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_positionbased"
>title="Anpassad"
>abstract="Definiera din egen positionsbaserad attribueringsvikt."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_algorithmic"
>title="Algoritmisk"
>abstract="Krediten bestäms dynamiskt utifrån en statistisk algoritm."

{{attribution-models-details}}


## Behållare {#container}

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_container"
>title="Behållare"
>abstract="Välj en behållare för att ange önskat omfång för attribueringen."

{{attribution-container}}


## Fönstret Lookback {#lookback-winwow}

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_lookbackwindow"
>title="Fönstret Lookback"
>abstract="Den här inställningen bestämmer fönstret för den dataattribuering som ska användas för varje konvertering."

{{attribution-lookback-window}}

## Exempel

{{attribution-example}}


<!--
When [building a calculated metric](/help/components/calculated-metrics/workflow/c-build-metrics/cm-build-metrics.md), you can specify the metric type and the attribution model.

## Metric type

To specify the metric type when building a calculated metric:

1. Select the gear icon next to the metric whose type you want to select.

   ![](assets/cm-type-alloc.png) 

1. Choose from the following options:

   |  Metric Type  | Definition  |
   |---|---|
   |  Standard  | These metrics are the same metrics used in standard [!DNL Analytics] reporting. If a formula consisted of a single standard metric, it displays identical data to its non-calculated-metric counterpart. Standard metrics are useful for creating calculated metrics specific to each individual line item. For example, [Orders] / [Visits] takes orders for that specific line item and divides it by the number of visits for that specific line item.  |
   |  Grand total  | Use Grand total for the reporting period in every line item. If a formula consisted of a single Grand total metric, it displays the same total number on every line item. Grand total metrics are useful for creating calculated metrics that compare against site total data. For example, [Orders] / [Total Visits] shows the proportion of orders against ALL visits to your site, not just the visits to the specific line item.  |

## How linear allocation works

[Attribution](/help/analyze/analysis-workspace/attribution/overview.md) is how allocation models in calculated metrics are evaluated.

For a full list of non-default attribution models and lookback windows supported, see [Attribution models and lookback windows](/help/analyze/analysis-workspace/attribution/models.md).

The following example illustrates how calculated metrics with linear allocations work in reporting: 

| | Hit 1 | Hit 2 | Hit 3 | Hit 4 | Hit 5 | Hit 6 | Hit 7 |
|--- |--- |--- |--- |--- |--- |--- |--- |
|Data Sent In|PROMO A|-|PROMO A|PROMO B|-|PROMO C|$10|
|Last Touch eVar|PROMO A|PROMO A|PROMO A|PROMO B|PROMO B|PROMO C|$10|
|First Touch eVar|PROMO A|PROMO A|PROMO A|PROMO A|PROMO A|PROMO A|$10|
|Example prop|PROMO A|-|PROMO A|PROMO B|-|PROMO C|$10|

In this example, the values A, B, and C were sent into a variable on hits 1, 3, 4, and 6 before a $10 purchase was made on hit 7. In the second row, those values persist across hits on a last touch visit basis. The third row illustrates a first-touch visit persistence. Finally, the last row illustrates how data would be recorded for a prop which does not have persistence.

-->