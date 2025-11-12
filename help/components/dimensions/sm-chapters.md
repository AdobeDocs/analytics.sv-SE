---
title: Kapiteldimensioner för direktuppspelande media
description: Tillgängliga dimensioner när du aktiverar [!UICONTROL Media Chapters] för en rapportserie.
feature: Dimensions
exl-id: cac66a0b-3f83-46a9-b35c-ba08e0eafb92
source-git-commit: 936644c719f46a1327c8a5aa247ed69a14d3da1e
workflow-type: tm+mt
source-wordcount: '168'
ht-degree: 1%

---

# Kapiteldimensioner för direktuppspelande medietjänster

*Den här sidan beskriver de tillgängliga dimensionerna när du aktiverar [!UICONTROL Media Chapters] för en rapportserie. Se [Kapitelmått för direktuppspelande medietjänster](../metrics/sm-chapters.md) för tillgängliga mått.*

Kapiteldimensioner för direktuppspelande medietjänster ger extra rapporteringsfunktioner för datainsamling via bibliotek för direktuppspelande medietjänster. Användningen av de här dimensionerna kräver **[!UICONTROL Adobe Analytics for Streaming Media Add-on]**. Kontakta Adobe Account Team för mer information.

När du aktiverar **[!UICONTROL Media Chapters]** under [Medierapportering](/help/admin/tools/manage-rs/edit-settings/media-management.md) är följande dimension tillgänglig:

| Dimension name | Beskrivning | Skickat med | Sammanhangsdatavariabel | XDM-fält |
| --- | --- | --- | --- | --- |
| **[!UICONTROL Chapter]** | Det automatiskt genererade kapitel-ID:t. | Stängd kapitel | `a.media.chapter.name` | `xdm.mediaReporting.`<br>`chapterDetails.ID` |

Utöver ovanstående dimensioner skapar Adobe automatiskt följande klassificeringsdimensioner. Du måste överföra klassificeringsdata för att visa rapporter som använder dessa dimensioner.

| Klassificeringsnamn | Överordnad dimension | Beskrivning |
| --- | --- | --- |
| **[!UICONTROL Originator]** | [[!UICONTROL Content]](sm-core.md) | Innehållets skapare. |
| **[!UICONTROL Chapter length]** | [!UICONTROL Chapter] | Kapitelns längd i sekunder. |
| **[!UICONTROL Chapter name]** | [!UICONTROL Chapter] | Kapitelns egna namn. |
| **[!UICONTROL Chapter offset]** | [!UICONTROL Chapter] | Kapitelns förskjutning i innehållet från början, i sekunder. |
| **[!UICONTROL Chapter position]** | [!UICONTROL Chapter] | Indexpositionen för kapitlet i innehållet. |
