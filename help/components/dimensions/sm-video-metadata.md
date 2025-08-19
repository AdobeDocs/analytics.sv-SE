---
title: Metadata för video i direktuppspelande medietjänster
description: Tillgängliga dimensioner när du aktiverar [!UICONTROL Video Metadata] för en rapportserie.
feature: Dimensions
exl-id: e476c19a-9542-4a6f-9b79-5f801e2a7bf8
source-git-commit: 7609ecb3c34fb0bc8293fc1ecd409cfabb327295
workflow-type: tm+mt
source-wordcount: '235'
ht-degree: 0%

---

# Metadata för video i direktuppspelande medietjänster

*Den här sidan beskriver de tillgängliga dimensionerna när du aktiverar [!UICONTROL Video Metadata] för en rapportserie. Mer information finns i [Metadata för direktuppspelande medietjänster](../metrics/sm-video-metadata.md).*

Direktuppspelning av medietjänster och dimensioner ger extra rapporteringsfunktioner för datainsamling via bibliotek för insamling av direktuppspelade medietjänster. Användningen av de här dimensionerna kräver **[!UICONTROL Adobe Analytics for Streaming Media Ad-on]**. Kontakta Adobe Account Team för mer information.

När du aktiverar **[!UICONTROL Video Metadata]** under [Medierapportering](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/media-management.md) är följande dimensioner tillgängliga:

| Dimension name | Beskrivning | Skickat med | Sammanhangsdatavariabel |
| --- | --- | --- | --- |
| Annonsladdningar | Den typ av annons som lästs in. | TBD | `a.media.adLoad` |
| Dygnsindelning | Tidpunkten på dagen när innehållet sändes eller spelades upp. Alla strängvärden stöds. | Mediestart, stäng media | `a.media.dayPart` |
| Episod | Avsnittsnumret. | Mediestart, stäng media | `a.media.episode` |
| Mediefeedtyp | Typen av feed. | Mediestart, stäng media | `a.media.feed` |
| Genre | Typ eller gruppering av innehåll enligt innehållsproducentens definition. Den här dimensionen stöder flera värden, avgränsade med kommatecken. | Mediestart, stäng media | `a.media.genre` |
| MVPD | MVPD enligt Adobe-autentisering. | Mediestart, stäng media | `a.media.pass.mvpd` |
| Nätverk | Nätverks- eller kanalnamn | Mediestart, stäng media | `a.media.network` |
| Säsong | Det säsongsnummer som programmet tillhör. | Mediestart, stäng media | `a.media.season` |
| Visa | Program- eller serienamnet. | Mediestart, stäng media | `a.media.show` |
| Visa typ | Ett heltal som representerar innehållstypen.<br>`0`: Fullständigt avsnitt <br>`1`: Förhandsgranska eller efteråt<br>`2`: Klipp<br>`3`: Annat | Mediestart, stäng media | `a.media.type` |

{style="table-layout:auto"}
