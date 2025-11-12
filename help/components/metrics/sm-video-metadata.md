---
title: Metadata för direktuppspelande medietjänster
description: Tillgängliga mätvärden när du aktiverar [!UICONTROL Video Metadata] för en rapportserie.
feature: Metrics
exl-id: b2f60a34-e139-4498-bf71-74d291759ef2
source-git-commit: 936644c719f46a1327c8a5aa247ed69a14d3da1e
workflow-type: tm+mt
source-wordcount: '112'
ht-degree: 0%

---

# Metadata för direktuppspelande medietjänster

*Den här sidan beskriver tillgängliga mätvärden när du aktiverar [!UICONTROL Video metadata] för en rapportserie. Se [Metadata för videometadata för direktuppspelande medietjänster](../dimensions/sm-video-metadata.md) för tillgängliga dimensioner.*

Metadata för direktuppspelande medietjänster ger extra rapporteringsfunktioner för datainsamling via bibliotek för direktuppspelande medietjänster. Användningen av dessa mått kräver **[!UICONTROL Adobe Analytics for Streaming Media Add-on]**. Kontakta Adobe Account Team för mer information.

När du aktiverar **[!UICONTROL Video Metadata]** under [Medierapportering](/help/admin/tools/manage-rs/edit-settings/media-management.md) är följande mått tillgängliga:

| Måttnamn | Beskrivning | Skickat med | Sammanhangsdatavariabel | XDM-fält |
| --- | --- | --- | --- | --- |
| **[!UICONTROL Authorized]** | Ett booleskt värde som utlöses när användaren autentiseras via Adobe. | Mediestart, stäng media | `a.media.pass.auth` | `xdm.mediaCollection.`<br>`sessionDetails.authorized`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.authorized` |
