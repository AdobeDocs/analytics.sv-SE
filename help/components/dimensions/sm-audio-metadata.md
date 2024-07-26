---
title: Metadata för direktuppspelat ljud
description: Tillgängliga dimensioner när du aktiverar [!UICONTROL Audio Metadata] för en rapportserie.
feature: Dimensions
source-git-commit: 45b371bd20223b86d0f17d9bdb48cffb2de15468
workflow-type: tm+mt
source-wordcount: '135'
ht-degree: 1%

---

# Metadata för direktuppspelat ljud

Med annonsdimensionerna för direktuppspelning av media får datainsamlingen extra funktioner via bibliotek för direktuppspelad mediainsamling. Användningen av de här dimensionerna kräver **[!UICONTROL Adobe Streaming Media Collection Add-on]**. Kontakta kontoteamet på Adobe för mer information.

När du aktiverar **[!UICONTROL Audio Metadata]** under [Medierapportering](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/media-management.md) är följande dimensioner tillgängliga:

| Dimensionens namn | Beskrivning | Skickat med | Sammanhangsdatavariabel |
| --- | --- | --- | --- |
| Album | Namnet på albumet. | Mediestart, stäng media | `a.media.album` |
| Konstnär | Namnet på artisten. | Mediestart, stäng media | `a.media.artist` |
| Upphovsman | Namnet på författaren av ljudboken. | Mediestart, stäng media | `a.media.author` |
| Etikett | Namnet på postetiketten. | Mediestart, stäng media | `a.media.label` |
| Utgivare | Namnet på ljudinnehållsutgivaren. | Mediestart, stäng media | `a.media.publisher` |
| Station | Namn eller ID för radiostationen. | Mediestart, stäng media | `a.media.station` |

{style="table-layout:auto"}
