---
title: Kärnstatistik för direktuppspelande medietjänster
description: Tillgängliga mätvärden när du aktiverar [!UICONTROL Media Core] för en rapportserie.
feature: Metrics
exl-id: f4ff5f84-18b6-4e67-b808-133faeaf8605
source-git-commit: 936644c719f46a1327c8a5aa247ed69a14d3da1e
workflow-type: tm+mt
source-wordcount: '357'
ht-degree: 0%

---

# Kärnstatistik för direktuppspelande medietjänster

*Den här sidan beskriver tillgängliga mätvärden när du aktiverar [!UICONTROL Media Core] för en rapportserie. Se [Kärndimensioner för direktuppspelande medietjänster](../dimensions/sm-core.md) för tillgängliga dimensioner.*

De viktigaste mätvärdena för direktuppspelade medietjänster ger grundläggande rapporteringsfunktioner för data som samlas in via bibliotek för insamling av medietjänster. Användningen av dessa mått kräver **[!UICONTROL Adobe Analytics for Streaming Media Add-on]**. Kontakta Adobe Account Team för mer information.

När du aktiverar **[!UICONTROL Media Core]** under [Medierapportering](/help/admin/tools/manage-rs/edit-settings/media-management.md) är följande mått tillgängliga:

| Måttnamn | Beskrivning | Skickat med | Sammanhangsdatavariabel | XDM-fält |
| --- | --- | --- | --- | --- |
| **[!UICONTROL Average minute audience]** | Den totala tid som har ägnats åt ett visst innehållsavsnitt, dividerat med längden för alla uppspelningssessioner.<br>`[Time spent] / [Media length]` | Stäng media | `a.media.`<br>`averageMinuteAudience` | `xdm.mediaReporting.`<br>`sessionDetails.`<br>`averageMinuteAudience` |
| **[!UICONTROL Content completes]** | Utlöses när en del av innehållet är klart. Det här måttet behöver inte nödvändigtvis innebära att de såg hela innehållet. De kunde ha hoppat över i förväg. Det betyder bara att de har nått slutet av innehållet. | | `a.media.complete` | `xdm.mediaReporting.`<br>`sessionDetails.isCompleted` |
| **[!UICONTROL Paused impacted streams]** | Ett booleskt värde som utlöses om en eller flera pauser inträffar under uppspelningen av innehållet. | Stäng media | `a.media.pause` | `xdm.mediaReporting.`<br>`sessionDetails.`<br>`hasPauseImpactedStreams` |
| **[!UICONTROL Pause events]** | Antal pauser som inträffade under en uppspelningssession. | Stäng media | `a.media.pauseCount` | `xdm.mediaReporting.`<br>`sessionDetails.pauseCount` |
| **[!UICONTROL Total pause duration]** | Den totala längden för alla paushändelser, i sekunder. | Stäng media | `a.media.pauseTime` | `xdm.mediaReporting.`<br>`sessionDetails.pauseTime` |
| **[!UICONTROL Content starts]** | Den första bildrutan med media förbrukas. Om en användare hoppar under en annons eller under buffring utlöses inte den här händelsen. | Stäng media | `a.media.play` | `xdm.mediaReporting.`<br>`sessionDetails.isPlayed` |
| **[!UICONTROL 10% progress marker]**<br>**[!UICONTROL 25% progress marker]**<br>**[!UICONTROL 50% progress marker]**<br>**[!UICONTROL 75% progress marker]**<br>**[!UICONTROL 95% progress marker]** | Spelhuvudet skickar den angivna innehållsmarkören baserat på längden. Varje markör räknas bara en gång, även om du söker bakåt. Om du söker framåt räknas inte överhoppade markörer. | Stäng media | `a.media.progress10`<br>`a.media.progress25`<br>`a.media.progress50`<br>`a.media.progress75`<br>`a.media.progress95` | `xdm.mediaReporting.`<br>`sessionDetails.hasProgress10`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.hasProgress25`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.hasProgress50`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.hasProgress75`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.hasProgress95` |
| **[!UICONTROL Content resumes]** | Ett booleskt värde som utlöses när innehållet återupptas efter mer än 30 minuters buffring, paus eller uppehåll. Utlöses också om det anges av spelaren på VideoInfo trackPlay. | Stäng media | `a.media.resume` | `xdm.mediaCollection.`<br>`sessionDetails.hasResume`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.hasResume` |
| **[!UICONTROL Content segment views]** | Ett booleskt värde som utlöser den första bildrutan i det visade segmentet. | Stäng media | `a.media.segmentView` | `xdm.mediaReporting.`<br>`sessionDetails.`<br>`hasSegmentView` |
| **[!UICONTROL Media starts]** | Ett booleskt värde som utlöses när mediet först läses in. Den här händelsen innehåller annonser, buffring och fel. | Mediestart | `a.media.view` | `xdm.mediaReporting.`<br>`sessionDetails.isViewed` |
| **[!UICONTROL Content time spent]** | Den totala händelselängden för alla händelser av typen PLAY i huvudinnehållet, i sekunder. | Stäng media | `a.media.timePlayed` | `xdm.mediaReporting.`<br>`sessionDetails.timePlayed` |
| **[!UICONTROL Unique time played]** | Den totala tiden som unikt innehåll spelas upp, i sekunder. Det här måttet utesluter den tid som spelas upp när upprepat innehåll visas, t.ex. sökning bakåt. | Stäng media | `a.media.`<br>`uniqueTimePlayed` | `xdm.mediaReporting.`<br>`sessionDetails.`<br>`uniqueTimePlayed` |
