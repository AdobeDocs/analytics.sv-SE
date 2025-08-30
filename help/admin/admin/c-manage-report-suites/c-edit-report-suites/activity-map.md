---
description: Aktivera dimensioner så att Activity Map kan samla in data.
title: Activity Map Reporting
feature: Admin Tools
exl-id: 9300c12e-3ade-4850-8a22-cba61b35ca67
source-git-commit: 24101efe2b860734c9d176ba8be8f17e26429442
workflow-type: tm+mt
source-wordcount: '142'
ht-degree: 0%

---

# Activity Map Reporting

Gör att du kan aktivera dimensioner för användning med [Activity Map](/help/analyze/activity-map/overview.md).

**[!UICONTROL Admin]** > **[!UICONTROL Report Suites]** > Välj rapportserie > **[!UICONTROL Edit Settings]** > **[!UICONTROL Activity Map]** > **[!UICONTROL Activity Map Reporting]**

I det här avsnittet av dokumentationen fokuseras på att aktivera dimensioner som används i Activity Map. Mer information om övertäckning, implementeringsvariabler och dimensioner finns i [Activity Map-översikt](/help/analyze/activity-map/overview.md).

När du väljer knappen **[!UICONTROL Enable Activity Map Reports]** skapas följande dimensioner:

* [[!UICONTROL Activity Map Link]](/help/components/dimensions/activity-map-link.md): Det länknamn som klickades på.
* [[!UICONTROL Activity Map Region]](/help/components/dimensions/activity-map-region.md): Regionnamnet som klickades på.
* [[!UICONTROL Activity Map Page]](/help/components/dimensions/activity-map-page.md): Sidnamnet när användaren klickar på länken.
* [[!UICONTROL Activity Map Link By Region]](/help/components/dimensions/activity-map-link-by-region.md): Ett sammanfogat värde för Activity Map Link och Activity Map Region.

När den är aktiverad kan implementeringen börja skicka data till de här dimensionerna för användning i [Analysis Workspace](/help/analyze/analysis-workspace/home.md) och [webbläsartilläggsövertäckningen](/help/analyze/activity-map/overlay/overview.md).

>[!NOTE]
>
>När du aktiverar Activity Map för en rapportserie aktiveras den permanent utan något sätt att inaktivera den i framtiden.
