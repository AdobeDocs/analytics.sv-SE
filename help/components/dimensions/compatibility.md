---
title: Analytics Dimensions-kompatibilitet
description: Referens för Analytics dimensioner och rapporter.
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '985'
ht-degree: 8%

---


# Analytics Dimensions-kompatibilitet

På den här sidan visas de dimensioner som stöds i deras respektive Analytics-funktioner.

>[!NOTE]
>
>Anpassade variabelnamn, klassificeringar och besökarattribut tas inte med i listan. Dessa dimensionsvärden är specifika för enskilda rapportsviter.

>[!NOTE]
>
>Det finns vissa överlappningar där Analytics-verktyg använder olika termer för liknande dimensioner. Rapporter och Analytics använder till exempel `browserwidth` medan Analysis Workspace använder `browserwidthbucketed`.

## Dimensioner som stöds i både Reports &amp; Analytics och Analysis Workspace

| Dimensionsnamn (visas i Analytics UI) | Dimension-ID (används i API-begäranden) |
|---|---|
| Analytics för Target | `targetraw` |
| Målgrupps-ID | `mcaudiences` |
| Webbläsare | `browser` |
| Typ av webbläsare | `browsertype` |
| Kategori | `category` |
| Städer | `geocity` |
| Färgdjup | `colordepth` |
| Anslutningstyp | `connectiontype` |
| Cookie-stöd | `cookie` |
| Länder | `geocountry` |
| Kundlojalitet | `customerloyalty` |
| Anpassade konverteringsvariabler | `evar1`, `evar2`osv. |
| Custom Insight Vars | `prop1`, `prop2`osv. |
| Anpassad länk | `customlink` |
| Dagar före första köp | `daysbeforefirstpurchase` |
| Dagar sedan senaste köp | `dayssincelastpurchase` |
| Domän | `filtereddomain` |
| Hämta länk | `downloadlink` |
| Startsida | `entrypage` |
| Inmatningssidans originalformat | `entrypageoriginal` |
| Avsluta länk | `exitlink` |
| Första beröringskanalen | `firsttouchchannel` |
| Första beröringskanaldetalj | `firsttouchchanneldetail` |
| Java aktiverat | `javaenabled` |
| Språk | `language` |
| Senaste beröringskanal | `lasttouchchannel` |
| Senaste beröringskanaldetalj | `lasttouchchanneldetail` |
| Listvariabler | `listvariables` |
| Marknadsföringskanal | `marketingchannel` |
| Stöd för mobilljud | `mobileaudiosupport` |
| Mobiloperatör | `mobilecarrier` |
| Mobil färgdjup | `mobilecolordepth` |
| Stöd för Mobile Cookie | `mobilecookiesupport` |
| Mobil enhet | `mobiledevicename` |
| Typ av mobil enhet | `mobiledevicetype` |
| Maximal e-postlängd för mobil | `mobileemaillength` |
| Stöd för mobilbilder | `mobileimagesupport` |
| Mobiltillverkare | `mobilemanufacturer` |
| Mobiloperativsystem (borttaget) | `mobileos` |
| Höjd på mobilskärm | `mobilescreenheight` |
| Storlek på mobilskärm | `mobilescreensize` |
| Bredd på mobilskärm | `mobilescreenwidth` |
| Högsta URL-längd för mobil webbläsare | `mobileurllength` |
| Stöd för mobilvideo | `mobilevideosupport` |
| Bildskärmsupplösning | `monitorresolution` |
| Operativsystem | `operatingsystem` |
| Ursprunglig referensdomän | `referringdomainoriginal` |
| Sida | `page` |
| Sidor som inte hittades | `pagesnotfound` |
| Produkt | `product` |
| Referent | `referrer` |
| Referenstyp | `referrertype` |
| Refererande domän | `referringdomain` |
| Regioner | `georegion` |
| Återbesöksfrekvens | `returnfrequency` |
| SC-TnT | `tntbase` |
| Sökmotor | `searchengine` |
| Sök nyckelord | `searchenginekeyword` |
| Sökmotor - naturlig | `searchenginenatural` |
| Sökmotor - betald | `searchenginepaid` |
| Söknyckelord - naturligt | `searchenginenaturalkeyword` |
| Söknyckelord - Betald | `searchenginepaidkeyword` |
| Alla söksidrankning | `searchenginepagerank` |
| Server | `server` |
| Besök på en sida | `singlepagevisits` |
| Platsavsnitt | `sitesections` |
| Tillagd tid per besök - granulerad | `sitetime` |
| Spårningskod | `campaign` |
| US DMA | `geodma` |
| USA | `state` |
| Tid före händelse | `timeprior` |
| Tid per besök - paketerad | `timespent` |
| Besöksdjup | `pathlength` |
| Besöksnummer | `visitnumber` |
| Postnummer | `zip` |

## Dimensioner stöds endast i Analysis Workspace

| Dimensionsnamn (visas i Analytics UI) | Dimension-ID (används i API-begäranden) |
|--- |--- |
| AM/PM | `timepartampm` |
| Webbläsarhöjd - paketerad | `browserheightbucketed` |
| Webbläsarbredd - paketerad | `browserwidthbucketed` |
| Dag | `daterangeday` |
| Dag i månaden | `timepartdayofmonth` |
| Veckodag | `dayofweek` |
| Veckodag | `timepartdayofweek` |
| Dag på året | `timepartdayofyear` |
| Dagar sedan senaste besök | `dayssincelastvisit` |
| Anpassade insikter för inträde | `entryprops` |
| Variabler för anmälningslista | `entrylistvariables` |
| Startserver | `entryserver` |
| Avsnittet Inmatningswebbplats | `entrysitesections` |
| Avsluta anpassade insikter | `exitprops` |
| Avsluta listvariabler | `exitlistvariables` |
| Avsluta sidan | `exitpage` |
| Avsluta servern | `exitserver` |
| Avsluta webbplatsavsnittet | `exitsitesections` |
| Träff-djup | `hitdepth` |
| Träfftyp | `hittype` |
| Timme | `daterangehour` |
| Timme på dagen | `timeparthourofday` |
| Information om marknadsföringskanal | `marketingchanneldetail` |
| Minut | `daterangeminute` |
| Max bokmärkeslängd för mobil | `mobilebookmarklength` |
| Mobilenhetsnummer | `mobiledevicenumber` |
| Mobil DRM | `mobiledrm` |
| Mobile Information Services | `mobileinformationservices` |
| Mobile Java VM | `mobilejavavm` |
| Dekoration av mobilpost | `mobilemaildecoration` |
| Mobile Net-protokoll | `mobilenetprotocols` |
| Mobil push to Talk | `mobilepushtotalk` |
| Månad | `daterangemonth` |
| Månad på året | `timepartmonthofyear` |
| Operativsystemstyper | `operatingsystemgroup` |
| Betalsökning | `paidsearch` |
| Stöd för permanenta cookies | `persistentcookie` |
| Kvartal | `daterangequarter` |
| Kvartal på året | `timepartquarterofyear` |
| Undersökning | `surveybase` |
| Tid som använts på sidan - paketerad | `averagepagetime` |
| Tid som använts på sidan - Detaljerad | `pagetimeseconds` |
| Orsak till avanmälan av spårning | `optoutreason` |
| Veckodag/Veckoslut | `timepartweekdayweekend` |
| Vecka | `daterangeweek` |
| År | `daterangeyear` |

## Innehållsmedvetna dimensioner stöds endast i Analysis Workspace

| Dimensionsnamn (visas i Analytics UI) | Dimension-ID (används i API-begäranden) |
|--- |--- |
| Activity Map XY | `clickmapxy` |
| ID för mediesession | `videosessionid` |
| Nielsen Access Method | `nielsenaccmethod` |
| Nielsen App ID | `nielsenappid` |
| Nielsen Channel Asset | `nielsenchannelasset` |
| Nielsen Content Type | `nielsencontenttype` |

## Dimensioner stöds endast i rapporter och Analytics

| Dimensionsnamn (visas i Analytics UI) | Dimension-ID (används i API-begäranden) |
|--- |--- |
| Webbläsarhöjd | `browserheight` |
| Bredd på webbläsare | `browserwidth` |
| Dagliga unika kunder | `dailyuniquecustomers` |
| JavaScript | `javascriptsupport` |
| JavaScript-version | `javascriptversion` |
| Månatliga unika kunder | `monthlyuniquecustomers` |
| Kunder som är unika varje kvartal | `quarterlyuniquecustomers` |
| Tidszoner | `timezone` |
| Domäner på översta nivån | `topleveldomain` |
| Besökarläge | `legacystate` |
| Unika kunder varje vecka | `weeklyuniquecustomers` |
| Årliga unika kunder | `yearlyuniquecustomers` |

## Innehållsmedvetna dimensioner stöds av både Reports &amp; Analytics och Analysis Workspace

### Video (Media Analytics)

| Dimensionsnamn (visas i Analytics UI) | Dimension-ID (används i API-begäranden) |
|--- |--- |
| Innehåll | `video` |
| Innehållssegment | `videosegment` |
| Innehållstyp | `videocontenttype` |
| Namn på annonsspelare | `videoadplayername` |
| Lägg till i rutposition | `videoadinpod` |
| Släppta bildrutor | `videoqoedroppedframecountevar` |
| Fel | `videoqoeerrorcountevar` |
| Genomsnittlig bithastighet | `videoqoebitrateaverageevar` |
| Bithastighetsändringar | `videoqoebitratechangecountevar` |
| Buffertvaraktighet totalt | `videoqoebuffertimeevar` |
| Bufferthändelser | `videoqoebuffercountevar` |
| Starttid | `videoqoetimetostartevar` |
| Annonsruta | `videoadpod` |
| Mediesökväg | `videopath` |
| Annons | `videoad` |
| Innehållsspelarens namn | `videoplayername` |
| Innehållskanal | `videochannel` |
| Kapitel | `videochapter` |
| Innehållsnamn (variabel) | `videoname` |
| Innehållslängd (variabel) | `videolength` |
| Annonsnamn (variabel) | `videoadname` |
| Annonslängd (variabel) | `videoadlength` |
| Visa | `videoshow` |
| Säsong | `videoseason` |
| Episod | `videoepisode` |
| Nätverk | `videonetwork` |
| Visa typ | `videoshowtype` |
| Annonsladdningar | `videoadload` |
| MVPD | `videomvpd` |
| Dag - del | `videodaypart` |
| Annonsör | `videoadadvertiser` |
| Kampanj-ID | `videoadcampaign` |
| Genre | `videogenre` |
| Strömtyp | `videostreamtype` |
| Fel-ID för Player SDK | `videoqoeplayersdkerrors` |
| Externa fel-ID:n | `videoqoeextneralerrors` |
| Medieflödestyp | `videofeedtype` |
| Ange mediesökväg | `entryvideopath` |
| Avsluta mediasökväg | `exitvideopath` |
| Anmälningsgenre | `entryvideogenre` |
| Avsluta genre | `exitvideogenre` |
| Fel-ID för Entry Player SDK | `entryvideoqoeplayersdkerrors` |
| Avsluta SDK-fel-ID för spelaren | `exitvideoqoeplayersdkerrors` |
| Externa fel-ID för post | `entryvideoqoeextneralerrors` |
| Avsluta externa fel-ID:n | `exitvideoqoeextneralerrors` |

### Adobe Social

| Dimensionsnamn (visas i Analytics UI) | Dimension-ID (används i API-begäranden) |
|--- |--- |
| Villkor | `socialterm` |
| Sociala plattformar/egenskaper | `socialcontentprovider` |
| Författare | `socialauthor` |
| Språk | `sociallanguage` |
| Latitud/longitud | `sociallatlong` |
| Spårningskoder för tillgångar | `socialassettrackingcode` |
| Ägda sociala egenskaper | `socialaccountandappids` |
| Ägda post-ID:n | `socialownedpostids` |
| Ägda sociala definitioner | `socialinteractiontype` |
| Ägda egenskaps-ID | `socialownedpropertyid` |
| Ägd egenskap kontra program | `socialownedpropertypropertyvsapp` |
| Namn på ägd egenskap | `socialownedpropertyname` |
| Egenskap för ägd definition kontra post | `socialowneddefinitionpropertyvspost` |
| Insiktstyp för ägardefinition | `socialowneddefinitioninsighttype` |
| Insiktsvärde för ägardefinition | `socialowneddefinitioninsightvalue` |
| Ägardefinitionsmått | `socialowneddefinitionmetric` |
| Tillgång | `socialmediaid` |

### Mobile SDK

| Dimensionsnamn (visas i Analytics UI) | Dimension-ID (används i API-begäranden) |
|--- |--- |
| Första startdatum | `mobileinstalldate` |
| Program-ID | `mobileappid` |
| Startnummer | `mobilelaunchnumber` |
| Dagar sedan första användningen | `mobiledayssincefirstuse` |
| Dagar sedan senaste användning | `mobiledayssincelastuse` |
| Timme på dagen (SDK) | `mobilehourofday` |
| Veckodag (SDK) | `mobiledayofweek` |
| Operativsystem (SDK) | `mobileosenvironment` |
| Dagar sedan senaste uppgraderingen | `mobiledayssincelastupgrade` |
| Startar sedan senaste uppgraderingen | `mobilelaunchessincelastupgrade` |
| Enhetsnamn (SDK) | `mobiledevice` |
| Operativsystemversion (SDK) | `mobileosversion` |
| Beacon Major | `mobilebeaconmajor` |
| Beacon Minor | `mobilebeaconminor` |
| Beacon UUID | `mobilebeaconuuid` |
| Beacon Proximity | `mobilebeaconproximity` |
| Placering (ned till 10 km) | `latlon1` |
| Plats (ned till 100 m) | `latlon23` |
| Plats (ned till 1 m) | `latlon45` |
| Intressepunktens namn | `pointofinterest` |
| Avstånd till intressecentrum | `pointofinterestdistance` |
| Positionsnoggrannhet | `mobileplaceaccuracy` |
| Montera kategori | `mobileplacecategory` |
| Plats-ID | `mobileplaceid` |
| Betaversion av ingång | `entrymobilebeaconmajor` |
| Avsluta Beacon Major | `exitmobilebeaconmajor` |
| Anmäl dig till Beacon Minor | `entrymobilebeaconminor` |
| Avsluta Beacon Minor | `exitmobilebeaconminor` |
| Anmäl Beacon UUID | `entrymobilebeaconuuid` |
| Avsluta Beacon UUID | `exitmobilebeaconuuid` |
| Anmäl beacon-närhet | `entrymobilebeaconproximity` |
| Avsluta Beacon-närhet | `exitmobilebeaconproximity` |

### Adobe Advertising Cloud (AMO)

| Dimensionsnamn (visas i Analytics UI) | Dimension-ID (används i API-begäranden) |
|--- |--- |
| AMO EF-ID | `amo_ef_id` |
| AMO-ID | `amo_cid` |

### Activity Map

| Dimensionsnamn (visas i Analytics UI) | Dimension-ID (används i API-begäranden) |
|--- |--- |
| Activity Map Link per region | `clickmaplinkbyregion` |
| Activity Map | `clickmapregion` |
| Länk till Activity Map | `clickmaplink` |
| Sida för Activity Map | `clickmappage` |

### Nielsen Integration

Mer information om hur du implementerar den här integreringen finns i [Nielsen-tillägget](https://exchange.adobe.com/experiencecloud.details.101361.html).

| Dimensionsnamn (visas i Analytics UI) | Dimension-ID (används i API-begäranden) |
|--- |--- |
| Nielsen Ad Model | `nielsenadmodel` |
| Nielsen Segment C | `nielsensegmentc` |
| Nielsen Segment B | `nielsensegmentb` |
| Nielsen Segment A | `nielsensegmenta` |
| Nielsen Content ID | `nielsencontentid` |
| Nielsen Asset/Program | `nielsenasset` |
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

| Dimensionsnamn (visas i Analytics UI) | Dimension-ID (används i API-begäranden) |
|--- |--- |
| Tillgångs-ID | `aemassetid` |
| Resurskälla | `aemassetsource` |
| Klickat på resurs-ID | `aemclickedassetid` |
| Inmatningstillgångs-ID | `entryaemassetid` |
| Avsluta resurs-ID | `exitaemassetid` |

### Adobe Campaign

| Dimensionsnamn (visas i Analytics UI) | Dimension-ID (används i API-begäranden) |
|--- |--- |
| Adobe Campaign Executed Delivery ID | `ac_delivery_internal_name` |
