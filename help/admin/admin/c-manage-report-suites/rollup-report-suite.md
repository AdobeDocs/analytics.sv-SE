---
description: Beskrivningar av globala rapportsviter
title: Globala rapportsviter
feature: Report Suite Settings
exl-id: 97bdc9bd-2212-436b-b3b4-ec518624f9e6
role: Admin
source-git-commit: 2f61febc3e19b4b8d57833204b987cb64a9b7467
workflow-type: tm+mt
source-wordcount: '400'
ht-degree: 0%

---

# Globala rapportsviter

En global rapportserie samlar in data från alla domäner och appar som organisationen äger. Implementeringen kräver att alla bildbegäranden skickas till en enda rapportserie.

Adobe rekommenderar att man i de flesta fall genomför en global rapportserie. Se [Överväganden för den globala rapportsviten](https://experienceleague.adobe.com/docs/analytics/implementation/prepare/global-rs.html) för fördelarna med att implementera en global rapportserie.

Du kan tillhandahålla deluppsättningar av företagets globala rapportsvitsdata till olika slutanvändare med hjälp av taggningen *multi-suite* och *Virtual Report Suite* :

* **Taggar för flera programsviter**: Med taggning för flera programsviter kan du skicka bildbegäranden inte bara till en global rapportsvit utan även till enskilda underordnade rapportsviter. De globala rapportdata dedupliceras i alla rapportsviter.

  Du kan till exempel samla in alla data i en global rapportserie och även skapa sekundära rapportsviter baserade på varumärke, region eller annan differentiator. De olika teamen i företaget kan sedan fokusera på data i de rapportsviter som är relevanta för dem.

  Om du vill använda flera svittaggar implementerar du underordnade rapportsviter och en global rapportserie som innehåller alla data från de underordnade. Spårningskoden för dina webbsidor och appar inkluderar Report Suite ID (RSID) för den globala rapportsviten och även RSID:n för de tillämpliga underordnade rapportsviterna.<!-- Wording/be more specific? And include any links? -->

  Ett separat serveranrop görs till varje rapportssvit i bildbegäran. Anropen till de underordnade rapportsviterna är sekundära anrop.

* **Virtuellt rapportpaket**: En [virtuell rapportsvit](/help/components/vrs/vrs-about.md) är en fråga om angivna segment som samlats in i en global rapportsvit och som är tillgängliga för angivna användargrupper. Med virtuella rapportsviter kan du strukturera rapportelement för olika slutanvändare utan att behöva använda flera svittaggar, vilket undviker sekundära serveranrop.

  Om du vill använda virtuella rapportsviter implementerar du en global rapportsvit och tolkar sedan data för att skapa virtuella rapportsviter med specifika segment och med specifika gruppbehörigheter. Du kan skapa virtuella rapportsviter i Virtual Report Suites-hanteraren ([!UICONTROL Components] > [!UICONTROL Virtual report suites]). Mer information finns i [Arbetsflödet för den virtuella rapportsviten](/help/components/vrs/c-workflow-vrs/vrs-workflow.md).

Att använda virtuella rapportsviter i stället för taggning i flera sviter är ofta en bra metod, men virtuella rapportsviter har vissa begränsningar. Se [Virtuella rapportsviter och taggningsöverväganden för flera programsviter](/help/components/vrs/vrs-considerations.md) för att ta reda på vilken rapportritmetod som är det bästa valet för ditt företags behov. En detaljerad jämförelse av virtuella rapportsviter och taggningsfunktioner för flera sviter finns i [Virtuella rapportsviter jämfört med taggning för flera sviter](/help/components/vrs/vrs-about.md#section_317E4D21CCD74BC38166D2F57D214F78).

<!---## Rollup reports

>[!NOTE]
>
>[!DNL Reports & Analytics] is the only tool that supported rollup reports. Reports & Analytics was end-of-lifed on January 17, 2024.

Limitations of Rollup Reports {#limitations-rollups}

* Rollups provide total data, but they do not report individual values in reports. For example, eVar1 values are not included, but their aggregate total can be.
* Data is not deduplicated when the rollup combines data across report suites.
* Rollups run nightly at midnight.
* When you add a report suite to an existing rollup, historical data is not included in the rollup.
* All child report suites must have data in them for a rollup to function. If new report suites are included in a rollup, make sure to send at least one page view to each of those report suites.
* Rollup report suites can include a maximum of 40 child report suites.
* Rollup report suites can include a maximum of 100 events.
* Data contained in rollup report suites does not support breakdowns or segments.
* The Pages report is replaced with the Most Popular Sites report, which reports on metrics at the child-suite level.

## Comparison of Global Report Suite and Rollup Report  Features

**Secondary server calls**: Rollups do not incur any additional server calls beyond what a single report suite collects. If your organization uses multi-suite tagging, secondary server calls are made for each additional report suite included in an image request.

>[!TIP]
>
>If you use only a global report suite with [virtual report suites](/help/components/vrs/vrs-considerations.md), no secondary server calls are needed.

**Implementation changes**: Rollups do not require any implementation changes, while global report suites require you to include the global report suite ID in your implementation.

**Duplication**: Global report suites deduplicate unique visitors, while rollups do not. For example, if a user visits three of your domains in the same day, rollups would count three daily unique visitors. Global report suites would record one unique visitor.

**Time frame**: Rollups are only processed at midnight each night, while global report suites report data with standard latency.

**Breadth**: Rollups have no way to communicate between report suites. Global report suites can attribute credit to conversion variables between report suites and provide pathing across report suites.

**Historical data**: Rollups can aggregate historical data, while global report suites only report data from the point they were implemented.

**Reports**: Global report suites provide data on all dimensions; rollups provide aggregate data on only high-level reports.

**Supported products**: Rollups could only be used in Reports & Analytics. They are not supported in Analysis Workspace, or Data Warehouse. Global report suites can be used across all products.

**Number of aggregated report suites**: Rollups only support a maximum of 40 child report suites. Global report suites can be implemented on any number of domains or apps that you own.--->
