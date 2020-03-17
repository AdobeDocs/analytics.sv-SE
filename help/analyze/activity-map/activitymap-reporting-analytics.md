---
description: Beskriver hur du anger behörigheter och vilka dimensioner som är tillgängliga i Analytics.
title: Rapportering av aktivitetskarta i analyser
topic: Activity map
uuid: 057c6ab2-aa06-4779-ac16-f9b367d9ea43
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Rapportering av aktivitetskarta i analyser

Beskriver hur du anger behörigheter och vilka dimensioner som är tillgängliga i Analytics.

## Ange behörigheter {#section_BDCD9914B31A4066A50D23DDDF1ABB37}

Innan användare kan rapportera aktivitetskartdimensioner måste du som administratör

* [Lägg till användare i åtkomstgruppen](/help/analyze/activity-map/activitymap-getting-started/activitymap-getting-started-admins/activitymap-enable.md)för aktivitetskarta.
* Lägg till rapportsviter som du vill ha tillgång till i den här gruppen. Navigera till **[!UICONTROL Admin]** > **[!UICONTROL User Management]** > **[!UICONTROL Groups]** > **[!UICONTROL Activity Map Access]** > **[!UICONTROL Edit]**.
* Anpassa användaråtkomst till dimensioner. Se avsnittet nedan.

## Dimensioner för aktivitetskarta för analyser {#section_9395A7A5585F4ABE9F7C6CD0124B02A5}

Du kan [anpassa användaråtkomst till dimensioner](https://marketing.adobe.com/resources/help/en_US/reference/groups-dimensions.html) på detaljnivå. Här är aktivitetskartans dimensioner tillgängliga i Analytics:

| Dimension | Beskrivning |
|---|---|
| Sida för aktivitetskarta | Visar de sidor där en länk klickades. |
| Område för aktivitetskarta | Listar alla samlade länkregioner på hela webbplatsen. Observera att om ett område visas på flera sidor, kommer måttet att slås samman på alla sidor. |
| Länkar till aktivitetskarta | Visar alla samlade länkar på hela webbplatsen. |
| Länkar och region för aktivitetskarta | Visar alla samlade länkar med deras region på hela webbplatsen. |
| Aktivitetskarta XY | Oanvänd |

* Dessa dimensioner bör vara tillgängliga i Analysis Workspace, Reports &amp; Analytics och Report Builder, förutsatt att din Analytics-implementering är [aktiverad för Activity Map](/help/analyze/activity-map/activitymap-getting-started/activitymap-getting-started-admins/activitymap-enable.md).
* Navigera till **[!UICONTROL View All Reports]** > **[!UICONTROL Activity Map]** i Rapporter och analyser.

* Om du vill se på en länk och ett område för en viss sida behöver du bara skapa en uppdelning från den önskade sidan för aktivitetskarta i Länkar och region för aktivitetskarta.

