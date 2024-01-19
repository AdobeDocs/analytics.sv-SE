---
description: Beskriver hur du anger behörigheter och vilka dimensioner som är tillgängliga i Analytics.
title: Rapportering från Activity Map i analyser
feature: Activity Map
role: User, Admin
exl-id: 8d7be302-bdfc-4370-b8f0-ab1af1e439ca
source-git-commit: a979fc8787fa96f8fa8317996ac66341a6f54354
workflow-type: tm+mt
source-wordcount: '233'
ht-degree: 1%

---

# Rapportering från Activity Map i analyser

Beskriver hur du anger behörigheter och vilka dimensioner som är tillgängliga i Analytics.

## Ange behörigheter {#permissions}

Innan användare kan rapportera Activity Map-dimensioner måste du som administratör

* [Lägga till användare i produktprofilen för Activity Map Access](/help/analyze/activity-map/activitymap-getting-started/activitymap-enable.md).
* Anpassa användaråtkomst till dimensioner. Se avsnittet nedan.

## Dimensioner för Analytics Activity Map {#dimensions}

Du kan [anpassa användaråtkomst till dimensioner](https://experienceleague.adobe.com/docs/analytics/admin/user-product-management/customize-report-access/groups-dimensions.html) på detaljnivå. Här är Activity Map-dimensionerna i Analytics:

| Dimension | Beskrivning |
|---|---|
| Sida för Activity Map | Visar de sidor där en länk klickades. |
| Activity Map | Listar alla samlade länkregioner på hela webbplatsen. Observera att om ett område visas på flera sidor, kommer måttet att slås samman på alla sidor. |
| Activity Map Links | Visar alla samlade länkar på hela webbplatsen. |
| Activity Map Links &amp; Region | Visar alla samlade länkar med deras region på hela webbplatsen. |
| Activity Map XY | Oanvänd |

* Dessa dimensioner bör vara tillgängliga i Analysis Workspace och Report Builder, förutsatt att din Analytics-implementering är [aktiverat för Activity Map](/help/analyze/activity-map/activitymap-getting-started/activitymap-enable.md).
* I Analysis Workspace drar du in de aktivitetskartrelaterade dimensionerna till en rapport.
* Om du vill se en länk och ett område för en viss sida behöver du bara skapa en uppdelning från den önskade Activity Map-sidan till länkarna och regionen Activity Map.
