---
title: Röstanalysstatistik
description: Röstanalysstatistik
feature: Metrics
exl-id: 3c1b4e4e-d8d2-446f-9582-a2ce5580a8d3
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '97'
ht-degree: 1%

---

# Röstanalysstatistik

När du aktiverar [!UICONTROL Voice and Chatbots] på [[!UICONTROL Application reporting]](/help/admin/tools/manage-rs/edit-settings/app-reporting.md) skapas följande mått (och [dimensioner](../dimensions/voice-dimensions.md)). Du kan använda [kontextdatavariabler](/help/implement/vars/page-vars/contextdata.md) för att ange dem till värdet `1` (eller mer om tillämpligt). När det är aktiverat i rapportsvitens inställningar skapas [Bearbetningsregler](/help/admin/tools/manage-rs/edit-settings/general/processing-rules/pr-overview.md) automatiskt som mappar röstanalysvärden till deras associerade kontextdatavariabel.

| Måttnamn | Beskrivning | Sammanhangsdatavariabel |
| --- | --- | --- |
| Röstlöften | Utlöses när ett kommando skickas till en röstassistent. | `a.voiceutterances` |
| Röstslutssession | Utlöses när röstappen stängs. | `a.voiceendsession` |
| Röstfel | Utlöses när röstappen påträffar ett fel. | `a.voiceerror` |

{style="table-layout:auto"}
