---
title: Streaming Media - reklamstatistik
description: Tillgängliga mätvärden när du aktiverar [!UICONTROL Media Ads] för en rapportserie.
feature: Metrics
exl-id: f0ddf3e0-ab55-4a05-a8ae-f040ba26e704
source-git-commit: fdd66c9558f070cd760f37a39e5911f0dac22612
workflow-type: tm+mt
source-wordcount: '142'
ht-degree: 0%

---

# Streaming Media - reklamstatistik

*Den här sidan beskriver tillgängliga mätvärden när du aktiverar [!UICONTROL Media Ads] för en rapportserie. Se [annonsdimensioner för direktuppspelningsmedia](../dimensions/sm-ads.md) för tillgängliga dimensioner.*

Streaming Media-annonsstatistik ger extra rapporteringsfunktioner för datainsamling via bibliotek för direktuppspelad mediainsamling. Användningen av dessa mått kräver **[!UICONTROL Adobe Streaming Media Collection]**. Kontakta kontoteamet på Adobe för mer information.

När du aktiverar **[!UICONTROL Media Ads]** under [Medierapportering](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/media-management.md) är följande mått tillgängliga:

| Måttnamn | Beskrivning | Skickat med | Sammanhangsdatavariabel |
| --- | --- | --- | --- |
| Ad complete | Utlöses när en videoannons är klar. | Stäng annons | `a.media.ad.complete` |
| Annonser börjar | Utlöses när en videoannons börjar. | Annonsstart | `a.media.ad.view` |
| Annonstid | Total tid i sekunder som har ägnats åt att titta på annonsen. | Stäng annons | `a.media.ad.timePlayed` |
| Medietid | Sammanställer händelsens varaktighet för alla PLAY-händelser (både huvud- och annonsinnehåll), i sekunder. | Stäng media | `a.media.totalTimePlayed` |

{style="table-layout:auto"}
