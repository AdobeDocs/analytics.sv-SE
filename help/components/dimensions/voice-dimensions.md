---
title: Röstanalysdimensioner
description: Röstanalysdimensioner
feature: Dimensions
exl-id: 6e1275c4-3b17-4c65-a308-d420ea1acdf6
source-git-commit: c2adf6d2e328378332cc290ba2dfd75ee6587ef6
workflow-type: tm+mt
source-wordcount: '128'
ht-degree: 0%

---

# Röstanalysdimensioner

När du aktiverar [!UICONTROL Voice and Chatbots] på [[!UICONTROL Application reporting]](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/app-reporting.md) skapas följande dimensioner (och [mått](../metrics/voice-metrics.md)). Du kan använda [kontextdatavariabler](/help/implement/vars/page-vars/contextdata.md) för att ange dem till det önskade strängvärdet. När det är aktiverat i rapportsvitens inställningar skapas [Bearbetningsregler](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/processing-rules/pr-overview.md) automatiskt som mappar röstanalysdimensioner till deras associerade kontextdatavariabel.

| Dimension name | Beskrivning | Sammanhangsdatavariabel |
| --- | --- | --- |
| Röstfelstyp | Den typ av fel som påträffades. | `a.voiceerrortype` |
| Röstspråk | Språket som användaren interagerar med din röstapp. | `a.voicelanguage` |
| Röstmetod | Det kommando som användaren tänker köra. | `a.voiceintent` |
| Röstappssvar | Svaret som röstappen returnerade till användaren. | `a.voiceappresponse` |
| Röstautentisering | Användarens autentiserade tillstånd vid interaktion med röstappen. | `a.voiceauthentication` |
| Intressepunkts-ID | Intresse-ID. | `a.loc.poi.id` |

{style="table-layout:auto"}
