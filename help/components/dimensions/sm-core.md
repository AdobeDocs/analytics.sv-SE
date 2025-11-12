---
title: Kärndimensioner för direktuppspelande medietjänster
description: Tillgängliga dimensioner när du aktiverar [!UICONTROL Media Core] för en rapportserie.
feature: Dimensions
exl-id: 1316a646-a31a-49a4-a670-d56d90dd462b
source-git-commit: 936644c719f46a1327c8a5aa247ed69a14d3da1e
workflow-type: tm+mt
source-wordcount: '367'
ht-degree: 0%

---

# Kärndimensioner för direktuppspelande medietjänster

*Den här sidan beskriver de tillgängliga dimensionerna när du aktiverar [!UICONTROL Media Core] för en rapportserie. Se [Kärnstatistik för direktuppspelande medietjänster](../metrics/sm-core.md) för tillgängliga mått.*

De viktigaste dimensionerna för direktuppspelande medietjänster ger grundläggande rapporteringsfunktioner för data som samlas in via bibliotek för direktuppspelande medietjänster. Användningen av de här dimensionerna kräver **[!UICONTROL Adobe Analytics for Streaming Media Add-on]**. Kontakta Adobe Account Team för mer information.

När du aktiverar **[!UICONTROL Media Core]** under [Medierapportering](/help/admin/tools/manage-rs/edit-settings/media-management.md) är följande dimensioner tillgängliga:

| Dimension name | Beskrivning | Skickat med | Sammanhangsdatavariabel | XDM-fält |
| --- | --- | --- | --- | --- |
| **[!UICONTROL Content]** | Innehållets innehålls-ID. | Mediestart, stäng media | `a.media.`<br>`name` | `xdm.mediaCollection.`<br>`sessionDetails.name`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.name` |
| **[!UICONTROL Content channel]** | Distributionsstationen eller kanalen där innehållet spelas. Alla strängvärden är giltiga. | Mediestart, stäng media | `a.media.`<br>`channel` | `xdm.mediaCollection.`<br>`sessionDetails.channel`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.channel` |
| **[!UICONTROL Content length (variable)]** | Den maximala längden (eller längden) för det innehåll som används, i sekunder. Den här dimensionen krävs för flera mått, inklusive [!UICONTROL Average minute audience]. Om den här dimensionen inte anges är beroende mått inte tillgängliga.<br><br>En klassificeringsdimension med namnet [!UICONTROL Video length] är också tillgänglig, vilket ger ett liknande syfte. Denna dimension och klassificeringen behandlas som två olika dimensioner. | Mediestart, stäng media | `a.media.`<br>`length` | `xdm.mediaCollection.`<br>`sessionDetails.length`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.length` |
| **[!UICONTROL Content name (variable)]** | Innehållets egna namn. Det finns också en klassificering med namnet [!UICONTROL Video name], vilket ger ett liknande syfte. Denna dimension och klassificeringen behandlas som två olika dimensioner. | Mediestart, stäng media | `a.media.`<br>`friendlyName` | `xdm.mediaCollection.`<br>`sessionDetails.friendlyName`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.friendlyName` |
| **[!UICONTROL Content player name]** | Namnet på innehållsspelaren. | Mediestart, stäng media | `a.media.`<br>`playerName` | `xdm.mediaCollection.`<br>`sessionDetails.playerName`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.playerName` |
| **[!UICONTROL Content segment]** | Intervallet som beskriver den del av innehållet som har visats, i minuter. Segmentet beräknas som min och max för spelhuvudets värden under en uppspelningssession. | Stäng media | `a.media.`<br>`segment` | `xdm.mediaReporting.`<br>`sessionDetails.segment` |
| **[!UICONTROL Content type]** | Innehållstypen. Giltiga värden är `song`, `podcast`, `audiobook`, `radio`, `VoD`, `Live`, `Linear`, `UGC`, `DVoD` eller ett anpassat värde. | Mediestart, stäng media | `a.contentType` | `xdm.mediaCollection.`<br>`sessionDetails.contentType`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.contentType` |
| **[!UICONTROL Media path]** | Sökvägen som besökaren tog för att nå innehållet. | Mediestart | `a.media.path` | |
| **[!UICONTROL Stream type]** | Strömtypen. Giltiga värden är `audio` och `video`. | Mediestart, stäng media | `a.media.`<br>`streamType` | `xdm.mediaCollection.`<br>`sessionDetails.streamType`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.streamType` |

Utöver ovanstående dimensioner skapar Adobe automatiskt följande klassificeringsdimensioner. Du måste överföra klassificeringsdata för att visa rapporter som använder dessa dimensioner.

| Klassificeringsnamn | Överordnad dimension | Beskrivning |
| --- | --- | --- |
| **[!UICONTROL Video length]** | [!UICONTROL Content] | Den maximala längden (eller längden) för det innehåll som används, i sekunder. Mätvärden som är beroende av innehållslängd kan inte använda den här klassificeringen. Du måste skapa ett beräknat mätvärde för att få mätvärden som [!UICONTROL Average minute audience] med den här klassificeringen. |
| **[!UICONTROL Video name]** | [!UICONTROL Content] | Innehållets egna namn. Det är klassificeringsekvivalenten för [!UICONTROL Content name (variable)]. |
