---
description: Steg för att skapa en grundläggande begäran om Report Builder-data.
title: Skapa en databegäran
topic: Report builder
uuid: 5d0151f1-e23d-43eb-84a4-96ae06c3a564
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Skapa en Report Builder-databegäran

Steg för att skapa en grundläggande databegäran.

1. Klicka i Excel **[!UICONTROL Create]**.
1. I [!UICONTROL Request Wizard: Step 1] fönstret väljer du en [rapportserie](/help/analyze/report-builder/data-requests/selecting-report-suites/t-select-report-suites.md).
1. (Valfritt) Markera ett segment som ska användas i begäran. När du har markerat ett eller flera segment flyttas de högst upp i listan.

   I Report Builder används segment på samma sätt som i Adobe Analytics. Se [Analytics Segmentation Guide](https://marketing.adobe.com/resources/help/en_US/analytics/segment/). 1. (Valfritt) Välj en [publiceringslista](/help/analyze/report-builder/data-requests/allow-publishing-list-overrides.md) som ska användas för distribution.
1. Välj en [rapporttyp](/help/analyze/report-builder/data-requests/c-report-types/select-report-types.md).
1. Ange ett [datumintervall](/help/analyze/report-builder/data-requests/configuring-report-dates/custom-calendar.md) och rapportera [granularitet](/help/analyze/report-builder/data-requests/configuring-report-dates/granularity.md).
1. Klicka på **[!UICONTROL Next]**.
1. Ange en layout i fönstret [Layout - Request Wizard Step 2](/help/analyze/report-builder/layout/layout.md) :

   | Element | Beskrivning |
   |---|---|
   | Pivotlayout | Innehåller ett rad-, kolumn- och måttstödraster för layout, som liknar Excel-standardtabeller. Med den här layouten kan du lägga till brytningsbegäranden i en ursprunglig begäran. |
   | Anpassad layout | Innehåller det mesta av funktionaliteten i [!UICONTROL Pivot Layout] men låter dig välja var varje objekt i rutnätet ska placeras i kalkylbladet. Den här layouten ger den flexibilitet som finns i tidigare versioner. |

1. Dubbelklicka på (eller dra) mätvärden i trädet på [!UICONTROL Metrics] fliken för att lägga till dem i [!UICONTROL Metrics] rutnätet.
1. Dubbelklicka (eller dra) på [!UICONTROL Dimensions] fliken till [!UICONTROL Row Labels] rutnätet.

   Vilka [dimensioner](https://marketing.adobe.com/resources/help/en_US/reference/dimensions.html) som är tillgängliga i steg 2 beror på den basrapport du valde i steg 1 och på konfigurationen av rapportsviten. Dimensionerna är artiklar som korrelerar, underrelaterar eller är en klassificering av det ursprungliga rapporttypsmåttet som du valde i [!UICONTROL Request Wizard: Step 1] fönstret. Om du lägger till mer än en dimension i steg 2 skapar du en uppdelning i din databegäran.

   Mer information finns i [Lägg till mått](/help/analyze/report-builder/layout/c-metrics-dimensions/t-add-metrics-and-dimensions.md) .
