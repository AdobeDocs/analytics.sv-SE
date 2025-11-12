---
title: Kvalitetsdimensioner för direktuppspelande medietjänster
description: Tillgängliga dimensioner när du aktiverar [!UICONTROL Media Quality] för en rapportserie.
feature: Dimensions
exl-id: e3794d8c-3c03-425d-850c-a735b579324b
source-git-commit: 936644c719f46a1327c8a5aa247ed69a14d3da1e
workflow-type: tm+mt
source-wordcount: '277'
ht-degree: 0%

---

# Kvalitetsdimensioner för direktuppspelande medietjänster

*Den här sidan beskriver de tillgängliga dimensionerna när du aktiverar [!UICONTROL Media Quality] för en rapportserie. Mer information finns i [Kvalitetsstatistik för direktuppspelande medietjänster](../metrics/sm-quality.md).*

Kvalitetsdimensioner för direktuppspelande medietjänster ger rapporter om kvaliteten på det innehåll som besökaren använder. Användningen av de här dimensionerna kräver **[!UICONTROL Adobe Analytics for Streaming Media Add-on]**. Kontakta Adobe Account Team för mer information.

När du aktiverar **[!UICONTROL Media Quality]** under [Medierapportering](/help/admin/tools/manage-rs/edit-settings/media-management.md) är följande dimensioner tillgängliga:

| Dimensionsnamn | Beskrivning | Skickat med | Sammanhangsdatavariabel | XDM-fält |
| --- | --- | --- | --- | --- |
| **[!UICONTROL Average bitrate]** | Genomsnittlig bithastighet i 100-KBPS-intervall. Den beräknas som ett vägt genomsnitt av alla bithastighetsvärden i relation till uppspelningstiden för en viss uppspelningssession. | Stäng media | `a.media.qoe.`<br>`bitrateAverageBucket` | `xdm.mediaCollection.`<br>`qoeDataDetails.`<br>`bitrate`<br><br>`xdm.mediaReporting.`<br>`qoeDataDetails.`<br>`bitrateAverageBucket` |
| **[!UICONTROL Bitrate changes]** | Antalet bithastighetsändringar som inträffade under en uppspelningssession. | Stäng media | `a.media.qoe.`<br>`bitrateChangeCount` | `xdm.mediaCollection.`<br>`qoeDataDetails.`<br>`bitrateChangeCount`<br><br>`xdm.mediaReporting.`<br>`qoeDataDetails.`<br>`bitrateChangeCount` |
| **[!UICONTROL Buffer events]** | Antalet gånger som mediespelaren gick in i ett buffertläge under en uppspelningssession. | Stäng media | `a.media.qoe.`<br>`bufferCount` | `xdm.mediaReporting.`<br>`qoeDataDetails.`<br>`bufferCount` |
| **[!UICONTROL Total buffer duration]** | Den totala buffringstiden i sekunder. | Stäng media | `a.media.qoe.`<br>`bufferTime` | `xdm.mediaReporting.`<br>`qoeDataDetails.`<br>`bufferTime` |
| **[!UICONTROL Dropped frames]** | Det totala antalet uteslutna bildrutor som inträffade under en uppspelningssession. | Stäng media | `a.media.qoe.`<br>`droppedFrameCount` | `xdm.mediaCollection.`<br>`qoeDataDetails.`<br>`droppedFrames`<br><br>`xdm.mediaReporting.`<br>`qoeDataDetails.`<br>`droppedFrames` |
| **[!UICONTROL Errors]** | Det totala antalet fel som uppstod under en uppspelningssession. | Stäng media | `a.media.qoe.`<br>`errorCount` | `xdm.mediaReporting.`<br>`qoeDataDetails.`<br>`errorCount` |
| **[!UICONTROL External error IDs]** | Alla unika fel-ID:n från externa källor, till exempel CDN-fel. Du måste ange önskade felkoder eller ID:n. Flera fel-ID:n tillåts. | Stäng media | `a.media.qoe.`<br>`externalErrors` | `xdm.mediaReporting.`<br>`qoeDataDetails.`<br>`externalErrors` |
| **[!UICONTROL Player SDK error IDs]** | Alla unika fel-ID:n som genereras av innehållsspelaren SDK. Du måste ange önskade felkoder eller ID:n. Flera fel-ID:n tillåts. | Stäng media | `a.media.qoe.`<br>`playerSdkErrors` | `xdm.mediaReporting.`<br>`qoeDataDetails.`<br>`playerSdkErrors` |
| **[!UICONTROL Time to start]** | Standardvärdet är `0` om det inte anges via QoSObject. Ange värdet i millisekunder. Analysis Workspace rapporterar den här dimensionen på några sekunder. | Mediestart, stäng media | `a.media.qoe.`<br>`timeToStart` | `xdm.mediaCollection.`<br>`qoeDataDetails.`<br>`timeToStart`<br><br>`xdm.mediaReporting.`<br>`qoeDataDetails.`<br>`timeToStart` |
