---
description: Report Builder 5.2 har stöd för Adobe Analytics Unified Calculated Metrics. Bland andra innovationer har alla beräknade värden nu ett globalt ID - de är inte längre begränsade till ett rapportpaket.
title: Beräknade mått
uuid: c9814894-cda6-40ff-8ec4-3ab2c1908ebc
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Beräknade mått

Report Builder 5.2 har stöd för Adobe Analytics Unified Calculated Metrics. Bland andra innovationer har alla beräknade värden nu ett globalt ID - de är inte längre begränsade till ett rapportpaket.

> [!NOTE] Befintliga arbetsböcker kan peka på begäranden med äldre metriska ID:n. När du använder Report Builder 5.2 konverteras dessa äldre mått-ID:n till det nya globala ID:t. Om du delar den här arbetsboken med en användare av Report Builder v5.1 eller tidigare, kan den användaren inte se de beräknade måtten.

Mer information om hur du skapar och hanterar beräknade värden med nya Calculated Metric Builder och Manager finns i [Calculated Metrics](https://marketing.adobe.com/resources/help/en_US/analytics/calcmetrics) Guide.

I steg 2 i begärandeguiden kan du filtrera och använda beräknade värden.

## Filtrera beräknade värden {#section_376E986D3E684999A7CDB08E53854159}

**Filtrera** beräknade mätvärden genom att klicka på filterikonen:  ![](assets/segment_filter.png)

. Dialogrutan Avancerade filter innehåller både standardvärden och beräknade värden.

Tillgängliga filter:

![](assets/advanced_filters_(2).png)

| Filternamn | Beskrivning |
|---|---|
| Taggar | Gör att du kan filtrera efter beräknade värden med specifika taggar. Observera att taggfilter använder operatorn AND. Om du markerar två taggar visar den högra rutan mått som har taggats med **båda** taggarna. |
| Rapportsviter | Om du använder filtret&quot;Endast *rapportsvitens namn*&quot; i verktyget Beräknade mätvärden i [!DNL Reports & Analytics]och sedan visar det avancerade filtret i [!DNL Report Builder], visar filtret Avancerat endast beräknade värden för den valda rapportsviten. |
| Ägare | Gör att du kan filtrera mätvärden efter ägare. Observera att ägarfilter använder operatorn OR. Om du markerar två ägare visar den högra rutan mått som ägs av **någon** av ägarna. |
| Andra filter > Godkänt | Visar alla officiellt godkända mätvärden. |
| Andra filter > Favoriter | Visar alla mått som du har markerat som Favoriter. |
| Andra filter > Mitt | Visar alla mätvärden som du äger. |
| Andra filter > Delat med mig | Visar alla mått som andra delar med dig. |

## Använd beräknade värden {#section_DF5CF349460A45FDA4B6E6BB8B52F18E}

När du har valt filter klickar du på dem för **[!UICONTROL Apply]** att tillämpa dem på din begäran. De valda måtten läggs nu till i rapportlayouten.

![](assets/filtering_for_metric.png)

