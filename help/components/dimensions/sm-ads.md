---
title: Direktuppspelning av medietjänster och dimensioner
description: Tillgängliga dimensioner när du aktiverar [!UICONTROL Media Ads] för en rapportserie.
feature: Dimensions
exl-id: 3f17bacc-8c36-499a-a863-9298e2d54370
source-git-commit: 936644c719f46a1327c8a5aa247ed69a14d3da1e
workflow-type: tm+mt
source-wordcount: '399'
ht-degree: 0%

---

# Direktuppspelning av medietjänster och dimensioner

*Den här sidan beskriver de tillgängliga dimensionerna när du aktiverar [!UICONTROL Media Ads] för en rapportserie. Se [annonsstatistik för direktuppspelningsmedia](../metrics/sm-ads.md) för tillgängliga mått.*

Direktuppspelning av medietjänster och dimensioner ger extra rapporteringsfunktioner för datainsamling via bibliotek för direktuppspelande medietjänster. Användningen av de här dimensionerna kräver **[!UICONTROL Adobe Analytics for Streaming Media Add-on]**. Kontakta Adobe Account Team för mer information.

När du aktiverar **[!UICONTROL Media Ads]** under [Medierapportering](/help/admin/tools/manage-rs/edit-settings/media-management.md) är följande dimensioner tillgängliga:

| Dimension name | Beskrivning | Skickat med | Sammanhangsdatavariabel | XDM-fält |
| --- | --- | --- | --- | --- |
| **[!UICONTROL Ad]** | Annonsens unika identifierare. | Annonsstart, annonsstängning | `a.media.ad.`<br>`name` | `xdm.mediaCollection.`<br>`advertisingDetails.name`<br><br>`xdm.mediaReporting.`<br>`advertisingDetails.name` |
| **[!UICONTROL Ad name (variable)]** | Annonsens egna namn. En klassificeringsdimension med namnet [!UICONTROL Ad name] är också tillgänglig, vilket ger ett liknande syfte. Denna dimension och klassificeringen behandlas som två olika dimensioner. | Annonsstart, annonsstängning | `a.media.ad.`<br>`friendlyName` | `xdm.mediaCollection.`<br>`advertisingDetails.friendlyName`<br><br>`xdm.mediaReporting.`<br>`advertisingDetails.friendlyName` |
| **[!UICONTROL Ad player name]** | Namnet på spelaren som återger annonsen. | Annonsstart, annonsstängning | `a.media.ad.`<br>`playerName` | `xdm.mediaCollection.`<br>`advertisingDetails.playerName`<br><br>`xdm.mediaReporting.`<br>`advertisingDetails.playerName` |
| **[!UICONTROL Ad length (variable)]** | Längden på videoannonsen, i sekunder. | Annonsstart, annonsstängning | `a.media.ad.`<br>`length` | `xdm.mediaCollection.`<br>`advertisingDetails.length`<br><br>`xdm.mediaReporting.`<br>`advertisingDetails.length` |
| **[!UICONTROL Ad pod]** | Den unika identifieraren för annonstavlan. | Annonsstart, annonsstängning | `a.media.ad.`<br>`pod` | |
| **[!UICONTROL Ad in pod position]** | Indexpositionen för annonsen inuti den överordnade annonsbrytningen (0-indexerad). | Annonsstart, annonsstängning | `a.media.ad.`<br>`podPosition` | `xdm.mediaCollection.`<br>`advertisingDetails.podPosition`<br><br>`xdm.mediaReporting.`<br>`advertisingDetails.podPosition` |
| **[!UICONTROL Advertiser]** | Företaget eller varumärket som fanns med i annonsen. | Annonsstart, annonsstängning | `a.media.ad.`<br>`advertiser` | `xdm.mediaCollection.`<br>`advertisingDetails.advertiser`<br><br>`xdm.mediaReporting.`<br>`advertisingDetails.advertiser` |
| **[!UICONTROL Campaign ID]** | ID:t för annonskampanjen | Annonsstart, annonsstängning | `a.media.ad.`<br>`campaign` | `xdm.mediaCollection.`<br>`advertisingDetails.campaignID`<br><br>`xdm.mediaReporting.`<br>`advertisingDetails.campaignID` |

Utöver ovanstående dimensioner skapar Adobe automatiskt följande klassificeringsdimensioner. Du måste överföra klassificeringsdata för att visa rapporter som använder dessa dimensioner.

| Klassificeringsnamn | Överordnad dimension | Beskrivning |
| --- | --- | --- |
| **[!UICONTROL Asset ID]** | [[!UICONTROL Content]](sm-core.md) | Den unika identifieraren för medieresursens innehåll. Exempel är TV-seriens avsnittsidentifierare, identifierare för filmresurs eller live-händelseidentifierare. Dessa ID:n härleds vanligtvis från metadatamyndigheter som EIDR, TMS/Gracenote, Rovi eller från andra egna eller interna system. |
| **[!UICONTROL Content rating]** | [[!UICONTROL Content]](sm-core.md) | Betyg enligt definitionen i TV:s föräldrariktlinjer. |
| **[!UICONTROL First air date]** | [[!UICONTROL Content]](sm-core.md) | Det datum då innehållet först skrevs på tv. Eftersom den här klassificeringsdimensionen är en sträng tillåts alla datumformat. Adobe rekommenderar att du använder ett konsekvent datumformat, till exempel `YYYY-MM-DD`. |
| **[!UICONTROL First digital date]** | [[!UICONTROL Content]](sm-core.md) | Det datum då innehållet först skrevs på en digital kanal eller plattform. Eftersom den här klassificeringsdimensionen är en sträng tillåts alla datumformat. Adobe rekommenderar att du använder ett konsekvent datumformat, till exempel `YYYY-MM-DD`. |
| **[!UICONTROL Ad length]** | [!UICONTROL Ad] | Längden på videoannonsen, i sekunder. |
| **[!UICONTROL Ad name]** | [!UICONTROL Ad] | Annonsens egna namn. Det är klassificeringsekvivalenten för [!UICONTROL Ad name (variable)]. |
| **[!UICONTROL Creative ID]** | [!UICONTROL Ad] | Annonspersonalens ID. |
| **[!UICONTROL Pod name]** | [!UICONTROL Ad pod] | Det egna namnet på annonstavlan. |
| **[!UICONTROL Pod position]** | [!UICONTROL Ad pod] | Annonsens förskjutning i innehållet, i sekunder. |
