---
title: Activity Map Link per region
description: Ett sammanfogat värde för länk och region.
feature: Dimensions
role: User, Admin
source-git-commit: 65e75a1c2b39823e72abfb0e5b61122c62f1f013
workflow-type: tm+mt
source-wordcount: '151'
ht-degree: 0%

---

# Activity Map Link per region

Activity Map Link By Region [dimension](overview.md) visar en sammanfogning av [Activity Map Link](activity-map-link.md) och [Activity Map Region](activity-map-link-by-region.md). Den här dimensionen är användbar när du har länkar som har liknande namn, men som finns i olika delar av webbplatsen. Om du t.ex. har flera länkar till din hemsida som alla är märkta med&quot;Hem&quot;, kan du använda den här dimensionen för att skilja på länkarna i de olika platsområdena.

## Fyll den här dimensionen med data

Den här dimensionen hämtar data från [kontextdatavariablerna &#x200B;](/help/implement/vars/page-vars/contextdata.md) `c.a.activitymap.link` och `c.a.activitymap.region`. Dessa två värden är sammanfogade och avgränsade med en pipe (`|`). Om implementeringen använder [Activity Map](/help/analyze/activity-map/overview.md) samlar dessa kontextdatavariabler automatiskt in data när någon klickar på länkar.

## Dimensioner

Dimension-objekt innehåller värden från [Activity Map Link](activity-map-link.md) och [Activity Map Region](activity-map-link-by-region.md). Organisationens webbplatsstruktur och implementering avgör de exakta värden som samlas in.
