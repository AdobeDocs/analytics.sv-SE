---
title: Kärndimensioner för direktuppspelande medietjänster
description: Tillgängliga dimensioner när du aktiverar [!UICONTROL Media Core] för en rapportserie.
feature: Dimensions
exl-id: 1316a646-a31a-49a4-a670-d56d90dd462b
source-git-commit: 7609ecb3c34fb0bc8293fc1ecd409cfabb327295
workflow-type: tm+mt
source-wordcount: '404'
ht-degree: 1%

---

# Kärndimensioner för direktuppspelande medietjänster

*Den här sidan beskriver de tillgängliga dimensionerna när du aktiverar [!UICONTROL Media Core] för en rapportserie. Se [Kärnstatistik för direktuppspelande medietjänster](../metrics/sm-core.md) för tillgängliga mått.*

De viktigaste dimensionerna för direktuppspelande medietjänster ger grundläggande rapporteringsfunktioner för data som samlas in via bibliotek för direktuppspelande medietjänster. Användningen av de här dimensionerna kräver **[!UICONTROL Adobe Analytics for Streaming Media Ad-on]**. Kontakta Adobe Account Team för mer information.

När du aktiverar **[!UICONTROL Media Core]** under [Medierapportering](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/media-management.md) är följande dimensioner tillgängliga:

| Dimension name | Beskrivning | Skickat med | Sammanhangsdatavariabel |
| --- | --- | --- | --- |
| Innehåll | Innehållets innehålls-ID. | Mediestart, stäng media | `a.media.name` |
| Innehållskanal | Distributionsstationen eller kanalen där innehållet spelas. Alla strängvärden är giltiga. | Mediestart, stäng media | `a.media.channel` |
| Innehållslängd (variabel) | Den maximala längden (eller längden) för det innehåll som används, i sekunder. Den här dimensionen krävs för flera mätvärden, inklusive&quot;genomsnittlig minutmålgrupp&quot;. Om den här dimensionen inte anges är beroende mått inte tillgängliga.<br><br>Det finns också en klassificeringsdimension med namnet &quot;Videolängd&quot;, som har ett liknande syfte. Denna dimension och klassificeringen behandlas som två olika dimensioner. | Mediestart, stäng media | `a.media.length` |
| Innehållsnamn (variabel) | Innehållets egna namn. Det finns också en klassificering med namnet &quot;Videonamn&quot;, som har ett liknande syfte. Denna dimension och klassificeringen behandlas som två olika dimensioner. | Mediestart, stäng media | `a.media.friendlyName` |
| Innehållsspelarens namn | Namnet på innehållsspelaren. | Mediestart, stäng media | `a.media.playerName` |
| Innehållssegment | Intervallet som beskriver den del av innehållet som har visats, i minuter. Segmentet beräknas som min och max för spelhuvudets värden under en uppspelningssession. | Stäng media | `a.media.segment` |
| Innehållstyp | Innehållstypen. Giltiga värden är `song`, `podcast`, `audiobook`, `radio`, `VoD`, `Live`, `Linear`, `UGC`, `DVoD` eller ett anpassat värde. | Mediestart, stäng media | `a.contentType` |
| Mediesökväg | Sökvägen som besökaren tog för att nå innehållet. | Mediestart | `a.media.path` |
| Strömtyp | Strömtypen. Giltiga värden är `audio` och `video`. | Mediestart, stäng media | `a.media.streamType` |

{style="table-layout:auto"}

Utöver ovanstående dimensioner skapar Adobe automatiskt följande klassificeringsdimensioner. Du måste överföra klassificeringsdata för att visa rapporter som använder dessa dimensioner.

| Klassificeringsnamn | Överordnad dimension | Beskrivning |
| --- | --- | --- |
| Videolängd | Innehåll | Den maximala längden (eller längden) för det innehåll som används, i sekunder. Mätvärden som är beroende av innehållslängd kan inte använda den här klassificeringen. Du måste skapa ett beräknat mätvärde för att få mätvärden som&quot;genomsnittlig minutmålgrupp&quot; med den här klassificeringen. |
| Videonamn | Innehåll | Innehållets egna namn. Det är klassificeringsekvivalenten för innehållsnamn (variabel). |

{style="table-layout:auto"}
