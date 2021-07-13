---
description: Report Builder 5.2 stöder Adobe Analytics Unified Calculated Metrics. Bland andra innovationer har alla beräknade värden nu ett globalt ID - de är inte längre begränsade till ett rapportpaket.
title: Beräknade mätvärden
uuid: c9814894-cda6-40ff-8ec4-3ab2c1908ebc
role: User, Admin
exl-id: 462086eb-675f-443c-b3a6-b4fa390254da
source-git-commit: 7226b4c77371b486006671d72efa9e0f0d9eb1ea
workflow-type: tm+mt
source-wordcount: '359'
ht-degree: 13%

---

# Beräknade mätvärden

Report Builder 5.2 stöder Adobe Analytics Unified Calculated Metrics. Bland andra innovationer har alla beräknade värden nu ett globalt ID - de är inte längre begränsade till ett rapportpaket.

>[!NOTE]
>
>Befintliga arbetsböcker kan peka på begäranden med äldre metriska ID:n. När du använder Report Builder 5.2 konverteras dessa äldre mätnings-ID:n till det nya globala ID:t. Om du delar den här arbetsboken med en användare av Report Builder v5.1 eller tidigare, kan den användaren inte se de beräknade måtten.

Mer information om hur du skapar och hanterar beräknade värden med nya Calculated Metric Builder och Manager finns i [Calculated Metrics](https://experienceleague.adobe.com/docs/analytics/components/calculated-metrics/cm-overview.html) Guide.

I steg 2 i begärandeguiden kan du filtrera och använda beräknade värden.

## Filtrera beräknade värden {#section_376E986D3E684999A7CDB08E53854159}

**Filterberäknade** mätvärden genom att klicka på filterikonen:   ![](assets/segment_filter.png)

. Dialogrutan Avancerade filter innehåller både standardvärden och beräknade värden.

Tillgängliga filter:

![](assets/advanced_filters.png)

| Filternamn | Beskrivning |
|---|---|
| Taggar | Gör att du kan filtrera efter beräknade värden med specifika taggar. Observera att taggfilter använder operatorn AND. Om du markerar två taggar visar den högra rutan mått som har taggats med **båda**-taggar. |
| Rapportsviter | Om du använder filtret&quot;Endast *rapportsvitens namn*&quot; i verktyget Beräknade mätvärden i [!DNL Reports & Analytics] och sedan visar det avancerade filtret i [!DNL Report Builder], visar filtret Avancerat endast beräknade värden för den valda rapportsviten. |
| Ägare | Gör att du kan filtrera mätvärden efter ägare. Observera att ägarfilter använder operatorn OR. Om du markerar två ägare visar den högra rutan mått som ägs av **antingen**-ägaren. |
| Andra filter > Godkänt | Visar alla officiellt godkända mätvärden. |
| Andra filter > Favoriter | Visar alla mått som du har markerat som Favoriter. |
| Andra filter > Mitt | Visar alla mätvärden som du äger. |
| Andra filter > Delat med mig | Visar alla mått som andra delar med dig. |

## Använd beräknade värden {#section_DF5CF349460A45FDA4B6E6BB8B52F18E}

När du har valt filter klickar du på **[!UICONTROL Apply]** för att tillämpa dem på din begäran. De valda måtten läggs nu till i rapportlayouten.

![](assets/filtering_for_metric.png)
