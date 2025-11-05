---
description: Tabelldata som beskriver kolumnerna i dataflödet.
keywords: Datafeed;kolumner
subtopic: data feeds
title: Referens för datakolumn
feature: Data Feeds
exl-id: e1492147-6e7f-4921-b509-898e7efda596
source-git-commit: 8866608bc6d4e31c876c08894a90bfb982a7d19e
workflow-type: tm+mt
source-wordcount: '3670'
ht-degree: 0%

---

# Referens för datakolumn

Använd den här sidan om du vill veta vilka data som finns i varje kolumn. De flesta implementeringar använder inte alla kolumner, så den här sidan kan refereras när du avgör vilka kolumner som ska inkluderas i en datafeedexport.

>[!IMPORTANT]
>
>För en given kolumn (till exempel en kolumn som är definierad som 255 tecken) kan ytterligare tecken skickas i en datafeed på grund av att tecken som undgår värden läggs till i en sträng. Tänk på dessa potentiella extra tecken om implementeringen regelbundet skickar värden som överskrider teckengränserna.

## Kolumner, beskrivningar och datatyper

>[!NOTE]
>
>De flesta kolumner innehåller en liknande kolumn med prefixet `post_`. Bokför kolumner innehåller värden efter serversidans logik, bearbetningsregler och VISTA-regler. Adobe rekommenderar att du i de flesta fall använder inläggskolumner. Mer information finns i [Vanliga frågor om dataflöden](../df-faq.md).

Tidigare uppdateringar av den här tabellen finns på den här sidans [implementeringshistorik på GitHub](https://github.com/AdobeDocs/analytics.en/commits/main/help/export/analytics-data-feed/c-df-contents/datafeeds-reference.md).

| Kolumnnamn | Kolumnbeskrivning | Datatyp |
| --- | --- | --- |
| **`accept_language`** | Visar alla godkända språk enligt HTTP-huvudet Accept-Language i en bildbegäran. | char(20) |
| **`adload`** | Inläsningar av mediaannonser | varchar(255) |
| **`aemassetid`** | En variabel med flera värden som motsvarar tillgångs-ID:n (GUID) för en uppsättning Adobe Experience Manager Assets. Ökar imponeringshändelser. | text |
| **`aemassetsource`** | Identifierar resurshändelsens källa. Används i Adobe Experience Manager. | varchar(255) |
| **`aemclickedassetid`** | Tillgångs-ID för en Adobe Experience Manager-resurs. Ökningar Klicka på händelser. | varchar(255) |
| **`browser`** | Ett numeriskt ID som representerar webbläsaren. Refererar till `browser.tsv`-söktabellen. | int unsigned |
| **`browser_height`** | Dimensionen [Webbläsarhöjd](/help/components/dimensions/browser-height.md). | smallint unsigned |
| **`browser_width`** | Bredd på [webbläsaren](/help/components/dimensions/browser-width.md) | smallint unsigned |
| **`c_color`** | Färgpalettens bitdjup. Används som en del av beräkningen av dimensionen [Färgdjup](/help/components/dimensions/color-depth.md). AppMeasurement använder JavaScript-funktionen `screen.colorDepth()`. | char(20) |
| **`campaign`** | Dimensionen [Spårningskod](/help/components/dimensions/tracking-code.md). | varchar(255) |
| **`carrier`** | Adobe Advertising integrationsvariabel. Anger mobiloperatör. Nyckelvärdet för `carrier.tsv` [dynamisk sökning](dynamic-lookups.md). | varchar(100) |
| **`ch_hdr`** | Klienttips som samlats in via HTTP-begärandehuvudet. | text |
| **`ch_js`** | Klienttips som samlats in via JavaScript-API:t för användaragenttips för klienttips. | text |
| **`channel`** | Dimensionen [Webbplatsavsnitt](/help/components/dimensions/site-section.md). | varchar(100) |
| **`clickmaplink`** | Länk till Activity Map | varchar(255) |
| **`clickmaplinkbyregion`** | Activity Map link by region | varchar(255) |
| **`clickmappage`** | Activity Map page | varchar(255) |
| **`clickmapregion`** | Activity Map | varchar(255) |
| **`code_ver`** | API- eller klient-SDK-version som används för att kompilera och skicka bildbegäran. | char(16) |
| **`color`** | Färgdjup-ID baserat på värdet för kolumnen `c_color`. Refererar till `color_depth.tsv`-söktabellen. | smallint unsigned |
| **`connection_type`** | Ett numeriskt ID som representerar anslutningstypen. Dimensionen [Anslutningstyp](/help/components/dimensions/connection-type.md). Refererar till `connection_type.tsv`-söktabellen. | tinyint unsigned |
| **`cookies`** | Dimensionen [Cookie stöder](/help/components/dimensions/cookie-support.md).<br>Y: Aktiverad<br>N: Inaktiverad<br>U: Okänd | char(1) |
| **`country`** | Ett numeriskt ID som representerar besökarens land. Refererar till `country.tsv`-söktabellen. | smallint unsigned |
| **`ct_connect_type`** | Relaterat till kolumnen `connection_type`. De vanligaste värdena är LAN/Wifi, mobiloperatör och modem. | char(20) |
| **`curr_factor`** | Bestämmer valutadecimalen och används för valutakonvertering. USD använder till exempel två decimaler, så det här kolumnvärdet blir `2`. | tinyint |
| **`curr_rate`** | Växelkursen när transaktionen inträffade. Adobe samarbetar med XE för att fastställa dagens växelkurs. | decimal(24,12) |
| **`currency`** | Valutakoden som användes under transaktionen. Ange med [`currencyCode`](/help/implement/vars/config-vars/currencycode.md). | char(8) |
| **`cust_hit_time_gmt`** | Endast tidsstämpelaktiverade rapportsviter. Tidsstämpeln som skickades med träffen, baserat på UNIX®-tid. | int |
| **`cust_visid`** | Det anpassade besökar-ID:t, om [`visitorID`](/help/implement/vars/config-vars/visitorid.md) används. | varchar(255) |
| **`customer_perspective`** | Avgör om träffen är en mobilbakgrundträff. Mer information finns i [Kontextmedvetna sessioner](/help/components/vrs/vrs-mobile-visit-processing.md). | tinyint unsigned |
| **`daily_visitor`** | En flagga som avgör om träffen är en ny daglig besökare. | tinyint unsigned |
| **`dataprivacyconsentoptin`** | Dimensionen [Medgivandehanteringsanmälan](/help/components/dimensions/cm-opt-in.md). Flera värden kan finnas per träff, avgränsade med ett rör (`\|`). Giltiga värden är `DMP` och `SELL`. | varchar(100) |
| **`dataprivacyconsentoptout`** | Dimensionen [Medgivandehanteringsavanmälan](/help/components/dimensions/cm-opt-out.md). Flera värden kan finnas per träff, avgränsade med ett rör (`\|`). Giltiga värden är `SSF`, `DMP` och `SELL`. | varchar(100) |
| **`dataprivacydmaconsent`** | Ett värde som identifierar om samtycke inhämtas för att skicka data från Adobe Analytics via Adobe Advertising till tredjepartsleverantörer av annonser (som Google). Mer information finns i [Lägg till samtycke](/help/components/dimensions/ad-consent.md). | varchar(100) |
| **`date_time`** | Tidpunkten för träffen i läsbart format, baserat på rapportsvitens tidszon. | datetime |
| **`domain`** | Dimensionen [Domain](/help/components/dimensions/domain.md). Baserat på besökarens Internetanslutningspunkt. | varchar(100) |
| **`duplicate_events`** | Listar varje händelse som räknats som en dubblett. | varchar(255) |
| **`duplicate_purchase`** | En flagga som avgör om köphändelsen för den här träffen ignoreras eftersom den är en dubblett. | tinyint unsigned |
| **`duplicated_from`** | Används endast i rapportsviter som innehåller VISTA-regler för träffkopior. Anger vilken rapportsvit som träffen kopierades från. | varchar(40) |
| **`ef_id`** | `ef_id` som används i Adobe Advertising-integreringar. | varchar(255) |
| **`evar1 - evar250`** | Egna variabler 1-250. Används i måtten [eVar](/help/components/dimensions/evar.md). Varje organisation använder eVars på olika sätt. Det bästa stället för mer information om hur din organisation fyller i respektive eVars är ett [lösningsdesigndokument](/help/implement/prepare/solution-design.md) som är specifikt för din organisation. | varchar(255) |
| **`event_list`** | Kommaavgränsad lista med numeriska ID:n som representerar händelser som utlöses vid träffen. Innehåller både standardhändelser och [anpassade händelser 1-1000](/help/components/metrics/custom-events.md). Använder `event.tsv`-sökning. | text |
| **`exclude_hit`** | En flagga som avgör om träffen utesluts från rapportering. Kolumnen `visit_num` ökas inte för uteslutna träffar.<br>1: Används inte. En del av en skrapad funktion.<br>2: Används inte. En del av en skrapad funktion.<br>3: Används inte längre. Undantag för användaragent<br>4: Undantag baserat på IP-adress<br>5: Information om träffar saknas, t.ex. `page_url`, `pagename`, `page_event` eller `event_list`<br>6: JavaScript bearbetade inte korrekt träffen<br>7: Kontospecifikt undantag, t.ex. i VISTA-regler<br>8: Används inte. Alternativt kontospecifikt undantag.<br>9: Används inte. En del av en skrapad funktion.<br>10: Ogiltig valutakod<br>11: Träff saknar en tidsstämpel i en rapportsvit som bara innehåller tidsstämplar, eller en träff innehöll en tidsstämpel i en rapportsvit som inte är en tidsstämpel.<br>12: Används inte. En del av en skrapad funktion.<br>13: Används inte. En del av en skrapad funktion.<br>14: Målträff som inte matchar en Analytics-träff<br>15: Används inte just nu.<br>16: Advertising Cloud-träff som inte matchar en Analytics-träff | tinyint unsigned |
| **`first_hit_page_url`** | Besökarens allra första URL. | varchar(255) |
| **`first_hit_pagename`** | Den ursprungliga dimensionen för [startsidan](/help/components/dimensions/entry-dimensions.md). Besökarens ursprungliga startsidnamn. | varchar(100) |
| **`first_hit_ref_domain`** | Den [ursprungliga refererande domänen](/help/components/dimensions/original-referring-domain.md)-dimensionen. Baserat på `first_hit_referrer`. Den första refererande domänen för besökaren. | varchar(100) |
| **`first_hit_ref_type`** | Ett numeriskt ID som representerar referenstypen för besökarens första referent. Refererar till `referrer_type.tsv`-söktabellen. | tinyint unsigned |
| **`first_hit_referrer`** | Den första refererande URL:en för besökaren. | varchar(255) |
| **`first_hit_time_gmt`** | Tidsstämpel för besökarens första träff i UNIX®-tid. | int |
| **`geo_city`** | Namnet på den stad som träffen kom från, baserat på IP. Används i dimensionen [Städer](/help/components/dimensions/cities.md). | char(32) |
| **`geo_country`** | Förkortningen för det land som träffen kom från, baserat på IP. Används i dimensionen [Länder](/help/components/dimensions/countries.md). | char(4) |
| **`geo_dma`** | Ett numeriskt ID för det demografiska område som träffen kom från, baserat på IP. Används i [US DMA](/help/components/dimensions/us-dma.md)-dimensionen. | int unsigned |
| **`geo_region`** | Namnet på den stat eller region som träffen kom från, baserat på IP. Används i dimensionen [Områden](/help/components/dimensions/regions.md). | char(32) |
| **`geo_zip`** | Postnumret som träffen kom från, baserat på IP. Hjälper till att fylla i dimensionen [Postnummer](/help/components/dimensions/zip-code.md). Se även `zip`. | varchar(16) |
| **`hit_source`** | Källan som träffen kom från. Träffkällor 1, 2 och 6 faktureras. <br>1: Standardbildbegäran utan tidsstämpel <br> <br>: Standardbildbegäran med tidsstämpel <br> <br> 3: Överföring av livdatakälla med tidsstämplar 5: Överföring av generisk datakälla <br>6: Överföring av datakälla med fullständig bearbetning <br>7: Överföring av TransactionID-datakälla <br>8: Används inte längre; tidigare versioner av Adobe Advertising Cloud-data Källor <br>9: Används inte längre, Adobe Social-sammanfattningsmått <br> : Audience Manager serversidans vidarebefordran används | tinyint unsigned |
| **`hit_time_gmt`** | Tidsstämpeln för Adobe datainsamlingsservrar tog emot träffen, baserat på UNIX®-tid. | int |
| **`hitid_high`** | Används med `hitid_low` för att identifiera en träff. | bigint unsigned |
| **`hitid_low`** | Används med `hitid_high` för att identifiera en träff. | bigint unsigned |
| **`hourly_visitor`** | En flagga som avgör om träffen är en ny timbesökare. | tinyint unsigned |
| **`ip`** | IPv4-adressen, baserad på HTTP-huvudet i bildbegäran. Mutuellt exklusiv för `ipv6`. Om den här kolumnen innehåller en icke-konfidentiell IP-adress är `ipv6` tom. | char(20) |
| **`ipv6`** | Den komprimerade IPv6-adressen, om den är tillgänglig. Mutuellt exklusiv för `ip`. Om den här kolumnen innehåller en icke-konfidentiell IP-adress är `ip` tom. | varchar(40) |
| **`j_jscript`** | Den version av JavaScript som stöds av webbläsaren. | char(5) |
| **`java_enabled`** | [[!UICONTROL Java enabled]](/help/components/dimensions/java-enabled.md). <br>Y: Aktiverad <br>N: Inaktiverad <br>U: Okänd | char(1) |
| **`javascript`** | Ett söknings-ID för JavaScript-version, baserat på `j_jscript`. Refererar till `javascript_version`-söktabellen. | tinyint unsigned |
| **`language`** | Ett numeriskt ID som representerar besökarens språk. Refererar till `languages.tsv`-söktabellen. | smallint unsigned |
| **`last_hit_time_gmt`** | Tidsstämpel (i UNIX®-tid) för föregående träff. Används för att beräkna dimensionen [[!UICONTROL Days since last visit]](/help/components/dimensions/days-since-last-visit.md). | int |
| **`last_purchase_num`** | Dimensionen [Kundlojalitet](/help/components/dimensions/customer-loyalty.md). Antalet tidigare inköp som besökaren har gjort. <br>0: Inga tidigare inköp (inte en kund) <br>1: 1 tidigare inköp (ny kund) <br>2: 2 tidigare inköp (returkund) <br>3: 3 eller fler tidigare inköp (lojal kund) | int unsigned |
| **`last_purchase_time_gmt`** | Används i dimensionen [[!UICONTROL Days since last purchase]](/help/components/dimensions/days-since-last-purchase.md). Tidsstämpel (i UNIX®-tid) för det senaste köpet. För förstagångsköp och besökare som inte har gjort något inköp tidigare är det här värdet `0`. | int |
| **`latlon1`** | Placering (ned till 10 km) | varchar(255) |
| **`latlon23`** | Plats (ned till 100 m) | varchar(255) |
| **`latlon45`** | Plats (ned till 1 m) | varchar(255) |
| **`mc_audiences`** | Lista med Audience Manager segment-ID:n som besökaren tillhör. Kolumnen `post_mc_audiences` ändrar avgränsaren till `--**--`. | text |
| **`mcvisid`** | Experience Cloud Visitor-ID. 128-bitars nummer som består av två sammanfogade 64-bitars tal som fyllts med 19 siffror. | varchar(255) |
| **`mobile_id`** | Om användaren använder en mobil enhet anger du enhetens numeriska ID. Nyckelvärdet för `mobile_attributes.tsv` [dynamisk sökning](dynamic-lookups.md). | int |
| **`mobileaction`** | Mobilåtgärd. Samlas in automatiskt när `trackAction` anropas i mobilimplementeringar. Tillåter automatisk åtgärdspunkt i appen. | varchar(100) |
| **`mobileappid`** | ID för mobilapp. Lagrar programnamnet och versionen i följande format: `[AppName] [BundleVersion]` | varchar(255) |
| **`mobileappperformanceappid`** | Används i Apteligent-dataanslutningen. Program-ID som används i Apteligent. | varchar(255) |
| **`mobileappperformancecrashid`** | Används i Apteligent-dataanslutningen. Det krasch-ID som används i Apteligent. | varchar(255) |
| **`mobileappstoreobjectid`** | Används i dataanslutningen [!DNL Appfigures]. Objekt-ID för App Store. | varchar(255) |
| **`mobilebeaconmajor`** | Mobiltjänster är viktiga | varchar(100) |
| **`mobilebeaconminor`** | Mobiltjänster är mindre | varchar(100) |
| **`mobilebeaconproximity`** | Avstånd för mobiltjänster | varchar(255) |
| **`mobilebeaconuuid`** | Beacon UUID för mobiltjänster | varchar(100) |
| **`mobilecampaigncontent`** | Namnet eller ID för innehållet som visade länken. Fylls i av Anskaffning av mobilapp. | varchar(255) |
| **`mobilecampaignmedium`** | Marknadsföringsmedium, som banner eller e-post. Fylls i av Anskaffning av mobilapp. | varchar(255) |
| **`mobilecampaignname`** | Namnet på kampanjen, som också lagras i kampanjvariabeln. Fylls i av Anskaffning av mobilapp. | varchar(255) |
| **`mobilecampaignsource`** | Ursprunglig hänvisare, t.ex. nyhetsbrev eller sociala medier. Fylls i av Anskaffning av mobilapp. | varchar(255) |
| **`mobilecampaignterm`** | Betalnyckelord eller andra termer som du vill spåra med förvärvet. Fylls i av Anskaffning av mobilapp. | varchar(255) |
| **`mobiledayofweek`** | Nummer på den veckodag då appen startades. | varchar(255) |
| **`mobiledayssincefirstuse`** | Antal dagar sedan appen kördes för första gången. | varchar(255) |
| **`mobiledayssincelastuse`** | Antal dagar sedan appen senast kördes. | varchar(255) |
| **`mobiledeeplinkid`** | Samlades in från kontextdatavariabeln `a.deeplink.id`. Används i förvärvsrapporter som en identifierare för länken för mobilförvärv. | varchar(255) |
| **`mobiledevice`** | Namn på mobil enhet. I iOS lagras den som en kommaavgränsad tvåsiffrig sträng. Det första numret representerar enhetsgenereringen och det andra representerar enhetsfamiljen. | varchar(255) |
| **`mobilehourofday`** | Definierar timmen på dagen då appen startades. Använder ett numeriskt format på 24 timmar. | varchar(255) |
| **`mobileinstalldate`** | Datum för mobilinstallation. Anger datumet för första gången som en användare öppnar mobilappen. | varchar(255) |
| **`mobilelaunchnumber`** | Ökningar med ett varje gång mobilappen startas. | varchar(255) |
| **`mobilemessagebuttonname`** | Samlades in från kontextdatavariabeln `a.message.button.id`. Används för meddelanden i appen för att identifiera knappen som stängde meddelandet. | varchar(100) |
| **`mobilemessageid`** | Meddelande-ID i appen | varchar(255) |
| **`mobilemessageonline`** | Meddelande i appen online | varchar(255) |
| **`mobilemessagepushoptin`** | Samlades in från kontextdatavariabeln `a.push.optin`. Ange som&quot;true&quot; när användaren väljer att skicka meddelanden, annars är värdet&quot;false&quot;. | varchar(255) |
| **`mobilemessagepushpayloadid`** | Samlades in från kontextdatavariabeln `a.push.payloadid`. Används i push-meddelanden som nyttolast-ID. | varchar(255) |
| **`mobileosversion`** | Mobiltjänstens operativsystemversion | varchar(255) |
| **`mobileplaceaccuracy`** | Samlades in från kontextdatavariabeln `a.loc.acc`. Anger GPS-noggrannheten i meter vid insamlingen. | varchar(255) |
| **`mobileplacecategory`** | Samlades in från kontextdatavariabeln `a.loc.category`. Beskriver kategorin för en viss plats. | varchar(255) |
| **`mobileplaceid`** | Samlades in från kontextdatavariabeln `a.loc.id`. Identifierare för en viss intressepunkt. | varchar(255) |
| **`mobilepushoptin`** | Push-deltagande för mobiltjänster | varchar(255) |
| **`mobilepushpayloadid`** | Push-nyttolast-ID för mobiltjänster | varchar(255) |
| **`mobilerelaunchcampaigncontent`** | Startinnehåll för mobiltjänster | varchar(255) |
| **`mobilerelaunchcampaignmedium`** | Startmedium för mobiltjänster | varchar(255) |
| **`mobilerelaunchcampaignsource`** | Startkälla för Mobile Services | varchar(255) |
| **`mobilerelaunchcampaignterm`** | Startperiod för Mobile Services | varchar(255) |
| **`mobilerelaunchcampaigntrackingcode`** | Samlades in från kontextdatavariabeln `a.launch.campaign.trackingcode`. Används i anskaffning som spårningskod för lanseringskampanj. | varchar(255) |
| **`mobileresolution`** | Den mobila enhetens upplösning. `[Width] x [Height]` i pixlar. | varchar(255) |
| **`monthly_visitor`** | En flagga som avgör om besökaren är unik för den aktuella månaden. | tinyint unsigned |
| **`mvvar1`** - `mvvar3` | [Listvariabelvärden](/help/implement/vars/page-vars/list.md). Innehåller en avgränsad lista med anpassade värden beroende på implementering. Kolumnerna `post_mvvar1` - `post_mvvar3` ersätter den ursprungliga avgränsaren med `--**--`. | text |
| **`mvvar1_instances`** - `mvvar3_instances` | Listvariabelvärdena som angavs för den aktuella träffen. Ersätter den ursprungliga avgränsaren med `--**--`. Kolumnerna `post` innehåller vanligtvis inga data. | text |
| **`new_visit`** | En flagga som avgör om den aktuella träffen är ett nytt besök. Anges av Adobe efter 30 minuters inaktivitet. | tinyint unsigned |
| **`os`** | Ett numeriskt ID som representerar besökarens operativsystem. Baserat på kolumnen `user_agent`. Nyckelvärdet för `operating_system.tsv` standardsökning och `operating_system_type.tsv` [dynamisk sökning](dynamic-lookups.md). | int unsigned |
| **`page_event`** | Den typ av träff som skickas i bildbegäran (standardträff, nedladdningslänk, anpassad länk, slutlänk). Se [Sökning efter sidhändelser](datafeeds-page-event.md). | tinyint unsigned |
| **`page_event_var1`** | Används endast vid förfrågningar om länkspårningsbilder. URL-adressen till den nedladdningslänk, den avslutningslänk eller anpassade länk som du klickar på. | text |
| **`page_event_var2`** | Används endast vid förfrågningar om länkspårningsbilder. Länkens anpassade namn (om det anges). Anger den [anpassade länken](/help/components/dimensions/custom-link.md), [Hämta länken](/help/components/dimensions/download-link.md) eller [Avsluta länken](/help/components/dimensions/exit-link.md) beroende på värdet i `page_event`. | varchar(100) |
| **`page_type`** | Dimensionen [Sidorna hittades inte](/help/components/dimensions/pages-not-found.md), som vanligtvis används för 404 sidor. | char(20) |
| **`page_url`** | URL:en för träffen. Observera att `post_page_url` har rensats för förfrågningar om länkspårningsbild ([`tl()`](/help/implement/vars/functions/tl-method.md)) och använder datatypen varchar(255). | text |
| **`pagename`** | Dimensionen [Sida](/help/components/dimensions/page.md). Om variabeln [`pagename`](/help/implement/vars/page-vars/pagename.md) är tom används `page_url` i stället. | varchar(100) |
| **`pagename_no_url`** | Liknar `pagename`, förutom att den inte faller tillbaka till `page_url`. Endast kolumnen `post` är tillgänglig. | varchar(100) |
| **`paid_search`** | En flagga som avgör om träffen matchar betalsökningsidentifiering. | tinyint unsigned |
| **`persistent_cookie`** | Används i dimensionen [Persistent cookie support](/help/components/dimensions/persistent-cookie-support.md). Anger om besökaren stöder cookies som inte tas bort efter varje träff. | char(1) |
| **`pointofinterest`** | Intressepunktsnamn för mobiltjänster | varchar(255) |
| **`pointofinterestdistance`** | Avstånd för mobiltjänster till intressanta center | varchar(255) |
| **`post_`** kolumner | Innehåller det värde som används i rapporterna. Varje inläggskolumn fylls i efter serversidans logik, bearbetningsregler och VISTA-regler. Adobe rekommenderar att du i de flesta fall använder inläggskolumner. | Se respektive icke-postkolumn |
| **`product_list`** | Sidvariabeln [`products`](/help/implement/vars/page-vars/products.md). Hjälper till att fylla i flera dimensioner och mätvärden, inklusive [Kategori](/help/components/dimensions/category.md), [Produkt](/help/components/dimensions/product.md), [Enheter](/help/components/metrics/units.md) och [Intäkter](/help/components/metrics/revenue.md). | text |
| **`prop1`** - `prop75` | Anpassade trafikvariabler 1-75. Används i måtten [Prop](/help/components/dimensions/prop.md). | varchar(100) |
| **`purchaseid`** | Unik identifierare för ett köp, enligt inställningen med variabeln [`purchaseID`](/help/implement/vars/page-vars/purchaseid.md). Används av kolumnen `duplicate_purchase`. | char(20) |
| **`quarterly_visitor`** | En flagga som avgör om träffen är en ny kvartalsbesökare. | tinyint unsigned |
| **`ref_domain`** | Dimensionen [Referensdomän &#x200B;](/help/components/dimensions/referring-domain.md). Baserat på kolumnen `referrer`. | varchar(100) |
| **`ref_type`** | Ett numeriskt ID som representerar typen av hänvisning för träffen. Används i dimensionen [Referenstyp](/help/components/dimensions/referrer-type.md). <ul><li>Inuti din webbplats</li><li>Andra webbplatser</li> <li>Sökmotorer</li> <li> AI-verktyg för konversation</li><li>Hårddisk</li> <li>USENET</li> <li>Typed/Bookmarked (ingen referent)</li> <li>E-post</li> <li>Ingen JavaScript</li> <li>Sociala nätverk</li></ul> | tinyint unsigned |
| **`referrer`** | Dimensionen [Referent](/help/components/dimensions/referrer.md). Observera att medan `referrer` använder datatypen varchar(255) använder `post_referrer` datatypen varchar(244). | varchar(255) |
| **`resolution`** | Ett numeriskt ID som representerar bildskärmens upplösning. Används i dimensionen [Bildskärmsupplösning](/help/components/dimensions/monitor-resolution.md). Använder `resolution.tsv`-uppslagstabell. | smallint unsigned |
| **`s_kwcid`** | Nyckelord-ID som används i Adobe Advertising-integreringar. | varchar(255) |
| **`s_resolution`** | Upplösningsvärde för Raw-skärm. Samlades in med JavaScript-funktionen `screen.width x screen.height`. | char(20) |
| **`search_engine`** | Ett numeriskt ID som representerar sökmotorn som refererade besökaren till din webbplats. Används i dimensionerna för [sökmotorn](/help/components/dimensions/search-engine.md). Refererar till `search_engines.tsv`-söktabellen. | smallint unsigned |
| **`search_page_num`** | Används av dimensionen [All söksidrankning](/help/components/dimensions/all-search-page-rank.md). Anger vilken sida med sökresultat som din webbplats visade sig på innan användaren klickade igenom till din webbplats. | smallint unsigned |
| **`secondary_hit`** | En flagga som avgör om träffen är en sekundär träff. Den här flaggan kommer vanligtvis från taggar för flera programsviter och VISTA-regler som kopierar träffar. | tinyint unsigned |
| **`sourceid`** | SOURCE ID | int unsigned |
| **`state`** | State-variabel. | varchar(50) |
| **`stats_server`** | Inte till användning. Adobe interna server som bearbetade träffen. | char(30) |
| **`t_time_info`** | Lokal tid för besökaren. Formatet är: `M/D/YYYY HH:MM:SS Month (0-11, 0=January) Timezone offset (in minutes)` | varchar(100) |
| **`tnt`** | Används i Adobe Target integreringar. Representerar alla tester som är kvalificerade för tillfället. Formatet är: `TargetCampaignID:TargetRecipeID:TargetType\|Event/Action`. | text |
| **`tnt_action`** | Används i Adobe Target integreringar. Representerar alla tester som träffen är kvalificerad för. | text |
| **`tnt_instances`** | Används i Adobe Target integreringar. Målförekomstvariabel. | text |
| **`transactionid`** | En unik identifierare där olika datapunkter kan överföras senare via datakällor. Samlades in med variabeln [`transactionID`](/help/implement/vars/page-vars/transactionid.md). | text |
| **`truncated_hit`** | En flagga som anger att bildbegäran har trunkerats. Anger att en partiell träff togs emot. <br>Y: Träff trunkerades. Partiell träff togs emot <br>N: Trädet trunkerades inte, fullständig träff togs emot | char(1) |
| **`user_agent`** | Användaragentsträngen som skickas i HTTP-huvudet i bildbegäran. | text |
| **`user_hash`** | Inte till användning. Hash för rapportens Suite-ID. Använd `username` i stället. | int unsigned |
| **`user_server`** | Används i dimensionen [Server](/help/components/dimensions/server.md). | varchar(100) |
| **`userid`** | Inte till användning. Det numeriska ID:t för rapportsvitens ID. Använd `username` i stället. | int unsigned |
| **`username`** | Rapportsvitens ID för träffen. | char(40) |
| **`va_closer_detail`** | Dimensionen [Senaste beröringsdetalj](/help/components/dimensions/last-touch-detail.md). | varchar(255) |
| **`va_closer_id`** | Ett numeriskt ID som identifierar dimensionen [Senaste beröringskanal](/help/components/dimensions/last-touch-channel.md). Sökningen efter detta ID finns i Marketing Channel Manager. | tinyint unsigned |
| **`va_finder_detail`** | Dimensionen [Första beröringsdetalj](/help/components/dimensions/first-touch-detail.md). | varchar(255) |
| **`va_finder_id`** | Ett numeriskt ID som identifierar dimensionen för den [första beröringskanalen](/help/components/dimensions/first-touch-channel.md). Sökningen efter detta ID finns i Marketing Channel Manager. | tinyint unsigned |
| **`va_instance_event`** | En flagga som identifierar marknadsföringskanalen [instanser](/help/components/metrics/instances.md). | tinyint unsigned |
| **`va_new_engagement`** | En flagga som identifierar marknadsföringskanalen [Nya engagemang](/help/components/metrics/new-engagements.md). | tinyint unsigned |
| **`video`** | Dimensionen [Innehåll](/help/components/dimensions/sm-core.md) för direktuppspelande medietjänster. | varchar(255) |
| **`videoad`** | Dimensionen [Ad](/help/components/dimensions/sm-ads.md) för direktuppspelande medietjänster. | varchar(255) |
| **`videoadinpod`** | Dimensionen [Ad in pod position](/help/components/dimensions/sm-ads.md) för direktuppspelande medietjänster. | varchar(255) |
| **`videoadlength`** | Dimensionen [Ad length (variabel)](/help/components/dimensions/sm-ads.md) för direktuppspelande medietjänster. | heltal |
| **`videoadload`** | [Ad läser in &#x200B;](/help/components/dimensions/sm-ads.md)-dimensionen för direktuppspelande medietjänster. | varchar(255) |
| **`videoadname`** | Dimensionen [Ad name (variabel)](/help/components/dimensions/sm-ads.md) för direktuppspelande medietjänster. | varchar(255) |
| **`videoadplayername`** | Dimensionen för [annonsspelarnamn](/help/components/dimensions/sm-ads.md) för direktuppspelande medietjänster. | varchar(255) |
| **`videoadpod`** | Dimensionen [Ad pod](/help/components/dimensions/sm-ads.md) för direktuppspelande medietjänster. | varchar(255) |
| **`videoadvertiser`** | Dimensionen [Advertiser](/help/components/dimensions/sm-ads.md) för direktuppspelande medietjänster. | varchar(255) |
| **`videoaudioalbum`** | Dimensionen [Album](/help/components/dimensions/sm-audio-metadata.md) för direktuppspelande medietjänster. | varchar(255) |
| **`videoaudioartist`** | Dimensionen [Konstnär](/help/components/dimensions/sm-audio-metadata.md) för direktuppspelande medietjänster. | varchar(255) |
| **`videoaudioauthor`** | Dimensionen [Författare](/help/components/dimensions/sm-audio-metadata.md) för direktuppspelande medietjänster. | varchar(255) |
| **`videoaudiolabel`** | Dimensionen [Etikett](/help/components/dimensions/sm-audio-metadata.md) för direktuppspelande medietjänster. | varchar(255) |
| **`videoaudiopublisher`** | Dimensionen [Utgivare](/help/components/dimensions/sm-audio-metadata.md) för direktuppspelande medietjänster. | varchar(255) |
| **`videoaudiostation`** | Dimensionen [Station](/help/components/dimensions/sm-audio-metadata.md) för direktuppspelande medietjänster. | varchar(255) |
| **`videocampaign`** | Dimensionen [Kampanj-ID](/help/components/dimensions/sm-ads.md) för direktuppspelande medietjänster. | varchar(255) |
| **`videochannel`** | Dimensionen [Medietjänster för direktuppspelning i innehållskanalen](/help/components/dimensions/sm-core.md). | varchar(255) |
| **`videochapter`** | Dimensionen [Kapitel](/help/components/dimensions/sm-chapters.md) för direktuppspelande medietjänster. | varchar(255) |
| **`videocontenttype`** | Dimensionen för [innehållstyp](/help/components/dimensions/sm-core.md) för direktuppspelande medietjänster. | varchar(255) |
| **`videodaypart`** | [Dagdelen](/help/components/dimensions/sm-video-metadata.md) av dimensionen för tjänster för direktuppspelning av media. | varchar(255) |
| **`videoepisode`** | Dimensionen för [Episod](/help/components/dimensions/sm-video-metadata.md) för direktuppspelande medietjänster. | varchar(255) |
| **`videofeedtype`** | Dimensionen för [Medieflödestyp](/help/components/dimensions/sm-video-metadata.md) för direktuppspelande medietjänster. | varchar(255) |
| **`videogenre`** | Dimensionen [Genre](/help/components/dimensions/sm-video-metadata.md) för direktuppspelande medietjänster. Denna dimension tillåter flera värden i samma träff, avgränsade med kommatecken. | text |
| **`videolength`** | Dimensionen [Innehållslängd (variabel)](/help/components/dimensions/sm-core.md) för direktuppspelande medietjänster. | heltal |
| **`videomvpd`** | Dimensionen [MVPD](/help/components/dimensions/sm-video-metadata.md) för direktuppspelande medietjänster. | varchar(255) |
| **`videoname`** | Dimensionen [Innehållsnamn (variabel)](/help/components/dimensions/sm-core.md) för direktuppspelande medietjänster. | varchar(255) |
| **`videonetwork`** | Dimensionen [Nätverks](/help/components/dimensions/sm-video-metadata.md) för direktuppspelande medietjänster. | varchar(255) |
| **`videopath`** | Dimensionen för [mediesökväg](/help/components/dimensions/sm-core.md) för direktuppspelning av medietjänster. | varchar(100) |
| **`videoplayername`** | Dimensionen för [Innehållsspelarens namn](/help/components/dimensions/sm-core.md) för direktuppspelande medietjänster. | varchar(255) |
| **`videotime`** | [Innehållstid som använts](/help/components/metrics/sm-core.md) för att strömma medietjänster. | heltal |
| **`videoqoebitrateaverageevar`** | Den [genomsnittliga bithastigheten](/help/components/dimensions/sm-quality.md) för tjänster för direktuppspelning av media. | varchar(255) |
| **`videoqoebitratechangecountevar`** | [Bithastigheten ändras](/help/components/dimensions/sm-quality.md) i dimensionen för direktuppspelande medietjänster. | varchar(255) |
| **`videoqoebuffercountevar`** | Dimensionen för [Bufferthändelser](/help/components/dimensions/sm-quality.md) för direktuppspelande medietjänster. | varchar(255) |
| **`videoqoebuffertimeevar`** | Dimensionen för [Total buffertvaraktighet](/help/components/dimensions/sm-quality.md) för direktuppspelande medietjänster. | varchar(255) |
| **`videoqoedroppedframecountevar`** | Dimensionen för [uteslutna bildrutor](/help/components/dimensions/sm-quality.md) för direktuppspelande medietjänster. | varchar(255) |
| **`videoqoeerrorcountevar`** | Dimensionen [Fel](/help/components/dimensions/sm-quality.md) för direktuppspelande medietjänster. | varchar(255) |
| **`videoqoeextneralerrors`** | Dimensionen [Externa fel-ID:n](/help/components/dimensions/sm-quality.md) för direktuppspelande medietjänster. Denna dimension tillåter flera värden i samma träff. | text |
| **`videoqoeplayersdkerrors`** | [Player SDK-fel-ID:n](/help/components/dimensions/sm-quality.md) för direktuppspelning av medietjänster. Denna dimension tillåter flera värden i samma träff. | text |
| **`videoqoetimetostartevar`** | Den [tid det tar att starta](/help/components/dimensions/sm-quality.md)-dimensionen för direktuppspelande medietjänster. | varchar(255) |
| **`videoseason`** | Dimensionen [Säsong](/help/components/dimensions/sm-video-metadata.md) för direktuppspelande medietjänster. | varchar(255) |
| **`videosegment`** | Dimensionen [Innehållssegment](/help/components/dimensions/sm-core.md) för direktuppspelande medietjänster. | varchar(255) |
| **`videoshow`** | Dimensionen [Visa](/help/components/dimensions/sm-video-metadata.md) för direktuppspelande medietjänster. | varchar(255) |
| **`videoshowtype`** | Dimensionen för [Visa typ](/help/components/dimensions/sm-video-metadata.md) för direktuppspelande medietjänster. | varchar(255) |
| **`videostreamtype`** | Dimensionen för [direktuppspelningstyp](/help/components/dimensions/sm-core.md) för medietjänster. | varchar(255) |
| **`visid_high`** | Används med `visid_low` för att unikt identifiera en besökare. | bigint unsigned |
| **`visid_low`** | Används med `visid_high` för att unikt identifiera en besökare. | bigint unsigned |
| **`visid_new`** | En flagga som avgör om träffen innehåller ett nyligen genererat besökar-ID. | char(1) |
| **`visid_timestamp`** | Om ett besökar-ID nyligen genereras, anger tidsstämpeln i UNIX®-tid när besökar-ID:t genererades. | int |
| **`visid_type`** | Ej för extern användning; används internt av Adobe för optimering av bearbetningen. Ett numeriskt ID som representerar den metod som används för att identifiera besökaren.<br>`0`: Anpassat besökar-ID eller Okänt/ej tillämpligt<br>`1`: IP- och användaragentåtergång <br>`2`: HTTP Mobile Subscriber Header <br>`3`: Legacy cookie value (`s_vi`) <br>`4`: Fallback cookie value (`s_fid`) <br>`5`: Identity Service | tinyint unsigned |
| **`visit_keywords`** | Dimensionen [Söknyckelord](/help/components/dimensions/search-keyword.md). I den här kolumnen används en icke-standard teckengräns på varchar(244) för att rymma den serverlogik som används av Adobe. | varchar(244) |
| **`visit_num`** | Dimensionen [Besök nummer](/help/components/dimensions/visit-number.md). Börjar vid 1 och ökar stegvis varje gång ett nytt besök påbörjas per besökare. | int unsigned |
| **`visit_page_num`** | Dimensionen [Träff](/help/components/dimensions/hit-depth.md). Ökar med 1 för varje träff som besökaren skapar. Återställer varje besök. | int unsigned |
| **`visit_ref_domain`** | Baserat på kolumnen `visit_referrer`. Den första refererande domänen för besöket. | varchar(100) |
| **`visit_ref_type`** | Ett numeriskt ID som representerar referenstypen för besökets första referent. Refererar till `referrer_type.tsv`-söktabellen. | tinyint unsigned |
| **`visit_referrer`** | Den första referenten till besöket. | varchar(255) |
| **`visit_search_engine`** | Ett numeriskt ID som representerar besökets första sökmotor. Refererar till `search_engines.tsv`-söktabellen. | smallint unsigned |
| **`visit_start_page_url`** | Besökets första URL. | varchar(255) |
| **`visit_start_pagename`** | Värdet för Sidnamn i den första träffen av besöket. | varchar(100) |
| **`visit_start_time_gmt`** | Tidsstämpel (i UNIX®-tid) för första besöket. | int |
| **`weekly_visitor`** | En flagga som avgör om träffen är en ny besökare varje vecka. | tinyint unsigned |
| **`yearly_visitor`** | En flagga som avgör om träffen är en ny årlig besökare. | tinyint unsigned |
| **`zip`** | Hjälper till att fylla i dimensionen [Postnummer](/help/components/dimensions/zip-code.md). Se även `geo_zip`. | varchar(50) |

{style="table-layout:auto"}

## Oanvända eller indragna kolumner

Följande kolumnlista är oanvända, indragna eller innehåller inget värde i rapporteringen. Vissa av dessa kolumner är kopplade till funktioner som har solnedgångar, medan andra inte längre behövs på grund av nya och mer robusta funktioner. De flesta av dessa kolumner innehåller inga data. Kolumner som fortfarande kan innehålla data stöds inte av aktuella datainsamlingsbibliotek och är inte tillgängliga dimensioner i Analysis Workspace.

* `adclassificationcreative`
* `click_action`
* `click_action_type`
* `click_context`
* `click_context_type`
* `click_sourceid`
* `click_tag`
* `hier1` - `hier5`
* `homepage`
* `ip2`
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
* `mobiledayssincelastupgrade`
* `mobiledeeplinkid.name`
* `mobileinstalls`
* `mobilelaunches`
* `mobilelaunchessincelastupgrade`
* `mobileltv`
* `mobileltvtotal`
* `mobilemessageclicks`
* `mobilemessageid.dest`
* `mobilemessageid.name`
* `mobilemessageid.type`
* `mobilemessageimpressions`
* `mobilemessagepushpayloadid.name`
* `mobilemessageviews`
* `mobilemonthlyengagedusers`
* `mobileosenvironment`
* `mobileplacedwelltime`
* `mobileplaceentry`
* `mobileplaceexit`
* `mobileprevsessionlength`
* `mobilerelaunchcampaigntrackingcode.name`
* `mobileupgrades`
* `namespace`
* `p_plugins`
* `page_event_var3`
* `partner_plugins`
* `plugins`
* `prev_page`
* `product_merchandising`
* `sampled_hit`
* `service`
* `socialaccountandappids`
* `socialassettrackingcode`
* `socialauthor`
* `socialaveragesentiment`
* `socialaveragesentiment (deprecated)`
* `socialcontentprovider`
* `socialfbstories`
* `socialfbstorytellers`
* `socialinteractioncount`
* `socialinteractiontype`
* `sociallanguage`
* `sociallatlong`
* `sociallikeadds`
* `sociallink`
* `sociallink (deprecated)`
* `socialmentions`
* `socialowneddefinitioninsighttype`
* `socialowneddefinitioninsightvalue`
* `socialowneddefinitionmetric`
* `socialowneddefinitionpropertyvspost`
* `socialownedpostids`
* `socialownedpropertyid`
* `socialownedpropertyname`
* `socialownedpropertypropertyvsapp`
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
* `survey`
* `survey_instances`
* `tnt_post_vista`
* `ua_color`
* `ua_os`
* `ua_pixels`
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

>[!MORELIKETHIS]
>
>[Variabelmappning för XDM-objekt](/help/implement/aep-edge/xdm-var-mapping.md)
>[Variabelmappning för dataobjekt &#x200B;](/help/implement/aep-edge/data-var-mapping.md)
