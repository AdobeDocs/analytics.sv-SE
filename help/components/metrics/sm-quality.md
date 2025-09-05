---
title: Kvalitetsstatistik för direktuppspelande medietjänster
description: Tillgängliga mätvärden när du aktiverar [!UICONTROL Media Quality] för en rapportserie.
feature: Metrics
exl-id: a64829b5-d45b-44c6-80c3-5acf1a6d9919
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '319'
ht-degree: 0%

---

# Kvalitetsstatistik för direktuppspelande medietjänster

*Den här sidan beskriver tillgängliga mätvärden när du aktiverar [!UICONTROL Media Quality] för en rapportserie. Se [Kvalitetsdimensioner för direktuppspelande medietjänster](../dimensions/sm-quality.md) för tillgängliga dimensioner.*

Kvalitetsstatistik för direktuppspelande medietjänster ger ytterligare rapporteringsfunktioner för datainsamling via bibliotek för direktuppspelande medietjänster. Användningen av dessa mått kräver **[!UICONTROL Adobe Analytics for Streaming Media Ad-on]**. Kontakta Adobe Account Team för mer information.

När du aktiverar **[!UICONTROL Media Quality]** under [Medierapportering](/help/admin/tools/manage-rs/edit-settings/media-management.md) är följande mått tillgängliga:

| Måttnamn | Beskrivning | Skickat med | Sammanhangsdatavariabel |
| --- | --- | --- | --- |
| Genomsnittlig bithastighet | Ett viktat genomsnitt av alla bithastighetsvärden för uppspelningens längd. | Stäng media | `a.media.qoe.bitrateAverage` |
| Bithastighetsändring påverkar strömmar | Ett booleskt värde som utlöses om bithastigheten ändras minst en gång under en uppspelningssession. | Stäng media | `a.media.qoe.bitrateChange` |
| Bithastighetsändringar | Antalet gånger som bithastigheten har ändrats. | Stäng media | `a.media.qoe.bitrateChangeCount` |
| Buffertpåverkade strömmar | Ett booleskt värde som utlöses om videon går in i buffertläge minst en gång. | Stäng media | `a.media.qoe.buffer` |
| Bufferthändelser | Antalet gånger som videon buffrades under en uppspelningssession. | Stäng media | `a.media.qoe.bufferCount` |
| Total buffertlängd | Den tid i sekunder som en video lade på att buffra alla bufferthändelser. | Stäng media | `a.media.qoe.bufferTime` |
| Droppar före start | Ett booleskt värde som utlöses om en användare avslutar innan videons huvudinnehåll börjar. | Stäng media | `a.media.qoe.dropBeforeStart` |
| Släppta bildrutor | Ett heltal som representerar det totala antalet bildrutor som släpptes under en uppspelningssession. | Stäng media | `a.media.qoe.droppedFrameCount` |
| Släppta bildruteeffekter | Ett booleskt värde som utlöses när bildrutor släpps under en uppspelningssession. | Stäng media | `a.media.qoe.droppedFrames` |
| Fel som påverkar strömmar | Ett booleskt värde som utlöses när ett fel inträffar under en uppspelningssession. | Stäng media | `a.media.qoe.error` |
| Felhändelser | Ett heltal som representerar det totala antalet fel som påträffas under en uppspelningssession. | Stäng media | `a.media.qoe.errorCount` |
| Tid att starta | Hur lång tid det tar att starta en video, i millisekunder. Adobe konverterar och lagrar det här värdet på några sekunder. | Stäng media | `a.media.qoe.timeToStart` |
