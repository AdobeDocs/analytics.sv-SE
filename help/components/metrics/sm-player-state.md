---
title: Mätvärden för spårning av direktuppspelningsstatus för mediespelare
description: Tillgängliga mätvärden när du aktiverar [!UICONTROL Player State Tracking] för en rapportserie.
feature: Metrics
source-git-commit: 26c131a37fa1f30c83fd99b290523a97d3c954db
workflow-type: tm+mt
source-wordcount: '361'
ht-degree: 0%

---

# Mätvärden för spårning av direktuppspelningsstatus för mediespelare

Mätvärden för spårning av direktuppspelad mediaspelarstatus ger extra rapporteringsfunktioner för datainsamling via bibliotek för direktuppspelad mediainsamling. Användningen av dessa mått kräver **[!UICONTROL Adobe Streaming Media Collection Add-on]**. Kontakta kontoteamet på Adobe för mer information.

När du aktiverar **[!UICONTROL Player State Tracking]** under [Medierapportering](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/media-management.md) är följande mått tillgängliga:

| Måttnamn | Beskrivning | Skickat med | Sammanhangsdatavariabel |
| --- | --- | --- | --- |
| Strömmar som påverkas av undertexter | Utlöses om minst ett textningstillstånd inträffade under en uppspelningssession. | Stäng media | `a.media.states.closedcaptioning.set` |
| Antal undertexter | Antalet gånger som videon övergick till läget Undertexter. | Stäng media | `a.media.states.closedcaptioning.count` |
| Total varaktighet för undertexter | Den tid videon var i läget Undertexter, i sekunder. | Stäng media | `a.media.states.closedcaptioning.time` |
| Strömmar som påverkas av helskärm | Utlöses om minst ett helskärmsläge inträffar under en uppspelningssession. | Stäng media | `a.media.states.fullscreen.set` |
| Antal helskärmsbilder | Antalet gånger som videon övergick till helskärmsläge. | Stäng media | `a.media.states.fullscreen.count` |
| Total längd för helskärm | Den tid videon var i helskärmsläge, i sekunder. | Stäng media | `a.media.states.fullscreen.time` |
| Strömmar som påverkas av i fokus | Utlöses om minst ett I fokus-läge inträffar under en uppspelningssession. | Stäng media | `a.media.states.infocus.set` |
| Antal i fokus | Antalet gånger som videon har försatts i läget I fokus. | Stäng media | `a.media.states.infocus.count` |
| Total längd för fokus | Den tid som videon var i fokus, i sekunder. | Stäng media | `a.media.states.infocus.time` |
| Strömmar som påverkas av tystnad | Utlöses om minst ett avstängt läge inträffar under en uppspelningssession. | Stäng media | `a.media.states.mute.set` |
| Stäng av räkningar | Antalet gånger som videon övergick till läget Ljud av. | Stäng media | `a.media.states.mute.count` |
| Ljud av total varaktighet | Den tid videon var i läget Ljud av, i sekunder. | Stäng media | `a.media.states.mute.time` |
| Strömmar som påverkas av bild-i-bild | Utlöses om minst ett bild-i-bild-läge inträffar under en uppspelningssession. | Stäng media | `a.media.states.pictureinpicture.set` |
| Bild-i-bildantal | Antalet gånger som videon övergick till läget Bild-i-bild. | Stäng media | `a.media.states.pictureinpicture.count` |
| Total längd för bild | Den tid videon var i läget Bild-i-bild, i sekunder. | Stäng media | `a.media.states.pictureinpicture.time` |

{style="table-layout:auto"}
