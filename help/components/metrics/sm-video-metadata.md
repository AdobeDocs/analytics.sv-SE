---
title: Metadata för direktuppspelande medietjänster
description: Tillgängliga mätvärden när du aktiverar [!UICONTROL Video Metadata] för en rapportserie.
feature: Metrics
exl-id: b2f60a34-e139-4498-bf71-74d291759ef2
source-git-commit: 7609ecb3c34fb0bc8293fc1ecd409cfabb327295
workflow-type: tm+mt
source-wordcount: '111'
ht-degree: 0%

---

# Metadata för direktuppspelande medietjänster

*Den här sidan beskriver tillgängliga mätvärden när du aktiverar [!UICONTROL Video metadata] för en rapportserie. Se [Metadata för videometadata för direktuppspelande medietjänster](../dimensions/sm-video-metadata.md) för tillgängliga dimensioner.*

Metadata för direktuppspelande medietjänster ger extra rapporteringsfunktioner för datainsamling via bibliotek för direktuppspelande medietjänster. Användningen av dessa mått kräver **[!UICONTROL Adobe Analytics for Streaming Media Ad-on]**. Kontakta Adobe Account Team för mer information.

När du aktiverar **[!UICONTROL Video Metadata]** under [Medierapportering](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/media-management.md) är följande mått tillgängliga:

| Måttnamn | Beskrivning | Skickat med | Sammanhangsdatavariabel |
| --- | --- | --- | --- |
| Auktoriserad | Ett booleskt värde som utlöses när användaren autentiseras via Adobe. | Mediestart, stäng media | `a.media.pass.auth` |

{style="table-layout:auto"}
