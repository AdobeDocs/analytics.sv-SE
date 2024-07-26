---
title: Streaming Media, kapitelstatistik
description: Tillgängliga mätvärden när du aktiverar [!UICONTROL Media Chapters] för en rapportserie.
feature: Metrics
source-git-commit: 26c131a37fa1f30c83fd99b290523a97d3c954db
workflow-type: tm+mt
source-wordcount: '125'
ht-degree: 0%

---

# Streaming Media, kapitelstatistik

*Den här sidan beskriver tillgängliga mätvärden när du aktiverar [!UICONTROL Media Chapters] för en rapportserie. Se [Kapiteldimensioner för direktuppspelningsmedia](../dimensions/sm-chapters.md) för tillgängliga dimensioner.*

Streaming Media-kapitelstatistik ger extra rapporteringsfunktioner för datainsamling via bibliotek för direktuppspelad mediainsamling. Användningen av dessa mått kräver **[!UICONTROL Adobe Streaming Media Collection Add-on]**. Kontakta kontoteamet på Adobe för mer information.

När du aktiverar **[!UICONTROL Media Chapters]** under [Medierapportering](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/media-management.md) är följande mått tillgängliga:

| Måttnamn | Beskrivning | Skickat med | Sammanhangsdatavariabel |
| --- | --- | --- | --- |
| Kapitel slutförs | Ett booleskt värde som aktiveras när ett kapitel slutförs. | Stängd kapitel | `a.media.chapter.complete` |
| Kapitlet börjar | Ett booleskt värde som utlöses när ett kapitel börjar. | Kapitelstart | `a.media.chapter.view` |
| Kapiteltid | Den tid som har ägnats åt kapitlet, i sekunder. | Stängd kapitel | `a.media.chapter.timePlayed` |

{style="table-layout:auto"}
