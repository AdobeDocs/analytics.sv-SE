---
title: Metadata för video i direktuppspelande medietjänster
description: Tillgängliga dimensioner när du aktiverar [!UICONTROL Video Metadata] för en rapportserie.
feature: Dimensions
exl-id: e476c19a-9542-4a6f-9b79-5f801e2a7bf8
source-git-commit: 936644c719f46a1327c8a5aa247ed69a14d3da1e
workflow-type: tm+mt
source-wordcount: '221'
ht-degree: 0%

---

# Metadata för video i direktuppspelande medietjänster

*Den här sidan beskriver de tillgängliga dimensionerna när du aktiverar [!UICONTROL Video Metadata] för en rapportserie. Mer information finns i [Metadata för direktuppspelande medietjänster](../metrics/sm-video-metadata.md).*

Direktuppspelning av medietjänster och dimensioner ger extra rapporteringsfunktioner för datainsamling via bibliotek för insamling av direktuppspelade medietjänster. Användningen av de här dimensionerna kräver **[!UICONTROL Adobe Analytics for Streaming Media Add-on]**. Kontakta Adobe Account Team för mer information.

När du aktiverar **[!UICONTROL Video Metadata]** under [Medierapportering](/help/admin/tools/manage-rs/edit-settings/media-management.md) är följande dimensioner tillgängliga:

| Dimension name | Beskrivning | Skickat med | Sammanhangsdatavariabel | XDM-fält |
| --- | --- | --- | --- | --- |
| **[!UICONTROL Ad loads]** | Den typ av annons som lästs in. | | `a.media.adLoad` | `xdm.mediaCollection.`<br>`sessionDetails.adLoad` |
| **[!UICONTROL Day part]** | Tidpunkten på dagen när innehållet sändes eller spelades upp. Alla strängvärden stöds. | Mediestart, stäng media | `a.media.dayPart` | `xdm.mediaCollection.`<br>`sessionDetails.dayPart`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.dayPart` |
| **[!UICONTROL Episode]** | Avsnittsnumret. | Mediestart, stäng media | `a.media.episode` | `xdm.mediaCollection.`<br>`sessionDetails.episode`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.episode` |
| **[!UICONTROL Media feed type]** | Typen av feed. | Mediestart, stäng media | `a.media.feed` | `xdm.mediaCollection.`<br>`sessionDetails.feed`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.feed` |
| **[!UICONTROL Genre]** | Typ eller gruppering av innehåll enligt innehållsproducentens definition. Den här dimensionen stöder flera värden, avgränsade med kommatecken. | Mediestart, stäng media | `a.media.genre` | `xdm.mediaCollection.`<br>`sessionDetails.genre`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.genreList` |
| **[!UICONTROL MVPD]** | MVPD enligt Adobe-autentisering. | Mediestart, stäng media | `a.media.pass.mvpd` | `xdm.mediaCollection.`<br>`sessionDetails.mvpd`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.mvpd` |
| **[!UICONTROL Network]** | Nätverks- eller kanalnamnet. | Mediestart, stäng media | `a.media.network` | `xdm.mediaCollection.`<br>`sessionDetails.network`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.network` |
| **[!UICONTROL Season]** | Det säsongsnummer som programmet tillhör. | Mediestart, stäng media | `a.media.season` | `xdm.mediaCollection.`<br>`sessionDetails.season`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.season` |
| **[!UICONTROL Show]** | Program- eller serienamnet. | Mediestart, stäng media | `a.media.show` | `xdm.mediaCollection.`<br>`sessionDetails.show`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.show` |
| **[!UICONTROL Show type]** | Ett heltal som representerar innehållstypen.<br>`0`: Fullständigt avsnitt <br>`1`: Förhandsgranska eller efteråt<br>`2`: Klipp<br>`3`: Annat | Mediestart, stäng media | `a.media.type` | `xdm.mediaCollection.`<br>`sessionDetails.showType`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.showType` |

