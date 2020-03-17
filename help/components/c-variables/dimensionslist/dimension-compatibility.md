---
title: Analysdimensioner - kompatibilitet
description: Referens för analysdimensioner och rapporter.
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Analysdimensioner - kompatibilitet

I den här referensartikeln listas de dimensioner/rapporter som stöds i både rapport- och analysarbetsytan, endast i analysarbetsytan och endast i rapporter och analyser.

Kom ihåg att

* Dessa är inte uttömmande listor. Varje rapportsvit kan ha en given uppsättning produktvariabler aktiverade eller inte. Dessutom kan ett visst rapportpaket ha valfritt antal anpassade variabler aktiverade, inaktiverade eller mappade till produktvariabler. Vi har också utelämnat besökarattribut och klassificeringar, eftersom de är unika för varje rapportserie.

* Det finns vissa fall av överlappning där analysverktygen använder olika termer för det som i själva verket är samma sak, till exempel: `browserwidth` och `browserwidthbucketed`.

## Dimensioner som stöds i både rapport- och analysarbetsytan

| Dimensionsnamn (visas i analysgränssnittet) | Dimension-ID (används i API-begäranden) |
|---|---|
| Analyser för Target | målraw |
| Målgrupps-ID | försiktighetsåtgärder |
| Webbläsare | webbläsare |
| Typ av webbläsare | browsertype |
| Kategori | kategori |
| Städer | geocity |
| Färgdjup | färgdjup |
| Anslutningstyp | anslutningstyp |
| Cookie-stöd | cookie |
| Länder | geocountry |
| Kundlojalitet | kundlojalitet |
| Anpassade konverteringsvariabler | evar1, evar2 osv. |
| Custom Insight-variabler | prop1, prop2 osv. |
| Egen länk | anpassad länk |
| Dagar före första köpet | dagar före första köp |
| Dagar sedan senaste köp | dagsincelastpurchase |
| Domän | filterdomän |
| Hämta länk | nedladdningslänk |
| Startsida | entrypage |
| Inmatningssidans originalformat | entrypageoriginal |
| Avsluta länk | exitlink |
| Första beröringskanalen | firstTouchchannel |
| Första beröringskanaldetalj | firstTouchchanneldetail |
| Java aktiverat | javaenabled |
| Språk | språk |
| Senaste beröringskanal | lasttouchchannel |
| Senaste beröringskanaldetalj | lasttouchchanneldetail |
| Listvariabler | listvariabler |
| Marknadsföringskanal | marknadsföringskanal |
| Stöd för mobilljud | mobileaudiosupport |
| Mobiloperatör | mobiloperatör |
| Mobil färgdjup | mobilekolordjup |
| Stöd för Mobile Cookie | mobilekookiessupport |
| Mobil enhet | mobiledevicename |
| Typ av mobil enhet | mobiledevicetype |
| Maximal e-postlängd för mobil | mobileemaillength |
| Stöd för mobilbilder | mobileimagessupport |
| Mobiltillverkare | mobiltillverkare |
| Mobiloperativsystem (borttaget) | mobileos |
| Höjd på mobilskärm | mobilescreenheight |
| Storlek på mobilskärm | mobilescreensize |
| Bredd på mobilskärm | mobilescreenwidth |
| Högsta URL-längd för mobil webbläsare | mobileurlength |
| Stöd för mobilvideo | stöd för mobilvideo |
| Bildskärmsupplösning | skärmupplösning |
| Operativsystem | operativsystem |
| Ursprunglig referensdomän | referringdomainoriginal |
| Sida | page |
| Sidorna hittades inte | pagesnot hittades |
| Produkt | produkt |
| Referent | hänvisare |
| Referenstyp | referenstyp |
| Refererande domän | hänvisningsdomän |
| Regioner | georegion |
| Returfrekvens | returfrekvens |
| SC-TnT | tbase |
| Sökmotor | sökmotor |
| Sök nyckelord | sökmotornyckelord |
| Sökmotor - naturlig | sökmotor |
| Sökmotor - betald | searchenginepaid |
| Söknyckelord - naturligt | sökmotorinenaturnyckelord |
| Söknyckelord - Betald | searchenginepaidnyckelord |
| Alla söksidrankning | searchenginepagerank |
| Server | server |
| Besök på en sida | singlepagevisier |
| Platsavsnitt | webbplatser |
| Tillagd tid per besök - granulerad | sitetime |
| Spårningskod | kampanj |
| US DMA | geodma |
| USA | läge |
| Tid före händelse | timeBefore |
| Tid per besök - paketerad | tidsspenderad |
| Besöksdjup | banlängd |
| Besök nummer | visitnummer |
| Postnummer | zip |

## Dimensioner stöds endast i Analysis Workspace

| Dimensionsnamn (visas i analysgränssnittet) | Dimension-ID (används i API-begäranden) |
|--- |--- |
| AM/PM | timepartampm |
| Webbläsarhöjd - paketerad | browserheightBucketed |
| Webbläsarbredd - paketerad | webbläsarwidgetköpta |
| Dag | daterangeday |
| Dag i månaden | timepartday, månad |
| Veckodag | veckodag |
| Veckodag | timepartdayofweek |
| Dag på året | timepartday |
| Dagar sedan senaste besök | dagsinsbesök |
| Anpassade insikter för inträde | entryprops |
| Variabler för anmälningslista | entrylistvariables |
| Startserver | entryserver |
| Avsnittet Inmatningswebbplats | entryplatser |
| Avsluta anpassade insikter | exitprops |
| Avsluta listvariabler | exitlistvariabler |
| Avsluta sidan | exitpage |
| Avsluta servern | exitserver |
| Avsluta webbplatsavsnittet | exitsitestioner |
| Träff-djup | hitdepth |
| Träfftyp | hittype |
| Timme | daterangehour |
| Timme på dagen | timeparnattrofday |
| Information om marknadsföringskanal | marketingchannelDetaljer |
| Minut | daterangeminute |
| Max bokmärkeslängd för mobil | mobilebookmarklength |
| Mobilenhetsnummer | mobiledevicenumner |
| Mobil DRM | mobiledrm |
| Mobile Information Services | mobileinformationstjänster |
| Mobile Java VM | mobilejavm |
| Dekoration av mobilpost | mobile-postdekoration |
| Mobile Net-protokoll | mobilnätprotokoll |
| Mobil push to Talk | mobilepushtotalk |
| Månad | daterangemonth |
| Månad på året | timepartmonofyear |
| Operativsystemstyper | operatingsystemgrupp |
| Betalsökning | paidsearch |
| Stöd för permanenta cookies | persistentcookie |
| Kvartal | daterangequarter |
| Kvartal på året | timepartquarterofyear |
| Undersökning | surveyBase |
| Tid som använts på sidan - paketerad | genomsnittstid |
| Tid som använts på sidan - Detaljerad | pagetimeseconds |
| Orsak till avanmälan av spårning | optoutreason |
| Veckodag/Veckoslut | timeparthelg |
| Vecka | daterangeweek |
| År | daterangeyear |

## Innehållsmedvetna dimensioner stöds endast i Analysis Workspace

| Dimensionsnamn (visas i analysgränssnittet) | Dimension-ID (används i API-begäranden) |
|--- |--- |
| Aktivitetskarta XY | clickmapxy |
| ID för mediesession | videosessionid |
| Nielsen Access Method | nielsenaccmethod |
| Nielsen App ID | nielsenappid |
| Nielsen Channel Asset | nielsenchannelAssets |
| Nielsen Content Type | nielsencontenttype |

## Dimensioner stöds endast i rapporter och analyser

| Dimensionsnamn (visas i analysgränssnittet) | Dimension-ID (används i API-begäranden) |
|--- |--- |
| Webbläsarhöjd | browserheight |
| Bredd på webbläsare | webbläsarbredd |
| Dagliga unika kunder | unika kunder |
| JavaScript | javascriptsupport |
| JavaScript-version | javascriptversion |
| Månatliga unika kunder | månatliga kunder |
| Kunder som är unika varje kvartal | kvarterlyuniqueccustomers |
| Tidszoner | tidszon |
| Domäner på översta nivån | topleveldomain |
| Besökarläge | legacystate |
| Unika kunder varje vecka | weeklyuniqueccustomers |
| Årliga unika kunder | årligt unika kunder |

## Förkonfigurerade rapporter i rapporter och analyser

Rapporter och analyser innehåller flera förkonfigurerade rapporter som antingen inte mappar till en viss dimension, eller så används en klass av dimensioner i rapporten. Rapporterna är listade här:

* URL-längd för bokmärke
* Webbläsare
* Webbläsartyper
* Kampanjkonverteringsström
* Konverteringsfunktion för kundvagn
* Städer
* Klicka på sidan
* Länder
* Korsförsäljning
* Anpassad händelsetabell
* Stöd för dekoration av e-post
* Överföring av enhetsnummer (PÅ/AV)
* Domäner
* DRM
* Inmatningssidor
* Avsluta sidor
* Utfall
* Fullständiga banor
* ICties
* Informationstjänster
* Java-version
* Språk
* De längsta banorna
* Media Concurrent Viewers
* Media Daypart
* Medieinformation
* Medieöversikt
* Bildskärmslösningar
* Nettoprotokoll
* Netscape-plugin-program
* Nästa sida
* Nästa sidflöde
* Operativsystem
* Operativsystemstyper
* Siddjup
* Sidsammanfattning
* PathFinder
* Föregående sidflöde
* Föregående sida
* PTT
* Produktkonverteringsfunktion
* Inköpskonverteringsström
* Refererande domäner
* Regioner
* Läs in igen
* Sökmotorer - alla
* Sökmotorer - naturliga
* Sökmotorer - betalda
* Sök nyckelord - alla
* Sök nyckelord - naturligt
* Söknyckelord - Betald
* Information om målaktivitet
* Tid som använts på sidan
* Tidszoner
* Domäner på översta nivån
* U.S. DMA
* USA
* Besök nummer
* Besökarens hemsida

## Innehållsmedvetna dimensioner stöds av arbetsytan för både rapporter och analyser

### Video (Media Analytics)

| Dimensionsnamn (visas i analysgränssnittet) | Dimension-ID (används i API-begäranden) |
|--- |--- |
| Innehåll | video |
| Innehållssegment | videosegment |
| Innehållstyp | videoinnehålltyp |
| Namn på annonsspelare | videoadplayername |
| Lägg till i rutposition | videoadinpod |
| Släppta bildrutor | videoqoedroppedframecountevar |
| Fel | videoqoeerrorcountevar |
| Genomsnittlig bithastighet | videoqoebitrateaverageevar |
| Bithastighetsändringar | videoqoebitratechangecountevar |
| Buffertvaraktighet totalt | videoqoebuffer timeevar |
| Bufferthändelser | videoqoebuffcountevar |
| Starttid | videoqoetimetostartevar |
| Annonsruta | videoadpod |
| Mediesökväg | videopath |
| Annons | video |
| Innehållsspelarens namn | videoplayername |
| Innehållskanal | videochchannel |
| Kapitel | videokort |
| Innehållsnamn (variabel) | videonamn |
| Innehållslängd (variabel) | videolängd |
| Annonsnamn (variabel) | videoadname |
| Annonslängd (variabel) | videoadlength |
| Visa | videoshow |
| Säsong | videosäsong |
| Episod | videoavsnitt |
| Nätverk | videonätverk |
| Visa typ | videoshowtype |
| Annonsladdningar | videoadload |
| MVPD | videomvpd |
| Dag - del | videodaypart |
| Annonsör | videoadannonser |
| Kampanj-ID | videoadcampaign |
| Genre | videogener |
| Strömtyp | videoströmtype |
| Fel-ID för Player SDK | videoinspelaredkerrors |
| Externa fel-ID:n | videoqoeextneralerrors |
| Medieflödestyp | videofeedtyp |
| Ange mediesökväg | entryvideopath |
| Avsluta mediasökväg | exitvideopath |
| Anmälningsgenre | entryvideogener |
| Avsluta genre | exitvideogener |
| Fel-ID för Entry Player SDK | entryvideoqoeplayerdkerrors |
| Avsluta SDK-fel-ID för spelaren | exitvideoqoeplayerdkerrors |
| Externa fel-ID för post | entryvideoqoeextneralerrors |
| Avsluta externa fel-ID:n | exitvideoqoeextneralerrors |

### Adobe Social

| Dimensionsnamn (visas i analysgränssnittet) | Dimension-ID (används i API-begäranden) |
|--- |--- |
| Villkor | social |
| Sociala plattformar/egenskaper | social contentprovider |
| Författare | socialförfattare |
| Språk | socialt språk |
| Latitud/longitud | sociallatlong |
| Spårningskoder för tillgångar | social assettrackingcode |
| Ägda sociala egenskaper | socialräkenskapsapper |
| Ägda post-ID:n | socialägda poster |
| Ägda sociala definitioner | social interactiontype |
| Ägda egenskaps-ID | social ownedpropertyid |
| Ägd egenskap kontra program | social ownedPropertyPropertyApp |
| Namn på ägd egenskap | socialt ägdPropertyName |
| Egenskap för ägd definition kontra post | social owneddefinitionPropertySpets |
| Insiktstyp för ägardefinition | social owneddefinition insightype |
| Insiktsvärde för ägardefinition | socialt neddefinitionindatavärde |
| Ägardefinitionsmått | socialneddefinitionsmätning |
| Tillgång | socialförsäkring |

### Mobile SDK

| Dimensionsnamn (visas i analysgränssnittet) | Dimension-ID (används i API-begäranden) |
|--- |--- |
| Första startdatum | mobileinstalldate |
| Program-ID | mobileappid |
| Startnummer | mobilelaunchnumber |
| Dagar sedan första användningen | mobiledayssincefirstuse |
| Dagar sedan senaste användning | mobiledayssincelastuse |
| Timme på dagen (SDK) | mobilehourofday |
| Veckodag (SDK) | mobiledayofweek |
| Operativsystem (SDK) | mobileosmiljö |
| Dagar sedan senaste uppgraderingen | mobiledayssincelastuppgradering |
| Startar sedan senaste uppgraderingen | mobilelaunchessincelastupgrade |
| Enhetsnamn (SDK) | mobiledevice |
| Operativsystemversion (SDK) | mobileosversion |
| Beacon Major | mobilebeaconmajor |
| Beacon Minor | mobilebeaconminor |
| Beacon UUID | mobilebeaconuid |
| Beacon Proximity | mobilebeaconproximity |
| Placering (ned till 10 km) | latlon1 |
| Plats (ned till 100 m) | latlon23 |
| Plats (ned till 1 m) | latlon45 |
| Intressepunktens namn | pointofinterest |
| Avstånd till intressecentrum | pointränteavstånd |
| Positionsnoggrannhet | mobileplaceprecision |
| Montera kategori | mobileplaceccategory |
| Plats-ID | mobileplaceid |
| Betaversion av ingång | entrymobilebeaconmajor |
| Avsluta Beacon Major | exitmobilebeaconmajor |
| Anmäl dig till Beacon Minor | entrymobilebeaconminor |
| Avsluta Beacon Minor | exitmobilebeaconminor |
| Anmäl Beacon UUID | entrymobilebeaconuuid |
| Avsluta Beacon UUID | exitmobilebeaconuuid |
| Anmäl beacon-närhet | entrymobilebeaconproximity |
| Avsluta Beacon-närhet | exitmobilebeaconproximity |

### Adobe Advertising Cloud (AMO)

| Dimensionsnamn (visas i analysgränssnittet) | Dimension-ID (används i API-begäranden) |
|--- |--- |
| AMO EF-ID | amo_ef_id |
| AMO-ID | amo_cid |

### Aktivitetskarta

| Dimensionsnamn (visas i analysgränssnittet) | Dimension-ID (används i API-begäranden) |
|--- |--- |
| Länk till aktivitetskarta efter region | clickmaplinkbyregion |
| Område för aktivitetskarta | clickmapregion |
| Länk till aktivitetskarta | klickmaplink |
| Sida för aktivitetskarta | klickmappning |

### Nielsen Integration

Mer information om hur du implementerar integreringen finns i [partnerskapet](https://marketing.adobe.com/resources/help/en_US/sc/appmeasurement/hbvideo/nielsen-partnership.html)mellan Nielsen.

| Dimensionsnamn (visas i analysgränssnittet) | Dimension-ID (används i API-begäranden) |
|--- |--- |
| Nielsen Ad Model | nielsenadmodel |
| Nielsen Segment C | nielsensegmentering |
| Nielsen Segment B | nielsensegmentb |
| Nielsen Segment A | nielsensegmenta |
| Nielsen Content ID | nielsencontentid |
| Nielsen Asset/Program | nielsenasset |
| Nielsen VCID | nielsenvcid |
| Nielsen Opt Out | nielsenoptout |
| Nielsen Client ID + VCID | nielsenklientidvcid |
| Nielsen Client ID | nielsenclientid |
| Anmäl dig till Nielsen Opt Out | entrynielsenoptout |
| Avsluta Nielsen Opt Out | exitnielsenoptout |
| Klient-ID för inträde i Nielsen + VCID | entrynielsenclientidvcid |
| Exit Nielsen Client ID + VCID | exitnielsenclientidvcid |
| Klient-ID för tävlingsbidrag till Nielsen | entrynielsenclientid |
| Exit Nielsen Client ID | exitnielsenclientid |

### Adobe Experience Manager (AEM)

| Dimensionsnamn (visas i analysgränssnittet) | Dimension-ID (används i API-begäranden) |
|--- |--- |
| Tillgångs-ID | aemassetid |
| Resurskälla | aemassetsource |
| Klickat på resurs-ID | aemclickedassetid |
| Inmatningstillgångs-ID | entryaemassetid |
| Avsluta resurs-ID | exitaemassetid |

### Adobe Campaign

| Dimensionsnamn (visas i analysgränssnittet) | Dimension-ID (används i API-begäranden) |
|--- |--- |
| Adobe Campaign Executed Delivery ID | ac_delivery_internal_name |
