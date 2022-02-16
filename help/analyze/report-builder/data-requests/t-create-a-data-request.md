---
description: Steg för att skapa en grundläggande databegäran från Report Builder.
title: Skapa en dataförfrågan
feature: Report Builder
role: User, Admin
exl-id: 21d552a0-7a58-4217-ba8a-7c87eb4757f6
source-git-commit: 1ee50c6a2231795b2ad0015a79e09b7c1c74d850
workflow-type: tm+mt
source-wordcount: '286'
ht-degree: 2%

---

# Skapa en databegäran från Report Builder

Steg för att skapa en grundläggande databegäran.

1. I Excel klickar du på **[!UICONTROL Create]**.
1. I [!UICONTROL Request Wizard: Step 1] väljer du ett [rapportsvit](/help/analyze/report-builder/data-requests/selecting-report-suites/t-select-report-suites.md).
1. (Valfritt) Markera ett segment som ska användas i begäran. När du har markerat ett eller flera segment flyttas de högst upp i listan.

   Report Builder använder segment på samma sätt som Adobe Analytics använder dem. Se [Segmenteringshandbok för analyser](https://experienceleague.adobe.com/docs/analytics/components/segmentation/seg-home.html). 1. (Valfritt) Välj en [publiceringslista](/help/analyze/report-builder/data-requests/allow-publishing-list-overrides.md) för distribution.
1. Välj en [rapporttyp](/help/analyze/report-builder/data-requests/c-report-types/select-report-types.md).
1. Ange en [datumintervall](/help/analyze/report-builder/data-requests/configuring-report-dates/custom-calendar.md) och rapportera [granularitet](/help/analyze/report-builder/data-requests/configuring-report-dates/granularity.md).
1. Klicka på **[!UICONTROL Next]**.
1. I [Layout - guide för begäran Steg 2](/help/analyze/report-builder/layout/layout.md) fönster, ange en layout:

   | Element | Beskrivning |
   |---|---|
   | Pivotlayout | Innehåller ett rad-, kolumn- och måttstödraster för layout, som liknar Excel-standardtabeller. Med den här layouten kan du lägga till brytningsbegäranden i en ursprunglig begäran. |
   | Anpassad layout | Innehåller det mesta av funktionaliteten i [!UICONTROL Pivot Layout] men låter dig välja var varje objekt i rutnätet ska placeras i kalkylbladet. Den här layouten ger den flexibilitet som finns i tidigare versioner. |

1. På [!UICONTROL Metrics] dubbelklicka (eller dra) på mätvärden i trädet för att lägga till dem i [!UICONTROL Metrics] rutnät.
1. På [!UICONTROL Dimensions] dubbelklicka (eller dra) på en flik [!UICONTROL Row Labels] rutnät.

   The [dimensioner](https://experienceleague.adobe.com/docs/analytics/analyze/report-builder/layout/filter-dimenson/filter-dimensions.html) som är tillgängliga i steg 2 beror på den basrapport du valde i steg 1 och på konfigurationen av rapportsviten. Dimensionerna är artiklar som korrelerar, underrelaterar eller är en klassificering av det ursprungliga rapporttypsmåttet som du valde på [!UICONTROL Request Wizard: Step 1] -fönstret. Om du lägger till mer än en dimension i steg 2 skapar du en uppdelning i din databegäran.

   Se [Lägg till mått och Dimensioner](/help/analyze/report-builder/layout/c-metrics-dimensions/t-add-metrics-and-dimensions.md) för mer information.
