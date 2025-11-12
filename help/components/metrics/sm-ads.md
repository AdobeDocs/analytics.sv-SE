---
title: Streaming media services and metrics
description: Tillgängliga mätvärden när du aktiverar [!UICONTROL Media Ads] för en rapportserie.
feature: Metrics
exl-id: f0ddf3e0-ab55-4a05-a8ae-f040ba26e704
source-git-commit: 936644c719f46a1327c8a5aa247ed69a14d3da1e
workflow-type: tm+mt
source-wordcount: '137'
ht-degree: 0%

---

# Streaming media services and metrics

*Den här sidan beskriver tillgängliga mätvärden när du aktiverar [!UICONTROL Media Ads] för en rapportserie. Se [Direktuppspelning av medietjänster och dimensioner](../dimensions/sm-ads.md) för tillgängliga dimensioner.*

Direktuppspelning av medietjänster och mätvärden ger extra rapporteringsfunktioner för datainsamling via bibliotek för direktuppspelande medietjänster. Användningen av dessa mått kräver **[!UICONTROL Adobe Analytics for Streaming Media Add-on]**. Kontakta Adobe Account Team för mer information.

När du aktiverar **[!UICONTROL Media Ads]** under [Medierapportering](/help/admin/tools/manage-rs/edit-settings/media-management.md) är följande mått tillgängliga:

| Måttnamn | Beskrivning | Skickat med | Sammanhangsdatavariabel | XDM-fält |
| --- | --- | --- | --- | --- |
| **[!UICONTROL Ad completes]** | Utlöses när en videoannons är klar. | Stäng annons | `a.media.ad.complete` | `xdm.mediaReporting.`<br>`advertisingDetails.isCompleted` |
| **[!UICONTROL Ad starts]** | Utlöses när en videoannons börjar. | Annonsstart | `a.media.ad.view` | `xdm.mediaReporting.`<br>`advertisingDetails.isStarted` |
| **[!UICONTROL Ad time spent]** | Total tid i sekunder som har ägnats åt att titta på annonsen. | Stäng annons | `a.media.ad.timePlayed` | `xdm.mediaReporting.`<br>`advertisingDetails.timePlayed` |
| **[!UICONTROL Media time spent]** | Sammanställer händelsens varaktighet för alla [!UICONTROL Play]-händelser (både huvud- och annonsinnehåll), i sekunder. | Stäng media | `a.media.totalTimePlayed` | `xdm.mediaReporting.`<br>`sessionDetails.totalTimePlayed` |
