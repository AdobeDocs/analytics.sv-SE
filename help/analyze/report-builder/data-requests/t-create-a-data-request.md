---
description: Steg för att skapa en grundläggande databegäran från Report Builder.
title: Skapa en databegäran
feature: Report Builder
role: User, Admin
exl-id: 21d552a0-7a58-4217-ba8a-7c87eb4757f6
source-git-commit: d2e4a6eed54fa8b3e080b162a5e841fc2f5a0e59
workflow-type: tm+mt
source-wordcount: '266'
ht-degree: 1%

---

# Skapa en databegäran från Report Builder

Steg för att skapa en grundläggande databegäran.

1. Klicka på **[!UICONTROL Create]** i Excel.
1. I fönstret [!UICONTROL Request Wizard: Step 1] väljer du en [rapportserie](/help/analyze/report-builder/data-requests/selecting-report-suites/t-select-report-suites.md).
1. (Valfritt) Markera ett segment som ska användas i begäran. När du har markerat ett eller flera segment flyttas de högst upp i listan.

   Report Builder använder segment på samma sätt som Adobe Analytics använder dem. Se [segmenteringshandboken för analyser](https://experienceleague.adobe.com/docs/analytics/components/segmentation/seg-home.html).
1. Välj en [rapporttyp](/help/analyze/report-builder/data-requests/c-report-types/select-report-types.md).
1. Ange ett [datumintervall](/help/analyze/report-builder/data-requests/configuring-report-dates/custom-calendar.md) och rapportera [granularitet](/help/analyze/report-builder/data-requests/configuring-report-dates/granularity.md).
1. Klicka på **[!UICONTROL Next]**.
1. I fönstret [Layout - Request Wizard Step 2](/help/analyze/report-builder/layout/layout.md) anger du en layout:

   | Element | Beskrivning |
   |---|---|
   | Pivotlayout | Innehåller ett rad-, kolumn- och måttstödraster för layout, som liknar Excel-standardtabeller. Med den här layouten kan du lägga till brytningsbegäranden i en ursprunglig begäran. |
   | Anpassad layout | Tillhandahåller de flesta av funktionerna i [!UICONTROL Pivot Layout] men låter dig välja var varje objekt i rutnätet ska placeras i kalkylbladet. Den här layouten ger den flexibilitet som finns i tidigare versioner. |

1. Dubbelklicka (eller dra) på fliken [!UICONTROL Metrics] i trädet för att lägga till dem i stödrastret [!UICONTROL Metrics].
1. Dubbelklicka (eller dra) på [!UICONTROL Dimensions]-fliken till stödrastret [!UICONTROL Row Labels].

   Vilka [dimensioner](https://experienceleague.adobe.com/docs/analytics/analyze/report-builder/layout/filter-dimenson/filter-dimensions.html) som är tillgängliga i steg 2 beror på vilken basrapport du valde i steg 1 och på konfigurationen för rapportsviten. Dimensionerna är artiklar som korrelerar, underrelaterar eller är en klassificering av den ursprungliga rapporttypen som du valde i fönstret [!UICONTROL Request Wizard: Step 1]. Om du lägger till mer än en dimension i steg 2 skapar du en uppdelning i din databegäran.

   Mer information finns i [Lägg till mått och Dimensioner](/help/analyze/report-builder/layout/c-metrics-dimensions/t-add-metrics-and-dimensions.md).
