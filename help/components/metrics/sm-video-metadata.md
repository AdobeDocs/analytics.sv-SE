---
title: Metadata för direktuppspelad video
description: Tillgängliga mätvärden när du aktiverar [!UICONTROL Video Metadata] för en rapportserie.
feature: Metrics
source-git-commit: 26c131a37fa1f30c83fd99b290523a97d3c954db
workflow-type: tm+mt
source-wordcount: '107'
ht-degree: 0%

---

# Metadata för direktuppspelad video

*Den här sidan beskriver tillgängliga mätvärden när du aktiverar [!UICONTROL Video metadata] för en rapportserie. Se [Metadata för direktuppspelad medievideo](../dimensions/sm-video-metadata.md) för tillgängliga dimensioner.*

Metadata för direktuppspelad medievideo ger extra rapporteringsfunktioner för datainsamling via bibliotek för direktuppspelad mediainsamling. Användningen av dessa mått kräver **[!UICONTROL Adobe Streaming Media Collection Add-on]**. Kontakta kontoteamet på Adobe för mer information.

När du aktiverar **[!UICONTROL Video Metadata]** under [Medierapportering](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/media-management.md) är följande mått tillgängliga:

| Måttnamn | Beskrivning | Skickat med | Sammanhangsdatavariabel |
| --- | --- | --- | --- |
| Auktoriserad | Ett booleskt värde som utlöses när användaren autentiseras via Adobe. | Mediestart, stäng media | `a.media.pass.auth` |

{style="table-layout:auto"}
