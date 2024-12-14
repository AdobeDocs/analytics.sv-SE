---
title: Streaming Media och dimensioner
description: Tillgängliga dimensioner när du aktiverar [!UICONTROL Media Ads] för en rapportserie.
feature: Dimensions
exl-id: 3f17bacc-8c36-499a-a863-9298e2d54370
source-git-commit: fdd66c9558f070cd760f37a39e5911f0dac22612
workflow-type: tm+mt
source-wordcount: '449'
ht-degree: 0%

---

# Streaming Media och dimensioner

*Den här sidan beskriver de tillgängliga dimensionerna när du aktiverar [!UICONTROL Media Ads] för en rapportserie. Se [annonsstatistik för direktuppspelningsmedia](../metrics/sm-ads.md) för tillgängliga mått.*

Med annonsdimensionerna för direktuppspelning av media får datainsamlingen extra funktioner via bibliotek för direktuppspelad mediainsamling. Användningen av de här dimensionerna kräver **[!UICONTROL Adobe Streaming Media Collection]**. Kontakta kontoteamet på Adobe för mer information.

När du aktiverar **[!UICONTROL Media Ads]** under [Medierapportering](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/media-management.md) är följande dimensioner tillgängliga:

| Dimensionens namn | Beskrivning | Skickat med | Sammanhangsdatavariabel |
| --- | --- | --- | --- |
| Annons | Annonsens unika identifierare. | Annonsstart, annonsstängning | `a.media.ad.name` |
| Annonsnamn (variabel) | Annonsens egna namn. Det finns också en klassificeringsdimension med namnet&quot;annonsnamn&quot;, som har ett liknande syfte. Denna dimension och klassificeringen behandlas som två olika dimensioner. | Annonsstart, annonsstängning | `a.media.ad.friendlyName` |
| Namn på annonsspelare | Namnet på spelaren som återger annonsen. | Annonsstart, annonsstängning | `a.media.ad.playerName` |
| Annonslängd (variabel) | Längden på videoannonsen, i sekunder. | Annonsstart, annonsstängning | `a.media.ad.length` |
| Annonsruta | Den unika identifieraren för annonstavlan. | Annonsstart, annonsstängning | `a.media.ad.pod` |
| Lägg till i posta position | Indexpositionen för annonsen inuti den överordnade annonsbrytningen (0-indexerad). | Annonsstart, annonsstängning | `a.media.ad.podPosition` |
| Annonsör | Företaget eller varumärket som fanns med i annonsen. | Annonsstart, annonsstängning | `a.media.ad.advertiser` |
| Kampanj-ID | ID:t för annonskampanjen | Annonsstart, annonsstängning | `a.media.ad.campaign` |

{style="table-layout:auto"}

Förutom ovanstående dimensioner skapar Adobe automatiskt följande klassificeringsdimensioner. Du måste överföra klassificeringsdata för att visa rapporter som använder dessa dimensioner.

| Klassificeringsnamn | Överordnad dimension | Beskrivning |
| --- | --- | --- |
| Tillgångs-ID | [Innehåll](sm-core.md) | Den unika identifieraren för medieresursens innehåll. Exempel är TV-seriens avsnittsidentifierare, identifierare för filmresurs eller live-händelseidentifierare. Dessa ID:n härleds vanligtvis från metadatamyndigheter som EIDR, TMS/Gracenote, Rovi eller från andra egna eller interna system. |
| Innehållsklassificering | [Innehåll](sm-core.md) | Betyg enligt definitionen i TV:s föräldrariktlinjer. |
| Första luftdatum | [Innehåll](sm-core.md) | Det datum då innehållet först skrevs på tv. Eftersom den här klassificeringsdimensionen är en sträng tillåts alla datumformat. Adobe rekommenderar att du använder ett konsekvent datumformat, till exempel `YYYY-MM-DD`. |
| Första digitala datum | [Innehåll](sm-core.md) | Det datum då innehållet först skrevs på en digital kanal eller plattform. Eftersom den här klassificeringsdimensionen är en sträng tillåts alla datumformat. Adobe rekommenderar att du använder ett konsekvent datumformat, till exempel `YYYY-MM-DD`. |
| Annonslängd | Annons | Längden på videoannonsen, i sekunder. |
| Annonsnamn | Annons | Annonsens egna namn. Det är klassificeringsekvivalenten för &#39;annonsnamn (variabel)&#39;. |
| Kreativt ID | Annons | Annonspersonalens ID. |
| Pod name | Annonsruta | Det egna namnet på annonstavlan. |
| Pod position | Annonsruta | Annonsens förskjutning i innehållet, i sekunder. |

{style="table-layout:auto"}
