---
title: Röstanalysstatistik
description: Röstanalysstatistik
feature: Metrics
exl-id: 3c1b4e4e-d8d2-446f-9582-a2ce5580a8d3
source-git-commit: c2adf6d2e328378332cc290ba2dfd75ee6587ef6
workflow-type: tm+mt
source-wordcount: '97'
ht-degree: 1%

---

# Röstanalysstatistik

När du aktiverar [!UICONTROL Voice and Chatbots] på [[!UICONTROL Application reporting]](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/app-reporting.md) skapas följande mått (och [dimensioner](../dimensions/voice-dimensions.md)). Du kan använda [kontextdatavariabler](/help/implement/vars/page-vars/contextdata.md) för att ange dem till värdet `1` (eller mer om tillämpligt). När det är aktiverat i rapportsvitens inställningar skapas [Bearbetningsregler](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/processing-rules/pr-overview.md) automatiskt som mappar röstanalysvärden till deras associerade kontextdatavariabel.

| Måttnamn | Beskrivning | Sammanhangsdatavariabel |
| --- | --- | --- |
| Röstlöften | Utlöses när ett kommando skickas till en röstassistent. | `a.voiceutterances` |
| Röstslutssession | Utlöses när röstappen stängs. | `a.voiceendsession` |
| Röstfel | Utlöses när röstappen påträffar ett fel. | `a.voiceerror` |

{style="table-layout:auto"}
