---
title: Mätvärden för spårning av spelartillstånd för direktuppspelning av medietjänster
description: Tillgängliga mätvärden när du aktiverar [!UICONTROL Player State Tracking] för en rapportserie.
feature: Metrics
exl-id: 324936cc-0c7a-4710-a618-b24cc6a2c2cf
source-git-commit: 936644c719f46a1327c8a5aa247ed69a14d3da1e
workflow-type: tm+mt
source-wordcount: '306'
ht-degree: 0%

---

# Mätvärden för spårning av spelartillstånd för direktuppspelning av medietjänster

Mätvärden för statusspårning för direktuppspelning av medietjänster ger ytterligare rapporteringsfunktioner för datainsamling via bibliotek för direktuppspelande medietjänster. Användningen av dessa mått kräver **[!UICONTROL Adobe Analytics for Streaming Media Add-on]**. Kontakta Adobe Account Team för mer information.

När du aktiverar **[!UICONTROL Player State Tracking]** under [Medierapportering](/help/admin/tools/manage-rs/edit-settings/media-management.md) är följande mått tillgängliga:

| Måttnamn | Beskrivning | Skickat med | Sammanhangsdatavariabel | XDM-fält |
| --- | --- | --- | --- | --- |
| **[!UICONTROL Streams impacted by closed captioning]** | Utlöses om minst ett textningstillstånd inträffade under en uppspelningssession. | Stäng media | `a.media.states.`<br>`closedcaptioning.set` | `mediaReporting.`<br>`states.[*].isSet` |
| **[!UICONTROL Closed captioning counts]** | Antalet gånger som videon övergick till läget Undertexter. | Stäng media | `a.media.states.`<br>`closedcaptioning.count` | `xdm.mediaReporting.`<br>`states.[*].count` |
| **[!UICONTROL Closed captioning total duration]** | Den tid videon var i läget Undertexter, i sekunder. | Stäng media | `a.media.states.`<br>`closedcaptioning.time` | `xdm.mediaReporting.`<br>`states.[*].time` |
| **[!UICONTROL Streams impacted by full screen]** | Utlöses om minst ett helskärmsläge inträffar under en uppspelningssession. | Stäng media | `a.media.states.`<br>`fullscreen.set` | `xdm.mediaReporting.`<br>`states.[*].isSet` |
| **[!UICONTROL Full screen counts]** | Antalet gånger som videon övergick till helskärmsläge. | Stäng media | `a.media.states.`<br>`fullscreen.count` | `xdm.mediaReporting.`<br>`states.[*].count` |
| **[!UICONTROL Full screen total duration]** | Den tid videon var i helskärmsläge, i sekunder. | Stäng media | `a.media.states.`<br>`fullscreen.time` | `xdm.mediaReporting.`<br>`states.[*].time` |
| **[!UICONTROL Streams impacted by in focus]** | Utlöses om minst ett I fokus-läge inträffar under en uppspelningssession. | Stäng media | `a.media.states.`<br>`infocus.set` | `mediaReporting.`<br>`states.[*].isSet` |
| **[!UICONTROL In focus counts]** | Antalet gånger som videon har försatts i läget I fokus. | Stäng media | `a.media.states.`<br>`infocus.count` | `xdm.mediaReporting.`<br>`states.[*].count` |
| **[!UICONTROL In focus total duration]** | Den tid som videon var i fokus, i sekunder. | Stäng media | `a.media.states.`<br>`infocus.time` | `xdm.mediaReporting.`<br>`states.[*].time` |
| **[!UICONTROL Streams impacted by mute]** | Utlöses om minst ett avstängt läge inträffar under en uppspelningssession. | Stäng media | `a.media.states.`<br>`mute.set` | `xdm.mediaReporting.`<br>`states.[*].isSet` |
| **[!UICONTROL Mute counts]** | Antalet gånger som videon övergick till läget Ljud av. | Stäng media | `a.media.states.`<br>`mute.count` | `xdm.mediaReporting.`<br>`states.[*].count` |
| **[!UICONTROL Mute total duration]** | Den tid videon var i läget Ljud av, i sekunder. | Stäng media | `a.media.states.`<br>`mute.time` | `xdm.mediaReporting.`<br>`states.[*].time` |
| **[!UICONTROL Streams impacted by picture in picture]** | Utlöses om minst ett bild-i-bild-läge inträffar under en uppspelningssession. | Stäng media | `a.media.states.`<br>`pictureinpicture.set` | `mediaReporting.states.`<br>`[*].isSet` |
| **[!UICONTROL Picture in picture counts]** | Antalet gånger som videon övergick till läget Bild-i-bild. | Stäng media | `a.media.states.`<br>`pictureinpicture.count` | `xdm.mediaReporting.`<br>`states.[*].count` |
| **[!UICONTROL Picture in picture total duration]** | Den tid videon var i läget Bild-i-bild, i sekunder. | Stäng media | `a.media.states.`<br>`pictureinpicture.time` | `xdm.mediaReporting.`<br>`states.[*].time` |
