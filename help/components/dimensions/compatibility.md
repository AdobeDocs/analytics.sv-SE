---
title: Analytics-Dimensioners kompatibilitet
description: Referens för analysdimensioner och rapporter.
feature: Dimensions
exl-id: 1884bc20-b04d-4f9a-b057-2b2fbe53190d
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '985'
ht-degree: 8%

---

# Analytics-Dimensioners kompatibilitet

Den här sidlistan [dimensioner](overview.md) stöds i deras respektive Analytics-funktioner.

>[!NOTE]
>
>Anpassade variabelnamn, klassificeringar och besökarattribut tas inte med i listan. Dessa dimensionsobjekt är specifika för enskilda rapportsviter.

>[!NOTE]
>
>Det finns vissa överlappningar där analysverktygen använder olika termer för liknande dimensioner. Rapporter och analyser använder till exempel `browserwidth` när Analysis Workspace använder `browserwidthbucketed`.

## Dimensioner som stöds i både Reports &amp; Analytics och Analysis Workspace

| Dimensionens namn (visas i analysgränssnittet) | Dimension-ID (används i API-begäranden) |
|---|---|
| Analyser för Target | `targetraw` |
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
| Anpassade konverteringsvariabler | `evar1`, `evar2`, osv. |
| Custom Insight Vars | `prop1`, `prop2`, osv. |
| Anpassad länk | `customlink` |
| Dagar före första köp | `daysbeforefirstpurchase` |
| Dagar sedan senaste köp | `dayssincelastpurchase` |
| Domän | `filtereddomain` |
| Hämta länk | `downloadlink` |
| Inmatningssida | `entrypage` |
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

## Dimensioner som bara stöds i Analysis Workspace

| Dimensionens namn (visas i analysgränssnittet) | Dimension-ID (används i API-begäranden) |
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
| Mobil Java VM | `mobilejavavm` |
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
| Veckodag/vecka | `timepartweekdayweekend` |
| Vecka | `daterangeweek` |
| År | `daterangeyear` |

## Innehållsmedvetna dimensioner stöds endast i Analysis Workspace

| Dimensionens namn (visas i analysgränssnittet) | Dimension-ID (används i API-begäranden) |
|--- |--- |
| Activity Map XY | `clickmapxy` |
| ID för mediesession | `videosessionid` |
| Nielsen Access Method | `nielsenaccmethod` |
| Nielsen App ID | `nielsenappid` |
| Nielsen Channel Asset | `nielsenchannelasset` |
| Nielsen Content Type | `nielsencontenttype` |

## Dimensioner som bara stöds i rapporter och analyser

| Dimensionens namn (visas i analysgränssnittet) | Dimension-ID (används i API-begäranden) |
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

## Innehållsmedvetna dimensioner stöds av både Rapporter &amp; Analytics och Analysis Workspace

### Video (Media Analytics)

| Dimensionens namn (visas i analysgränssnittet) | Dimension-ID (används i API-begäranden) |
|--- |--- |
| Innehåll | `video` |
| Innehållssegment | `videosegment` |
| Innehållstyp | `videocontenttype` |
| Namn på annonsspelaren | `videoadplayername` |
| Lägg till i rutposition | `videoadinpod` |
| Släppta bildrutor | `videoqoedroppedframecountevar` |
| Fel | `videoqoeerrorcountevar` |
| Genomsnittlig bithastighet | `videoqoebitrateaverageevar` |
| Bithastighetsändringar | `videoqoebitratechangecountevar` |
| Buffertvaraktighet totalt | `videoqoebuffertimeevar` |
| Bufferthändelser | `videoqoebuffercountevar` |
| Tid att starta | `videoqoetimetostartevar` |
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
| Externa fel-ID | `videoqoeextneralerrors` |
| Medieflödestyp | `videofeedtype` |
| Ange mediesökväg | `entryvideopath` |
| Avsluta mediasökväg | `exitvideopath` |
| Anmälningsgenre | `entryvideogenre` |
| Avsluta genre | `exitvideogenre` |
| SDK-fel-ID för Entry Player | `entryvideoqoeplayersdkerrors` |
| Avsluta SDK-fel-ID för spelaren | `exitvideoqoeplayersdkerrors` |
| Externa fel-ID för post | `entryvideoqoeextneralerrors` |
| Avsluta externa fel-ID | `exitvideoqoeextneralerrors` |

### Adobe Social

| Dimensionens namn (visas i analysgränssnittet) | Dimension-ID (används i API-begäranden) |
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

### Mobil-SDK

| Dimensionens namn (visas i analysgränssnittet) | Dimension-ID (används i API-begäranden) |
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
| Ange Beacon UUID | `entrymobilebeaconuuid` |
| Avsluta Beacon UUID | `exitmobilebeaconuuid` |
| Anmäl beacon-närhet | `entrymobilebeaconproximity` |
| Avsluta Beacon-närhet | `exitmobilebeaconproximity` |

### Adobe Advertising Cloud (AMO)

| Dimensionens namn (visas i analysgränssnittet) | Dimension-ID (används i API-begäranden) |
|--- |--- |
| AMO EF-ID | `amo_ef_id` |
| AMO-ID | `amo_cid` |

### Activity Map

| Dimensionens namn (visas i analysgränssnittet) | Dimension-ID (används i API-begäranden) |
|--- |--- |
| Activity Map Link per region | `clickmaplinkbyregion` |
| Activity Map | `clickmapregion` |
| Länk till Activity Map | `clickmaplink` |
| Sida för Activity Map | `clickmappage` |

### Nielsen Integration

Mer information om hur du implementerar integreringen finns i [Nielsen Extension](https://exchange.adobe.com/experiencecloud.details.101361.html).

| Dimensionens namn (visas i analysgränssnittet) | Dimension-ID (används i API-begäranden) |
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

| Dimensionens namn (visas i analysgränssnittet) | Dimension-ID (används i API-begäranden) |
|--- |--- |
| Tillgångs-ID | `aemassetid` |
| Resurskälla | `aemassetsource` |
| Klickat på resurs-ID | `aemclickedassetid` |
| Inmatningstillgångs-ID | `entryaemassetid` |
| Avsluta resurs-ID | `exitaemassetid` |

### Adobe Campaign

| Dimensionens namn (visas i analysgränssnittet) | Dimension-ID (används i API-begäranden) |
|--- |--- |
| Adobe Campaign Executed Delivery ID | `ac_delivery_internal_name` |
