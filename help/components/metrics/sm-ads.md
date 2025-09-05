---
title: Streaming media services and metrics
description: Tillgängliga mätvärden när du aktiverar [!UICONTROL Media Ads] för en rapportserie.
feature: Metrics
exl-id: f0ddf3e0-ab55-4a05-a8ae-f040ba26e704
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '146'
ht-degree: 0%

---

# Streaming media services and metrics

*Den här sidan beskriver tillgängliga mätvärden när du aktiverar [!UICONTROL Media Ads] för en rapportserie. Se [Direktuppspelning av medietjänster och dimensioner](../dimensions/sm-ads.md) för tillgängliga dimensioner.*

Direktuppspelning av medietjänster och mätvärden ger extra rapporteringsfunktioner för datainsamling via bibliotek för direktuppspelande medietjänster. Användningen av dessa mått kräver **[!UICONTROL Adobe Analytics for Streaming Media Ad-on]**. Kontakta Adobe Account Team för mer information.

När du aktiverar **[!UICONTROL Media Ads]** under [Medierapportering](/help/admin/tools/manage-rs/edit-settings/media-management.md) är följande mått tillgängliga:

| Måttnamn | Beskrivning | Skickat med | Sammanhangsdatavariabel |
| --- | --- | --- | --- |
| Ad complete | Utlöses när en videoannons är klar. | Stäng annons | `a.media.ad.complete` |
| Annonser börjar | Utlöses när en videoannons börjar. | Annonsstart | `a.media.ad.view` |
| Annonstid | Total tid i sekunder som har ägnats åt att titta på annonsen. | Stäng annons | `a.media.ad.timePlayed` |
| Medietid | Sammanställer händelsens varaktighet för alla PLAY-händelser (både huvud- och annonsinnehåll), i sekunder. | Stäng media | `a.media.totalTimePlayed` |

{style="table-layout:auto"}
