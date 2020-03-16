---
description: Tabelldata som beskriver kolumnerna i dataflödet.
keywords: Data Feed;columns
subtopic: data feeds
title: Referens för datakolumn
topic: Reports and analytics
uuid: 9042a274-7124-4323-8cd6-5c84ab3eef6d
translation-type: tm+mt
source-git-commit: e9158f4c1ea2fc338116df34d6c6edf93ff7050e

---


# Referens för datakolumn

Använd den här sidan om du vill veta vilka data som finns i varje kolumn. De flesta implementeringar använder inte alla kolumner, så den här sidan kan refereras när du avgör vilka kolumner som ska inkluderas i en datafeedexport.

> [!IMPORTANT] För en given kolumn (till exempel en kolumn som är definierad som 255 tecken) kan ytterligare tecken skickas i en datafeed på grund av att tecken som undgår värden läggs till i en sträng. Tänk på dessa potentiella extra tecken om implementeringen regelbundet skickar värden som överskrider teckengränserna.

## Kolumner, beskrivningar och datatyper

> [!NOTE] De flesta kolumner innehåller en liknande kolumn med prefixet `post_`. Bokför kolumner innehåller värden efter serversidans logik, bearbetningsregler och VISTA-regler. I de flesta fall bör du använda inläggskolumner. Mer information finns i Vanliga frågor om [dataflöden](../df-faq.md) .

| Kolumnnamn | Kolumnbeskrivning | Datatyp |
| --- | --- | --- |
| `accept_language` | Visar alla godkända språk enligt HTTP-huvudet Accept-Language i en bildbegäran. | char(20) |
| `aemassetid` | En variabel med flera värden som motsvarar tillgångs-ID:n (GUID:n) för en uppsättning Adobe Experience Manager-resurser. Ökar imponeringshändelser. | text |
| `aemassetsource` | Identifierar resurshändelsens källa. Används i Adobe Experience Manager. | varchar(255) |
| `aemclickedassetid` | Tillgångs-ID för en Adobe Experience Manager-resurs. Ökningar Klicka på händelser. | varchar(255) |
| `browser` | Numeriskt ID för webbläsaren. Refererar till söktabellen browser.tsv. | int unsigned |
| `browser_height` | Höjd i pixlar i webbläsarfönstret. | smallint unsigned |
| `browser_width` | Bredd i pixlar i webbläsarfönstret. | smallint unsigned |
| `c_color` | Färgpalettens bitdjup. Används som en del av beräkningen av färgdjupsdimensionen. Använder JavaScript-funktionen screen.colorDepth(). | char(20) |
| `campaign` | Variabel som används i spårningskoddimensionen. | varchar(255) |
| `carrier` | Integrationsvariabel för Adobe Advertising Cloud. Anger mobiloperatör. Refererar till transportörens sökregister. | varchar(100) |
| `channel` | Variabel som används i dimensionen Platsavsnitt. | varchar(100) |
| `click_action` | Används inte längre. Adress för länkad som klickats i det äldre klickningsverktyget. | varchar(100) |
| `click_action_type` | Används inte längre. Länktyp för det äldre klickmappsverktyget.<br>0: HREF URL<br>1: Anpassat ID<br>2: JavaScript onClick event<br>3: Formulärelement | tinyint unsigned |
| `click_context` | Används inte längre. Sidnamn där länkklickningen inträffade. En del av det gamla klickmappsverktyget. | varchar(255) |
| `click_context_type` | Används inte längre. Anger om click_context har ett sidnamn eller har en sidadress som standard.<br>0: Sidans URL<br>1: Sidnamn | tinyint unsigned |
| `click_sourceid` | Används inte längre. Numeriskt ID för platsen på den sida där länken klickades. En del av det gamla klickmappsverktyget. | int unsigned |
| `click_tag` | Används inte längre. Typ av HTML-element som klickades på. | char(10) |
| `clickmaplink` | Länk till aktivitetskarta | varchar(255) |
| `clickmaplinkbyregion` | Länk till aktivitetskarta per region | varchar(255) |
| `clickmappage` | Sidan Activity Map | varchar(255) |
| `clickmapregion` | Område för aktivitetskarta | varchar(255) |
| `code_ver` | AppMeasurement Library-version som används för att kompilera och skicka bildbegäran. | char(16) |
| `color` | ID för färgdjup baserat på värdet för kolumnen c_color. Refererar till söktabellen color_depth.tsv. | smallint unsigned |
| `connection_type` | Numeriskt ID som representerar anslutningstypen. Variabel som används i dimensionen Anslutningstyp. Refererar till söktabellen connection_type.tsv. | tinyint unsigned |
| `cookies` | Variabel som används i Cookie-supportdimensionen.<br>Y:<br>EnabledN:<br>DisabledU: Okänd | char(1) |
| `country` | Numeriskt ID som representerar det land som träffen kom från. Adobe samarbetar med Digital Envoy för att matcha IP-adressen med landet. Använder country.tsv-sökning. | smallint unsigned |
| `ct_connect_type` | Relaterat till kolumnen connection_type. De vanligaste värdena är LAN/Wifi, mobiloperatör och modem. | char(20) |
| `curr_factor` | Bestämmer valutadecimalen och används för valutakonvertering. USD använder till exempel två decimaler, så det här kolumnvärdet blir 2. | tinyint |
| `curr_rate` | Växelkursen när transaktionen inträffade. Adobe samarbetar med XE för att fastställa dagens växelkurs. | decimal(24,12) |
| `currency` | Valutakoden som användes under transaktionen. | char(8) |
| `cust_hit_time_gmt` | Endast tidsstämpelaktiverade rapportsviter. Tidsstämpeln som skickades med träffen, baserat på Unix-tid. | int |
| `cust_visid` | Om ett anpassat besökar-ID anges fylls det i i den här kolumnen. | varchar(255) |
| `daily_visitor` | Flagga som avgör om träffen är en ny daglig besökare. | tinyint unsigned |
| `date_time` | Tidpunkten för träffen i läsbart format, baserat på rapportsvitens tidszon. | datetime |
| `domain` | Variabel som används i domändimensionen. Baserat på användarens internetleverantör. | varchar(100) |
| `duplicate_events` | Listar varje händelse som räknats som en dubblett. | varchar(255) |
| `duplicate_purchase` | Flagga som anger att köphändelsen för den här träffen ska ignoreras eftersom den är en dubblett. | tinyint unsigned |
| `duplicated_from` | Används endast i rapportsviter som innehåller VISTA-regler för träffkopior. Anger vilken rapportsvit som träffen kopierades från. | varchar(40) |
| `ef_id` | Det ef_id som används i Adobe Advertising Cloud-integreringar. | varchar(255) |
| `evar1 - evar250` | Egna variabler 1-250. Varje organisation använder eVars på olika sätt. Det bästa stället att få mer information om hur er organisation fyller i respektive eVars är ett dokument som är specifikt för er organisation. | varchar(255) |
| `event_list` | Kommaavgränsad lista med numeriska ID:n som representerar händelser som utlöses vid träffen. Innehåller både standardhändelser och anpassade händelser 1-1000. Använder Event.tsv-sökning. | text |
| `exclude_hit` | Flagga som anger att träffen har uteslutits från rapportering. Kolumnen besök_num ökas inte för uteslutna träffar.<br>1: Används inte. En del av en skrapad funktion.<br>2: Används inte. En del av en skrapad funktion.<br>3: Används inte längre. Undantag<br>för användaragent 4: Undantag baserat på IP-adress<br>5: Viktig träffinformation saknas, t.ex. page_url, pagename, page_event eller event_list<br>6: JavaScript bearbetade inte korrekt träff<br>7: Kontospecifikt undantag, som i VISTA-regler<br>8: Används inte. Alternativt kontospecifikt undantag.<br>9: Används inte. En del av en skrapad funktion.<br>10: Ogiltig valutakod<br>11: Träffen saknade en tidsstämpel i en rapportsserie som bara innehåller tidsstämplar, eller en träff innehöll en tidsstämpel i en rapportsvit<br>som inte är en tidsstämpel: 12: Används inte. En del av en skrapad funktion.<br>13: Används inte. En del av en skrapad funktion.<br>14: Målträff som inte matchar en Analytics-träff<br>15: Används inte för närvarande.<br>16: Advertising Cloud-träff som inte matchar en Analytics-träff | tinyint unsigned |
| `first_hit_page_url` | Besökarens allra första URL. | varchar(255) |
| `first_hit_pagename` | Variabel som används i dimensionen Ursprungligt på startsidan. Besökarens ursprungliga startsidnamn. | varchar(100) |
| `first_hit_ref_domain` | Variabel som används i den ursprungliga referensdomändimensionen. Baserat på first_hit_reference. Den första refererande domänen för besökaren. | varchar(100) |
| `first_hit_ref_type` | Numeriskt ID som representerar referenstypen för besökarens allra första referent. Använder referrer_type.tsv-sökning. | tinyint unsigned |
| `first_hit_referrer` | Den första refererande URL:en för besökaren. | varchar(255) |
| `first_hit_time_gmt` | Tidsstämpel för besökarens första träff i Unix-tid. | int |
| `geo_city` | Namnet på den stad som träffen kom från, baserat på IP. Adobe samarbetar med Digital Envoy för att matcha IP-adressen med staden. | char(32) |
| `geo_country` | Förkortning av det land som träffen kom från, baserat på IP. Adobe samarbetar med Digital Envoy för att matcha IP-adressen med landet. | char(4) |
| `geo_dma` | Numeriskt ID för det demografiska område som träffen kom från, baserat på IP. Adobe samarbetar med Digital Envoy för att matcha IP-adressen med det demografiska området. | int unsigned |
| `geo_region` | Namnet på den stat eller region som träffen kom från, baserat på IP. Adobe samarbetar med Digital Envoy för att matcha IP-adressen med delstat/region. | char(32) |
| `geo_zip` | Postnumret som träffen kom från baseras på IP. Adobe samarbetar med Digital Envoy för att matcha IP-adressen med postkoden. | varchar(16) |
| `hier1 - hier5` | Används av hierarkivariabler. Innehåller en avgränsad lista med värden. Avgränsaren väljs under rapportsvitens inställningar. | varchar(255) |
| `hit_source` | Anger vilken källa träffen kom ifrån. <br>1: Standardbildbegäran utan tidsstämpel <br>2: Standardbildbegäran med tidsstämpel <br>3: Ladda upp datakällor live med tidsstämplar <br>4: Används inte <br>5: Allmän överföring av datakälla <br>6: Uppladdning av datakälla med fullständig bearbetning <br>7: Överföring av datakälla för TransactionID <br>8: Används inte längre. Tidigare versioner av datakällor i Adobe Advertising Cloud <br>9: Används inte längre. Sammanfattningsstatistik för Adobe Social | tinyint unsigned |
| `hit_time_gmt` | Tidsstämpeln för de träffande Adobe-datainsamlingsservrarna tog emot träffen, baserat på Unix-tid. | int |
| `hitid_high` | Används i kombination med hitid_low för att unikt identifiera en träff. | bigint unsigned |
| `hitid_low` | Används i kombination med hitid_high för att unikt identifiera en träff. | bigint unsigned |
| `homepage` | Används inte längre. Anger om den aktuella URL:en är webbläsarens hemsida. | char(1) |
| `hourly_visitor` | Flagga för att avgöra om träffen är en ny timbesökare. | tinyint unsigned |
| `ip` | IP-adress, baserat på HTTP-huvudet i bildbegäran. | char(20) |
| `ip2` | Används inte. Referensvariabel för serverdel för rapportsviter som innehåller VISTA-regler baserade på IP-adressen. | char(20) |
| `j_jscript` | Den version av JavaScript som stöds av webbläsaren. | char(5) |
| `java_enabled` | Flagga som anger om Java är aktiverat. <br>Y: Aktiverat <br>N: Inaktiverad <br>U: Okänd | char(1) |
| `javascript` | Uppslags-ID för JavaScript-version, baserat på j_jscript. Använder uppslagstabell. | tinyint unsigned |
| `language` | Numeriskt ID för språk. Använder uppslagstabellen languages.tsv. | smallint unsigned |
| `last_hit_time_gmt` | Tidsstämpel (i Unix-tid) för föregående träff. Används för att beräkna dimensionen Dagar sedan senaste besök. | int |
| `last_purchase_num` | Variabel som används i kundlojalitetsdimensionen. Anger antalet tidigare inköp som besökaren har gjort. <br>0: Inga tidigare inköp (inte en kund) <br>1: 1 inköp (ny kund) <br>2: 2 tidigare inköp (returkund) <br>3: 3 eller fler tidigare inköp (lojal kund) | int unsigned |
| `last_purchase_time_gmt` | Används i dimensionen Dagar sedan senaste köp. Tidsstämpel (i Unix-tid) för det senaste köpet. För förstagångsköp och besökare som inte har gjort något inköp tidigare är värdet 0. | int |
| `latlon1` | Placering (ned till 10 km) | varchar(255) |
| `latlon23` | Plats (ned till 100 m) | varchar(255) |
| `latlon45` | Plats (ned till 1 m) | varchar(255) |
| `mc_audiences` | Lista över segment-ID för Audience Manager som besökaren tillhör. | text |
| `mcvisid` | Experience Cloud-besökar-ID. 128-bitars nummer som består av två sammanfogade 64-bitars tal som fyllts med 19 siffror. | varchar(255) |
| `mobile_id` | Om användaren använder en mobil enhet anger du enhetens numeriska ID. | int |
| `mobileaction` | Mobilåtgärd. Samlas automatiskt in när trackAction anropas i Mobile Services. Tillåter automatisk åtgärdspunkt i appen. | varchar(100) |
| `mobileappid` | ID för mobilapp. Lagrar programnamnet och versionen i följande format:[AppName] [BundleVersion] | varchar(255) |
| `mobileappperformanceappid` | Används i Apteligent-dataanslutningen. Program-ID som används i Apteligent. | varchar(255) |
| `mobileappperformancecrashid` | Används i Apteligent-dataanslutningen. Det krasch-ID som används i Apteligent. | varchar(255) |
| `mobileappstoreobjectid` | Används i Appfigurations dataanslutning. Objekt-ID för App Store | varchar(255) |
| `mobilebeaconmajor` | Mobiltjänster är viktiga | varchar(100) |
| `mobilebeaconminor` | Mobiltjänster är mindre | varchar(100) |
| `mobilebeaconproximity` | Avstånd för mobiltjänster | varchar(255) |
| `mobilebeaconuuid` | Beacon UUID för mobiltjänster | varchar(100) |
| `mobilecampaigncontent` | Namnet eller ID för innehållet som visade länken. Fylls i av Anskaffning av mobilapp. | varchar(255) |
| `mobilecampaignmedium` | Marknadsföringsmedium, som banner eller e-post. Fylls i av Anskaffning av mobilapp. | varchar(255) |
| `mobilecampaignname` | Namnet på kampanjen, som också lagras i kampanjvariabeln. Fylls i av Anskaffning av mobilapp. | varchar(255) |
| `mobilecampaignsource` | Ursprunglig hänvisare, till exempel nyhetsbrev eller sociala medier. Fylls i av Anskaffning av mobilapp. | varchar(255) |
| `mobilecampaignterm` | Betalnyckelord eller andra termer som du vill spåra med förvärvet. Fylls i av Anskaffning av mobilapp. | varchar(255) |
| `mobiledayofweek` | Nummer på den veckodag då appen startades. | varchar(255) |
| `mobiledayssincefirstuse` | Antal dagar sedan appen kördes för första gången. | varchar(255) |
| `mobiledayssincelastupgrade` | Samlas in från kontextdatavariabeln a.DaysSinceLastUpgrade. Antalet dagar som har gått sedan föregående session. | varchar(255) |
| `mobiledayssincelastuse` | Antal dagar sedan appen senast kördes. | varchar(255) |
| `mobiledeeplinkid` | Samlas in från kontextdatavariabeln a.<span>deeplink</span>.id. Används i förvärvsrapporter som en identifierare för länken för mobilförvärv. | varchar(255) |
| `mobiledevice` | Namn på mobil enhet. I iOS lagras den som en kommaavgränsad 2-siffrig sträng. Det första numret representerar enhetsgenereringen och det andra representerar enhetsfamiljen. | varchar(255) |
| `mobilehourofday` | Definierar timmen på dagen då appen startades. Använder ett numeriskt format på 24 timmar. | varchar(255) |
| `mobileinstalldate` | Datum för mobilinstallation. Anger datumet för första gången en användare öppnar mobilappen. | varchar(255) |
| `mobilelaunchessincelastupgrade` | Samlas in från kontextdatavariabeln a.LaunchesSinceUpgrade. Rapporterar antalet starter sedan den senaste uppgraderingen. | varchar(255) |
| `mobilelaunchnumber` | Ökningar med ett varje gång mobilappen startas. | varchar(255) |
| `mobileltv` | Används inte längre. Fylls i av trackLifetimeValue-metoder. | varchar(255) |
| `mobilemessagebuttonname` | Samlas in från kontextdatavariabeln a.<span>message</span>.button.id. Används för meddelanden i appen för att identifiera knappen som stängde meddelandet. | varchar(100) |
| `mobilemessageid` | Meddelande-ID i appen | varchar(255) |
| `mobilemessageonline` | Meddelande i appen online | varchar(255) |
| `mobilemessagepushoptin` | Samlas in från kontextdatavariabeln a.push.optin. Ange som&quot;true&quot; när användaren väljer att skicka meddelanden; i annat fall är värdet &quot;false&quot;. | varchar(255) |
| `mobilemessagepushpayloadid` | Samlas in från kontextdatavariabeln a.push.paylodid. Används i push-meddelanden som nyttolast-ID. | varchar(255) |
| `mobileosenvironment` | Samlas in från kontextdatavariabeln a.OSEenvironment. Lägesmiljö, t.ex. Android eller iOS. | varchar(255) |
| `mobileosversion` | Mobiltjänstens operativsystemversion | varchar(255) |
| `mobileplaceaccuracy` | Samlas in från kontextdatavariabeln a.loc.acc. Anger GPS-noggrannheten i meter vid insamlingen. | varchar(255) |
| `mobileplacecategory` | Samlas in från kontextdatavariabeln a.loc.category. Beskriver kategorin för en viss plats. | varchar(255) |
| `mobileplaceid` | Samlas in från kontextdatavariabeln a.<span>loc</span>.id. Identifierare för en viss intressepunkt. | varchar(255) |
| `mobilerelaunchcampaigncontent` | Startinnehåll för mobiltjänster | varchar(255) |
| `mobilerelaunchcampaignmedium` | Startmedium för mobiltjänster | varchar(255) |
| `mobilerelaunchcampaignsource` | Startkälla för Mobile Services | varchar(255) |
| `mobilerelaunchcampaignterm` | Startperiod för Mobile Services | varchar(255) |
| `mobilerelaunchcampaigntrackingcode` | Samlas in från kontextdatavariabeln a.launch.campaign.trackingcode. Används i anskaffning som spårningskod för lanseringskampanj. | varchar(255) |
| `mobileresolution` | Upplösning för den mobila enheten. Bredd x höjd i pixlar. | varchar(255) |
| `monthly_visitor` | Flagga som anger att besökaren är unik för den aktuella månaden. | tinyint unsigned |
| `mvvar1` - `mvvar3` | Lista variabelvärden. Innehåller en avgränsad lista med anpassade värden beroende på implementering. | text |
| `namespace` | Används inte. En del av en kasserad funktion för många år sedan. | varchar(50) |
| `new_visit` | Flagga som avgör om den aktuella träffen är ett nytt besök. Anges av Adobes servrar efter 30 minuters inaktivitet. | tinyint unsigned |
| `os` | Numeriskt ID som representerar besökarens operativsystem. Baserat på kolumnen user_agent. Använder OS-sökning. | int unsigned |
| `p_plugins` | Används inte längre. Lista över plugin-program som är tillgängliga för webbläsaren. Använder JavaScript-funktionen navigator.plugins(). | text |
| `page_event` | Den typ av träff som skickas i bildbegäran (standardträff, nedladdningslänk, anpassad länk, slutlänk). Se [Sökning efter](datafeeds-page-event.md)sidhändelser. | tinyint unsigned |
| `page_event_var1` | Används endast vid förfrågningar om länkspårningsbilder. URL-adressen till den nedladdningslänk, den avslutningslänk eller anpassade länk som du klickat på. | text |
| `page_event_var2` | Används endast vid förfrågningar om länkspårningsbilder. Länkens anpassade namn (om det anges). | varchar(100) |
| `page_event_var3` | Används inte längre. Behållna data från undersökningen och mediemodulen. Fyllda gamla videorapporter i tidigare versioner av Adobe Analytics. | text |
| `page_type` | Används för att fylla i dimensionen Ej hittade sidor, som används exklusivt för 404 sidor. Variabeln ska antingen vara tom eller innehålla ErrorPage. | char(20) |
| `page_url` | URL:en för träffen. Används inte i bildbegäranden för länkspårning. | varchar(255) |
| `pagename` | Används för att fylla siddimensionen. Om sidnamnsvariabeln är tom använder Analytics page_url i stället. | varchar(100) |
| `paid_search` | Flagga som anges om träffen matchar betald sökningsidentifiering. | tinyint unsigned |
| `partner_plugins` | Används inte. En del av en kasserad funktion för många år sedan. | varchar(255) |
| `persistent_cookie` | Används av Persistent Cookie Support-dimensionen. Anger om besökaren stöder cookies som inte tas bort efter varje träff. | char(1) |
| `plugins` | Används inte längre. Lista med numeriska ID:n som motsvarar plugin-program som är tillgängliga i webbläsaren. Använder plugins.tsv-sökning. | varchar(180) |
| `pointofinterest` | Intressepunktsnamn för mobiltjänster | varchar(255) |
| `pointofinterestdistance` | Avstånd för mobiltjänster till intressanta center | varchar(255) |
| `post_ columns` | Innehåller värdet som används i rapporterna. Varje inläggskolumn fylls i efter serversidans logik, bearbetningsregler och VISTA-regler. I de flesta fall bör du använda inläggskolumner. | Se respektive icke-postkolumn |
| `prev_page` | Används inte. Adobes egen identifierare för föregående sida. | int unsigned |
| `product_list` | Produktlistan har skickats in via produktvariabeln. Produkterna avgränsas med kommatecken medan de enskilda produktegenskaperna avgränsas med semikolon. | text |
| `product_merchandising` | Används inte. Använd product_list i stället. | text |
| `prop1` - `prop75` | Anpassade trafikvariabler 1-75. | varchar(100) |
| `purchaseid` | Unik identifierare för ett köp, enligt inställningen med variabeln s_purchaseID. Används av kolumnen duplicate_purchase. | char(20) |
| `quarterly_visitor` | Flagga som avgör om träffen är en ny kvartalsbesökare. | tinyint unsigned |
| `ref_domain` | Baserat på referenskolumnen. Den refererande domänen för träffen. | varchar(100) |
| `ref_type` | Ett numeriskt ID som representerar typen av referens för träffen.<br>1: Inuti din webbplats<br>2: Andra webbplatser <br>3: Sökmotorer <br>4: Hårddisk <br>5: USENET <br>6: Typed/Bookmarked (ingen referent) <br>7: E-post <br>8: Ingen JavaScript <br>9: Sociala nätverk | tinyint unsigned |
| `referrer` | Föregående sidas URL. Observera, att medan `referrer` datatypen varchar(255) används `post_referrer` datatypen varchar(244). | varchar(255) |
| `resolution` | Numeriskt ID som representerar bildskärmens upplösning. Fyller i skärmupplösningsdimensionen. Använder uppslagstabellen resolution.tsv. | smallint unsigned |
| `s_kwcid` | Nyckelord-ID som används i Adobe Advertising Cloud-integreringar. | varchar(255) |
| `s_resolution` | Upplösningsvärde för råformat. Insamlas med JavaScript-funktionen screen.width x screen.height. | char(20) |
| `sampled_hit` | Används inte längre. Användes tidigare för provtagning i ad hoc-analys. | char(1) |
| `search_engine` | Numeriskt ID som representerar sökmotorn som refererade besökaren till webbplatsen. Använder search_engines.tsv-sökning. | smallint unsigned |
| `search_page_num` | Används av dimensionen Rankning för alla söksidor. Anger vilken sida av sökresultat din webbplats hade innan användaren klickade igenom till din webbplats. | smallint unsigned |
| `secondary_hit` | Flagga som spårar sekundära träffar. Ursprungligen kommer taggar för flera programsviter och VISTA-regler som kopierar träffar. | tinyint unsigned |
| `service` | Används inte. Använd page_event i stället. | char(2) |
| `socialaccountandappids` | Används inte längre. Socialt konto och program-ID | varchar(255) |
| `socialassettrackingcode` | Används inte längre. Variabel för social kampanj | varchar(255) |
| `socialauthor` | Används inte längre. Variabel för sociala författare | varchar(255) |
| `socialcontentprovider` | Används inte längre. Sociala plattformar/egenskaper | varchar(255) |
| `socialinteractiontype` | Används inte längre. Typ av social interaktion | varchar(255) |
| `sociallanguage` | Används inte längre. Socialt språk | varchar(255) |
| `sociallatlong` | Används inte längre. Social Latitude/longitud | varchar(255) |
| `socialowneddefinitioninsighttype` | Används inte längre. Typ av definitionsinsikter som ägs av sociala medier | varchar(255) |
| `socialowneddefinitioninsightvalue` | Används inte längre. Socialt ägt definitionsinsiktsvärde | varchar(255) |
| `socialowneddefinitionmetric` | Används inte längre. Definitionsmått som ägs av sociala medier | varchar(255) |
| `socialowneddefinitionpropertyvspost` | Används inte längre. Definitionsegenskap som ägs av sociala medier kontra post | varchar(255) |
| `socialownedpostids` | Används inte längre. Socialt ägda post-ID:n | varchar(255) |
| `socialownedpropertyid` | Används inte längre. ID för socialt ägd egendom | varchar(255) |
| `socialownedpropertyname` | Används inte längre. Namn på egendom som ägs av sociala medier | varchar(255) |
| `socialownedpropertypropertyvsapp` | Används inte längre. Egendom i sociala medier kontra app | varchar(255) |
| `state` | State-variabel. | varchar(50) |
| `stats_server` | Inte till användning. Adobes interna server som bearbetade träffen. | char(30) |
| `t_time_info` | Lokal tid för besökaren. Formatet är följande: M/D/YYYY HH:MM:SS Month (0-11, 0=January) Tidszonsförskjutning (i minuter) | varchar(100) |
| `tnt` | Används i Adobe Target-integreringar. | text |
| `tnt_action` | Används i Adobe Target-integreringar. | text |
| `tnt_post_vista` | Används inte längre. Använd post_tnt i stället. | text |
| `transactionid` | En unik identifierare där olika datapunkter kan överföras senare via datakällor. | text |
| `truncated_hit` | En flagga som anger att bildbegäran har trunkerats. Anger att en partiell träff togs emot. <br>Y: Träet trunkerades. partiell träff mottagen <br>N: Träet trunkerades inte. fullständig träff mottagen | char(1) |
| `ua_color` | Används inte längre. Används tidigare som reserv för färgdjup. | char(20) |
| `ua_os` | Används inte längre. Används tidigare som reserv för operativsystemet. | char(80) |
| `ua_pixels` | Används inte längre. Används tidigare som reserv för webbläsarens höjd och bredd. | char(20) |
| `user_agent` | Användaragentsträng som skickas i HTTP-huvudet i bildbegäran. | text |
| `user_hash` | Inte till användning. Hash för rapportens Suite-ID. Använd användarnamn i stället. | int unsigned |
| `user_server` | Variabel som används i serverdimensionen. | varchar(100) |
| `userid` | Inte till användning. Det numeriska ID:t för rapportsvitens ID. Använd användarnamn i stället. | int unsigned |
| `username` | Rapportsvitens ID för träffen. | char(40) |
| `va_closer_detail` | Variabel som används i dimensionen Senaste beröringsdetalj. | varchar(255) |
| `va_closer_id` | Numeriskt ID som identifierar dimensionen Sista beröringskanalen. En sökning efter detta ID finns i Marketing Channel Manager. | tinyint unsigned |
| `va_finder_detail` | Variabel som används i dimensionen Första beröringsdetalj. | varchar(255) |
| `va_finder_id` | Numeriskt ID som identifierar den första beröringskanaldimensionen. En sökning efter detta ID finns i Marketing Channel Manager. | tinyint unsigned |
| `va_instance_event` | Flagga för att identifiera instanser av marknadsföringskanaler. Används av mätvärdet för sista beröringsinstansen i marknadsföringskanalen. | tinyint unsigned |
| `va_new_engagement` | Flagga för att identifiera nya engagemang i Marketing Channel. Används av måttet New Engagements. | tinyint unsigned |
| `video` | Videoinnehåll | varchar(255) |
| `videoad` | Namn på videoannons | varchar(255) |
| `videoadinpod` | Videoannons i podposition | varchar(255) |
| `videoadlength` | Videoannons | varchar(255) |
| `videoadload` | Videoannonser | varchar(255) |
| `videoadname` | Namn på videoannons | varchar(255) |
| `videoadplayername` | Namn på video- och videospelare | varchar(255) |
| `videoadpod` | Video och pod | varchar(255) |
| `videoadvertiser` | Videoreklam | varchar(255) |
| `videoaudioalbum` | Videoljudalbum | varchar(255) |
| `videoaudioartist` | Videoljudartist | varchar(255) |
| `videoaudioauthor` | Videoljudförfattare | varchar(255) |
| `videoaudiolabel` | Etikett för videoljud | varchar(255) |
| `videoaudiopublisher` | Videoljudspublicering | varchar(255) |
| `videoaudiostation` | Videoljudstation | varchar(255) |
| `videocampaign` | Videokampanj | varchar(255) |
| `videochannel` | Videokanal | varchar(255) |
| `videochapter` | Namn på videokapitel | varchar(255) |
| `videocontenttype` | Videoinnehållstyp. Ange automatiskt som Video för alla videovyer | varchar(255) |
| `videodaypart` | Video day part | varchar(255) |
| `videoepisode` | Videoavsnitt | varchar(255) |
| `videofeedtype` | Typ av videofeed | varchar(255) |
| `videogenre` | Videogenre | text |
| `videolength` | Videolängd | varchar(255) |
| `videomvpd` | Video MVPD | varchar(255) |
| `videoname` | Videonamn | varchar(255) |
| `videonetwork` | Videonätverk | varchar(255) |
| `videopath` | Videosökväg | varchar(100) |
| `videoplayername` | Videospelarens namn | varchar(255) |
| `videoqoebitrateaverageevar` | Genomsnittlig bithastighet för videokvalitet | varchar(255) |
| `videoqoebitratechangecountevar` | Antal ändringar av videokvalitet | varchar(255) |
| `videoqoebuffercountevar` | Buffertantal för videokvalitet | varchar(255) |
| `videoqoebuffertimeevar` | Bufferttid för videokvalitet | varchar(255) |
| `videoqoedroppedframecountevar` | Antal uteslutna bildrutor för videokvalitet | varchar(255) |
| `videoqoeerrorcountevar` | Antal fel för videokvalitet | varchar(255) |
| `videoqoeextneralerrors` | Externa fel i videokvalitet | text |
| `videoqoeplayersdkerrors` | SDK-fel för videokvalitet | text |
| `videoqoetimetostartevar` | Tidpunkt för videokvalitet till start | varchar(255) |
| `videoseason` | Videoårstid | varchar(255) |
| `videosegment` | Videosegment | varchar(255) |
| `videoshow` | Videoprogram | varchar(255) |
| `videoshowtype` | Videovisningstyp | varchar(255) |
| `videostreamtype` | Typ av videoström | varchar(255) |
| `visid_high` | Används i kombination med visid_low för att unikt identifiera ett besök. | bigint unsigned |
| `visid_low` | Används i kombination med visid_high för att unikt identifiera ett besök. | bigint unsigned |
| `visid_new` | Flagga som identifierar om träffen innehåller ett nyligen genererat besökar-ID. | char(1) |
| `visid_timestamp` | Om besökar-ID nyligen genererades, anger tidsstämpeln (i Unix-tid) för när besökar-ID genererades. | int |
| `visid_type` | Numeriskt ID som representerar vilken metod som användes för att identifiera besökaren. <br>0: Anpassat besökarID <br>1: IP-adress och reserv för användaragent <br>2: HTTP Mobile Subscriber Header <br>3: Äldre cookie-värde (s_vi) <br>4: Värde för reservcookie (s_fid) <br>5: Identitetstjänst | tinyint unsigned |
| `visit_keywords` | Variabel som används i söknyckelordsdimensionen. I den här kolumnen används en teckengräns som inte är standard för att rymma den serverlogik som används av Adobe. | varchar(244) |
| `visit_num` | Variabel som används i dimensionen Besöksnummer. Börjar vid 1 och ökar stegvis varje gång ett nytt besök påbörjas per besökare. | int unsigned |
| `visit_page_num` | Variabel som används i dimensionen Träff. Ökar med 1 för varje träff som användaren skapar. Återställer varje besök. | int unsigned |
| `visit_ref_domain` | Baserat på kolumnen visit_reference. Den första refererande domänen för besöket. | varchar(100) |
| `visit_ref_type` | Numeriskt ID som representerar referenstypen för besökets första referent. Använder söktabellen referrer_type.tsv. | tinyint unsigned |
| `visit_referrer` | Den första referenten till besöket. | varchar(255) |
| `visit_search_engine` | Numeriskt ID för besökets första sökmotor. Använder söktabellen search_engines.tsv. | smallint unsigned |
| `visit_start_page_url` | Besökets första URL. | varchar(255) |
| `visit_start_pagename` | Besökets första sidnamn. | varchar(100) |
| `visit_start_time_gmt` | Tidsstämpel (i Unix-tid) för besökets första träff. | int |
| `weekly_visitor` | Flagga som avgör om träffen är en ny besökare varje vecka. | tinyint unsigned |
| `yearly_visitor` | Flagga som avgör om träffen är en ny årlig besökare. | tinyint unsigned |
| `zip` | Används för att fylla i postkodsdimensionen. | varchar(50) |

## Tomma kolumner

Följande kolumnlista används inte och innehåller inga data:

* mobilequitionclicks
* mobileactioninapptime
* mobileactiontotaltime
* mobileappperformanceaffectedanvändare
* mobileappperformanceappid<span>.</span>app-perf-app-name
* mobileappperformanceappid<span>.</span>app-perf-platform
* mobileappperformanska kramper
* mobileappperformancrashid<span>.</span>app-perf-crash-name
* mobileappperformanceloads
* mobileappstoreavgrating
* mobileappstoredownloads
* mobileappstoreapprevenue
* mobileappstoåteranvändningsavgifter
* mobileappstoreobjectid<span>.</span>app-store-user
* mobileappstoreobjectid<span>.</span>application-name
* mobileappstoreobjectid<span>.</span>application-version
* mobileappstoreobjectid<span>.</span>appstore-name
* mobileappstoreobjectid<span>.</span>category-name
* mobileappstoreobjectid<span>.</span>country-name
* mobileappstoreobjectid<span>.</span>enhetstillverkare
* mobileappstoreobjectid<span>.</span>device-name
* mobileappstoreobjectid<span>.</span>in-app-name
* mobileappstoreobjectid<span>.</span>platform-name-version
* mobileappstoreobjectid<span>.</span>rankningskategori-typ
* mobileappstoreobjectid<span>.</span>region-name
* mobileappstoreobjectid<span>.</span>review-comment
* mobileappstoreobjectid<span>.</span>review-title
* mobileappstoreoneoffrevenue
* mobileappstoreoneoffroyalty
* mobileappstorepurchase
* mobileappstorerank
* mobileappstorerankdivisor
* mobileappstorerating
* mobileappstoratingdivisor
* mobileavgprevisessionlength
* mobilkrascher
* mobilkraschränta
* mobiledailyengagedusers
* mobiledeplinboy<span>.</span>name
* mobileinstalls
* mobilenheter
* mobileltvtotal
* mobilemessageclicks
* mobilemessageid<span>.</span>dest
* mobilemessageid<span>.</span>name
* mobilemessageid<span>.</span>type
* mobilemessagevisningar
* mobilemessagepushpayloadid<span><span>.</span></span>name
* mobilemessagevisions
* mobilemonthlyengagedusers
* mobileplacedwelltime
* mobileplaceentry
* mobileplaceexit
* mobilepreventsessionlength
* mobilerelaunchcampaignTrackingcode<span><span>.</span></span>name
* mobileupgrades
* social aversionsenhet
* social aversionsinsats (utgått)
* socialfbstories
* socialfbstorytellers
* social interactioncount
* sociallikeadding
* sociallink
* social länk (borttagen)
* sociala omnämnanden
* socialpagevisions
* sociala vyvyer
* social egendom
* social egendom (utgått)
* sociala kommentarer
* sociala inlägg
* social pubrecommended
* socialtjänsten
* social
* socialtermslista
* socialtermslist (utgått)
* social totaluppfattning
* sourceid
* videoauktoriserad
* videoaverageminutepublik
* videochaptercomplete
* videochapterstart
* videochaptertime
* videopaus
* videopausecount
* videopausetime
* videospela
* videoprogress10
* videoprogress25
* videoprogress50
* videoprogress75
* videoprogress96
* videoqoebitrateGenomsnitt
* videoqoebitratchange
* videoqoebuffer
* videoQuoedropförstart
* videoedroppedframes
* videoqoeerror
* videoresume
* videototaltime
* videokortiketimespelad
