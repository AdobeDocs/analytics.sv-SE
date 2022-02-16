---
description: Tabelldata som beskriver kolumnerna i dataflödet.
keywords: Datafeed;kolumner
subtopic: data feeds
title: Referens för datakolumner
feature: Data Feeds
exl-id: e1492147-6e7f-4921-b509-898e7efda596
source-git-commit: 4daa5c8bdbcb483f23a3b8f75dde9eeb48516db8
workflow-type: tm+mt
source-wordcount: '3445'
ht-degree: 0%

---

# Referens för datakolumner

Använd den här sidan om du vill veta vilka data som finns i varje kolumn. De flesta implementeringar använder inte alla kolumner, så den här sidan kan refereras när du avgör vilka kolumner som ska inkluderas i en datafeedexport.

>[!IMPORTANT]
>
>För en given kolumn (till exempel en kolumn som är definierad som 255 tecken) kan ytterligare tecken skickas i en datafeed på grund av att tecken som undgår värden läggs till i en sträng. Tänk på dessa potentiella extra tecken om implementeringen regelbundet skickar värden som överskrider teckengränserna.

## Kolumner, beskrivningar och datatyper

>[!NOTE]
>
>De flesta kolumner innehåller en liknande kolumn med ett prefix på `post_`. Bokför kolumner innehåller värden efter serversidans logik, bearbetningsregler och VISTA-regler. Adobe rekommenderar att du i de flesta fall använder inläggskolumner. Se [Vanliga frågor om dataflöden](../df-faq.md) för mer information.

| Kolumnnamn | Kolumnbeskrivning | Datatyp |
| --- | --- | --- |
| `accept_language` | Visar alla godkända språk enligt HTTP-huvudet Accept-Language i en bildbegäran. | char(20) |
| `aemassetid` | En variabel med flera värden som motsvarar tillgångar-ID:n (GUID:n) för en uppsättning Adobe Experience Manager Assets. Ökar imponeringshändelser. | text |
| `aemassetsource` | Identifierar resurshändelsens källa. Används i Adobe Experience Manager. | varchar(255) |
| `aemclickedassetid` | Tillgångs-ID för en Adobe Experience Manager-resurs. Ökningar Klicka på händelser. | varchar(255) |
| `browser` | Numeriskt ID för webbläsaren. Refererar till `browser.tsv` uppslagstabell. | int unsigned |
| `browser_height` | Höjd i pixlar i webbläsarfönstret. | smallint unsigned |
| `browser_width` | Bredd i pixlar i webbläsarfönstret. | smallint unsigned |
| `c_color` | Färgpalettens bitdjup. Används som en del av beräkningen av [Färgdjup](/help/components/dimensions/color-depth.md) dimension. AppMeasurement använder JavaScript-funktionen `screen.colorDepth()`. | char(20) |
| `campaign` | Variabel som används i [Spårningskod](/help/components/dimensions/tracking-code.md) dimension. | varchar(255) |
| `carrier` | Adobe Advertising Cloud integrationsvariabel. Anger mobiloperatör. Refererar till `carrier` uppslagstabell. | varchar(100) |
| `channel` | Variabel som används i [Platsavsnitt](/help/components/dimensions/site-section.md) dimension. | varchar(100) |
| `click_action` | Används inte längre. Adress för länkad som klickats i det äldre klickningsverktyget. | varchar(100) |
| `click_action_type` | Används inte längre. Länktyp för det äldre klickmappsverktyget.<br>0: HREF-URL<br>1: Anpassat ID<br>2: JavaScript-händelsen onClick<br>3: Formulärelement | tinyint unsigned |
| `click_context` | Används inte längre. Sidnamn där länkklickningen inträffade. En del av det gamla klickmappsverktyget. | varchar(255) |
| `click_context_type` | Används inte längre. Anger om click_context har ett sidnamn eller har en sidadress som standard.<br>0: Sidans URL<br>1: Sidnamn | tinyint unsigned |
| `click_sourceid` | Används inte längre. Numeriskt ID för platsen på den sida där länken klickades. En del av det gamla klickmappsverktyget. | int unsigned |
| `click_tag` | Används inte längre. Typ av HTML-element som du klickade på. | char(10) |
| `clickmaplink` | Activity Map link | varchar(255) |
| `clickmaplinkbyregion` | Activity Map länk per region | varchar(255) |
| `clickmappage` | Activity Map page | varchar(255) |
| `clickmapregion` | Activity Map | varchar(255) |
| `code_ver` | AppMeasurement Library-version som används för att kompilera och skicka bildbegäran. | char(16) |
| `color` | ID för färgdjup baserat på värdet för `c_color` kolumn. Refererar till `color_depth.tsv` uppslagstabell. | smallint unsigned |
| `connection_type` | Numeriskt ID som representerar anslutningstypen. Variabel som används i [Anslutningstyp](/help/components/dimensions/connection-type.md) dimension. Refererar till `connection_type.tsv` uppslagstabell. | tinyint unsigned |
| `cookies` | Variabel som används i [Cookie-stöd](/help/components/dimensions/cookie-support.md) dimension.<br>Y: Aktiverad<br>N: Handikappade<br>U: Okänd | char(1) |
| `country` | Numeriskt ID som representerar värden som finns i `country.tsv` sökning. Används i rapporten för toppnivådomäner i Rapporter och analyser. | smallint unsigned |
| `ct_connect_type` | Relaterat till `connection_type` kolumn. De vanligaste värdena är LAN/Wifi, mobiloperatör och modem. | char(20) |
| `curr_factor` | Bestämmer valutadecimalen och används för valutakonvertering. USD använder till exempel två decimaler, så det här kolumnvärdet blir 2. | tinyint |
| `curr_rate` | Växelkursen när transaktionen inträffade. Adobe samarbetar med XE för att fastställa dagens växelkurs. | decimal(24,12) |
| `currency` | Valutakoden som användes under transaktionen. | char(8) |
| `cust_hit_time_gmt` | Endast tidsstämpelaktiverade rapportsviter. Tidsstämpeln som skickades med träffen, baserat på Unix-tid. | int |
| `cust_visid` | Om ett anpassat besökar-ID anges fylls det i i den här kolumnen. | varchar(255) |
| `daily_visitor` | Flagga som avgör om träffen är en ny daglig besökare. | tinyint unsigned |
| `date_time` | Tidpunkten för träffen i läsbart format, baserat på rapportsvitens tidszon. | datetime |
| `domain` | Variabel som används i [Domän](/help/components/dimensions/domain.md) dimension. Baserat på besökarens internetanslutning. | varchar(100) |
| `duplicate_events` | Listar varje händelse som räknats som en dubblett. | varchar(255) |
| `duplicate_purchase` | Flagga som anger att köphändelsen för den här träffen ska ignoreras eftersom den är en dubblett. | tinyint unsigned |
| `duplicated_from` | Används endast i rapportsviter som innehåller VISTA-regler för träffkopior. Anger vilken rapportsvit som träffen kopierades från. | varchar(40) |
| `ef_id` | The `ef_id` används i Adobe Advertising Cloud-integreringar. | varchar(255) |
| `evar1 - evar250` | Egna variabler 1-250. Används i [eVar](/help/components/dimensions/evar.md) dimensioner. Varje organisation använder eVars på olika sätt. Det bästa stället att få mer information om hur er organisation fyller i respektive eVars är ett dokument som är specifikt för er organisation. | varchar(255) |
| `event_list` | Kommaavgränsad lista med numeriska ID:n som representerar händelser som utlöses vid träffen. Innehåller både standardhändelser och anpassade händelser 1-1000. Användningsområden `event.tsv` sökning. | text |
| `exclude_hit` | Flagga som anger att träffen är exkluderad från rapportering. The `visit_num` kolumnen ökas inte för uteslutna träffar.<br>1: Används inte. En del av en skrapad funktion.<br>2: Används inte. En del av en skrapad funktion.<br>3: Används inte längre. Undantag för användaragent<br>4: Uteslutning baserad på IP-adress<br>5: Information om viktig träff saknas, t.ex. `page_url`, `pagename`, `page_event`, eller `event_list`<br>6: JavaScript bearbetade inte träffen korrekt<br>7: Kontospecifikt undantag, t.ex. i VISTA-regler<br>8: Används inte. Alternativt kontospecifikt undantag.<br>9: Används inte. En del av en skrapad funktion.<br>10: Ogiltig valutakod<br>11: Träffen saknade en tidsstämpel i en rapportsserie som bara innehåller tidsstämplar, eller en träff innehöll en tidsstämpel i en rapportsvit som inte är en tidsstämpel<br>12: Används inte. En del av en skrapad funktion.<br>13: Används inte. En del av en skrapad funktion.<br>14: Målträff som inte matchar en Analytics-träff<br>15: Används inte för närvarande.<br>16: Advertising Cloud-träff som inte matchar en Analytics-träff | tinyint unsigned |
| `first_hit_page_url` | Besökarens allra första URL. | varchar(255) |
| `first_hit_pagename` | Variabel som används i [Startsida, original](/help/components/dimensions/entry-dimensions.md) dimension. Besökarens ursprungliga startsidnamn. | varchar(100) |
| `first_hit_ref_domain` | Variabel som används i [Ursprunglig hänvisande domän](/help/components/dimensions/original-referring-domain.md) dimension. Baserat på `first_hit_referrer`. Den första refererande domänen för besökaren. | varchar(100) |
| `first_hit_ref_type` | Numeriskt ID som representerar referenstypen för besökarens allra första referent. Användningsområden `referrer_type.tsv` sökning. | tinyint unsigned |
| `first_hit_referrer` | Den första refererande URL:en för besökaren. | varchar(255) |
| `first_hit_time_gmt` | Tidsstämpel för besökarens första träff i Unix-tid. | int |
| `geo_city` | Namnet på den stad som träffen kom från, baserat på IP. Används i [Städer](/help/components/dimensions/cities.md) dimension. | char(32) |
| `geo_country` | Förkortning av det land som träffen kom från, baserat på IP. Används i [Länder](/help/components/dimensions/countries.md) dimension. | char(4) |
| `geo_dma` | Numeriskt ID för det demografiska område som träffen kom från, baserat på IP. Används i [US DMA](/help/components/dimensions/us-dma.md) dimension. | int unsigned |
| `geo_region` | Namnet på den stat eller region som träffen kom från, baserat på IP. Används i [Regioner](/help/components/dimensions/regions.md) dimension. | char(32) |
| `geo_zip` | Postnumret som träffen kom från baseras på IP. Fyller i [Postnummer](/help/components/dimensions/zip-code.md) dimension. Se även `zip`. | varchar(16) |
| `hier1 - hier5` | Används av hierarkivariabler. Innehåller en avgränsad lista med värden. Avgränsaren väljs under rapportsvitens inställningar. | varchar(255) |
| `hit_source` | Anger vilken källa träffen kom ifrån. Träffkällor 1, 2 och 6 faktureras. <br>1: Standardbildbegäran utan tidsstämpel <br>2: Standardbildbegäran med tidsstämpel <br>3: Överföring av Live-datakällor med tidsstämplar <br>4: Används inte <br>5: Allmän överföring av datakälla <br>6: Överföring av datakälla med fullständig bearbetning <br>7: Överföring av datakälla för TransactionID <br>8: Används inte längre. Tidigare versioner av Adobe Advertising Cloud datakällor <br>9: Används inte längre. Adobe Social i korthet <br>10: Vidarebefordran på serversidan i Audience Manager används | tinyint unsigned |
| `hit_time_gmt` | Tidsstämpeln för Adobe-datainsamlingsservrarna tog emot träffen, baserat på Unix-tid. | int |
| `hitid_high` | Används i kombination med `hitid_low` för att identifiera en träff. | bigint unsigned |
| `hitid_low` | Används i kombination med `hitid_high` för att identifiera en träff. | bigint unsigned |
| `homepage` | Används inte längre. Anger om den aktuella URL:en är webbläsarens hemsida. | char(1) |
| `hourly_visitor` | Flagga för att avgöra om träffen är en ny timbesökare. | tinyint unsigned |
| `ip` | IP-adress, baserat på HTTP-huvudet i bildbegäran. | char(20) |
| `ip2` | Används inte. Referensvariabel för serverdel för rapportsviter som innehåller VISTA-regler baserade på IP-adressen. | char(20) |
| `j_jscript` | Den version av JavaScript som stöds av webbläsaren. | char(5) |
| `java_enabled` | Flagga som anger om Java är aktiverat. <br>Y: Aktiverad <br>N: Handikappade <br>U: Okänd | char(1) |
| `javascript` | Uppslags-ID för JavaScript-version, baserat på `j_jscript`. Använder uppslagstabell. | tinyint unsigned |
| `language` | Numeriskt ID för språk. Användningsområden `languages.tsv` uppslagstabell. | smallint unsigned |
| `last_hit_time_gmt` | Tidsstämpel (i Unix-tid) för föregående träff. Används för att beräkna [Dagar sedan senaste besök](/help/components/dimensions/days-since-last-visit.md) dimension. | int |
| `last_purchase_num` | Variabel som används i [Kundlojalitet](/help/components/dimensions/customer-loyalty.md) dimension. Antalet tidigare inköp som besökaren har gjort. <br>0: Inga tidigare inköp (inte en kund) <br>1: 1 tidigare inköp (ny kund) <br>2: 2 tidigare inköp (returkund) <br>3: 3 eller fler tidigare inköp (lojal kund) | int unsigned |
| `last_purchase_time_gmt` | Används i [Dagar sedan senaste köp](/help/components/dimensions/days-since-last-purchase.md) dimension. Tidsstämpel (i Unix-tid) för det senaste köpet. För förstagångsköp och besökare som inte har gjort något inköp tidigare är det här värdet `0`. | int |
| `latlon1` | Placering (ned till 10 km) | varchar(255) |
| `latlon23` | Plats (ned till 100 m) | varchar(255) |
| `latlon45` | Plats (ned till 1 m) | varchar(255) |
| `mc_audiences` | Lista med Audience Manager segment-ID som besökaren tillhör. The `post_mc_audiences` kolumnen ändrar avgränsaren till `--**--`. | text |
| `mcvisid` | Experience Cloud Visitor-ID. 128-bitars nummer som består av två sammanfogade 64-bitars tal som fyllts med 19 siffror. | varchar(255) |
| `mobile_id` | Om användaren använder en mobil enhet anger du enhetens numeriska ID. | int |
| `mobileaction` | Mobilåtgärd. Samlas in automatiskt när `trackAction` anropas i Mobiltjänster. Tillåter automatisk åtgärdspunkt i appen. | varchar(100) |
| `mobileappid` | ID för mobilapp. Lagrar programnamnet och versionen i följande format: `[AppName] [BundleVersion]` | varchar(255) |
| `mobileappperformanceappid` | Används i Apteligent-dataanslutningen. Program-ID som används i Apteligent. | varchar(255) |
| `mobileappperformancecrashid` | Används i Apteligent-dataanslutningen. Det krasch-ID som används i Apteligent. | varchar(255) |
| `mobileappstoreobjectid` | Används i Appfigurations dataanslutning. Objekt-ID för App Store. | varchar(255) |
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
| `mobiledeeplinkid` | Samlas in från kontextdatavariabeln `a.deeplink.id`. Används i förvärvsrapporter som en identifierare för länken för mobilförvärv. | varchar(255) |
| `mobiledevice` | Namn på mobil enhet. I iOS lagras den som en kommaavgränsad tvåsiffrig sträng. Det första numret representerar enhetsgenereringen och det andra representerar enhetsfamiljen. | varchar(255) |
| `mobilehourofday` | Definierar timmen på dagen då appen startades. Använder ett numeriskt format på 24 timmar. | varchar(255) |
| `mobileinstalldate` | Datum för mobilinstallation. Anger datumet för första gången en användare öppnar mobilappen. | varchar(255) |
| `mobilelaunchessincelastupgrade` | Samlas in från kontextdatavariabeln a.LaunchesSinceUpgrade. Rapporterar antalet starter sedan den senaste uppgraderingen. | varchar(255) |
| `mobilelaunchnumber` | Ökningar med ett varje gång mobilappen startas. | varchar(255) |
| `mobileltv` | Används inte längre. Fylls i av trackLifetimeValue-metoder. | varchar(255) |
| `mobilemessagebuttonname` | Samlas in från kontextdatavariabeln `a.message.button.id`. Används för meddelanden i appen för att identifiera knappen som stängde meddelandet. | varchar(100) |
| `mobilemessageid` | Meddelande-ID i appen | varchar(255) |
| `mobilemessageonline` | Meddelande i appen online | varchar(255) |
| `mobilemessagepushoptin` | Samlas in från kontextdatavariabeln `a.push.optin`. Ange som&quot;true&quot; när användaren väljer att skicka meddelanden; i annat fall är värdet &quot;false&quot;. | varchar(255) |
| `mobilemessagepushpayloadid` | Samlas in från kontextdatavariabeln `a.push.payloadid`. Används i push-meddelanden som nyttolast-ID. | varchar(255) |
| `mobileosenvironment` | Samlas in från kontextdatavariabeln `a.OSEnvironment`. Lägesmiljö, t.ex. Android eller iOS. | varchar(255) |
| `mobileosversion` | Mobiltjänstens operativsystemversion | varchar(255) |
| `mobileplaceaccuracy` | Samlas in från kontextdatavariabeln `a.loc.acc`. Anger GPS-noggrannheten i meter vid insamlingen. | varchar(255) |
| `mobileplacecategory` | Samlas in från kontextdatavariabeln `a.loc.category`. Beskriver kategorin för en viss plats. | varchar(255) |
| `mobileplaceid` | Samlas in från kontextdatavariabeln `a.loc.id`. Identifierare för en viss intressepunkt. | varchar(255) |
| `mobilerelaunchcampaigncontent` | Startinnehåll för mobiltjänster | varchar(255) |
| `mobilerelaunchcampaignmedium` | Startmedium för mobiltjänster | varchar(255) |
| `mobilerelaunchcampaignsource` | Startkälla för Mobile Services | varchar(255) |
| `mobilerelaunchcampaignterm` | Startperiod för Mobile Services | varchar(255) |
| `mobilerelaunchcampaigntrackingcode` | Samlas in från kontextdatavariabeln `a.launch.campaign.trackingcode`. Används i anskaffning som spårningskod för lanseringskampanj. | varchar(255) |
| `mobileresolution` | Upplösning för den mobila enheten. `[Width] x [Height]` i pixlar. | varchar(255) |
| `monthly_visitor` | Flagga som anger att besökaren är unik för den aktuella månaden. | tinyint unsigned |
| `mvvar1` - `mvvar3` | Lista variabelvärden. Innehåller en avgränsad lista med anpassade värden beroende på implementering. The `post_mvvar1` - `post_mvvar3` kolumner ersätter den ursprungliga avgränsaren med `--**--`. | text |
| `namespace` | Används inte. En del av en skrapad funktion. | varchar(50) |
| `new_visit` | Flagga som avgör om den aktuella träffen är ett nytt besök. Anges av Adobe-servrar efter 30 minuters besöksinaktivitet. | tinyint unsigned |
| `os` | Numeriskt ID som representerar besökarens operativsystem. Baserat på `user_agent` kolumn. Användningsområden `os` sökning. | int unsigned |
| `p_plugins` | Används inte längre. Lista över plugin-program som är tillgängliga för webbläsaren. Använda JavaScript-funktionen `navigator.plugins()`. | text |
| `page_event` | Den typ av träff som skickas i bildbegäran (standardträff, nedladdningslänk, anpassad länk, slutlänk). Se [Sökning efter sidhändelse](datafeeds-page-event.md). | tinyint unsigned |
| `page_event_var1` | Används endast vid förfrågningar om länkspårningsbilder. URL-adressen till den nedladdningslänk, den avslutningslänk eller anpassade länk som du klickat på. | text |
| `page_event_var2` | Används endast vid förfrågningar om länkspårningsbilder. Länkens anpassade namn (om det anges). | varchar(100) |
| `page_event_var3` | Används inte längre. Behållna data från undersökningen och mediemodulen. Fyllda gamla videorapporter i tidigare versioner av Adobe Analytics. | text |
| `page_type` | Används för att fylla i [Sidorna hittades inte](/help/components/dimensions/pages-not-found.md) dimension. Används endast för 404 sidor. Variabeln ska antingen vara tom eller innehålla värdet `ErrorPage`. | char(20) |
| `page_url` | URL:en för träffen. Observera att `post_page_url` tas bort för förfrågningar om länkspårningsbilder och använder datatypen varchar(255). | text |
| `pagename` | Används för att fylla i [Sida](/help/components/dimensions/page.md) dimension. Om [`pagename`](/help/implement/vars/page-vars/pagename.md) variabeln är tom, Analytics använder `page_url` i stället. | varchar(100) |
| `paid_search` | Flagga som anges om träffen matchar betald sökningsidentifiering. | tinyint unsigned |
| `partner_plugins` | Används inte. En del av en skrapad funktion. | varchar(255) |
| `persistent_cookie` | Används i [Stöd för permanenta cookies](/help/components/dimensions/persistent-cookie-support.md) dimension. Anger om besökaren stöder cookies som inte tas bort efter varje träff. | char(1) |
| `plugins` | Används inte längre. Lista med numeriska ID:n som motsvarar plugin-program som är tillgängliga i webbläsaren. Användningsområden `plugins.tsv` sökning. | varchar(180) |
| `pointofinterest` | Intressepunktsnamn för mobiltjänster | varchar(255) |
| `pointofinterestdistance` | Avstånd för mobiltjänster till intressanta center | varchar(255) |
| `post_` kolumner | Innehåller värdet som används i rapporterna. Varje inläggskolumn fylls i efter serversidans logik, bearbetningsregler och VISTA-regler. Adobe rekommenderar att du i de flesta fall använder inläggskolumner. | Se respektive icke-postkolumn |
| `prev_page` | Används inte. Adobe-unik identifierare för föregående sida. | int unsigned |
| `product_list` | Produktlistan har skickats in via [`products`](/help/implement/vars/page-vars/products.md) variabel. Produkterna avgränsas med kommatecken medan de enskilda produktegenskaperna avgränsas med semikolon. | text |
| `product_merchandising` | Används inte. Använd `product_list` i stället. | text |
| `prop1` - `prop75` | Anpassade trafikvariabler 1-75. Används i [Prop](/help/components/dimensions/prop.md) dimensioner. | varchar(100) |
| `purchaseid` | Unik identifierare för ett köp, enligt inställningen med [`purchaseID`](/help/implement/vars/page-vars/purchaseid.md) variabel. Används av `duplicate_purchase` kolumn. | char(20) |
| `quarterly_visitor` | Flagga som avgör om träffen är en ny kvartalsbesökare. | tinyint unsigned |
| `ref_domain` | Baserat på referenskolumnen. Den refererande domänen för träffen. Används i [Refererande domän](/help/components/dimensions/referring-domain.md) dimension. | varchar(100) |
| `ref_type` | Ett numeriskt ID som representerar typen av referens för träffen. Används i [Referenstyp](/help/components/dimensions/referrer-type.md) dimension. <br>1: Inuti din webbplats<br>2: Andra webbplatser <br>3: Sökmotorer <br>4: Hårddisk <br>5: USENET <br>6: Typed/Bookmarked (ingen referent) <br>7: E-post <br>8: Inget JavaScript <br>9: Sociala nätverk | tinyint unsigned |
| `referrer` | Föregående sidas URL. Används i [Referent](/help/components/dimensions/referrer.md) dimension. Observera att `referrer` använder datatypen varchar(255), `post_referrer` använder datatypen varchar(244). | varchar(255) |
| `resolution` | Numeriskt ID som representerar bildskärmens upplösning. Används i [Bildskärmsupplösning](/help/components/dimensions/monitor-resolution.md) dimension. Användningsområden `resolution.tsv` uppslagstabell. | smallint unsigned |
| `s_kwcid` | Nyckelord-ID som används i Adobe Advertising Cloud-integreringar. | varchar(255) |
| `s_resolution` | Upplösningsvärde för råformat. Samlas in med JavaScript-funktionen `screen.width x screen.height`. | char(20) |
| `search_engine` | Numeriskt ID som representerar sökmotorn som refererade besökaren till webbplatsen. Användningsområden `search_engines.tsv` sökning. | smallint unsigned |
| `search_page_num` | Används av [Alla söksidrankning](/help/components/dimensions/all-search-page-rank.md) dimension. Anger vilken sida av sökresultat din webbplats hade innan användaren klickade igenom till din webbplats. | smallint unsigned |
| `secondary_hit` | Flagga som spårar sekundära träffar. Ursprungligen kommer taggar för flera programsviter och VISTA-regler som kopierar träffar. | tinyint unsigned |
| `service` | Används inte. Använd `page_event` i stället. | char(2) |
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
| `stats_server` | Inte till användning. Adobe intern server som bearbetade träffen. | char(30) |
| `t_time_info` | Lokal tid för besökaren. Formatet är: `M/D/YYYY HH:MM:SS Month (0-11, 0=January) Timezone offset (in minutes)` | varchar(100) |
| `tnt` | Används i Adobe Target integreringar. Representerar alla tester som är kvalificerade för tillfället. Formatet är: `TargetCampaignID:TargetRecipeID:TargetType|Event/Action`. | text |
| `tnt_action` | Används i Adobe Target integreringar. Representerar alla tester som träffen är kvalificerad för. | text |
| `tnt_post_vista` | Används inte längre. Använd `post_tnt` i stället. | text |
| `transactionid` | En unik identifierare där olika datapunkter kan överföras senare via datakällor. Samlas med [`transactionID`](/help/implement/vars/page-vars/transactionid.md) variabel. | text |
| `truncated_hit` | En flagga som anger att bildbegäran har trunkerats. Anger att en partiell träff togs emot. <br>Y: Träet trunkerades. partiell träff mottagen <br>N: Träet trunkerades inte. fullständig träff mottagen | char(1) |
| `ua_color` | Används inte längre. Används tidigare som reserv för färgdjup. | char(20) |
| `ua_os` | Används inte längre. Används tidigare som reserv för operativsystemet. | char(80) |
| `ua_pixels` | Används inte längre. Används tidigare som reserv för webbläsarens höjd och bredd. | char(20) |
| `user_agent` | Användaragentsträng som skickas i HTTP-huvudet i bildbegäran. | text |
| `user_hash` | Inte till användning. Hash för rapportens Suite-ID. Använd `username` i stället. | int unsigned |
| `user_server` | Används i [Server](/help/components/dimensions/server.md) dimension. | varchar(100) |
| `userid` | Inte till användning. Det numeriska ID:t för rapportsvitens ID. Använd `username` i stället. | int unsigned |
| `username` | Rapportsvitens ID för träffen. | char(40) |
| `va_closer_detail` | Variabel som används i [Senaste beröringsdetalj](/help/components/dimensions/last-touch-detail.md) dimension. | varchar(255) |
| `va_closer_id` | Numeriskt ID som identifierar [Senaste pekkanal](/help/components/dimensions/last-touch-channel.md) dimension. En sökning efter detta ID finns i Marketing Channel Manager. | tinyint unsigned |
| `va_finder_detail` | Variabel som används i [Första beröringsdetalj](/help/components/dimensions/first-touch-detail.md) dimension. | varchar(255) |
| `va_finder_id` | Numeriskt ID som identifierar [Första beröringskanalen](/help/components/dimensions/first-touch-channel.md) dimension. En sökning efter detta ID finns i Marketing Channel Manager. | tinyint unsigned |
| `va_instance_event` | Flagga som identifierar marknadsföringskanal [Instanser](/help/components/metrics/instances.md). | tinyint unsigned |
| `va_new_engagement` | Flagga som identifierar marknadsföringskanal [Nya åtaganden](/help/components/metrics/new-engagements.md). | tinyint unsigned |
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
| `visid_high` | Används i kombination med `visid_low` för att unikt identifiera en besökare. | bigint unsigned |
| `visid_low` | Används i kombination med `visid_high` för att unikt identifiera en besökare. | bigint unsigned |
| `visid_new` | Flagga som identifierar om träffen innehåller ett nyligen genererat besökar-ID. | char(1) |
| `visid_timestamp` | Om besökar-ID nyligen genererades, anger tidsstämpeln (i Unix-tid) för när besökar-ID genererades. | int |
| `visid_type` | Ej för extern användning. som används internt av Adobe för att bearbeta optimeringar. Numeriskt ID som representerar den metod som används för att identifiera besökaren.<br>0: Anpassat besökar-ID eller Okänt/ej tillämpligt<br>1: Återställning av IP och användaragent <br>2: HTTP Mobile Subscriber Header <br>3: Äldre cookie-värde (`s_vi`) <br>4: Reservcookie-värde (`s_fid`) <br>5: Identitetstjänst | tinyint unsigned |
| `visit_keywords` | Variabel som används i [Söknyckelord](/help/components/dimensions/search-keyword.md) dimension. I den här kolumnen används en icke-standard teckengräns på varchar(244) för att rymma den serverlogik som används av Adobe. | varchar(244) |
| `visit_num` | Variabel som används i [Besöksnummer](/help/components/dimensions/visit-number.md) dimension. Börjar vid 1 och ökar stegvis varje gång ett nytt besök påbörjas per besökare. | int unsigned |
| `visit_page_num` | Variabel som används i [Träffdjup](/help/components/dimensions/hit-depth.md) dimension. Ökar med 1 för varje träff som användaren skapar. Återställer varje besök. | int unsigned |
| `visit_ref_domain` | Baserat på `visit_referrer` kolumn. Den första refererande domänen för besöket. | varchar(100) |
| `visit_ref_type` | Numeriskt ID som representerar referenstypen för besökets första referent. Använder `referrer_type.tsv` uppslagstabell. | tinyint unsigned |
| `visit_referrer` | Den första referenten till besöket. | varchar(255) |
| `visit_search_engine` | Numeriskt ID för besökets första sökmotor. Användningsområden `search_engines.tsv` sökning. | smallint unsigned |
| `visit_start_page_url` | Besökets första URL. | varchar(255) |
| `visit_start_pagename` | Värdet för Sidnamn i den första träffen av besöket. | varchar(100) |
| `visit_start_time_gmt` | Tidsstämpel (i Unix-tid) för besökets första träff. | int |
| `weekly_visitor` | Flagga som avgör om träffen är en ny besökare varje vecka. | tinyint unsigned |
| `yearly_visitor` | Flagga som avgör om träffen är en ny årlig besökare. | tinyint unsigned |
| `zip` | Fyller i [Postnummer](/help/components/dimensions/zip-code.md) dimension. Se även `geo_zip`. | varchar(50) |

## Tomma kolumner

Följande kolumnlista används inte och innehåller inga data:

* `mobileacquisitionclicks`
* `mobileactioninapptime`
* `mobileactiontotaltime`
* `mobileappperformanceaffectedusers`
* `mobileappperformanceappid.app-perf-app-name`
* `mobileappperformanceappid.app-perf-platform`
* `mobileappperformancecrashes`
* `mobileappperformancecrashid.app-perf-crash-name`
* `mobileappperformanceloads`
* `mobileappstoreavgrating`
* `mobileappstoredownloads`
* `mobileappstoreinapprevenue`
* `mobileappstoreinapproyalties`
* `mobileappstoreobjectid.app-store-user`
* `mobileappstoreobjectid.application-name`
* `mobileappstoreobjectid.application-version`
* `mobileappstoreobjectid.appstore-name`
* `mobileappstoreobjectid.category-name`
* `mobileappstoreobjectid.country-name`
* `mobileappstoreobjectid.device-manufacturer`
* `mobileappstoreobjectid.device-name`
* `mobileappstoreobjectid.in-app-name`
* `mobileappstoreobjectid.platform-name-version`
* `mobileappstoreobjectid.rank-category-type`
* `mobileappstoreobjectid.region-name`
* `mobileappstoreobjectid.review-comment`
* `mobileappstoreobjectid.review-title`
* `mobileappstoreoneoffrevenue`
* `mobileappstoreoneoffroyalties`
* `mobileappstorepurchases`
* `mobileappstorerank`
* `mobileappstorerankdivisor`
* `mobileappstorerating`
* `mobileappstoreratingdivisor`
* `mobileavgprevsessionlength`
* `mobilecrashes`
* `mobilecrashrate`
* `mobiledailyengagedusers`
* `mobiledeeplinkid.name`
* `mobileinstalls`
* `mobilelaunches`
* `mobileltvtotal`
* `mobilemessageclicks`
* `mobilemessageid.dest`
* `mobilemessageid.name`
* `mobilemessageid.type`
* `mobilemessageimpressions`
* `mobilemessagepushpayloadid.name`
* `mobilemessageviews`
* `mobilemonthlyengagedusers`
* `mobileplacedwelltime`
* `mobileplaceentry`
* `mobileplaceexit`
* `mobileprevsessionlength`
* `mobilerelaunchcampaigntrackingcode.name`
* `mobileupgrades`
* `socialaveragesentiment`
* `socialaveragesentiment (deprecated)`
* `socialfbstories`
* `socialfbstorytellers`
* `socialinteractioncount`
* `sociallikeadds`
* `sociallink`
* `sociallink (deprecated)`
* `socialmentions`
* `socialpageviews`
* `socialpostviews`
* `socialproperty`
* `socialproperty (deprecated)`
* `socialpubcomments`
* `socialpubposts`
* `socialpubrecommends`
* `socialpubsubscribers`
* `socialterm`
* `socialtermslist`
* `socialtermslist (deprecated)`
* `socialtotalsentiment`
* `sourceid`
* `videoauthorized`
* `videoaverageminuteaudience`
* `videochaptercomplete`
* `videochapterstart`
* `videochaptertime`
* `videopause`
* `videopausecount`
* `videopausetime`
* `videoplay`
* `videoprogress10`
* `videoprogress25`
* `videoprogress50`
* `videoprogress75`
* `videoprogress96`
* `videoqoebitrateaverage`
* `videoqoebitratechange`
* `videoqoebuffer`
* `videoqoedropbeforestart`
* `videoqoedroppedframes`
* `videoqoeerror`
* `videoresume`
* `videototaltime`
* `videouniquetimeplayed`
