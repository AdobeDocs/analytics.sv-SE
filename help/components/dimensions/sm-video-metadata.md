---
title: Metadata för direktuppspelad video
description: Tillgängliga dimensioner när du aktiverar [!UICONTROL Video Metadata] för en rapportserie.
feature: Dimensions
exl-id: e476c19a-9542-4a6f-9b79-5f801e2a7bf8
source-git-commit: fdd66c9558f070cd760f37a39e5911f0dac22612
workflow-type: tm+mt
source-wordcount: '230'
ht-degree: 0%

---

# Metadata för direktuppspelad video

*Den här sidan beskriver de tillgängliga dimensionerna när du aktiverar [!UICONTROL Video Metadata] för en rapportserie. Mer information finns i [Metadata för direktuppspelad medievideo](../metrics/sm-video-metadata.md).*

Med annonsdimensionerna för direktuppspelning av media får datainsamlingen extra funktioner via bibliotek för direktuppspelad mediainsamling. Användningen av de här dimensionerna kräver **[!UICONTROL Adobe Streaming Media Collection]**. Kontakta kontoteamet på Adobe för mer information.

När du aktiverar **[!UICONTROL Video Metadata]** under [Medierapportering](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/media-management.md) är följande dimensioner tillgängliga:

| Dimensionens namn | Beskrivning | Skickat med | Sammanhangsdatavariabel |
| --- | --- | --- | --- |
| Annonsladdningar | Den typ av annons som lästs in. | TBD | `a.media.adLoad` |
| Dygnsindelning | Tidpunkten på dagen när innehållet sändes eller spelades upp. Alla strängvärden stöds. | Mediestart, stäng media | `a.media.dayPart` |
| Episod | Avsnittsnumret. | Mediestart, stäng media | `a.media.episode` |
| Mediefeedtyp | Typen av feed. | Mediestart, stäng media | `a.media.feed` |
| Genre | Typ eller gruppering av innehåll enligt innehållsproducentens definition. Den här dimensionen stöder flera värden, avgränsade med kommatecken. | Mediestart, stäng media | `a.media.genre` |
| MVPD | MVPD som tillhandahålls av Adobe-autentisering. | Mediestart, stäng media | `a.media.pass.mvpd` |
| Nätverk | Nätverks- eller kanalnamn | Mediestart, stäng media | `a.media.network` |
| Säsong | Det säsongsnummer som programmet tillhör. | Mediestart, stäng media | `a.media.season` |
| Visa | Program- eller serienamnet. | Mediestart, stäng media | `a.media.show` |
| Visa typ | Ett heltal som representerar innehållstypen.<br>`0`: Fullständigt avsnitt <br>`1`: Förhandsgranska eller efteråt<br>`2`: Klipp<br>`3`: Annat | Mediestart, stäng media | `a.media.type` |

{style="table-layout:auto"}
