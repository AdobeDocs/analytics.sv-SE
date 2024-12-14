---
title: Streaming Media core metrics
description: Tillgängliga mätvärden när du aktiverar [!UICONTROL Media Core] för en rapportserie.
feature: Metrics
exl-id: f4ff5f84-18b6-4e67-b808-133faeaf8605
source-git-commit: fdd66c9558f070cd760f37a39e5911f0dac22612
workflow-type: tm+mt
source-wordcount: '517'
ht-degree: 0%

---

# Streaming Media core metrics

*Den här sidan beskriver tillgängliga mätvärden när du aktiverar [!UICONTROL Media Core] för en rapportserie. Se [Kärndimensioner för direktuppspelande media](../dimensions/sm-core.md) för tillgängliga dimensioner.*

Streaming Media Core-statistik ger grundläggande rapporteringsfunktioner för data som samlas in via bibliotek för mediesamling. Användningen av dessa mått kräver **[!UICONTROL Adobe Streaming Media Collection]**. Kontakta kontoteamet på Adobe för mer information.

När du aktiverar **[!UICONTROL Media Core]** under [Medierapportering](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/media-management.md) är följande mått tillgängliga:

| Måttnamn | Beskrivning | Skickat med | Sammanhangsdatavariabel |
| --- | --- | --- | --- |
| Genomsnittlig minutmålgrupp | Den totala tid som har ägnats åt ett visst innehållsavsnitt, dividerat med längden för alla uppspelningssessioner.<br>`[Time spent] / [Media length]` | Stäng media | `a.media.averageMinuteAudience` |
| Innehållet slutförs | Utlöses när en del av innehållet är klart. Det här måttet behöver inte nödvändigtvis innebära att de såg hela innehållet. De kunde ha hoppat över i förväg. Det betyder bara att de har nått slutet av innehållet. | `a.media.complete` |
| Pausade påverkade strömmar | Ett booleskt värde som utlöses om en eller flera pauser inträffar under uppspelningen av innehållet. | Stäng media | `a.media.pause` |
| Pausa händelser | Antal pauser som inträffade under en uppspelningssession. | Stäng media | `a.media.pauseCount` |
| Total paus | Den totala längden för alla paushändelser, i sekunder. | Stäng media | `a.media.pauseTime` |
| Innehållet börjar | Den första bildrutan med media förbrukas. Om en användare hoppar under en annons eller under buffring utlöses inte den här händelsen. | Stäng media | `a.media.play` |
| 10 % förloppsindikator | Spelhuvudet skickar 10 %-markören med innehåll baserat på längd. Den här markören räknas bara en gång, även om du söker bakåt. Om du söker framåt räknas inte överhoppade markörer. | Stäng media | `a.media.progress10` |
| 25 % förloppsmärke | Spelhuvudet skickar innehållets 25 %-markör baserat på längd. Den här markören räknas bara en gång, även om du söker bakåt. Om du söker framåt räknas inte överhoppade markörer. | Stäng media | `a.media.progress25` |
| Förloppsindikator för 50 % | Spelhuvudet skickar innehållets 50 %-markör baserat på längd. Den här markören räknas bara en gång, även om du söker bakåt. Om du söker framåt räknas inte överhoppade markörer. | Stäng media | `a.media.progress50` |
| 75 % förloppsmärke | Spelhuvudet skickar 75 %-markören med innehåll baserat på längd. Den här markören räknas bara en gång, även om du söker bakåt. Om du söker framåt räknas inte överhoppade markörer. | Stäng media | `a.media.progress75` |
| 95 % förloppsmärke | Spelhuvudet skickar 95 %-markören med innehåll baserat på längd. Den här markören räknas bara en gång, även om du söker bakåt. Om du söker framåt räknas inte överhoppade markörer. | Stäng media | `a.media.progress95` |
| Återuppta innehåll | Ett booleskt värde som utlöses när innehållet återupptas efter mer än 30 minuters buffring, paus eller uppehåll. Utlöses också om det anges av spelaren på VideoInfo trackPlay. | Stäng media | `a.media.resume` |
| Vyer för innehållssegment | Ett booleskt värde som utlöser den första bildrutan i det visade segmentet. | Stäng media | `a.media.segmentView` |
| Media börjar | Ett booleskt värde som utlöses när mediet först läses in. Den här händelsen innehåller annonser, buffring och fel. | Mediestart | `a.media.view` |
| Innehållstid | Den totala händelselängden för alla händelser av typen PLAY i huvudinnehållet, i sekunder. | Stäng media | `a.media.timePlayed` |
| Unik uppspelad tid | Den totala tiden som unikt innehåll spelas upp, i sekunder. Det här måttet utesluter den tid som spelas upp när upprepat innehåll visas, t.ex. sökning bakåt. | Stäng media | `a.media.uniqueTimePlayed` |

{style="table-layout:auto"}
