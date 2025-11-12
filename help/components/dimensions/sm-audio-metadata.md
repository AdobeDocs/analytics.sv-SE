---
title: Mått på metadata för direktuppspelande medietjänster
description: Tillgängliga dimensioner när du aktiverar [!UICONTROL Audio Metadata] för en rapportserie.
feature: Dimensions
exl-id: 2e4dc1e9-267b-47a2-b791-23d1e754a2c1
source-git-commit: 936644c719f46a1327c8a5aa247ed69a14d3da1e
workflow-type: tm+mt
source-wordcount: '134'
ht-degree: 0%

---

# Mått på metadata för direktuppspelande medietjänster

Direktuppspelning av medietjänster och dimensioner ger extra rapporteringsfunktioner för datainsamling via bibliotek för direktuppspelande medietjänster. Användningen av de här dimensionerna kräver **[!UICONTROL Adobe Analytics for Streaming Media Add-on]**. Kontakta Adobe Account Team för mer information.

När du aktiverar **[!UICONTROL Audio Metadata]** under [Medierapportering](/help/admin/tools/manage-rs/edit-settings/media-management.md) är följande dimensioner tillgängliga:

| Dimension name | Beskrivning | Skickat med | Sammanhangsdatavariabel | XDM-fält |
| --- | --- | --- | --- | --- |
| **[!UICONTROL Album]** | Namnet på albumet. | Mediestart, stäng media | `a.media.album` | `xdm.mediaCollection.`<br>`sessionDetails.album`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.album` |
| **[!UICONTROL Artist]** | Namnet på artisten. | Mediestart, stäng media | `a.media.artist` | `xdm.mediaCollection.`<br>`sessionDetails.artist`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.artist` |
| **[!UICONTROL Author]** | Namnet på författaren av ljudboken. | Mediestart, stäng media | `a.media.author` | `xdm.mediaCollection.`<br>`sessionDetails.author`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.author` |
| **[!UICONTROL Label]** | Namnet på postetiketten. | Mediestart, stäng media | `a.media.label` | `xdm.mediaCollection.`<br>`sessionDetails.label`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.label` |
| **[!UICONTROL Publisher]** | Namnet på ljudinnehållsutgivaren. | Mediestart, stäng media | `a.media.publisher` | `xdm.mediaCollection.`<br>`sessionDetails.publisher`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.publisher` |
| **[!UICONTROL Station]** | Namn eller ID för radiostationen. | Mediestart, stäng media | `a.media.station` | `xdm.mediaCollection.`<br>`sessionDetails.station`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.station` |
