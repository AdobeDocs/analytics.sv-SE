---
title: Kvalitetsstatistik för direktuppspelande medietjänster
description: Tillgängliga mätvärden när du aktiverar [!UICONTROL Media Quality] för en rapportserie.
feature: Metrics
exl-id: a64829b5-d45b-44c6-80c3-5acf1a6d9919
source-git-commit: 936644c719f46a1327c8a5aa247ed69a14d3da1e
workflow-type: tm+mt
source-wordcount: '288'
ht-degree: 0%

---

# Kvalitetsstatistik för direktuppspelande medietjänster

*Den här sidan beskriver tillgängliga mätvärden när du aktiverar [!UICONTROL Media Quality] för en rapportserie. Se [Kvalitetsdimensioner för direktuppspelande medietjänster](../dimensions/sm-quality.md) för tillgängliga dimensioner.*

Kvalitetsstatistik för direktuppspelande medietjänster ger ytterligare rapporteringsfunktioner för datainsamling via bibliotek för direktuppspelande medietjänster. Användningen av dessa mått kräver **[!UICONTROL Adobe Analytics for Streaming Media Add-on]**. Kontakta Adobe Account Team för mer information.

När du aktiverar **[!UICONTROL Media Quality]** under [Medierapportering](/help/admin/tools/manage-rs/edit-settings/media-management.md) är följande mått tillgängliga:

| Måttnamn | Beskrivning | Skickat med | Sammanhangsdatavariabel | XDM-fält |
| --- | --- | --- | --- | --- |
| **[!UICONTROL Average bitrate]** | Ett viktat genomsnitt av alla bithastighetsvärden för uppspelningens längd. | Stäng media | `a.media.qoe.`<br>`bitrateAverage` | `xdm.mediaReporting.`<br>`qoeDataDetails.bitrateAverage` |
| **[!UICONTROL Bitrate change impacted streams]** | Ett booleskt värde som utlöses om bithastigheten ändras minst en gång under en uppspelningssession. | Stäng media | `a.media.qoe.`<br>`bitrateChange` | `xdm.mediaReporting.`<br>`qoeDataDetails.`<br>`hasBitrateChangeImpactedStreams` |
| **[!UICONTROL Bitrate changes]** | Antalet gånger som bithastigheten har ändrats. | Stäng media | `a.media.qoe.`<br>`bitrateChangeCount` | `xdm.mediaCollection.`<br>`qoeDataDetails.`<br>`bitrateChangeCount`<br><br>`xdm.mediaReporting.`<br>`qoeDataDetails.`<br>`bitrateChangeCount` |
| **[!UICONTROL Buffer impacted streams]** | Ett booleskt värde som utlöses om videon går in i buffertläge minst en gång. | Stäng media | `a.media.qoe.`<br>`buffer` | `xdm.mediaReporting.`<br>`qoeDataDetails.`<br>`hasBufferImpactedStreams` |
| **[!UICONTROL Buffer events]** | Antalet gånger som videon buffrades under en uppspelningssession. | Stäng media | `a.media.qoe.`<br>`bufferCount` | `xdm.mediaReporting.`<br>`qoeDataDetails.bufferCount` |
| **[!UICONTROL Total buffer duration]** | Den tid i sekunder som en video lade på att buffra alla bufferthändelser. | Stäng media | `a.media.qoe.`<br>`bufferTime` | `xdm.mediaReporting.`<br>`qoeDataDetails.bufferTime` |
| **[!UICONTROL Drops before start]** | Ett booleskt värde som utlöses om en användare avslutar innan videons huvudinnehåll börjar. | Stäng media | `a.media.qoe.`<br>`dropBeforeStart` | `xdm.mediaReporting.`<br>`qoeDataDetails.`<br>`isDroppedBeforeStart` |
| **[!UICONTROL Dropped frames]** | Ett heltal som representerar det totala antalet bildrutor som släpptes under en uppspelningssession. | Stäng media | `a.media.qoe.`<br>`droppedFrameCount` | `xdm.mediaCollection.`<br>`qoeDataDetails.droppedFrames`<br><br>`xdm.mediaReporting.`<br>`qoeDataDetails.droppedFrames` |
| **[!UICONTROL Dropped frame impacted streams]** | Ett booleskt värde som utlöses när bildrutor släpps under en uppspelningssession. | Stäng media | `a.media.qoe.`<br>`droppedFrames` | `xdm.mediaReporting.`<br>`qoeDataDetails.`<br>`hasDroppedFrameImpactedStreams` |
| **[!UICONTROL Error impacted streams]** | Ett booleskt värde som utlöses när ett fel inträffar under en uppspelningssession. | Stäng media | `a.media.qoe.`<br>`error` | `xdm.mediaReporting.`<br>`qoeDataDetails.`<br>`hasErrorImpactedStreams` |
| **[!UICONTROL Error events]** | Ett heltal som representerar det totala antalet fel som påträffas under en uppspelningssession. | Stäng media | `a.media.qoe.`<br>`errorCount` | `xdm.mediaReporting.`<br>`qoeDataDetails.errorCount` |
| **[!UICONTROL Time to start]** | Hur lång tid det tar att starta en video, i millisekunder. Adobe konverterar och lagrar det här värdet på några sekunder. | Stäng media | `a.media.qoe.`<br>`timeToStart` | `xdm.mediaCollection.`<br>`qoeDataDetails.timeToStart`<br><br>`xdm.mediaReporting.`<br>`qoeDataDetails.timeToStart` |
