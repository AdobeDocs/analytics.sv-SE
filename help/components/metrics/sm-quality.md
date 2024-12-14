---
title: Mätning av direktuppspelad mediakvalitet
description: Tillgängliga mätvärden när du aktiverar [!UICONTROL Media Quality] för en rapportserie.
feature: Metrics
exl-id: a64829b5-d45b-44c6-80c3-5acf1a6d9919
source-git-commit: fdd66c9558f070cd760f37a39e5911f0dac22612
workflow-type: tm+mt
source-wordcount: '315'
ht-degree: 0%

---

# Mätning av direktuppspelad mediakvalitet

*Den här sidan beskriver tillgängliga mätvärden när du aktiverar [!UICONTROL Media Quality] för en rapportserie. Se [Kvalitetsdimensioner för direktuppspelning av media](../dimensions/sm-quality.md) för tillgängliga dimensioner.*

Streaming Media-kvalitetsmätningar ger extra rapporteringsfunktioner för datainsamling via bibliotek för direktuppspelad mediainsamling. Användningen av dessa mått kräver **[!UICONTROL Adobe Streaming Media Collection]**. Kontakta kontoteamet på Adobe för mer information.

När du aktiverar **[!UICONTROL Media Quality]** under [Medierapportering](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/media-management.md) är följande mått tillgängliga:

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
