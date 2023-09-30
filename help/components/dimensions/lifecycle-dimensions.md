---
title: Dimensioner för mobil livscykel
description: Dimensioner baserade på data som samlats in med Mobile SDK.
feature: Dimensions
source-git-commit: e32821dd3f30404166554b8437c508172e4764e5
workflow-type: tm+mt
source-wordcount: '68'
ht-degree: 1%

---

# Dimensioner för mobil livscykel

*Den här sidan innehåller referensdata som ofta spåras via Adobe Experience Platform Mobile SDK. Information om mobila enheter med användaragenten finns på [Dimensioner för mobilsökning](mobile-dimensions.md). Information om mätvärden som spåras med Mobile SDK finns i [Mätvärden för mobillivscykel](../metrics/lifecycle-metrics.md).*

| Namn på livscykeldimension | Beskrivning | Sammanhangsdatavariabel |
| --- | --- | --- |
| [!UICONTROL First Launch Date] | | TBD (är det här installationsdatumet?) |
| [!UICONTROL Device Name (SDK)] | | `a.DeviceName` |
| [!UICONTROL Operating System Version (SDK)] | | `a.OSVersion` |
| [!UICONTROL Resolution (SDK)] | | `a.Resolution` |
| [!UICONTROL Acquisition Source] | | `a.referrer.campaign.source` |
| [!UICONTROL App Id] | | `a.AppID` |
| [!UICONTROL Acquisition Medium] | | `a.referrer.campaign.medium` |
| [!UICONTROL Acquisition Term] | | `a.referrer.campaign.term` |
| [!UICONTROL Acquisition Content] | | `a.refferer.campaign.content` |
| [!UICONTROL Acquisition Name] | | `a.referrer.campaign.name` |
| [!UICONTROL Location (down to 10 km)] | | `a.loc.lat.a` + `a.loc.lon.a` |
| [!UICONTROL Location (down to 100 m)] | | `a.loc.lat.b` + `a.loc.lon.b` |
| [!UICONTROL Location (down to 1 m)] | | `a.loc.lat.c` + `a.loc.lon.c` |
| [!UICONTROL Point of Interest Name] | | `a.loc.poi` |
| [!UICONTROL Distance to Point of Interest Center] | | `a.loc.dist` |
| [!UICONTROL Launch Number] | | `a.Launches` |
| [!UICONTROL Days Since First Use] | | `a.DaysSinceFirstUse` |
| [!UICONTROL Action Name] | | TBD |
| [!UICONTROL Lifetime Value (evar)] | | `a.ltv.amount` |
| [!UICONTROL Beacon Major] | | TBD |
| [!UICONTROL Beacon Minor] | | TBD |
| [!UICONTROL Beacon UUID] | | TBD |
| [!UICONTROL Beacon Proximity] | | TBD |
| [!UICONTROL Days Since Last Use] | | `a.DaysSinceFirstUse` |
| [!UICONTROL Hour of Day (SDK)] | | `a.HourOfDay` |
| [!UICONTROL Day of Week (SDK)] | | `a.DayOfWeek` |
| [!UICONTROL Point of Interest ID] | | TBD |

{style="table-layout:auto"}

<!-- Missing: Install Date -->
