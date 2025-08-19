---
title: Kapitelstatistik för tjänster för direktuppspelning
description: Tillgängliga mätvärden när du aktiverar [!UICONTROL Media Chapters] för en rapportserie.
feature: Metrics
exl-id: bef379d5-9dc9-404f-8197-1ba66d11299d
source-git-commit: 7609ecb3c34fb0bc8293fc1ecd409cfabb327295
workflow-type: tm+mt
source-wordcount: '130'
ht-degree: 0%

---

# Kapitelstatistik för tjänster för direktuppspelning

*Den här sidan beskriver tillgängliga mätvärden när du aktiverar [!UICONTROL Media Chapters] för en rapportserie. Se [Kapiteldimensioner för direktuppspelande medietjänster](../dimensions/sm-chapters.md) för tillgängliga dimensioner.*

Kapitelmätvärden för direktuppspelande medietjänster ger ytterligare rapporteringsfunktioner för datainsamling via bibliotek för insamling av direktuppspelade medietjänster. Användningen av dessa mått kräver **[!UICONTROL Adobe Analytics for Streaming Media Ad-on]**. Kontakta Adobe Account Team för mer information.

När du aktiverar **[!UICONTROL Media Chapters]** under [Medierapportering](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/media-management.md) är följande mått tillgängliga:

| Måttnamn | Beskrivning | Skickat med | Sammanhangsdatavariabel |
| --- | --- | --- | --- |
| Kapitel slutförs | Ett booleskt värde som aktiveras när ett kapitel slutförs. | Stängd kapitel | `a.media.chapter.complete` |
| Kapitlet börjar | Ett booleskt värde som utlöses när ett kapitel börjar. | Kapitelstart | `a.media.chapter.view` |
| Kapiteltid | Den tid som har ägnats åt kapitlet, i sekunder. | Stängd kapitel | `a.media.chapter.timePlayed` |

{style="table-layout:auto"}
