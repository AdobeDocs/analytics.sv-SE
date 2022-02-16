---
description: 'Komponenterna i Analysis Workspace består av mått, mått, segment och datumintervall som du kan dra och släppa i ett projekt. '
title: Komponenter – översikt
feature: Components
role: User, Admin
exl-id: e2c98c77-64ee-4349-956a-3ab092e36017
source-git-commit: 10ae8213b8745439ab5968853f655a1176b8c38a
workflow-type: tm+mt
source-wordcount: '667'
ht-degree: 5%

---

# Komponenter – översikt

Komponenterna i Analysis Workspace består av mått, mått, segment och datumintervall som du kan dra och släppa i ett projekt.

Klicka på knappen **[!UICONTROL Components]** ikonen i den vänstra listen. Du kan växla mellan [Paneler](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/panels.html), [Visualiseringar](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.html)och komponenter från den vänstra listen eller genom att använda [snabbtangenter](/help/analyze/analysis-workspace/build-workspace-project/fa-shortcut-keys.md).

![](assets/component-overview.png)

Du kan också justera [Visa densitetsinställningar](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/view-density.html) för projektet att se fler värden i den vänstra listen samtidigt genom att gå till **[!UICONTROL Project > Project Info & Settings > View Density]**.

## Mått {#dimensions}

[**Dimensioner**](https://experienceleague.adobe.com/docs/analytics/components/dimensions/overview.html) är textattribut som beskriver besökarens beteende och kan visas, delas upp och jämföras i din analys. De finns i den vänstra delen av komponentraden (den orange delen) och används vanligtvis som rader i en tabell.

Exempel på dimensioner är [!UICONTROL Page Name], [!UICONTROL Marketing Channels], [!UICONTROL Device Type]och [!UICONTROL Products]. Dimensioner tillhandahålls av Adobe och hämtas via din anpassade implementering (eVar, utkast, klassificeringar osv.).

Varje dimension innehåller också **dimensionsposter** i den. Du hittar objekt i Dimensionen i den vänstra komponentlisten genom att klicka på högerpilen bredvid ett dimensionsnamn (objekten är gula).

Exempel på dimensionsobjekt är [!UICONTROL Homepage] (inom [!UICONTROL Page] dimension), [!UICONTROL Paid Search] (inom [!UICONTROL Marketing Channel] dimension), [!UICONTROL Tablet] (inom [!UICONTROL Mobile Device Type] dimension) och så vidare.

![](assets/dimensions.png)

## Mätvärden {#metrics}

[**Mått**](https://experienceleague.adobe.com/docs/analytics/components/metrics/overview.html) är kvantitativa mått på besökares beteende. De finns i den vänstra delen av komponentraden (grön del) och används vanligtvis som kolumner i en tabell.

Exempel på mätvärden är [!UICONTROL Page views], [!UICONTROL Visits], [!UICONTROL Orders], [!UICONTROL Average Time spent]och [!UICONTROL Revenue/Order]. Mätvärden tillhandahålls av Adobe eller hämtas via din anpassade implementering ([!UICONTROL Success events]), eller skapat med [Bygg beräknade mätvärden](https://experienceleague.adobe.com/docs/analytics/components/calculated-metrics/calcmetric-workflow/cm-build-metrics.html).

![](assets/metrics.png)

## Segment {#segments}

[**Segment**](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/components/segments/t-freeform-project-segment.html) är målgruppsfilter som tillämpas på din analys. De finns i den vänstra komponentlisten (blå sektion) och används vanligtvis längst upp på en panel eller ovanför måttkolumnerna i en tabell.

Exempel på segment är [!UICONTROL Mobile Device Visitors], [!UICONTROL Visits from Email]och [!UICONTROL Authenticated Hits]. Segmenten tillhandahålls av Adobe eller skapas i [panelens dropzon](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/panels.html)eller som skapats med [Segmentbyggare](https://experienceleague.adobe.com/docs/analytics/components/segmentation/segmentation-workflow/seg-build.html).

![](assets/segments.png)

## Datumintervall {#date-ranges}

[**Datumintervall**](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/components/calendar-date-ranges/calendar.html) är det datumintervall du utför analysen över. De finns i den vänstra komponentspåret (lila avsnitt) och används vanligtvis i kalendern för varje panel.

Exempel på datumintervall är juli 2019, [!UICONTROL Last 4 weeks]och [!UICONTROL This month]. Datumintervall tillhandahålls av Adobe, används i [panelkalender](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/panels.html)eller som skapats med [Bygg datumintervall](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/components/calendar-date-ranges/custom-date-ranges.html).

![](assets/date-ranges.png)

## Komponentåtgärder {#actions}

Du kan hantera komponenter (individuellt eller genom att markera mer än en) direkt i den vänstra listen. Högerklicka på en komponent eller klicka på ikonen Åtgärdspunkt längst upp i komponentlistan.

![](assets/component-actions.png)

| Komponentåtgärd | Beskrivning |
|--- |--- |
| Tagg | Ordna eller hantera komponenter genom att lägga till taggar i dem. Du kan sedan söka efter tagg i den vänstra listen genom att klicka på filtret eller skriva #. Taggar fungerar också som filter i komponenthanterarna. |
| Favorit | Lägg till komponenten i listan med favoriter. Precis som med taggar kan du söka efter Favoriter i den vänstra listen och filtrera efter dem i komponenthanterarna. |
| Godkänn | Markera komponenter som godkända för att signalera till användarna att komponenten är godkänd för organisationen. Precis som med taggar kan du söka efter Godkänd i den vänstra listen och filtrera efter dem i komponenthanterarna. |
| Dela | Dela komponenter med användare i organisationen. Det här alternativet är endast tillgängligt för anpassade komponenter, till exempel segment eller beräknade värden. |
| Ta bort | Ta bort komponenter som du inte längre behöver. Det här alternativet är endast tillgängligt för anpassade komponenter, till exempel segment eller beräknade värden. |

Anpassade komponenter kan också hanteras med respektive komponenthanterare. Till exempel [Segmenthanteraren](/help/components/segmentation/segmentation-workflow/seg-manage.md).
