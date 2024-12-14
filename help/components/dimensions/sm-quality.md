---
title: Kvalitetsdimensioner för direktuppspelande media
description: Tillgängliga dimensioner när du aktiverar [!UICONTROL Media Quality] för en rapportserie.
feature: Dimensions
exl-id: e3794d8c-3c03-425d-850c-a735b579324b
source-git-commit: fdd66c9558f070cd760f37a39e5911f0dac22612
workflow-type: tm+mt
source-wordcount: '293'
ht-degree: 0%

---

# Kvalitetsdimensioner för direktuppspelande media

*Den här sidan beskriver de tillgängliga dimensionerna när du aktiverar [!UICONTROL Media Quality] för en rapportserie. Mer information finns i [Värden för direktuppspelad mediekvalitet](../metrics/sm-quality.md).*

Dimensionerna för direktuppspelad mediakvalitet ger rapporter om kvaliteten på det innehåll som besökaren använder. Användningen av de här dimensionerna kräver [!UICONTROL Adobe Streaming Media Collection]. Kontakta kontoteamet på Adobe för mer information.

När du aktiverar **[!UICONTROL Media Quality]** under [Medierapportering](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/media-management.md) är följande dimensioner tillgängliga:

| Dimensionens namn | Beskrivning | Skickat med | Sammanhangsdatavariabel |
| --- | --- | --- | --- |
| Genomsnittlig bithastighet | Genomsnittlig bithastighet i 100-KBPS-intervall. Den beräknas som ett vägt genomsnitt av alla bithastighetsvärden i relation till uppspelningstiden för en viss uppspelningssession. | Stäng media | `a.media.qoe.bitrateAverageBucket` |
| Bithastighetsändringar | Antalet bithastighetsändringar som inträffade under en uppspelningssession. | Stäng media | `a.media.qoe.bitrateChangeCount` |
| Bufferthändelser | Antalet gånger som mediespelaren gick in i ett buffertläge under en uppspelningssession. | Stäng media | `a.media.qoe.bufferCount` |
| Total buffertlängd | Den totala buffringstiden i sekunder. | Stäng media | `a.media.qoe.bufferTime` |
| Släppta bildrutor | Det totala antalet uteslutna bildrutor som inträffade under en uppspelningssession. | Stäng media | `a.media.qoe.droppedFrameCount` |
| Fel | Det totala antalet fel som uppstod under en uppspelningssession. | Stäng media | `a.media.qoe.errorCount` |
| Externa fel-ID | Alla unika fel-ID:n från externa källor, till exempel CDN-fel. Du måste ange önskade felkoder eller ID:n. Flera fel-ID:n tillåts. | Stäng media | `a.media.qoe.externalErrors` |
| Fel-ID för Player SDK | Alla unika fel-ID:n som genereras av innehållsspelaren SDK. Du måste ange önskade felkoder eller ID:n. Flera fel-ID:n tillåts. | Stäng media | `a.media.qoe.playerSdkErrors` |
| Tid att starta | Standardvärdet är `0` om det inte anges via QoSObject. Ange värdet i millisekunder. Analysis Workspace rapporterar den här dimensionen på några sekunder. | Mediestart, stäng media | `a.media.qoe.timeToStart` |

{style="table-layout:auto"}
