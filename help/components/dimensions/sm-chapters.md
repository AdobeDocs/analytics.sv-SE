---
title: Kapiteldimensioner för direktuppspelande media
description: Tillgängliga dimensioner när du aktiverar [!UICONTROL Media Chapters] för en rapportserie.
feature: Dimensions
exl-id: cac66a0b-3f83-46a9-b35c-ba08e0eafb92
source-git-commit: 7609ecb3c34fb0bc8293fc1ecd409cfabb327295
workflow-type: tm+mt
source-wordcount: '181'
ht-degree: 1%

---

# Kapiteldimensioner för direktuppspelande medietjänster

*Den här sidan beskriver de tillgängliga dimensionerna när du aktiverar [!UICONTROL Media Chapters] för en rapportserie. Se [Kapitelmått för direktuppspelande medietjänster](../metrics/sm-chapters.md) för tillgängliga mått.*

Kapiteldimensioner för direktuppspelande medietjänster ger extra rapporteringsfunktioner för datainsamling via bibliotek för direktuppspelande medietjänster. Användningen av de här dimensionerna kräver **[!UICONTROL Adobe Analytics for Streaming Media Ad-on]**. Kontakta Adobe Account Team för mer information.

När du aktiverar **[!UICONTROL Media Chapters]** under [Medierapportering](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/media-management.md) är följande dimension tillgänglig:

| Dimension name | Beskrivning | Skickat med | Sammanhangsdatavariabel |
| --- | --- | --- | --- |
| Kapitel | Det automatiskt genererade kapitel-ID:t. | Stängd kapitel | `a.media.chapter.name` |

{style="table-layout:auto"}

Utöver ovanstående dimensioner skapar Adobe automatiskt följande klassificeringsdimensioner. Du måste överföra klassificeringsdata för att visa rapporter som använder dessa dimensioner.

| Klassificeringsnamn | Överordnad dimension | Beskrivning |
| --- | --- | --- |
| Originator | [Innehåll](sm-core.md) | Innehållets skapare. |
| Kapitellängd | Kapitel | Kapitelns längd i sekunder. |
| Kapitelnamn | Kapitel | Kapitelns egna namn. |
| Kapitelförskjutning | Kapitel | Kapitelns förskjutning i innehållet från början, i sekunder. |
| Kapitelposition | Kapitel | Indexpositionen för kapitlet i innehållet. |

{style="table-layout:auto"}
