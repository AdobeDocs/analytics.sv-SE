---
description: Tabelldata som beskriver kolumnerna i dataflödet.
keywords: Datafeed;kolumner
subtopic: data feeds
title: Referens för datakolumn
feature: Data Feeds
exl-id: e1492147-6e7f-4921-b509-898e7efda596
source-git-commit: fd5a38ca3c621e67f7a670f361e73b439ce9861a
workflow-type: tm+mt
source-wordcount: '3642'
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

| Bokför | Kolumnnamn | Kolumnbeskrivning | Datatyp |
| ---: | :--- | --- | --- |
| | **`accept_language`** | Visar alla godkända språk enligt HTTP-huvudet Accept-Language i en bildbegäran. | char(20) |
| **`post_`** | **`adload`** | Inläsningar av mediaannonser | varchar(255) |
| **`post_`** | **`aemassetid`** | En variabel med flera värden som motsvarar tillgångs-ID:n (GUID) för en uppsättning Adobe Experience Manager Assets. Ökar imponeringshändelser. | text |
| **`post_`** | **`aemassetsource`** | Identifierar resurshändelsens källa. Används i Adobe Experience Manager. | varchar(255) |
| **`post_`** | **`aemclickedassetid`** | Tillgångs-ID för en Adobe Experience Manager-resurs. Ökningar Klicka på händelser. | varchar(255) |
| **`post_`** | **`amo_cid`** | Dimensionen [AMO ID](/help/components/dimensions/amo-id.md) som används i Adobe Advertising-integreringar. | varchar(255) |
| **`post_`** | **`amo_ef_id`** | Dimensionen [AMO EF ID](/help/components/dimensions/amo-ef-id.md) som används i Adobe Advertising-integreringar. | varchar(255) |
| | **`browser`** | Ett numeriskt ID som representerar webbläsaren. Refererar till `browser.tsv`-söktabellen. | int unsigned |
| **`post_`** | **`browser_height`** | Dimensionen [Webbläsarhöjd](/help/components/dimensions/browser-height.md). | smallint unsigned |
| **`post_`** | **`browser_width`** | Bredd på [webbläsaren](/help/components/dimensions/browser-width.md) | smallint unsigned |
| **`post_`** | **`campaign`** | Dimensionen [Spårningskod](/help/components/dimensions/tracking-code.md). | varchar(255) |
| | **`carrier`** | Adobe Advertising integrationsvariabel. Anger mobiloperatör. Nyckelvärdet för `carrier.tsv` [dynamisk sökning](dynamic-lookups.md). | varchar(100) |
| **`post_`** | **`channel`** | Dimensionen [Webbplatsavsnitt](/help/components/dimensions/site-section.md). | varchar(100) |
| | **`ch_hdr`** | Klienttips som samlats in via HTTP-begärandehuvudet. | text |
| | **`ch_js`** | Klienttips som samlats in via JavaScript-API:t för användaragenttips för klienttips. | text |
| **`post_`** | **`clickmaplink`** | Dimensionen [Activity Map link](/help/components/dimensions/activity-map-link.md). | varchar(255) |
| **`post_`** | **`clickmaplinkbyregion`** | Activity Map-dimensionen [Länk efter region](/help/components/dimensions/activity-map-link-by-region.md). | varchar(255) |
| **`post_`** | **`clickmappage`** | Dimensionen för [Activity Map-sidan](/help/components/dimensions/activity-map-page.md). | varchar(255) |
| **`post_`** | **`clickmapregion`** | Dimensionen för [Activity Map-regionen](/help/components/dimensions/activity-map-region.md). | varchar(255) |
| | **`code_ver`** | API- eller klient-SDK-version som används för att kompilera och skicka bildbegäran. | char(16) |
| | **`color`** | Färgdjup-ID baserat på värdet för kolumnen `c_color`. Refererar till `color_depth.tsv`-söktabellen. | smallint unsigned |
| | **`connection_type`** | Numeriskt ID som representerar dimensionen [Anslutningstyp](/help/components/dimensions/connection-type.md). Refererar till `connection_type.tsv`-söktabellen. | tinyint unsigned |
| **`post_`** | **`cookies`** | Dimensionen [Cookie stöder](/help/components/dimensions/cookie-support.md).<br>Y: Aktiverad<br>N: Inaktiverad<br>U: Okänd | char(1) |
| | **`country`** | Ett numeriskt ID som representerar besökarens land. Refererar till `country.tsv`-söktabellen. | smallint unsigned |
| **`post_`** | **`currency`** | Valutakoden som användes under transaktionen. Ange med [`currencyCode`](/help/implement/vars/config-vars/currencycode.md). | char(8) |
| | **`ct_connect_type`** | Relaterat till kolumnen `connection_type`. De vanligaste värdena är LAN/Wifi, mobiloperatör och modem. | char(20) |
| | **`curr_factor`** | Bestämmer valutadecimalen. Används för valutakonvertering. USD använder till exempel två decimaler, så det här kolumnvärdet blir `2`. | tinyint |
| | **`curr_rate`** | Växelkursen när transaktionen inträffade. Adobe samarbetar med XE för att fastställa dagens växelkurs. | decimal(24,12) |
| **`post_`** | **`customer_perspective`** | Avgör om träffen är en mobilbakgrundträff. Mer information finns i [Kontextmedvetna sessioner](/help/components/vrs/vrs-mobile-visit-processing.md). | tinyint unsigned |
| **`post_`** | **`cust_hit_time_gmt`** | Endast tidsstämpelaktiverade rapportsviter. Tidsstämpeln som skickades med träffen, baserat på UNIX®-tid. | int |
| **`post_`** | **`cust_visid`** | Det anpassade besökar-ID:t, om [`visitorID`](/help/implement/vars/config-vars/visitorid.md) används. | varchar(255) |
| | **`c_color`** | Färgpalettens bitdjup. Används som en del av beräkningen av dimensionen [Färgdjup](/help/components/dimensions/color-depth.md). AppMeasurement använder JavaScript-funktionen `screen.colorDepth()`. | char(20) |
| | **`daily_visitor`** | En flagga som avgör om träffen är en ny daglig besökare. | tinyint unsigned |
| | **`dataprivacyconsentoptin`** | Dimensionen [Medgivandehanteringsanmälan](/help/components/dimensions/cm-opt-in.md). Flera värden kan finnas per träff, avgränsade med ett rör (`\|`). Giltiga värden är `DMP` och `SELL`. | varchar(100) |
| | **`dataprivacyconsentoptout`** | Dimensionen [Medgivandehanteringsavanmälan](/help/components/dimensions/cm-opt-out.md). Flera värden kan finnas per träff, avgränsade med ett rör (`\|`). Giltiga värden är `SSF`, `DMP` och `SELL`. | varchar(100) |
| | **`date_time`** | Tidpunkten för träffen i läsbart format, baserat på rapportsvitens tidszon. | datetime |
| | **`domain`** | Dimensionen [Domain](/help/components/dimensions/domain.md). Baserat på besökarens Internetanslutningspunkt. | varchar(100) |
| | **`duplicated_from`** | Används endast i rapportsviter som innehåller VISTA-regler för träffkopior. Anger vilken rapportsvit som träffen kopierades från. | varchar(40) |
| | **`duplicate_events`** | Listar varje händelse som räknats som en dubblett. | varchar(255) |
| | **`duplicate_purchase`** | En flagga som avgör om köphändelsen för den här träffen ignoreras eftersom den är en dubblett. | tinyint unsigned |
| **`post_`** | **`ef_id`** | Det EF-ID som används i Adobe Advertising-integreringar. | varchar(255) |
| **`post_`** | **`evar1 - evar250`** | Egna variabler 1-250. Används i måtten [eVar](/help/components/dimensions/evar.md). Varje organisation använder eVars på olika sätt. Det bästa stället för mer information om hur din organisation fyller i respektive eVars är ett [lösningsdesigndokument](/help/implement/prepare/solution-design.md) som är specifikt för din organisation. | varchar(255) |
| **`post_`** | **`event_list`** | Kommaavgränsad lista med numeriska ID:n som representerar händelser som utlöses vid träffen. Innehåller både e-handelshändelser och [anpassade händelser 1-1000](/help/components/metrics/custom-events.md). Använder `event.tsv`-sökning. | text |
| | **`exclude_hit`** | En flagga som avgör om träffen utesluts från rapportering. Kolumnen `visit_num` ökas inte för uteslutna träffar.<br>1: Används inte. En del av en skrapad funktion.<br>2: Används inte. En del av en skrapad funktion.<br>3: Används inte längre. Undantag för användaragent<br>4: Undantag baserat på IP-adress<br>5: Information om träffar saknas, t.ex. `page_url`, `pagename`, `page_event` eller `event_list`<br>6: JavaScript bearbetade inte korrekt träffen<br>7: Kontospecifikt undantag, t.ex. i VISTA-regler<br>8: Används inte. Alternativt kontospecifikt undantag.<br>9: Används inte. En del av en skrapad funktion.<br>10: Ogiltig valutakod<br>11: Träff saknar en tidsstämpel i en rapportsvit som bara innehåller tidsstämplar, eller en träff innehöll en tidsstämpel i en rapportsvit som inte är en tidsstämpel.<br>12: Används inte. En del av en skrapad funktion.<br>13: Används inte. En del av en skrapad funktion.<br>14: Målträff som inte matchar en Analytics-träff<br>15: Används inte just nu.<br>16: Advertising Cloud-träff som inte matchar en Analytics-träff | tinyint unsigned |
| | **`first_hit_pagename`** | Den ursprungliga dimensionen för [startsidan](/help/components/dimensions/entry-dimensions.md). Besökarens ursprungliga startsidnamn. | varchar(100) |
| | **`first_hit_page_url`** | Besökarens allra första URL. | varchar(255) |
| | **`first_hit_referrer`** | Den första refererande URL:en för besökaren. | varchar(255) |
| | **`first_hit_ref_domain`** | Den [ursprungliga refererande domänen](/help/components/dimensions/original-referring-domain.md)-dimensionen. Baserat på `first_hit_referrer`. Den första refererande domänen för besökaren. | varchar(100) |
| | **`first_hit_ref_type`** | Ett numeriskt ID som representerar referenstypen för besökarens första referent. Refererar till `referrer_type.tsv`-söktabellen. | tinyint unsigned |
| | **`first_hit_time_gmt`** | Tidsstämpel för besökarens första träff i UNIX®-tid. | int |
| | **`geo_city`** | Namnet på den stad som träffen kom från, baserat på IP. Används i dimensionen [Städer](/help/components/dimensions/cities.md). | char(32) |
| | **`geo_country`** | Förkortningen för det land som träffen kom från, baserat på IP. Används i dimensionen [Länder](/help/components/dimensions/countries.md). | char(4) |
| | **`geo_dma`** | Ett numeriskt ID för det demografiska område som träffen kom från, baserat på IP. Används i [US DMA](/help/components/dimensions/us-dma.md)-dimensionen. | int unsigned |
| | **`geo_region`** | Namnet på den stat eller region som träffen kom från, baserat på IP. Används i dimensionen [Områden](/help/components/dimensions/regions.md). | char(32) |
| | **`geo_zip`** | Postnumret som träffen kom från, baserat på IP. Hjälper till att fylla i dimensionen [Postnummer](/help/components/dimensions/zip-code.md). Se även `zip`. | varchar(16) |
| | **`hitid_high`** | Används med `hitid_low` för att identifiera en träff. | bigint unsigned |
| | **`hitid_low`** | Används med `hitid_high` för att identifiera en träff. | bigint unsigned |
| | **`hit_source`** | Källan som träffen kom från. Träffkällor 1 och 2 faktureras. <br>1: Standardbildbegäran utan tidsstämpel <br>2: Standardbildbegäran med tidsstämpel <br> 3: Överföring av Live-datakälla med tidsstämplar <br> <br>: Används inte <br>6: Överföring av allmän datakälla 6: Används inte längre; överföring av datakälla med fullständig bearbetning <br>7: Överföring av TransactionID-datakälla <br>8: Används inte längre; Tidigare versioner av Adobe Advertising-datakällor <br> 8&rbrace;9: Används inte längre, Adobe Social-sammanfattningsmått <br> : Audience Manager serversidans vidarebefordran används | tinyint unsigned |
| | **`hit_time_gmt`** | Tidsstämpeln för Adobe datainsamlingsservrar tog emot träffen, baserat på UNIX®-tid. | int |
| | **`hourly_visitor`** | En flagga som avgör om träffen är en ny timbesökare. | tinyint unsigned |
| | **`ip`** | IPv4-adressen, baserad på HTTP-huvudet i bildbegäran. Mutuellt exklusiv för `ipv6`. Om den här kolumnen innehåller en icke-konfidentiell IP-adress är `ipv6` tom. | char(20) |
| | **`ipv6`** | Den komprimerade IPv6-adressen, om den är tillgänglig. Mutuellt exklusiv för `ip`. Om den här kolumnen innehåller en icke-konfidentiell IP-adress är `ip` tom. | varchar(40) |
| | **`javascript`** | Ett söknings-ID för JavaScript-version, baserat på `j_jscript`. Refererar till `javascript_version`-söktabellen. | tinyint unsigned |
| **`post_`** | **`java_enabled`** | [[!UICONTROL Java enabled]](/help/components/dimensions/java-enabled.md). <br>Y: Aktiverad <br>N: Inaktiverad <br>U: Okänd | char(1) |
| | **`j_jscript`** | Den version av JavaScript som stöds av webbläsaren. | char(5) |
| | **`language`** | Ett numeriskt ID som representerar besökarens språk. Refererar till `languages.tsv`-söktabellen. | smallint unsigned |
| | **`last_hit_time_gmt`** | Tidsstämpel (i UNIX®-tid) för föregående träff. Används för att beräkna dimensionen [[!UICONTROL Days since last visit]](/help/components/dimensions/days-since-last-visit.md). | int |
| | **`last_purchase_num`** | Dimensionen [Kundlojalitet](/help/components/dimensions/customer-loyalty.md). Antalet tidigare inköp som besökaren har gjort. <br>0: Inga tidigare inköp (inte en kund) <br>1: 1 tidigare inköp (ny kund) <br>2: 2 tidigare inköp (returkund) <br>3: 3 eller fler tidigare inköp (lojal kund) | int unsigned |
| | **`last_purchase_time_gmt`** | Används i dimensionen [[!UICONTROL Days since last purchase]](/help/components/dimensions/days-since-last-purchase.md). Tidsstämpel (i UNIX®-tid) för det senaste köpet. För förstagångsköp och besökare som inte har gjort något inköp tidigare är det här värdet `0`. | int |
| | **`latlon1`** | Placering (ned till 10 km) | varchar(255) |
| | **`latlon23`** | Plats (ned till 100 m) | varchar(255) |
| | **`latlon45`** | Plats (ned till 1 m) | varchar(255) |
| | **`mcvisid`** | Experience Cloud Visitor-ID. 128-bitars nummer som består av två sammanfogade 64-bitars tal som fyllts med 19 siffror. | varchar(255) |
| **`post_`** | **`mc_audiences`** | Lista med Audience Manager segment-ID:n som besökaren tillhör. Kolumnen `post_mc_audiences` ändrar avgränsaren till `--**--`. | text |
| **`post_`** | **`mobileaction`** | Mobilåtgärd. Samlas in automatiskt när `trackAction` anropas i mobilimplementeringar. Tillåter automatisk åtgärdspunkt i appen. | varchar(100) |
| **`post_`** | **`mobileappid`** | ID för mobilapp. Lagrar programnamnet och versionen i följande format: `[AppName] [BundleVersion]` | varchar(255) |
| | **`mobileappperformanceappid`** | Används i Apteligent-dataanslutningen. Program-ID som används i Apteligent. | varchar(255) |
| | **`mobileappperformancecrashid`** | Används i Apteligent-dataanslutningen. Det krasch-ID som används i Apteligent. | varchar(255) |
| | **`mobileappstoreobjectid`** | Används i dataanslutningen [!DNL Appfigures]. Objekt-ID för App Store. | varchar(255) |
| | **`mobilebeaconmajor`** | Mobiltjänster är viktiga | varchar(100) |
| | **`mobilebeaconminor`** | Mobiltjänster är mindre | varchar(100) |
| | **`mobilebeaconproximity`** | Avstånd för mobiltjänster | varchar(255) |
| | **`mobilebeaconuuid`** | Beacon UUID för mobiltjänster | varchar(100) |
| **`post_`** | **`mobilecampaigncontent`** | Namnet eller ID för innehållet som visade länken. Fylls i av Anskaffning av mobilapp. | varchar(255) |
| **`post_`** | **`mobilecampaignmedium`** | Marknadsföringsmedium, som banner eller e-post. Fylls i av Anskaffning av mobilapp. | varchar(255) |
| **`post_`** | **`mobilecampaignname`** | Namnet på kampanjen, som också lagras i kampanjvariabeln. Fylls i av Anskaffning av mobilapp. | varchar(255) |
| **`post_`** | **`mobilecampaignsource`** | Ursprunglig hänvisare, t.ex. nyhetsbrev eller sociala medier. Fylls i av Anskaffning av mobilapp. | varchar(255) |
| **`post_`** | **`mobilecampaignterm`** | Betalnyckelord eller andra termer som du vill spåra med förvärvet. Fylls i av Anskaffning av mobilapp. | varchar(255) |
| **`post_`** | **`mobiledayofweek`** | Nummer på den veckodag då appen startades. | varchar(255) |
| **`post_`** | **`mobiledayssincefirstuse`** | Antal dagar sedan appen kördes för första gången. | varchar(255) |
| **`post_`** | **`mobiledayssincelastuse`** | Antal dagar sedan appen senast kördes. | varchar(255) |
| | **`mobiledeeplinkid`** | Samlades in från kontextdatavariabeln `a.deeplink.id`. Används i förvärvsrapporter som en identifierare för länken för mobilförvärv. | varchar(255) |
| **`post_`** | **`mobiledevice`** | Namn på mobil enhet. I iOS lagras den som en kommaavgränsad tvåsiffrig sträng. Det första numret representerar enhetsgenereringen och det andra representerar enhetsfamiljen. | varchar(255) |
| **`post_`** | **`mobilehourofday`** | Definierar timmen på dagen då appen startades. Använder ett numeriskt format på 24 timmar. | varchar(255) |
| **`post_`** | **`mobileinstalldate`** | Datum för mobilinstallation. Anger datumet för första gången som en användare öppnar mobilappen. | varchar(255) |
| **`post_`** | **`mobilelaunchnumber`** | Ökningar med ett varje gång mobilappen startas. | varchar(255) |
| **`post_`** | **`mobilemessagebuttonname`** | Samlades in från kontextdatavariabeln `a.message.button.id`. Används för meddelanden i appen för att identifiera knappen som stängde meddelandet. | varchar(100) |
| **`post_`** | **`mobilemessageid`** | Meddelande-ID i appen | varchar(255) |
| **`post_`** | **`mobilemessageonline`** | Meddelande i appen online | varchar(255) |
| **`post_`** | **`mobilemessagepushoptin`** | Samlades in från kontextdatavariabeln `a.push.optin`. Ange som&quot;true&quot; när användaren väljer att skicka meddelanden, annars är värdet&quot;false&quot;. | varchar(255) |
| **`post_`** | **`mobilemessagepushpayloadid`** | Samlades in från kontextdatavariabeln `a.push.payloadid`. Används i push-meddelanden som nyttolast-ID. | varchar(255) |
| **`post_`** | **`mobileosversion`** | Mobiltjänstens operativsystemversion | varchar(255) |
| | **`mobileplaceaccuracy`** | Samlades in från kontextdatavariabeln `a.loc.acc`. Anger GPS-noggrannheten i meter vid insamlingen. | varchar(255) |
| | **`mobileplacecategory`** | Samlades in från kontextdatavariabeln `a.loc.category`. Beskriver kategorin för en viss plats. | varchar(255) |
| | **`mobileplaceid`** | Samlades in från kontextdatavariabeln `a.loc.id`. Identifierare för en viss intressepunkt. | varchar(255) |
| **`post_`** | **`mobilepushoptin`** | Push-deltagande för mobiltjänster | varchar(255) |
| **`post_`** | **`mobilepushpayloadid`** | Push-nyttolast-ID för mobiltjänster | varchar(255) |
| | **`mobilerelaunchcampaigncontent`** | Startinnehåll för mobiltjänster | varchar(255) |
| | **`mobilerelaunchcampaignmedium`** | Startmedium för mobiltjänster | varchar(255) |
| | **`mobilerelaunchcampaignsource`** | Startkälla för Mobile Services | varchar(255) |
| | **`mobilerelaunchcampaignterm`** | Startperiod för Mobile Services | varchar(255) |
| | **`mobilerelaunchcampaigntrackingcode`** | Samlades in från kontextdatavariabeln `a.launch.campaign.trackingcode`. Används i anskaffning som spårningskod för lanseringskampanj. | varchar(255) |
| **`post_`** | **`mobileresolution`** | Den mobila enhetens upplösning. `[Width] x [Height]` i pixlar. | varchar(255) |
| | **`mobile_id`** | Om användaren använder en mobil enhet anger du enhetens numeriska ID. Nyckelvärdet för `mobile_attributes.tsv` [dynamisk sökning](dynamic-lookups.md). | int |
| | **`monthly_visitor`** | En flagga som avgör om besökaren är unik för den aktuella månaden. | tinyint unsigned |
| **`post_`** | **`mvvar1`** - **`mvvar3`** | [Listvariabelvärden](/help/implement/vars/page-vars/list.md). Innehåller en avgränsad lista med anpassade värden beroende på implementering. Kolumnerna `post_mvvar1` - `post_mvvar3` ersätter den ursprungliga avgränsaren med `--**--`. | text |
| **`post_`** | **`mvvar1_instances`** - **`mvvar3_instances`** | Listvariabelvärdena som angavs för den aktuella träffen. Ersätter den ursprungliga avgränsaren med `--**--`. Kolumnerna `post` innehåller vanligtvis inga data. | text |
| | **`new_visit`** | En flagga som avgör om den aktuella träffen är ett nytt besök. Anges av Adobe efter 30 minuters inaktivitet. | tinyint unsigned |
| | **`os`** | Ett numeriskt ID som representerar besökarens operativsystem. Baserat på kolumnen `user_agent`. Nyckelvärdet för `operating_system.tsv` standardsökning och `operating_system_type.tsv` [dynamisk sökning](dynamic-lookups.md). | int unsigned |
| **`post_`** | **`pagename`** | Dimensionen [Sida](/help/components/dimensions/page.md). Om variabeln [`pagename`](/help/implement/vars/page-vars/pagename.md) är tom används `page_url` i stället. | varchar(100) |
| **`post_`** | **`pagename_no_url`** | Liknar `pagename`, förutom att den inte faller tillbaka till `page_url`. Endast kolumnen `post` är tillgänglig. | varchar(100) |
| **`post_`** | **`page_event`** | Den typ av träff som skickas i bildbegäran (standardträff, nedladdningslänk, anpassad länk, slutlänk). Se [Sökning efter sidhändelser](datafeeds-page-event.md). | tinyint unsigned |
| **`post_`** | **`page_event_var1`** | Används endast vid förfrågningar om länkspårningsbilder. URL-adressen till den nedladdningslänk, den avslutningslänk eller anpassade länk som du klickar på. | text |
| **`post_`** | **`page_event_var2`** | Används endast vid förfrågningar om länkspårningsbilder. Länkens anpassade namn (om det anges). Anger den [anpassade länken](/help/components/dimensions/custom-link.md), [Hämta länken](/help/components/dimensions/download-link.md) eller [Avsluta länken](/help/components/dimensions/exit-link.md) beroende på värdet i `page_event`. | varchar(100) |
| **`post_`** | **`page_type`** | Dimensionen [Sidorna hittades inte](/help/components/dimensions/pages-not-found.md), som vanligtvis används för 404 sidor. | char(20) |
| **`post_`** | **`page_url`** | **`page_url`**: URL:en för träffen. Använder en datatyp för text.<br>**`post_page_url`**: Borttagen för förfrågningar om länkspårningsbild ([`tl()`](/help/implement/vars/functions/tl-method.md)). Använder datatypen varchar(255). | text<br>varchar(255) |
| | **`paid_search`** | En flagga som avgör om träffen matchar betalsökningsidentifiering. | tinyint unsigned |
| **`post_`** | **`persistent_cookie`** | Används i dimensionen [Persistent cookie support](/help/components/dimensions/persistent-cookie-support.md). Anger om besökaren stöder cookies som inte tas bort efter varje träff. | char(1) |
| **`post_`** | **`pointofinterest`** | Intressepunktsnamn för mobiltjänster | varchar(255) |
| **`post_`** | **`pointofinterestdistance`** | Avstånd för mobiltjänster till intressanta center | varchar(255) |
| **`post_`** | **`product_list`** | Sidvariabeln [`products`](/help/implement/vars/page-vars/products.md). Hjälper till att fylla i flera dimensioner och mätvärden, inklusive [Kategori](/help/components/dimensions/category.md), [Produkt](/help/components/dimensions/product.md), [Enheter](/help/components/metrics/units.md) och [Intäkter](/help/components/metrics/revenue.md). | text |
| **`post_`** | **`prop1`** - **`prop75`** | Anpassade trafikvariabler 1-75. Används i måtten [Prop](/help/components/dimensions/prop.md). | varchar(100) |
| **`post_`** | **`purchaseid`** | Unik identifierare för ett köp, enligt inställningen med variabeln [`purchaseID`](/help/implement/vars/page-vars/purchaseid.md). Används av kolumnen `duplicate_purchase`. | char(20) |
| | **`quarterly_visitor`** | En flagga som avgör om träffen är en ny kvartalsbesökare. | tinyint unsigned |
| **`post_`** | **`referrer`** | Dimensionen [Referent](/help/components/dimensions/referrer.md). Observera att medan `referrer` använder datatypen varchar(255) använder `post_referrer` datatypen varchar(244). | varchar(255)<br>varchar(244) |
| | **`ref_domain`** | Dimensionen [Referensdomän &#x200B;](/help/components/dimensions/referring-domain.md). Baserat på kolumnen `referrer`. | varchar(100) |
| | **`ref_type`** | Ett numeriskt ID som representerar typen av hänvisning för träffen. Används i dimensionen [Referenstyp](/help/components/dimensions/referrer-type.md).<br>1: Inuti din webbplats<br>2: Andra webbplatser<br>3: Sökmotorer<br>4: Hårddisk<br>5: USENET<br>6: Typed/Bookmarked (ingen referent)<br>7: Email<br>8: No JavaScript<br>9: Social Networks<br>10: Conversational AI tools | tinyint unsigned |
| | **`resolution`** | Ett numeriskt ID som representerar bildskärmens upplösning. Används i dimensionen [Bildskärmsupplösning](/help/components/dimensions/monitor-resolution.md). Använder `resolution.tsv`-uppslagstabell. | smallint unsigned |
| **`post_`** | **`search_engine`** | Ett numeriskt ID som representerar sökmotorn som refererade besökaren till din webbplats. Används i dimensionerna för [sökmotorn](/help/components/dimensions/search-engine.md). Refererar till `search_engines.tsv`-söktabellen. | smallint unsigned |
| | **`search_page_num`** | Används av dimensionen [All söksidrankning](/help/components/dimensions/all-search-page-rank.md). Anger vilken sida med sökresultat som din webbplats visade sig på innan användaren klickade igenom till din webbplats. | smallint unsigned |
| | **`secondary_hit`** | En flagga som avgör om träffen är en sekundär träff. Den här flaggan kommer vanligtvis från taggar för flera programsviter och VISTA-regler som kopierar träffar. | tinyint unsigned |
| | **`sourceid`** | SOURCE ID | int unsigned |
| | **`stats_server`** | Inte till användning. Adobe interna server som bearbetade träffen. | char(30) |
| **`post_`** | **`s_kwcid`** | Nyckelord-ID som används i Adobe Advertising-integreringar. | varchar(255) |
| | **`s_resolution`** | Upplösningsvärde för Raw-skärm. Samlades in med JavaScript-funktionen `screen.width x screen.height`. | char(20) |
| **`post_`** | **`tnt`** | Används i Adobe Target integreringar. Representerar alla tester som är kvalificerade för tillfället. Formatet är: `TargetCampaignID:TargetRecipeID:TargetType\|Event/Action`. | text |
| **`post_`** | **`tnt_action`** | Används i Adobe Target integreringar. Representerar alla tester som träffen är kvalificerad för. | text |
| | **`tnt_instances`** | Används i Adobe Target integreringar. Målförekomstvariabel. | text |
| **`post_`** | **`transactionid`** | En unik identifierare där olika datapunkter kan överföras senare via datakällor. Samlades in med variabeln [`transactionID`](/help/implement/vars/page-vars/transactionid.md). | text |
| | **`truncated_hit`** | En flagga som anger att bildbegäran trunkerades (en partiell träff togs emot). <br>Y: Träff trunkerades. Partiell träff togs emot <br>N: Trädet trunkerades inte, fullständig träff togs emot | char(1) |
| **`post_`** | **`t_time_info`** | Lokal tid för besökaren. Formatet är: `M/D/YYYY HH:MM:SS Month (0-11, 0=January) Timezone offset (in minutes)` | varchar(100) |
| | **`userid`** | Inte till användning. Det numeriska ID:t för rapportsvitens ID. Använd `username` i stället. | int unsigned |
| | **`username`** | Rapportsvitens ID för träffen. | char(40) |
| | **`user_agent`** | Användaragentsträngen som skickas i HTTP-huvudet i bildbegäran. | text |
| | **`user_hash`** | Inte till användning. Hash för rapportens Suite-ID. Använd `username` i stället. | int unsigned |
| **`post_`** | **`user_server`** | Används i dimensionen [Server](/help/components/dimensions/server.md). | varchar(100) |
| | **`va_closer_detail`** | Dimensionen [Senaste beröringsdetalj](/help/components/dimensions/last-touch-detail.md). | varchar(255) |
| | **`va_closer_id`** | Ett numeriskt ID som identifierar dimensionen [Senaste beröringskanal](/help/components/dimensions/last-touch-channel.md). Sökningen efter detta ID finns i Marketing Channel Manager. | tinyint unsigned |
| | **`va_finder_detail`** | Dimensionen [Första beröringsdetalj](/help/components/dimensions/first-touch-detail.md). | varchar(255) |
| | **`va_finder_id`** | Ett numeriskt ID som identifierar dimensionen för den [första beröringskanalen](/help/components/dimensions/first-touch-channel.md). Sökningen efter detta ID finns i Marketing Channel Manager. | tinyint unsigned |
| | **`va_instance_event`** | En flagga som identifierar marknadsföringskanalen [instanser](/help/components/metrics/instances.md). | tinyint unsigned |
| | **`va_new_engagement`** | En flagga som identifierar marknadsföringskanalen [Nya engagemang](/help/components/metrics/new-engagements.md). | tinyint unsigned |
| **`post_`** | **`video`** | Dimensionen [Innehåll](/help/components/dimensions/sm-core.md) för direktuppspelande medietjänster. | varchar(255) |
| **`post_`** | **`videoad`** | Dimensionen [Ad](/help/components/dimensions/sm-ads.md) för direktuppspelande medietjänster. | varchar(255) |
| **`post_`** | **`videoadinpod`** | Dimensionen [Ad in pod position](/help/components/dimensions/sm-ads.md) för direktuppspelande medietjänster. | varchar(255) |
| **`post_`** | **`videoadlength`** | Dimensionen [Ad length (variabel)](/help/components/dimensions/sm-ads.md) för direktuppspelande medietjänster. | heltal |
| **`post_`** | **`videoadname`** | Dimensionen [Ad name (variabel)](/help/components/dimensions/sm-ads.md) för direktuppspelande medietjänster. | varchar(255) |
| **`post_`** | **`videoadplayername`** | Dimensionen för [annonsspelarnamn](/help/components/dimensions/sm-ads.md) för direktuppspelande medietjänster. | varchar(255) |
| **`post_`** | **`videoadpod`** | Dimensionen [Ad pod](/help/components/dimensions/sm-ads.md) för direktuppspelande medietjänster. | varchar(255) |
| **`post_`** | **`videoadvertiser`** | Dimensionen [Advertiser](/help/components/dimensions/sm-ads.md) för direktuppspelande medietjänster. | varchar(255) |
| | **`videoaudioalbum`** | Dimensionen [Album](/help/components/dimensions/sm-audio-metadata.md) för direktuppspelande medietjänster. | varchar(255) |
| | **`videoaudioartist`** | Dimensionen [Konstnär](/help/components/dimensions/sm-audio-metadata.md) för direktuppspelande medietjänster. | varchar(255) |
| | **`videoaudioauthor`** | Dimensionen [Författare](/help/components/dimensions/sm-audio-metadata.md) för direktuppspelande medietjänster. | varchar(255) |
| | **`videoaudiolabel`** | Dimensionen [Etikett](/help/components/dimensions/sm-audio-metadata.md) för direktuppspelande medietjänster. | varchar(255) |
| | **`videoaudiopublisher`** | Dimensionen [Utgivare](/help/components/dimensions/sm-audio-metadata.md) för direktuppspelande medietjänster. | varchar(255) |
| | **`videoaudiostation`** | Dimensionen [Station](/help/components/dimensions/sm-audio-metadata.md) för direktuppspelande medietjänster. | varchar(255) |
| **`post_`** | **`videocampaign`** | Dimensionen [Kampanj-ID](/help/components/dimensions/sm-ads.md) för direktuppspelande medietjänster. | varchar(255) |
| **`post_`** | **`videochannel`** | Dimensionen [Medietjänster för direktuppspelning i innehållskanalen](/help/components/dimensions/sm-core.md). | varchar(255) |
| **`post_`** | **`videochapter`** | Dimensionen [Kapitel](/help/components/dimensions/sm-chapters.md) för direktuppspelande medietjänster. | varchar(255) |
| **`post_`** | **`videocontenttype`** | Dimensionen för [innehållstyp](/help/components/dimensions/sm-core.md) för direktuppspelande medietjänster. | varchar(255) |
| **`post_`** | **`videodaypart`** | [Dagdelen](/help/components/dimensions/sm-video-metadata.md) av dimensionen för tjänster för direktuppspelning av media. | varchar(255) |
| **`post_`** | **`videoepisode`** | Dimensionen för [Episod](/help/components/dimensions/sm-video-metadata.md) för direktuppspelande medietjänster. | varchar(255) |
| **`post_`** | **`videofeedtype`** | Dimensionen för [Medieflödestyp](/help/components/dimensions/sm-video-metadata.md) för direktuppspelande medietjänster. | varchar(255) |
| **`post_`** | **`videogenre`** | Dimensionen [Genre](/help/components/dimensions/sm-video-metadata.md) för direktuppspelande medietjänster. Denna dimension tillåter flera värden i samma träff, avgränsade med kommatecken. | text |
| **`post_`** | **`videolength`** | Dimensionen [Innehållslängd (variabel)](/help/components/dimensions/sm-core.md) för direktuppspelande medietjänster. | heltal |
| **`post_`** | **`videomvpd`** | Dimensionen [MVPD](/help/components/dimensions/sm-video-metadata.md) för direktuppspelande medietjänster. | varchar(255) |
| **`post_`** | **`videoname`** | Dimensionen [Innehållsnamn (variabel)](/help/components/dimensions/sm-core.md) för direktuppspelande medietjänster. | varchar(255) |
| **`post_`** | **`videonetwork`** | Dimensionen [Nätverks](/help/components/dimensions/sm-video-metadata.md) för direktuppspelande medietjänster. | varchar(255) |
| **`post_`** | **`videopath`** | Dimensionen för [mediesökväg](/help/components/dimensions/sm-core.md) för direktuppspelning av medietjänster. | varchar(100) |
| **`post_`** | **`videoplayername`** | Dimensionen för [Innehållsspelarens namn](/help/components/dimensions/sm-core.md) för direktuppspelande medietjänster. | varchar(255) |
| **`post_`** | **`videoqoebitrateaverageevar`** | Den [genomsnittliga bithastigheten](/help/components/dimensions/sm-quality.md) för tjänster för direktuppspelning av media. | varchar(255) |
| **`post_`** | **`videoqoebitratechangecountevar`** | [Bithastigheten ändras](/help/components/dimensions/sm-quality.md) i dimensionen för direktuppspelande medietjänster. | varchar(255) |
| **`post_`** | **`videoqoebuffercountevar`** | Dimensionen för [Bufferthändelser](/help/components/dimensions/sm-quality.md) för direktuppspelande medietjänster. | varchar(255) |
| **`post_`** | **`videoqoebuffertimeevar`** | Dimensionen för [Total buffertvaraktighet](/help/components/dimensions/sm-quality.md) för direktuppspelande medietjänster. | varchar(255) |
| **`post_`** | **`videoqoedroppedframecountevar`** | Dimensionen för [uteslutna bildrutor](/help/components/dimensions/sm-quality.md) för direktuppspelande medietjänster. | varchar(255) |
| **`post_`** | **`videoqoeerrorcountevar`** | Dimensionen [Fel](/help/components/dimensions/sm-quality.md) för direktuppspelande medietjänster. | varchar(255) |
| | **`videoqoeextneralerrors`** | Dimensionen [Externa fel-ID:n](/help/components/dimensions/sm-quality.md) för direktuppspelande medietjänster. Denna dimension tillåter flera värden i samma träff. | text |
| **`post_`** | **`videoqoeplayersdkerrors`** | [Player SDK-fel-ID:n](/help/components/dimensions/sm-quality.md) för direktuppspelning av medietjänster. Denna dimension tillåter flera värden i samma träff. | text |
| **`post_`** | **`videoqoetimetostartevar`** | Den [tid det tar att starta](/help/components/dimensions/sm-quality.md)-dimensionen för direktuppspelande medietjänster. | varchar(255) |
| **`post_`** | **`videoseason`** | Dimensionen [Säsong](/help/components/dimensions/sm-video-metadata.md) för direktuppspelande medietjänster. | varchar(255) |
| **`post_`** | **`videosegment`** | Dimensionen [Innehållssegment](/help/components/dimensions/sm-core.md) för direktuppspelande medietjänster. | varchar(255) |
| **`post_`** | **`videosessionid`** | Dimensionen [Media session-ID](/help/components/dimensions/sm-core.md) för direktuppspelande medietjänster. | varchar(255) |
| **`post_`** | **`videoshow`** | Dimensionen [Visa](/help/components/dimensions/sm-video-metadata.md) för direktuppspelande medietjänster. | varchar(255) |
| **`post_`** | **`videoshowtype`** | Dimensionen för [Visa typ](/help/components/dimensions/sm-video-metadata.md) för direktuppspelande medietjänster. | varchar(255) |
| | **`videostreamtype`** | Dimensionen för [direktuppspelningstyp](/help/components/dimensions/sm-core.md) för medietjänster. | varchar(255) |
| **`post_`** | **`visid_high`** | Används med `visid_low` för att unikt identifiera en besökare. | bigint unsigned |
| **`post_`** | **`visid_low`** | Används med `visid_high` för att unikt identifiera en besökare. | bigint unsigned |
| | **`visid_new`** | En flagga som avgör om träffen innehåller ett nyligen genererat besökar-ID. | char(1) |
| | **`visid_timestamp`** | Om ett besökar-ID nyligen genereras, anger tidsstämpeln i UNIX®-tid när besökar-ID:t genererades. | int |
| **`post_`** | **`visid_type`** | Ej för extern användning; används internt av Adobe för optimering av bearbetningen. Ett numeriskt ID som representerar den metod som används för att identifiera besökaren.<br>`0`: Anpassat besökar-ID eller Okänt/ej tillämpligt<br>`1`: IP- och användaragentåtergång <br>`2`: HTTP Mobile Subscriber Header <br>`3`: Legacy cookie value (`s_vi`) <br>`4`: Fallback cookie value (`s_fid`) <br>`5`: Identity Service | tinyint unsigned |
| **`post_`** | **`visit_keywords`** | Dimensionen [Söknyckelord](/help/components/dimensions/search-keyword.md). I den här kolumnen används en icke-standard teckengräns på varchar(244) för att rymma den serverlogik som används av Adobe. Den efterbearbetade kolumnen är `**post_keywords**`, inte `**post_visit_keywords**`. | varchar(244) |
| | **`visit_num`** | Dimensionen [Besök nummer](/help/components/dimensions/visit-number.md). Börjar vid 1 och ökar stegvis varje gång ett nytt besök påbörjas per besökare. | int unsigned |
| | **`visit_page_num`** | Dimensionen [Träff](/help/components/dimensions/hit-depth.md). Ökar med 1 för varje träff som besökaren skapar. Återställer varje besök. | int unsigned |
| | **`visit_referrer`** | Den första referenten till besöket. | varchar(255) |
| | **`visit_ref_domain`** | Baserat på kolumnen `visit_referrer`. Den första refererande domänen för besöket. | varchar(100) |
| | **`visit_ref_type`** | Ett numeriskt ID som representerar referenstypen för besökets första referent. Refererar till `referrer_type.tsv`-söktabellen. | tinyint unsigned |
| | **`visit_search_engine`** | Ett numeriskt ID som representerar besökets första sökmotor. Refererar till `search_engines.tsv`-söktabellen. | smallint unsigned |
| | **`visit_start_pagename`** | [Sida](/help/components/dimensions/page.md) av besökets första träff. | varchar(100) |
| | **`visit_start_page_url`** | URL till besökets första träff. | varchar(255) |
| | **`visit_start_time_gmt`** | Tidsstämpel (i UNIX®-tid) för första besöket. | int |
| | **`weekly_visitor`** | En flagga som avgör om träffen är en ny besökare varje vecka. | tinyint unsigned |
| | **`yearly_visitor`** | En flagga som avgör om träffen är en ny årlig besökare. | tinyint unsigned |
| **`post_`** | **`zip`** | Hjälper till att fylla i dimensionen [Postnummer](/help/components/dimensions/zip-code.md). Se även `geo_zip`. | varchar(50) |

## Oanvända eller indragna kolumner

Följande kolumnlista är oanvända, indragna eller innehåller inget värde i rapporteringen. Vissa av dessa kolumner är kopplade till funktioner som har solnedgångar, medan andra inte längre behövs på grund av nya och mer robusta funktioner. De flesta av dessa kolumner innehåller inga data. Kolumner som fortfarande kan innehålla data stöds inte av aktuella datainsamlingsbibliotek och är inte tillgängliga dimensioner i Analysis Workspace.

| Bokför | Kolumnnamn |
| ---: | :--- |
| `post_` | `adclassificationcreative` |
| | `click_action` |
| | `click_action_type` |
| | `click_context` |
| | `click_context_type` |
| | `click_sourceid` |
| | `click_tag` |
| | `dataprivacydmaconsent` |
| `post_` | `hier1` - `hier5` |
| | `homepage` |
| | `ip2` |
| | `mobileacquisitionclicks` |
| | `mobileactioninapptime` |
| | `mobileactiontotaltime` |
| | `mobileappperformanceaffectedusers` |
| | `mobileappperformanceappid.app-perf-app-name` |
| | `mobileappperformanceappid.app-perf-platform` |
| | `mobileappperformancecrashes` |
| | `mobileappperformancecrashid.app-perf-crash-name` |
| | `mobileappperformanceloads` |
| | `mobileappstoreavgrating` |
| | `mobileappstoredownloads` |
| | `mobileappstoreinapprevenue` |
| | `mobileappstoreinapproyalties` |
| | `mobileappstoreobjectid.app-store-user` |
| | `mobileappstoreobjectid.application-name` |
| | `mobileappstoreobjectid.application-version` |
| | `mobileappstoreobjectid.appstore-name` |
| | `mobileappstoreobjectid.category-name` |
| | `mobileappstoreobjectid.country-name` |
| | `mobileappstoreobjectid.device-manufacturer` |
| | `mobileappstoreobjectid.device-name` |
| | `mobileappstoreobjectid.in-app-name` |
| | `mobileappstoreobjectid.platform-name-version` |
| | `mobileappstoreobjectid.rank-category-type` |
| | `mobileappstoreobjectid.region-name` |
| | `mobileappstoreobjectid.review-comment` |
| | `mobileappstoreobjectid.review-title` |
| | `mobileappstoreoneoffrevenue` |
| | `mobileappstoreoneoffroyalties` |
| | `mobileappstorepurchases` |
| | `mobileappstorerank` |
| | `mobileappstorerankdivisor` |
| | `mobileappstorerating` |
| | `mobileappstoreratingdivisor` |
| | `mobileavgprevsessionlength` |
| | `mobilecrashes` |
| | `mobilecrashrate` |
| | `mobiledailyengagedusers` |
| | `mobiledayssincelastupgrade` |
| | `mobiledeeplinkid.name` |
| | `mobileinstalls` |
| | `mobilelaunches` |
| | `mobilelaunchessincelastupgrade` |
| `post_` | `mobileltv` |
| | `mobileltvtotal` |
| `post_` | `mobilemessageclicks` |
| `post_` | `mobilemessageid.dest` |
| `post_` | `mobilemessageid.name` |
| `post_` | `mobilemessageid.type` |
| `post_` | `mobilemessageimpressions` |
| `post_` | `mobilemessagepushpayloadid.name` |
| `post_` | `mobilemessageviews` |
| | `mobilemonthlyengagedusers` |
| | `mobileosenvironment` |
| | `mobileplacedwelltime` |
| | `mobileplaceentry` |
| | `mobileplaceexit` |
| | `mobileprevsessionlength` |
| | `mobilerelaunchcampaigntrackingcode.name` |
| | `mobileupgrades` |
| | `namespace` |
| | `p_plugins` |
| `post_` | `page_event_var3` |
| `post_` | `partner_plugins` |
| | `plugins` |
| | `prev_page` |
| | `product_merchandising` |
| | `sampled_hit` |
| | `service` |
| `post_` | `socialaccountandappids` |
| `post_` | `socialassettrackingcode` |
| `post_` | `socialauthor` |
| `post_` | `socialaveragesentiment` |
| `post_` | `socialaveragesentiment (deprecated)` |
| `post_` | `socialcontentprovider` |
| `post_` | `socialfbstories` |
| `post_` | `socialfbstorytellers` |
| `post_` | `socialinteractioncount` |
| `post_` | `socialinteractiontype` |
| `post_` | `sociallanguage` |
| `post_` | `sociallatlong` |
| `post_` | `sociallikeadds` |
| `post_` | `sociallink` |
| `post_` | `sociallink (deprecated)` |
| `post_` | `socialmentions` |
| `post_` | `socialowneddefinitioninsighttype` |
| `post_` | `socialowneddefinitioninsightvalue` |
| `post_` | `socialowneddefinitionmetric` |
| `post_` | `socialowneddefinitionpropertyvspost` |
| `post_` | `socialownedpostids` |
| `post_` | `socialownedpropertyid` |
| `post_` | `socialownedpropertyname` |
| `post_` | `socialownedpropertypropertyvsapp` |
| `post_` | `socialpageviews` |
| `post_` | `socialpostviews` |
| `post_` | `socialproperty` |
| `post_` | `socialproperty (deprecated)` |
| `post_` | `socialpubcomments` |
| `post_` | `socialpubposts` |
| `post_` | `socialpubrecommends` |
| `post_` | `socialpubsubscribers` |
| `post_` | `socialterm` |
| `post_` | `socialtermslist` |
| `post_` | `socialtermslist (deprecated)` |
| `post_` | `socialtotalsentiment` |
| `post_` | `state` |
| `post_` | `survey` |
| | `survey_instances` |
| | `tnt_post_vista` |
| | `ua_color` |
| | `ua_os` |
| | `ua_pixels` |
| | `videoadload` |
| `post_` | `videoauthorized` |
| | `videoaverageminuteaudience` |
| | `videochaptercomplete` |
| | `videochapterstart` |
| | `videochaptertime` |
| | `videopause` |
| | `videopausecount` |
| | `videopausetime` |
| | `videoplay` |
| | `videoprogress10` |
| | `videoprogress25` |
| | `videoprogress50` |
| | `videoprogress75` |
| | `videoprogress96` |
| | `videoqoebitrateaverage` |
| | `videoqoebitratechange` |
| | `videoqoebuffer` |
| | `videoqoedropbeforestart` |
| | `videoqoedroppedframes` |
| | `videoqoeerror` |
| | `videoresume` |
| | `videotime` |
| | `videototaltime` |
| | `videouniquetimeplayed` |

>[!MORELIKETHIS]
>
>[Variabelmappning för XDM-objekt](/help/implement/aep-edge/xdm-var-mapping.md)
>[Variabelmappning för dataobjekt &#x200B;](/help/implement/aep-edge/data-var-mapping.md)
