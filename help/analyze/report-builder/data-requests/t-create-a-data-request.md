---
description: Steg för att skapa en grundläggande databegäran från Report Builder.
title: Skapa en dataförfrågan
uuid: 5d0151f1-e23d-43eb-84a4-96ae06c3a564
feature: Report Builder
role: User, Admin
exl-id: 21d552a0-7a58-4217-ba8a-7c87eb4757f6
source-git-commit: 7226b4c77371b486006671d72efa9e0f0d9eb1ea
workflow-type: tm+mt
source-wordcount: '288'
ht-degree: 3%

---

# Skapa en databegäran från Report Builder

Steg för att skapa en grundläggande databegäran.

1. Klicka på **[!UICONTROL Create]** i Excel.
1. I fönstret [!UICONTROL Request Wizard: Step 1] väljer du en [rapportsvit](/help/analyze/report-builder/data-requests/selecting-report-suites/t-select-report-suites.md).
1. (Valfritt) Markera ett segment som ska användas i begäran. När du har markerat ett eller flera segment flyttas de högst upp i listan.

   Report Builder använder segment på samma sätt som Adobe Analytics använder dem. Se [Analytics Segmentation Guide](https://experienceleague.adobe.com/docs/analytics/components/segmentation/seg-home.html). 1. (Valfritt) Välj en [publiceringslista](/help/analyze/report-builder/data-requests/allow-publishing-list-overrides.md) som ska användas för distribution.
1. Välj en [rapporttyp](/help/analyze/report-builder/data-requests/c-report-types/select-report-types.md).
1. Ange ett [datumintervall](/help/analyze/report-builder/data-requests/configuring-report-dates/custom-calendar.md) och rapportera [granularitet](/help/analyze/report-builder/data-requests/configuring-report-dates/granularity.md).
1. Klicka på **[!UICONTROL Next]**.
1. I fönstret [Layout - Request Wizard Step 2](/help/analyze/report-builder/layout/layout.md) anger du en layout:

   | Element | Beskrivning |
   |---|---|
   | Pivotlayout | Innehåller ett rad-, kolumn- och måttstödraster för layout, som liknar Excel-standardtabeller. Med den här layouten kan du lägga till brytningsbegäranden i en ursprunglig begäran. |
   | Anpassad layout | Innehåller det mesta av funktionaliteten i [!UICONTROL Pivot Layout] men låter dig välja var varje objekt i rutnätet ska placeras i kalkylbladet. Den här layouten ger den flexibilitet som finns i tidigare versioner. |

1. Dubbelklicka (eller dra) på fliken [!UICONTROL Metrics] för att lägga till dem i [!UICONTROL Metrics]-rutnätet.
1. Dubbelklicka (eller dra) på fliken [!UICONTROL Dimensions] till rutnätet [!UICONTROL Row Labels].

   Vilka [dimensioner](https://experienceleague.adobe.com/docs/analytics/analyze/report-builder/layout/filter-dimenson/filter-dimensions.html) som är tillgängliga i steg 2 beror på vilken basrapport du valde i steg 1 och på hur rapportsviten är konfigurerad. Dimensionerna är artiklar som korrelerar, underrelaterar eller är en klassificering av det ursprungliga rapporttypsmåttet som du valde i [!UICONTROL Request Wizard: Step 1]-fönstret. Om du lägger till mer än en dimension i steg 2 skapar du en uppdelning i din databegäran.

   Mer information finns i [Lägg till mått och Dimensioner](/help/analyze/report-builder/layout/c-metrics-dimensions/t-add-metrics-and-dimensions.md).
