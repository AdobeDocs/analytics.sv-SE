---
description: Läs mer om
title: Mättyp och attribuering
feature: Calculated Metrics
exl-id: 3fb98227-e2ef-4829-ae84-812f845470ee
source-git-commit: 21c4d1b591daf7229bd36845e42e2dec473e792f
workflow-type: tm+mt
source-wordcount: '635'
ht-degree: 0%

---

# Mättyp och attribuering {#metric-type-attribution}

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


>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_container"
>title="Behållare"
>abstract="Välj en behållare för att ange önskat omfång för attribueringen."


>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_lookbackwindow"
>title="Fönstret Lookback"
>abstract="Den här inställningen bestämmer fönstret för den dataattribuering som ska användas för varje konvertering."

När du [skapar ett beräknat mått](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/cm-build-metrics.md) kan du ange måtttypen och attribueringsmodellen.

## Mätningstyp

Så här anger du måtttypen när du skapar ett beräknat mått:

1. Markera kugghjulsikonen bredvid mätvärdet vars typ du vill markera.

   ![](assets/cm_type_alloc.png)

1. Välj bland följande alternativ:

   | Mätningstyp | Definition |
   |---|---|
   | Standard | Dessa mått är samma mått som används i [!DNL Analytics]-standardrapporter. Om en formel består av ett enda standardmått visas data som är identiska med den icke-beräknade metriska motsvarigheten. Standardvärden är användbara när du vill skapa beräknade värden som är specifika för varje enskilt radobjekt. Till exempel tar [Beställningar] / [Besök] order för det specifika radobjektet och dividerar det med antalet besök för det specifika radobjektet. |
   | Summa | Använd totalsumma för rapporteringsperioden i varje radartikel. Om en formel består av ett enda totalmått visas samma totaltal på varje radartikel. Summavärden är användbara när du vill skapa beräknade värden som jämför med webbplatsens totala data. Till exempel visar [Beställningar] / [Totalt antal besök] andelen order mot ALLA besök på webbplatsen, inte bara besöken till det specifika radobjektet. |

## Så här fungerar linjär allokering

[Attribution](/help/analyze/analysis-workspace/attribution/overview.md) är hur allokeringsmodeller i beräknade värden utvärderas.

En fullständig lista över icke-standardattribueringsmodeller och uppslagsfönster som stöds finns i [Attribution models and lookback windows](/help/analyze/analysis-workspace/attribution/models.md).

I följande exempel visas hur beräknade mätvärden med linjära tilldelningar fungerar vid rapportering:

| | Träff 1 | Träff 2 | Träff 3 | Träff 4 | Träff 5 | Träff 6 | Träff 7 |
|--- |--- |--- |--- |--- |--- |--- |--- |
| Data skickade | PROMO A | - | PROMO A | PROMO B | - | PROMO C | 10 dollar |
| Senaste beröring av eVar | PROMO A | PROMO A | PROMO A | PROMO B | PROMO B | PROMO C | 10 dollar |
| First Touch eVar | PROMO A | PROMO A | PROMO A | PROMO A | PROMO A | PROMO A | 10 dollar |
| Exempel | PROMO A | - | PROMO A | PROMO B | - | PROMO C | 10 dollar |

I det här exemplet skickades värdena A, B och C till en variabel på träffar 1, 3, 4 och 6 innan ett köp på $10 gjordes på träffnummer 7. På den andra raden kvarstår dessa värden för alla träffar på grund av senaste beröringsbesök. Den tredje raden visar hur obestridliga besöken är. Slutligen visar den sista raden hur data skulle registreras för en prop som inte är beständig.

