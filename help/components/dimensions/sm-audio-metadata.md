---
title: Mått på metadata för direktuppspelande medietjänster
description: Tillgängliga dimensioner när du aktiverar [!UICONTROL Audio Metadata] för en rapportserie.
feature: Dimensions
exl-id: 2e4dc1e9-267b-47a2-b791-23d1e754a2c1
source-git-commit: 7609ecb3c34fb0bc8293fc1ecd409cfabb327295
workflow-type: tm+mt
source-wordcount: '138'
ht-degree: 1%

---

# Mått på metadata för direktuppspelande medietjänster

Direktuppspelning av medietjänster och dimensioner ger extra rapporteringsfunktioner för datainsamling via bibliotek för direktuppspelande medietjänster. Användningen av de här dimensionerna kräver **[!UICONTROL Adobe Analytics for Streaming Media Ad-on]**. Kontakta Adobe Account Team för mer information.

När du aktiverar **[!UICONTROL Audio Metadata]** under [Medierapportering](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/media-management.md) är följande dimensioner tillgängliga:

| Dimension name | Beskrivning | Skickat med | Sammanhangsdatavariabel |
| --- | --- | --- | --- |
| Album | Namnet på albumet. | Mediestart, stäng media | `a.media.album` |
| Konstnär | Namnet på artisten. | Mediestart, stäng media | `a.media.artist` |
| Upphovsman | Namnet på författaren av ljudboken. | Mediestart, stäng media | `a.media.author` |
| Etikett | Namnet på postetiketten. | Mediestart, stäng media | `a.media.label` |
| Utgivare | Namnet på ljudinnehållsutgivaren. | Mediestart, stäng media | `a.media.publisher` |
| Station | Namn eller ID för radiostationen. | Mediestart, stäng media | `a.media.station` |

{style="table-layout:auto"}
