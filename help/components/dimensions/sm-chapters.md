---
title: Kapiteldimensioner för direktuppspelande media
description: Tillgängliga dimensioner när du aktiverar [!UICONTROL Media Chapters] för en rapportserie.
feature: Dimensions
exl-id: cac66a0b-3f83-46a9-b35c-ba08e0eafb92
source-git-commit: fdd66c9558f070cd760f37a39e5911f0dac22612
workflow-type: tm+mt
source-wordcount: '178'
ht-degree: 1%

---

# Kapiteldimensioner för direktuppspelande media

*Den här sidan beskriver de tillgängliga dimensionerna när du aktiverar [!UICONTROL Media Chapters] för en rapportserie. Se [Kapitelmått för direktuppspelningsmedia](../metrics/sm-chapters.md) för tillgängliga mått.*

Kapiteldimensioner för direktuppspelande media ger extra rapporteringsfunktioner för datainsamling via bibliotek för direktuppspelande media. Användningen av de här dimensionerna kräver **[!UICONTROL Adobe Streaming Media Collection]**. Kontakta kontoteamet på Adobe för mer information.

När du aktiverar **[!UICONTROL Media Chapters]** under [Medierapportering](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/media-management.md) är följande dimension tillgänglig:

| Dimensionens namn | Beskrivning | Skickat med | Sammanhangsdatavariabel |
| --- | --- | --- | --- |
| Kapitel | Det automatiskt genererade kapitel-ID:t. | Stängd kapitel | `a.media.chapter.name` |

{style="table-layout:auto"}

Förutom ovanstående dimensioner skapar Adobe automatiskt följande klassificeringsdimensioner. Du måste överföra klassificeringsdata för att visa rapporter som använder dessa dimensioner.

| Klassificeringsnamn | Överordnad dimension | Beskrivning |
| --- | --- | --- |
| Originator | [Innehåll](sm-core.md) | Innehållets skapare. |
| Kapitellängd | Kapitel | Kapitelns längd i sekunder. |
| Kapitelnamn | Kapitel | Kapitelns egna namn. |
| Kapitelförskjutning | Kapitel | Kapitelns förskjutning i innehållet från början, i sekunder. |
| Kapitelposition | Kapitel | Indexpositionen för kapitlet i innehållet. |

{style="table-layout:auto"}
