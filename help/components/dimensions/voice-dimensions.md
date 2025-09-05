---
title: Röstanalysdimensioner
description: Röstanalysdimensioner
feature: Dimensions
exl-id: 6e1275c4-3b17-4c65-a308-d420ea1acdf6
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '128'
ht-degree: 0%

---

# Röstanalysdimensioner

När du aktiverar [!UICONTROL Voice and Chatbots] på [[!UICONTROL Application reporting]](/help/admin/tools/manage-rs/edit-settings/app-reporting.md) skapas följande dimensioner (och [mått](../metrics/voice-metrics.md)). Du kan använda [kontextdatavariabler](/help/implement/vars/page-vars/contextdata.md) för att ange dem till det önskade strängvärdet. När det är aktiverat i rapportsvitens inställningar skapas [Bearbetningsregler](/help/admin/tools/manage-rs/edit-settings/general/processing-rules/pr-overview.md) automatiskt som mappar röstanalysdimensioner till deras associerade kontextdatavariabel.

| Dimension name | Beskrivning | Sammanhangsdatavariabel |
| --- | --- | --- |
| Röstfelstyp | Den typ av fel som påträffades. | `a.voiceerrortype` |
| Röstspråk | Språket som användaren interagerar med din röstapp. | `a.voicelanguage` |
| Röstmetod | Det kommando som användaren tänker köra. | `a.voiceintent` |
| Röstappssvar | Svaret som röstappen returnerade till användaren. | `a.voiceappresponse` |
| Röstautentisering | Användarens autentiserade tillstånd vid interaktion med röstappen. | `a.voiceauthentication` |
| Intressepunkts-ID | Intresse-ID. | `a.loc.poi.id` |

{style="table-layout:auto"}
