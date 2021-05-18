---
description: Beskriver hur du anger behörigheter och vilka dimensioner som är tillgängliga i Analytics.
title: Activity Map-rapportering i Analytics
uuid: 057c6ab2-aa06-4779-ac16-f9b367d9ea43
feature: Activity Map
role: Business Practitioner, Administrator
exl-id: 8d7be302-bdfc-4370-b8f0-ab1af1e439ca
source-git-commit: d198e8ef0ec8415a4a555d3c385823baad6104fe
workflow-type: tm+mt
source-wordcount: '254'
ht-degree: 7%

---

# Activity Map-rapportering i Analytics

Beskriver hur du anger behörigheter och vilka dimensioner som är tillgängliga i Analytics.

## Ange behörigheter {#section_BDCD9914B31A4066A50D23DDDF1ABB37}

Innan användare kan rapportera Activity Map-dimensioner måste du som administratör

* [Lägg till användare i Activity Map Access Group](/help/analyze/activity-map/activitymap-getting-started/activitymap-getting-started-admins/activitymap-enable.md).
* Lägg till rapportsviter som du vill ha tillgång till i den här gruppen. Navigera till **[!UICONTROL Admin]** > **[!UICONTROL All admin]** > **[!UICONTROL User management]** > **[!UICONTROL Groups]** > **[!UICONTROL Activity Map Access]** > **[!UICONTROL Edit]**.
* Anpassa användaråtkomst till dimensioner. Se avsnittet nedan.

## Analytics Activity Map dimensions {#section_9395A7A5585F4ABE9F7C6CD0124B02A5}

Du kan [anpassa användaråtkomst till dimensioner](https://docs.adobe.com/content/help/en/analytics/admin/user-product-management/customize-report-access/groups-dimensions.html) på detaljnivå. Här är Activity Map-dimensionerna i Analytics:

| Dimension | Beskrivning |
|---|---|
| Sida för Activity Map | Visar de sidor där en länk klickades. |
| Activity Map | Listar alla samlade länkregioner på hela webbplatsen. Observera att om ett område visas på flera sidor, kommer måttet att slås samman på alla sidor. |
| Activity Map Links | Visar alla samlade länkar på hela webbplatsen. |
| Activity Map Links &amp; Region | Visar alla samlade länkar med deras region på hela webbplatsen. |
| Activity Map XY | Oanvänd |

* Dessa dimensioner bör vara tillgängliga i Analysis Workspace, Rapporter och analyser och Report Builder, förutsatt att din Analytics-implementering är [aktiverad för Activity Map](/help/analyze/activity-map/activitymap-getting-started/activitymap-getting-started-admins/activitymap-enable.md).
* Navigera till **[!UICONTROL View All Reports]** > **[!UICONTROL Activity Map]** i Rapporter och analyser.

* Om du vill se en länk och ett område för en viss sida behöver du bara skapa en uppdelning från den önskade Activity Map-sidan till länkarna och regionen Activity Map.
