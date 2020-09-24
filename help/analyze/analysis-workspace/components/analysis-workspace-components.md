---
description: 'Komponenterna i Analysis Workspace består av mått, mått, segment och datumintervall som du kan dra och släppa i ett projekt. '
title: Komponenter – översikt
translation-type: tm+mt
source-git-commit: 459d650b30355912f4c9195c05da6728610109e8
workflow-type: tm+mt
source-wordcount: '690'
ht-degree: 7%

---


# Komponenter – översikt

Komponenterna i Analysis Workspace består av mått, mått, segment och datumintervall som du kan dra och släppa i ett projekt.

Du öppnar komponentmenyn genom att klicka på **[!UICONTROL Components]** ikonen i det vänstra fältet. Du kan växla mellan [paneler](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/panels/panels.html), [visualiseringar](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.html)och komponenter från den vänstra listen eller med [snabbtangenterna](/help/analyze/analysis-workspace/build-workspace-project/fa-shortcut-keys.md).

![](assets/component-overview.png)

Du kan också justera inställningarna [för](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/build-workspace-project/view-density.html) visningsdensitet för projektet om du vill visa fler värden i den vänstra listen samtidigt genom att gå till **[!UICONTROL Project > Project Info & Settings > View Density]**.

## Dimensioner {#dimensions}

[**Dimensioner**](https://docs.adobe.com/content/help/en/analytics/components/dimensions/overview.html) är textattribut som beskriver besökarens beteende och kan visas, delas upp och jämföras i din analys. De finns i den vänstra delen av komponentraden (den orange delen) och används vanligtvis som rader i en tabell.

Exempel på dimensioner är [!UICONTROL Page Name], [!UICONTROL Marketing Channels], [!UICONTROL Device Type]och [!UICONTROL Products]. Dimensioner tillhandahålls av Adobe och hämtas via din anpassade implementering (eVar, utkast, klassificeringar osv.).

Varje dimension innehåller även **dimensionsobjekt** . Du hittar objekt i Dimensionen i den vänstra komponentlisten genom att klicka på högerpilen bredvid ett dimensionsnamn (objekten är gula).

Exempel på dimensionsobjekt är [!UICONTROL Homepage] (inom [!UICONTROL Page] dimensionen), [!UICONTROL Paid Search] (inom [!UICONTROL Marketing Channel] dimensionen), [!UICONTROL Tablet] (inom [!UICONTROL Mobile Device Type] dimensionen) och så vidare.

![](assets/dimensions.png)

## Mätvärden {#metrics}

[**Mätvärden**](https://docs.adobe.com/content/help/en/analytics/components/metrics/overview.html) är kvantitativa mått på besökares beteende. De finns i den vänstra komponenträlen (den gröna delen) och används vanligtvis som kolumner i en tabell.

Exempel på mätvärden är [!UICONTROL Page views], [!UICONTROL Visits], [!UICONTROL Orders], [!UICONTROL Average Time spent]och [!UICONTROL Revenue/Order]. Mätvärden tillhandahålls av Adobe, hämtas via din anpassade implementering ([!UICONTROL Success events]) eller skapas med [verktyget för beräkning av mätvärden](https://docs.adobe.com/content/help/en/analytics/components/calculated-metrics/calcmetric-workflow/cm-build-metrics.html).

![](assets/metrics.png)

## Segment {#segments}

[**Segment**](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/components/t-freeform-project-segment.html) är målgruppsfilter som tillämpas på din analys. De finns i den vänstra komponentlisten (blå sektion) och används vanligtvis längst upp på en panel eller ovanför måttkolumnerna i en tabell.

Exempel på segment är [!UICONTROL Mobile Device Visitors], [!UICONTROL Visits from Email]och [!UICONTROL Authenticated Hits]. Segmenten tillhandahålls av Adobe, skapas i [panelens dropzone](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/panels/panels.html)eller skapas med [Segment builder](https://docs.adobe.com/content/help/en/analytics/components/segmentation/segmentation-workflow/seg-build.html).

![](assets/segments.png)

## Datumintervall {#date-ranges}

[**Datumintervall**](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/components/calendar-date-ranges/calendar.html) är det datumintervall som du utför analysen på. De finns i den vänstra komponentspåret (lila avsnitt) och används vanligtvis i kalendern för varje panel.

Exempel på datumintervall är juli 2019, [!UICONTROL Last 4 weeks]och [!UICONTROL This month]. Datumintervall tillhandahålls av Adobe, används i [panelkalendern](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/panels/panels.html)eller skapas med [datumintervallverktyget](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/components/calendar-date-ranges/custom-date-ranges.html).

![](assets/date-ranges.png)

## Component Actions {#actions}

Du kan hantera komponenter (individuellt eller genom att markera mer än en) direkt i den vänstra listen. Högerklicka på en komponent eller klicka på ikonen Åtgärdspunkt längst upp i komponentlistan.

![](assets/component-actions.png)

| Komponentåtgärd | Beskrivning |
|--- |--- |
| Tagg | Ordna eller hantera komponenter genom att lägga till taggar i dem. Du kan sedan söka efter tagg i den vänstra listen genom att klicka på filtret eller skriva #. Taggar fungerar också som filter i komponenthanterarna. |
| Favorit | Lägg till komponenten i listan med favoriter. Precis som med taggar kan du söka efter Favoriter i den vänstra listen och filtrera efter dem i komponenthanterarna. |
| Godkänn | Markera komponenter som godkända för att signalera till användarna att komponenten är godkänd för organisationen. Precis som med taggar kan du söka efter Godkänd i den vänstra listen och filtrera efter dem i komponenthanterarna. |
| Dela | Dela komponenter med användare i organisationen. Det här alternativet är endast tillgängligt för anpassade komponenter, till exempel segment eller beräknade värden. |
| Ta bort | Ta bort komponenter som du inte längre behöver. Det här alternativet är endast tillgängligt för anpassade komponenter, till exempel segment eller beräknade värden. |

Anpassade komponenter kan också hanteras med respektive komponenthanterare. Exempel: [Segmenthanteraren](/help/components/segmentation/segmentation-workflow/seg-manage.md).
