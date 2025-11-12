---
title: Kapitelstatistik för tjänster för direktuppspelning
description: Tillgängliga mätvärden när du aktiverar [!UICONTROL Media Chapters] för en rapportserie.
feature: Metrics
exl-id: bef379d5-9dc9-404f-8197-1ba66d11299d
source-git-commit: 936644c719f46a1327c8a5aa247ed69a14d3da1e
workflow-type: tm+mt
source-wordcount: '125'
ht-degree: 0%

---

# Kapitelstatistik för tjänster för direktuppspelning

*Den här sidan beskriver tillgängliga mätvärden när du aktiverar [!UICONTROL Media Chapters] för en rapportserie. Se [Kapiteldimensioner för direktuppspelande medietjänster](../dimensions/sm-chapters.md) för tillgängliga dimensioner.*

Kapitelmätvärden för direktuppspelande medietjänster ger ytterligare rapporteringsfunktioner för datainsamling via bibliotek för insamling av direktuppspelade medietjänster. Användningen av dessa mått kräver **[!UICONTROL Adobe Analytics for Streaming Media Add-on]**. Kontakta Adobe Account Team för mer information.

När du aktiverar **[!UICONTROL Media Chapters]** under [Medierapportering](/help/admin/tools/manage-rs/edit-settings/media-management.md) är följande mått tillgängliga:

| Måttnamn | Beskrivning | Skickat med | Sammanhangsdatavariabel | XDM-fält |
| --- | --- | --- | --- | --- |
| **[!UICONTROL Chapter completes]** | Ett booleskt värde som aktiveras när ett kapitel slutförs. | Stängd kapitel | `a.media.chapter.complete` | `xdm.mediaReporting.`<br>`chapterDetails.isCompleted` |
| **[!UICONTROL Chapter starts]** | Ett booleskt värde som utlöses när ett kapitel börjar. | Kapitelstart | `a.media.chapter.view` | `xdm.mediaReporting.`<br>`chapterDetails.isStarted` |
| **[!UICONTROL Chapter time spent]** | Den tid som har ägnats åt kapitlet, i sekunder. | Stängd kapitel | `a.media.chapter.timePlayed` | `xdm.mediaReporting.`<br>`chapterDetails.timePlayed` |
