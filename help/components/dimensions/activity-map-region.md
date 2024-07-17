---
title: Activity Map
description: Regionen på din webbplats som du klickade på.
feature: Dimensions
role: User, Admin
source-git-commit: 05010d58ba2a3376473097e9d4543ee4415e83e1
workflow-type: tm+mt
source-wordcount: '249'
ht-degree: 0%

---

# Activity Map

Activity Map-regionen [dimension](overview.md) visar de områden på din webbplats som du klickade mest på. Den här dimensionen är användbar när du vill jämföra klickningar i olika områden på webbplatsen i stället för i enskilda länkar. Det är också användbart för områden på webbplatsen som hanterar dynamiskt innehåll. Om du till exempel har en framsida med roterande nyhetsartiklar är det svårt att använda dimensionen [Activity Map Link](activity-map-link.md) eftersom länktexten ändras kontinuerligt. Eftersom länkarna använder samma område kan du emellertid analysera hur området fungerar, även om enskilda länkar kan ändras varje dag.

## Fyll den här dimensionen med data

Den här dimensionen hämtar data från [kontextdatavariabeln ](/help/implement/vars/page-vars/contextdata.md) `c.a.activitymap.region`. Om implementeringen använder [Activity Map](/help/analyze/activity-map/overview.md) samlar den här kontextdatavariabeln automatiskt in data när någon klickar på länkar.

Kontrollera det överordnade DOM-elementet för en viss länk som du klickade på (i ordning) för följande (i ordning):

* Ett värde i attributet som anges av [`ActivityMap.regionIDAttribute`](/help/implement/vars/config-vars/activitymap-regionidattribute.md) - anges som standard till attributet `id`
* Ett värde i attributet `aria-label` när attributet `role="region"`
* De semantiska elementen `<header>`, `<main>`, `<footer>` eller `<nav>` (endast Web SDK)

Om det överordnade DOM-elementet inte uppfyller något av ovanstående villkor fortsätter sökningen rekursivt upp i DOM-hierarkin. Om inga matchande element hittas returneras värdet `BODY`.

## Dimensioner

Dimensioner innehåller områden som du har etiketterat på din webbplats. Värdena för specifika områden beror på vilka attribut som används och om det finns semantiska HTML-element.
