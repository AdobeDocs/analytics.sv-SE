---
title: Analysdimensioner - kompatibilitet
description: Referens för analysdimensioner och rapporter.
feature: Dimensions
exl-id: 1884bc20-b04d-4f9a-b057-2b2fbe53190d
source-git-commit: 7609ecb3c34fb0bc8293fc1ecd409cfabb327295
workflow-type: tm+mt
source-wordcount: '896'
ht-degree: 6%

---

# Analysdimensioner - kompatibilitet

På den här sidan visas [dimensioner](overview.md) som stöds i deras respektive Analytics-funktioner.

>[!NOTE]
>
>Anpassade variabelnamn, klassificeringar och besökarattribut tas inte med i listan. Dessa dimensionsobjekt är specifika för enskilda rapportsviter.

## Dimensioner som stöds i Analysis Workspace

| Dimension-namn (visas i analysgränssnittet) | Dimension ID (används i API-begäranden) |
|---|---|
| Analyser för Target | `targetraw` |
| Målgrupps-ID | `mcaudiences` |
| [Webbläsare](browser.md) | `browser` |
| [Webbläsartyp](browser-type.md) | `browsertype` |
| [Kategori](category.md) | `category` |
| [Städer](cities.md) | `geocity` |
| [Färgdjup](color-depth.md) | `colordepth` |
| [Anslutningstyp](connection-type.md) | `connectiontype` |
| [Cookie-stöd](cookie-support.md) | `cookie` |
| [Länder](countries.md) | `geocountry` |
| [Kundlojalitet](customer-loyalty.md) | `customerloyalty` |
| [Anpassade konverteringsvariabler](evar.md) | `evar1`, `evar2` osv. |
| [Custom Insight Vars](prop.md) | `prop1`, `prop2` osv. |
| [Anpassad länk](custom-link.md) | `customlink` |
| [Dagar före första köp](days-before-first-purchase.md) | `daysbeforefirstpurchase` |
| [Dagar sedan senaste köp](days-since-last-purchase.md) | `dayssincelastpurchase` |
| [Domän](domain.md) | `filtereddomain` |
| [Hämta länk](download-link.md) | `downloadlink` |
| [Startsida](entry-dimensions.md) | `entrypage` |
| [Startsida, original](entry-dimensions.md) | `entrypageoriginal` |
| [Avsluta länk](exit-link.md) | `exitlink` |
| [Första beröringskanalen](first-touch-channel.md) | `firsttouchchannel` |
| [Första beröringskanaldetalj](first-touch-detail.md) | `firsttouchchanneldetail` |
| [Java aktiverat](java-enabled.md) | `javaenabled` |
| [Språk](language.md) | `language` |
| [Senaste beröringskanal](last-touch-channel.md) | `lasttouchchannel` |
| [Senaste beröringskanalinformation](last-touch-detail.md) | `lasttouchchanneldetail` |
| Listvariabler | `listvariables` |
| [Marknadsföringskanal](marketing-channel.md) | `marketingchannel` |
| [Stöd för mobilljud](mobile-dimensions.md) | `mobileaudiosupport` |
| [Mobiloperatör](mobile-dimensions.md) | `mobilecarrier` |
| [Mobil färgdjup](mobile-dimensions.md) | `mobilecolordepth` |
| [Mobile Cookie-stöd](mobile-dimensions.md) | `mobilecookiesupport` |
| [Mobil enhet](mobile-dimensions.md) | `mobiledevicename` |
| [Typ av mobil enhet](mobile-dimensions.md) | `mobiledevicetype` |
| [Maximal längd för mobil e-post](mobile-dimensions.md) | `mobileemaillength` |
| [Stöd för mobilbilder](mobile-dimensions.md) | `mobileimagesupport` |
| [Mobil tillverkare](mobile-dimensions.md) | `mobilemanufacturer` |
| [Mobiloperativsystem (borttaget)](mobile-dimensions.md) | `mobileos` |
| [Höjd för mobilskärm](mobile-dimensions.md) | `mobilescreenheight` |
| [Storlek på mobilskärm](mobile-dimensions.md) | `mobilescreensize` |
| [Bredd på mobilskärm](mobile-dimensions.md) | `mobilescreenwidth` |
| [Högsta URL-längd för mobil webbläsare](mobile-dimensions.md) | `mobileurllength` |
| [Stöd för mobilvideo](mobile-dimensions.md) | `mobilevideosupport` |
| [Bildskärmsupplösning](monitor-resolution.md) | `monitorresolution` |
| [Operativsystem](operating-systems.md) | `operatingsystem` |
| [Ursprunglig referensdomän](original-referring-domain.md) | `referringdomainoriginal` |
| [Sida](page.md) | `page` |
| [Sidor som inte hittades](pages-not-found.md) | `pagesnotfound` |
| [Produkt](product.md) | `product` |
| [Referent](referrer.md) | `referrer` |
| [Referenstyp](referrer-type.md) | `referrertype` |
| [Referensdomän](referring-domain.md) | `referringdomain` |
| [Områden](regions.md) | `georegion` |
| [Återbesöksfrekvens](return-frequency.md) | `returnfrequency` |
| SC-TnT | `tntbase` |
| [Sökmotor](search-engine.md) | `searchengine` |
| [Sök nyckelord](search-keyword.md) | `searchenginekeyword` |
| [Sökmotor - naturlig](search-engine.md) | `searchenginenatural` |
| [Sökmotor - betald](search-engine.md) | `searchenginepaid` |
| [Söknyckelord - naturligt](search-keyword.md) | `searchenginenaturalkeyword` |
| [Söknyckelord - betald](search-keyword.md) | `searchenginepaidkeyword` |
| [Alla söksidrankning](all-search-page-rank.md) | `searchenginepagerank` |
| [Server](server.md) | `server` |
| [Besök på en sida](single-page-visits.md) | `singlepagevisits` |
| [Webbplatsavsnitt](site-section.md) | `sitesections` |
| [Tid per besök - granulär](time-spent-per-visit.md) | `sitetime` |
| [Spårningskod](tracking-code.md) | `campaign` |
| [US DMA](us-dma.md) | `geodma` |
| [USA](us-states.md) | `state` |
| [Tid före händelse](time-prior-to-event.md) | `timeprior` |
| [Tid per besök - paketerad](time-spent-per-visit.md) | `timespent` |
| [Besök djupet](visit-depth.md) | `pathlength` |
| [Besöksnummer](visit-number.md) | `visitnumber` |
| [Postnummer](zip-code.md) | `zip` |
| [AM/PM](am-pm.md) | `timepartampm` |
| [Webbläsarhöjd - paketerad](browser-height.md) | `browserheightbucketed` |
| [Webbläsarbredd - paketerad](browser-width.md) | `browserwidthbucketed` |
| [Dag](day.md) | `daterangeday` |
| [Dag i månaden](day-of-month.md) | `timepartdayofmonth` |
| [Veckodag](day-of-week.md) | `dayofweek` |
| [Veckodag](day-of-week.md) | `timepartdayofweek` |
| [Dag på året](day-of-year.md) | `timepartdayofyear` |
| [Dagar sedan senaste besök](days-since-last-visit.md) | `dayssincelastvisit` |
| [Anpassade insikter för inträde](entry-dimensions.md) | `entryprops` |
| [Variabler för anmälningslista](entry-dimensions.md) | `entrylistvariables` |
| [Startserver](entry-dimensions.md) | `entryserver` |
| [Deltagande på plats](entry-dimensions.md) | `entrysitesections` |
| [Avsluta anpassade insikter](exit-dimensions.md) | `exitprops` |
| [Avsluta listvariabler](exit-dimensions.md) | `exitlistvariables` |
| [Avsluta sidan](exit-dimensions.md) | `exitpage` |
| [Avsluta servern](exit-dimensions.md) | `exitserver` |
| [Avsluta webbplatsavsnitt](exit-dimensions.md) | `exitsitesections` |
| [Träffdjup](hit-depth.md) | `hitdepth` |
| [Träfftyp](hit-type.md) | `hittype` |
| [Timme](hour.md) | `daterangehour` |
| [Timme på dagen](hour-of-day.md) | `timeparthourofday` |
| [Information om marknadsföringskanal](marketing-detail.md) | `marketingchanneldetail` |
| [Minut](minute.md) | `daterangeminute` |
| [Maximal längd för mobilbokmärke](mobile-dimensions.md) | `mobilebookmarklength` |
| [Mobilenhetsnummer](mobile-dimensions.md) | `mobiledevicenumber` |
| [Mobil-DRM](mobile-dimensions.md) | `mobiledrm` |
| [Mobile Information Services](mobile-dimensions.md) | `mobileinformationservices` |
| [Mobil Java VM](mobile-dimensions.md) | `mobilejavavm` |
| [Dekoration av mobil e-post](mobile-dimensions.md) | `mobilemaildecoration` |
| [Mobile Net-protokoll](mobile-dimensions.md) | `mobilenetprotocols` |
| [Mobilt push-to-Talk](mobile-dimensions.md) | `mobilepushtotalk` |
| [Månad](month.md) | `daterangemonth` |
| [Månad på året](month-of-year.md) | `timepartmonthofyear` |
| [Operativsystemstyper](operating-system-types.md) | `operatingsystemgroup` |
| [Betald sökning](paid-search.md) | `paidsearch` |
| [Beständigt stöd för cookies](persistent-cookie-support.md) | `persistentcookie` |
| [Kvartal](quarter.md) | `daterangequarter` |
| [Kvartal på året](quarter-of-year.md) | `timepartquarterofyear` |
| Undersökning | `surveybase` |
| [Tid som använts på sidan - paketerad](time-spent-on-page.md) | `averagepagetime` |
| [Tid som använts på sidan - Detaljerad](time-spent-on-page.md) | `pagetimeseconds` |
| [Anledning till avanmälan för spårning](tracking-opt-out-reason.md) | `optoutreason` |
| [Veckodag/Veckoslut](weekday-weekend.md) | `timepartweekdayweekend` |
| [Vecka](week.md) | `daterangeweek` |
| [År](year.md) | `daterangeyear` |

## Innehållsmedvetna dimensioner stöds endast i Analysis Workspace

| Dimension-namn (visas i analysgränssnittet) | Dimension ID (används i API-begäranden) |
|--- |--- |
| Activity Map XY | `clickmapxy` |
| ID för mediesession | `videosessionid` |
| Nielsen Access Method | `nielsenaccmethod` |
| Nielsen App ID | `nielsenappid` |
| Nielsen Channel Asset | `nielsenchannelasset` |
| Nielsen Content Type | `nielsencontenttype` |

## Innehållsmedvetna dimensioner som stöds av Analysis Workspace

### Video (Streaming media services)

| Dimension-namn (visas i analysgränssnittet) | Dimension ID (används i API-begäranden) |
|--- |--- |
| [Innehåll](sm-core.md) | `video` |
| [Innehållssegment](sm-core.md) | `videosegment` |
| [Innehållstyp](sm-core.md) | `videocontenttype` |
| [Lägg till spelarnamn](sm-ads.md) | `videoadplayername` |
| [Lägg till i rutposition](sm-ads.md) | `videoadinpod` |
| [Släppta bildrutor](sm-quality.md) | `videoqoedroppedframecountevar` |
| [Fel](sm-quality.md) | `videoqoeerrorcountevar` |
| [Genomsnittlig bithastighet](sm-quality.md) | `videoqoebitrateaverageevar` |
| [Bithastighetsändringar](sm-quality.md) | `videoqoebitratechangecountevar` |
| [Total buffertvaraktighet](sm-quality.md) | `videoqoebuffertimeevar` |
| [Bufferthändelser](sm-quality.md) | `videoqoebuffercountevar` |
| [Tid att starta](sm-quality.md) | `videoqoetimetostartevar` |
| [Lägg till pod](sm-ads.md) | `videoadpod` |
| [Mediesökväg](sm-core.md) | `videopath` |
| [Lägg till](sm-ads.md) | `videoad` |
| [Innehållsspelarens namn](sm-core.md) | `videoplayername` |
| [Innehållskanal](sm-core.md) | `videochannel` |
| [Kapitel](sm-chapters.md) | `videochapter` |
| [Innehållsnamn (variabel)](sm-core.md) | `videoname` |
| [Innehållslängd (variabel)](sm-core.md) | `videolength` |
| [Annonsnamn (variabel)](sm-ads.md) | `videoadname` |
| [Lägg till längd (variabel)](sm-ads.md) | `videoadlength` |
| [Visa](sm-video-metadata.md) | `videoshow` |
| [Säsong](sm-video-metadata.md) | `videoseason` |
| [Episod](sm-video-metadata.md) | `videoepisode` |
| [Nätverk](sm-video-metadata.md) | `videonetwork` |
| [Visa typ](sm-video-metadata.md) | `videoshowtype` |
| [Annonsinläsningar](sm-ads.md) | `videoadload` |
| [MVPD](sm-video-metadata.md) | `videomvpd` |
| [Dagdel](sm-video-metadata.md) | `videodaypart` |
| [Advertiser](sm-ads.md) | `videoadadvertiser` |
| [Kampanj-ID](sm-ads.md) | `videoadcampaign` |
| [Genre](sm-video-metadata.md) | `videogenre` |
| [Strömtyp](sm-core.md) | `videostreamtype` |
| [Fel-ID för SDK Player](sm-quality.md) | `videoqoeplayersdkerrors` |
| [ID för externa fel](sm-quality.md) | `videoqoeextneralerrors` |
| [Medieflödestyp](sm-video-metadata.md) | `videofeedtype` |
| [Ange mediasökväg](entry-dimensions.md) | `entryvideopath` |
| [Avsluta mediasökväg](exit-dimensions.md) | `exitvideopath` |
| [Införselgenre](entry-dimensions.md) | `entryvideogenre` |
| [Avsluta genre](exit-dimensions.md) | `exitvideogenre` |
| [Fel-ID för Entry Player SDK](entry-dimensions.md) | `entryvideoqoeplayersdkerrors` |
| [Avsluta SDK-fel-ID:n för spelaren](exit-dimensions.md) | `exitvideoqoeplayersdkerrors` |
| [Ange externa fel-ID](entry-dimensions.md) | `entryvideoqoeextneralerrors` |
| [Avsluta externa fel-ID](exit-dimensions.md) | `exitvideoqoeextneralerrors` |

### Adobe Social

Adobe Social är pensionerat.

| Dimension-namn (visas i analysgränssnittet) | Dimension ID (används i API-begäranden) |
|--- |--- |
| Villkor | `socialterm` |
| Sociala plattformar/egenskaper | `socialcontentprovider` |
| Författare | `socialauthor` |
| Språk | `sociallanguage` |
| Latitud/longitud | `sociallatlong` |
| Spåra tillgångar | `socialassettrackingcode` |
| Ägda sociala egenskaper | `socialaccountandappids` |
| Ägda post-ID:n | `socialownedpostids` |
| Ägda sociala definitioner | `socialinteractiontype` |
| Ägda egenskaps-ID | `socialownedpropertyid` |
| Ägd egenskap kontra program | `socialownedpropertypropertyvsapp` |
| Namn på ägd egenskap | `socialownedpropertyname` |
| Ägd definitionsegenskap kontra post | `socialowneddefinitionpropertyvspost` |
| Insiktstyp för ägardefinition | `socialowneddefinitioninsighttype` |
| Insiktsvärde för ägardefinition | `socialowneddefinitioninsightvalue` |
| Ägardefinitionsmått | `socialowneddefinitionmetric` |
| Tillgång | `socialmediaid` |

### Mobile SDK

| Dimension-namn (visas i analysgränssnittet) | Dimension ID (används i API-begäranden) |
|--- |--- |
| [Första startdatum](lifecycle-dimensions.md) | `mobileinstalldate` |
| [Program-ID](lifecycle-dimensions.md) | `mobileappid` |
| [Startnummer](lifecycle-dimensions.md) | `mobilelaunchnumber` |
| [Dagar sedan första användningen](lifecycle-dimensions.md) | `mobiledayssincefirstuse` |
| [Dagar sedan senaste användning](lifecycle-dimensions.md) | `mobiledayssincelastuse` |
| [Timme på dagen (SDK)](lifecycle-dimensions.md) | `mobilehourofday` |
| [Veckodag (SDK)](lifecycle-dimensions.md) | `mobiledayofweek` |
| [Operativsystem (SDK)](lifecycle-dimensions.md) | `mobileosenvironment` |
| [Dagar sedan senaste uppgraderingen](lifecycle-dimensions.md) | `mobiledayssincelastupgrade` |
| [Startar sedan senaste uppgraderingen](lifecycle-dimensions.md) | `mobilelaunchessincelastupgrade` |
| [Enhetsnamn (SDK)](lifecycle-dimensions.md) | `mobiledevice` |
| [Operativsystemversion (SDK)](lifecycle-dimensions.md) | `mobileosversion` |
| [Beacon Major](lifecycle-dimensions.md) | `mobilebeaconmajor` |
| [Beacon Minor](lifecycle-dimensions.md) | `mobilebeaconminor` |
| [Beacon UUID](lifecycle-dimensions.md) | `mobilebeaconuuid` |
| [Proximity för fyr](lifecycle-dimensions.md) | `mobilebeaconproximity` |
| [Plats (ned till 10 km)](lifecycle-dimensions.md) | `latlon1` |
| [Plats (ned till 100 m)](lifecycle-dimensions.md) | `latlon23` |
| [Plats (ned till 1 m)](lifecycle-dimensions.md) | `latlon45` |
| [Intressepunktsnamn](lifecycle-dimensions.md) | `pointofinterest` |
| [Avstånd till centrum för intressepunkter](lifecycle-dimensions.md) | `pointofinterestdistance` |
| [Positionsnoggrannhet](lifecycle-dimensions.md) | `mobileplaceaccuracy` |
| [Placera kategori](lifecycle-dimensions.md) | `mobileplacecategory` |
| [Plats-ID](lifecycle-dimensions.md) | `mobileplaceid` |
| [Anmäl Beacon Major](lifecycle-dimensions.md) | `entrymobilebeaconmajor` |
| [Avsluta Beacon Major](lifecycle-dimensions.md) | `exitmobilebeaconmajor` |
| [Anmäl dig till Beacon Minor](lifecycle-dimensions.md) | `entrymobilebeaconminor` |
| [Avsluta Beacon Minor](lifecycle-dimensions.md) | `exitmobilebeaconminor` |
| [Anmäl Beacon UUID](lifecycle-dimensions.md) | `entrymobilebeaconuuid` |
| [Avsluta Beacon UUID](lifecycle-dimensions.md) | `exitmobilebeaconuuid` |
| [Anmäl beacon-närhet](lifecycle-dimensions.md) | `entrymobilebeaconproximity` |
| [Avsluta aviseringsavstånd](lifecycle-dimensions.md) | `exitmobilebeaconproximity` |

### Adobe Advertising Cloud (AMO)

| Dimension-namn (visas i analysgränssnittet) | Dimension ID (används i API-begäranden) |
|--- |--- |
| AMO EF-ID | `amo_ef_id` |
| AMO-ID | `amo_cid` |

### Activity Map

| Dimension-namn (visas i analysgränssnittet) | Dimension ID (används i API-begäranden) |
|--- |--- |
| [Activity Map Link By Region](activity-map-link-by-region.md) | `clickmaplinkbyregion` |
| [Activity Map-region](activity-map-region.md) | `clickmapregion` |
| [Activity Map Link](activity-map-link.md) | `clickmaplink` |
| [Activity Map Page](activity-map-page.md) | `clickmappage` |

### Nielsen Integration

Mer information om hur du implementerar den här integreringen finns i [Nielsen-tillägget](https://exchange.adobe.com/apps/ec/101361) på Adobe Exchange.

| Dimension-namn (visas i analysgränssnittet) | Dimension ID (används i API-begäranden) |
|--- |--- |
| Nielsen Ad Model | `nielsenadmodel` |
| Nielsen Segment C | `nielsensegmentc` |
| Nielsen Segment B | `nielsensegmentb` |
| Nielsen Segment A | `nielsensegmenta` |
| Nielsen Content ID | `nielsencontentid` |
| Nielsen Asset / Program | `nielsenasset` |
| Nielsen VCID | `nielsenvcid` |
| Nielsen Opt Out | `nielsenoptout` |
| Nielsen Client ID + VCID | `nielsenclientidvcid` |
| Nielsen Client ID | `nielsenclientid` |
| Anmäl dig till Nielsen Opt Out | `entrynielsenoptout` |
| Avsluta Nielsen Opt Out | `exitnielsenoptout` |
| Klient-ID för inträde i Nielsen + VCID | `entrynielsenclientidvcid` |
| Exit Nielsen Client ID + VCID | `exitnielsenclientidvcid` |
| Klient-ID för tävlingsbidrag till Nielsen | `entrynielsenclientid` |
| Exit Nielsen Client ID | `exitnielsenclientid` |

### Adobe Experience Manager (AEM)

| Dimension-namn (visas i analysgränssnittet) | Dimension ID (används i API-begäranden) |
|--- |--- |
| Tillgångs-ID | `aemassetid` |
| Resurs-Source | `aemassetsource` |
| Klickat på resurs-ID | `aemclickedassetid` |
| Inmatningstillgångs-ID | `entryaemassetid` |
| Avsluta resurs-ID | `exitaemassetid` |

### Adobe Campaign

| Dimension-namn (visas i analysgränssnittet) | Dimension ID (används i API-begäranden) |
|--- |--- |
| Adobe Campaign Executed Delivery ID | `ac_delivery_internal_name` |
