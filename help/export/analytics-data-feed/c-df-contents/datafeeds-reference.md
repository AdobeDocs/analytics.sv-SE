---
description: Tabelldata som beskriver kolumnerna i dataflödet.
keywords: Datafeed;kolumner
subtopic: data feeds
title: Referens för datakolumn
feature: Data Feeds
exl-id: e1492147-6e7f-4921-b509-898e7efda596
source-git-commit: 66be48d0f41061d259cc53fb835ebd155294a710
workflow-type: tm+mt
source-wordcount: '3415'
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
>De flesta kolumner innehåller en liknande kolumn med ett prefix på `post_`. Post-kolumner innehåller värden efter serversidans logik, bearbetningsregler och VISTA-regler. Adobe rekommenderar att du i de flesta fall använder inläggskolumner. Se [Vanliga frågor om dataflöden](../df-faq.md) för mer information.

Tidigare uppdateringar av tabellen finns på den här sidans [implementeringshistorik på GitHub](https://github.com/AdobeDocs/analytics.en/commits/main/help/export/analytics-data-feed/c-df-contents/datafeeds-reference.md).

| Kolumnnamn | Kolumnbeskrivning | Datatyp |
| --- | --- | --- |
| **`accept_language`** | Visar alla godkända språk enligt HTTP-huvudet Accept-Language i en bildbegäran. | char(20) |
| **`adload`** | Inläsningar av mediaannonser | varchar(255) |
| **`aemassetid`** | En variabel med flera värden som motsvarar tillgångs-ID:n (GUID) för en uppsättning Adobe Experience Manager Assets. Ökar imponeringshändelser. | SMS |
| **`aemassetsource`** | Identifierar källan till tillgångshändelsen. Används i Adobe Experience Manager. | Varchar(255) |
| **`aemclickedassetid`** | Tillgångs-ID för en Adobe Experience Manager-resurs. Ökningar Klicka på händelser. | varchar(255) |
| **`browser`** | Ett numeriskt ID som representerar webbläsaren. Refererar till `browser.tsv` uppslagstabell. | int osignerad |
| **`browser_height`** | Dimensionen [Webbläsarhöjd](/help/components/dimensions/browser-height.md) . | smallint osignerad |
| **`browser_width`** | Webbläsarens [bredd](/help/components/dimensions/browser-width.md) | smallint unsigned |
| **`c_color`** | Färgpalettens bitdjup. Används som en del av beräkningen av [Färgdjup](/help/components/dimensions/color-depth.md) dimension. AppMeasurementet använder JavaScript-funktionen `screen.colorDepth()`. | char(20) |
| **`campaign`** | The [Spårningskod](/help/components/dimensions/tracking-code.md) dimension. | varchar(255) |
| **`carrier`** | Integrationsvariabel Adobe Advertising. Anger mobiloperatör. Nyckelvärdet för `carrier.tsv` [Dynamisk sökning](dynamic-lookups.md). | varchar(100) |
| **`ch_hdr`** | Klienttips som samlats in via HTTP-begärandehuvudet. | text |
| **`ch_js`** | Klienttips som samlats in via JavaScript-API:t för användaragentklienten. | text |
| **`channel`** | The [Platsavsnitt](/help/components/dimensions/site-section.md) dimension. | varchar(100) |
| **`clickmaplink`** | Activity Map link | varchar(255) |
| **`clickmaplinkbyregion`** | Activity Map länk per region | varchar(255) |
| **`clickmappage`** | Activity Map page | varchar(255) |
| **`clickmapregion`** | Activity Map | varchar(255) |
| **`code_ver`** | API- eller klient-SDK-version som används för att kompilera och skicka bildbegäran. | char(16) |
| **`color`** | ID för färgdjup baserat på värdet för `c_color` kolumn. Refererar till `color_depth.tsv` uppslagstabell. | smallint unsigned |
| **`connection_type`** | Ett numeriskt ID som representerar anslutningstypen. The [Anslutningstyp](/help/components/dimensions/connection-type.md) dimension. Refererar till `connection_type.tsv` uppslagstabell. | tinyint unsigned |
| **`cookies`** | The [Cookie-stöd](/help/components/dimensions/cookie-support.md) dimension.<br>Y: Aktiverad<br>N: Inaktiverad<br>U: Okänd | char(1) |
| **`country`** | Ett numeriskt ID som representerar besökarens land. Refererar till `country.tsv` uppslagstabell. | smallint unsigned |
| **`ct_connect_type`** | Relaterat till `connection_type` kolumn. De vanligaste värdena är LAN/Wifi, mobiloperatör och modem. | char(20) |
| **`curr_factor`** | Bestämmer valutadecimalen och används för valutakonvertering. USD använder till exempel två decimaler, så det här kolumnvärdet blir `2`. | tinyint |
| **`curr_rate`** | Växelkursen när transaktionen inträffade. Adobe samarbetar med XE för att fastställa dagens växelkurs. | decimal(24,12) |
| **`currency`** | Valutakoden som användes under transaktionen. Ange med [`currencyCode`](/help/implement/vars/config-vars/currencycode.md). | char(8) |
| **`cust_hit_time_gmt`** | Endast tidsstämpelaktiverade rapportsviter. Tidsstämpeln som skickades med träffen, baserat på UNIX®-tid. | int |
| **`cust_visid`** | Anpassat besökar-ID, om det anges med [`visitorID`](/help/implement/vars/config-vars/visitorid.md). | Varchar(255) |
| **`daily_visitor`** | En flagga som avgör om träffen är en ny daglig besökare. | tinyint unsigned |
| **`dataprivacyconsentoptin`** | The [Medgivandehanteringsanmälan](/help/components/dimensions/cm-opt-in.md) dimension. Flera värden kan förekomma per träff, avgränsade med ett rör (`\|`). Giltiga värden är `DMP` och `SELL`. | varchar(100) |
| **`dataprivacyconsentoptout`** | The [Avanmäl dig till hantering av samtycke](/help/components/dimensions/cm-opt-out.md) dimension. Flera värden kan finnas per träff, avgränsade med ett lodstreck (`\|`). Giltiga värden är `SSF`, `DMP`och `SELL`. | varchar(100) |
| **`dataprivacydmaconsent`** | Ett värde som identifierar om samtycke inhämtas för att skicka data från Adobe Analytics via Adobe Advertising till tredjepartsannonsleverantörer (t.ex. Google). Se [Samtycke](/help/components/dimensions/ad-consent.md) till annons för mer information. | varchar(100) |
| **`date_time`** | Tidpunkten för träffen i läsbart format, baserat på rapportsvitens tidszon. | datetime |
| **`domain`** | The [Domän](/help/components/dimensions/domain.md) dimension. Baserat på besökarens Internetanslutningspunkt. | varchar(100) |
| **`duplicate_events`** | Listar varje händelse som räknats som en dubblett. | varchar(255) |
| **`duplicate_purchase`** | En flagga som avgör om köphändelsen för den här träffen ignoreras eftersom den är en dubblett. | tinyint unsigned |
| **`duplicated_from`** | Används endast i rapportsviter som innehåller VISTA-regler för träffkopior. Anger vilken rapportsvit som träffen kopierades från. | varchar(40) |
| **`ef_id`** | The `ef_id` används i integreringar med Adobe Advertising. | varchar(255) |
| **`evar1 - evar250`** | Egna variabler 1-250. Används i [eVar](/help/components/dimensions/evar.md) dimensioner. Varje organisation använder eVars på olika sätt. Det bästa stället för mer information om hur er organisation fyller i respektive eVars är en [konstruktionsdokument](/help/implement/prepare/solution-design.md) specifikt för din organisation. | varchar(255) |
| **`event_list`** | Kommaavgränsad lista med numeriska ID:n som representerar händelser som utlöses vid träffen. Innehåller både standardhändelser och [anpassade händelser 1-1000](/help/components/metrics/custom-events.md). Användningsområden `event.tsv` sökning. | text |
| **`exclude_hit`** | En flagga som avgör om träffen utesluts från rapportering. The `visit_num` kolumnen ökas inte för uteslutna träffar.<br>1: Används inte. En del av en skrapad funktion.<br>2: Används inte. En del av en skrapad funktion.<br>3: Används inte längre. Undantag för användaragent<br>4: Uteslutning baserad på IP-adress<br>5: Information om vitala träffar saknas, till exempel `page_url`, `pagename`, `page_event`, eller `event_list`<br>6: JavaScript bearbetade inte träffen korrekt<br>7: Kontospecifikt undantag, t.ex. i VISTA-regler<br>8: Används inte. Alternativt kontospecifikt undantag.<br>9: Används inte. En del av en skrapad funktion.<br>10: Ogiltig valutakod<br>11: Träffen saknade en tidsstämpel i en rapportsvit med endast tidsstämpling, eller en träff innehöll en tidsstämpel i en rapportsserie utan tidsstämpel<br>12: Används inte. En del av en skrapad funktion.<br>13: Används inte. En del av en skrapad funktion.<br>14: Målträff som inte matchar en Analytics-träff<br>15: Används inte för närvarande.<br>16: Advertising Cloud slog till som inte matchade en Analytics-träff | tinyint unsigned |
| **`first_hit_page_url`** | Besökarens allra första URL. | varchar(255) |
| **`first_hit_pagename`** | The [Startsida, original](/help/components/dimensions/entry-dimensions.md) dimension. Besökarens ursprungliga startsidnamn. | varchar(100) |
| **`first_hit_ref_domain`** | The [Ursprunglig hänvisande domän](/help/components/dimensions/original-referring-domain.md) dimension. Baserat på `first_hit_referrer`. Den första refererande domänen för besökaren. | varchar(100) |
| **`first_hit_ref_type`** | Ett numeriskt ID som representerar referenstypen för besökarens första referent. Refererar till `referrer_type.tsv` uppslagstabell. | tinyint unsigned |
| **`first_hit_referrer`** | Den första refererande URL:en för besökaren. | varchar(255) |
| **`first_hit_time_gmt`** | Tidsstämpel för besökarens första träff i UNIX®-tid. | int |
| **`geo_city`** | Namnet på den stad som träffen kom från, baserat på IP. Används i [Städer](/help/components/dimensions/cities.md) dimension. | char(32) |
| **`geo_country`** | Förkortningen för det land som träffen kom från, baserat på IP. Används i [Länder](/help/components/dimensions/countries.md) dimension. | char(4) |
| **`geo_dma`** | Ett numeriskt ID för det demografiska område som träffen kom från, baserat på IP. Används i den amerikanska DMA-dimensionen[](/help/components/dimensions/us-dma.md). | int osignerad |
| **`geo_region`** | Namnet på den stat eller region som träffen kom från, baserat på IP. Används i [Regioner](/help/components/dimensions/regions.md) dimension. | char(32) |
| **`geo_zip`** | Postnumret som träffen kom från, baserat på IP. Hjälper dig fylla i [Postnummer](/help/components/dimensions/zip-code.md) dimension. Se även `zip`. | varchar(16) |
| **`hit_source`** | Källan som träffen kom från. Träffkällor 1, 2 och 6 faktureras. <br>1: Standardbegäran om bild utan tidsstämpel <br>2: Standardbegäran om bilder med tidsstämpel <br>3: Överföring av Live-datakälla med tidsstämplar <br>4: Används inte <br>5: Allmän överföring av datakälla <br>6: Överföring av datakälla med fullständig bearbetning <br>7: Överföring av datakälla för TransactionID <br>8: Används inte längre; Tidigare versioner av Adobe Advertising Cloud datakällor <br>9: Används inte längre; Adobe Social sammanfattningsmått <br>10: Vidarebefordran på serversidan i Audience Manager används | tinyint unsigned |
| **`hit_time_gmt`** | Tidsstämpeln för träffservrarna för datainsamling i Adobe fick träffen, baserat på UNIX®-tid. | int |
| **`hitid_high`** | Används med `hitid_low` för att identifiera en träff. | bigint unsigned |
| **`hitid_low`** | Används med `hitid_high` för att identifiera en träff. | bigint unsigned |
| **`hourly_visitor`** | En flagga som avgör om träffen är en ny timbesökare. | tinyint unsigned |
| **`ip`** | IPv4-adressen, baserad på HTTP-huvudet i bildbegäran. Endast för `ipv6`; om den här kolumnen innehåller en icke-komplicerad IP-adress, `ipv6` är tom. | char(20) |
| **`ipv6`** | Den komprimerade IPv6-adressen, om den är tillgänglig. Endast för `ip`; om den här kolumnen innehåller en icke-komplicerad IP-adress, `ip` är tom. | varchar(40) |
| **`j_jscript`** | Den version av JavaScript som stöds av webbläsaren. | char(5) |
| **`java_enabled`** | The [[!UICONTROL Java enabled]](/help/components/dimensions/java-enabled.md). <br>Y: Aktiverad <br>N: Inaktiverad <br>U: Okänd | char(1) |
| **`javascript`** | Ett söknings-ID för JavaScript-version, baserat på `j_jscript`. Refererar till `javascript_version` uppslagstabell. | tinyint unsigned |
| **`language`** | Ett numeriskt ID som representerar besökarens språk. Refererar till `languages.tsv` uppslagstabell. | smallint unsigned |
| **`last_hit_time_gmt`** | Tidsstämpel (i UNIX®-tid) för föregående träff. Används för att beräkna [[!UICONTROL Days since last visit]](/help/components/dimensions/days-since-last-visit.md) dimension. | int |
| **`last_purchase_num`** | The [Kundlojalitet](/help/components/dimensions/customer-loyalty.md) dimension. Antalet tidigare inköp som besökaren har gjort. <br>0: Inga tidigare inköp (inte en kund) <br>1: 1 föregående köp (ny kund) <br>2: 2 tidigare inköp (returkund) <br>3: 3 eller fler tidigare inköp (lojal kund) | int unsigned |
| **`last_purchase_time_gmt`** | Används i [[!UICONTROL Days since last purchase]](/help/components/dimensions/days-since-last-purchase.md) dimension. Tidsstämpel (i UNIX®-tid) för det senaste köpet. För förstagångsköp och besökare som inte har gjort något inköp tidigare är det här värdet `0`. | int |
| **`latlon1`** | Placering (ned till 10 km) | varchar(255) |
| **`latlon23`** | Plats (ned till 100 m) | varchar(255) |
| **`latlon45`** | Plats (ned till 1 m) | varchar(255) |
| **`mc_audiences`** | Lista med Audience Manager segment-ID:n som besökaren tillhör. The `post_mc_audiences` kolumnen ändrar avgränsaren till `--**--`. | text |
| **`mcvisid`** | Experience Cloud Visitor-ID. 128-bitars nummer som består av två sammanfogade 64-bitars tal som fyllts med 19 siffror. | varchar(255) |
| **`mobile_id`** | Om användaren använder en mobil enhet anger du enhetens numeriska ID. Nyckelvärdet för `mobile_attributes.tsv` [Dynamisk sökning](dynamic-lookups.md). | int |
| **`mobileaction`** | Mobilåtgärd. Samlas in automatiskt när `trackAction` används i mobilimplementeringar. Tillåter automatisk åtgärdspunkt i appen. | varchar(100) |
| **`mobileappid`** | ID för mobilapp. Lagrar programnamnet och versionen i följande format: `[AppName] [BundleVersion]` | varchar(255) |
| **`mobileappperformanceappid`** | Används i Apteligent-dataanslutningen. Program-ID som används i Apteligent. | varchar(255) |
| **`mobileappperformancecrashid`** | Används i Apteligent-dataanslutningen. Det krasch-ID som används i Apteligent. | varchar(255) |
| **`mobileappstoreobjectid`** | Används i [!DNL Appfigures] dataanslutning. Objekt-ID för App Store. | varchar(255) |
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
| **`mobiledeeplinkid`** | Samlas in från kontextdatavariabeln `a.deeplink.id`. Används i förvärvsrapporter som en identifierare för länken för mobilförvärv. | varchar(255) |
| **`mobiledevice`** | Namn på mobil enhet. I iOS lagras den som en kommaavgränsad tvåsiffrig sträng. Det första numret representerar enhetsgenereringen och det andra representerar enhetsfamiljen. | varchar(255) |
| **`mobilehourofday`** | Definierar timmen på dagen då appen startades. Använder ett numeriskt format på 24 timmar. | varchar(255) |
| **`mobileinstalldate`** | Datum för mobilinstallation. Anger datumet för första gången som en användare öppnar mobilappen. | varchar(255) |
| **`mobilelaunchnumber`** | Ökningar med ett varje gång mobilappen startas. | varchar(255) |
| **`mobilemessagebuttonname`** | Samlas in från kontextdatavariabeln `a.message.button.id`. Används för meddelanden i appen för att identifiera knappen som stängde meddelandet. | varchar(100) |
| **`mobilemessageid`** | Meddelande-ID i appen | Varchar(255) |
| **`mobilemessageonline`** | Meddelande i appen online | varchar(255) |
| **`mobilemessagepushoptin`** | Samlas in från kontextdatavariabeln `a.push.optin`. Ange som&quot;true&quot; när användaren väljer att skicka meddelanden, annars är värdet&quot;false&quot;. | varchar(255) |
| **`mobilemessagepushpayloadid`** | Samlas in från kontextdatavariabeln `a.push.payloadid`. Används i push-meddelanden som nyttolast-ID. | varchar(255) |
| **`mobileosversion`** | Mobiltjänstens operativsystemversion | varchar(255) |
| **`mobileplaceaccuracy`** | Samlas in från kontextdatavariabeln `a.loc.acc`. Anger GPS-noggrannheten i meter vid insamlingen. | varchar(255) |
| **`mobileplacecategory`** | Samlas in från kontextdatavariabeln `a.loc.category`. Beskriver kategorin för en viss plats. | varchar(255) |
| **`mobileplaceid`** | Samlas in från kontextdatavariabeln `a.loc.id`. Identifierare för en viss intressepunkt. | varchar(255) |
| **`mobilepushoptin`** | Push-deltagande för mobiltjänster | varchar(255) |
| **`mobilepushpayloadid`** | Push-nyttolast-ID för mobiltjänster | varchar(255) |
| **`mobilerelaunchcampaigncontent`** | Startinnehåll för mobiltjänster | varchar(255) |
| **`mobilerelaunchcampaignmedium`** | Startmedium för mobiltjänster | varchar(255) |
| **`mobilerelaunchcampaignsource`** | Startkälla för Mobile Services | varchar(255) |
| **`mobilerelaunchcampaignterm`** | Startperiod för Mobile Services | varchar(255) |
| **`mobilerelaunchcampaigntrackingcode`** | Samlas in från kontextdatavariabeln `a.launch.campaign.trackingcode`. Används i anskaffning som spårningskod för lanseringskampanj. | varchar(255) |
| **`mobileresolution`** | Den mobila enhetens upplösning. `[Width] x [Height]` i pixlar. | varchar(255) |
| **`monthly_visitor`** | En flagga som avgör om besökaren är unik för den aktuella månaden. | tinyint unsigned |
| **`mvvar1`** - `mvvar3` | [Listvariabel](/help/implement/vars/page-vars/list.md) värden. Innehåller en avgränsad lista med anpassade värden beroende på implementering. The `post_mvvar1` - `post_mvvar3` kolumner ersätter den ursprungliga avgränsaren med `--**--`. | text |
| **`mvvar1_instances`** - `mvvar3_instances` | Listvariabelvärdena som angavs för den aktuella träffen. Ersätter den ursprungliga avgränsaren med `--**--`. Har inte en `post` kolumn. | text |
| **`new_visit`** | En flagga som avgör om den aktuella träffen är ett nytt besök. Anges av Adobe efter 30 minuters besöksinaktivitet. | tinyint unsigned |
| **`os`** | Ett numeriskt ID som representerar besökarens operativsystem. Baserat på `user_agent` kolumn. Nyckelvärdet för `operating_system.tsv` standardsökning och `operating_system_type.tsv` [Dynamisk sökning](dynamic-lookups.md). | int unsigned |
| **`page_event`** | Den typ av träff som skickas i bildbegäran (standardträff, nedladdningslänk, anpassad länk, slutlänk). Se [Sökning efter sidhändelse](datafeeds-page-event.md). | tinyint unsigned |
| **`page_event_var1`** | Används endast vid förfrågningar om länkspårningsbilder. URL-adressen till den nedladdningslänk, den avslutningslänk eller anpassade länk som du klickar på. | text |
| **`page_event_var2`** | Används endast vid förfrågningar om länkspårningsbilder. Länkens anpassade namn (om det anges). Anger [Egen länk](/help/components/dimensions/custom-link.md), [Hämta länk](/help/components/dimensions/download-link.md), eller [Avsluta länk](/help/components/dimensions/exit-link.md) beroende på värdet i `page_event`. | varchar(100) |
| **`page_type`** | Dimensionen [Sidor hittades](/help/components/dimensions/pages-not-found.md) inte, som vanligtvis används för 404-sidor. | Röding(20) |
| **`page_url`** | Webbadressen till träffen. Observera att `post_page_url` det är avskalat för bildbegäranden för länkspårning ([`tl()`](/help/implement/vars/functions/tl-method.md)) och använder datatypen varchar(255). | text |
| **`pagename`** | The [Sida](/help/components/dimensions/page.md) dimension. Om [`pagename`](/help/implement/vars/page-vars/pagename.md) variabeln är tom, Analytics använder `page_url` i stället. | varchar(100) |
| **`pagename_no_url`** | Liknar `pagename`, förutom att den inte går tillbaka till `page_url`. Endast `post` -kolumnen är tillgänglig. | varchar(100) |
| **`paid_search`** | En flagga som avgör om träffen matchar betalsökningsidentifiering. | tinyint unsigned |
| **`persistent_cookie`** | Används i [Stöd för permanenta cookies](/help/components/dimensions/persistent-cookie-support.md) dimension. Anger om besökaren stöder cookies som inte tas bort efter varje träff. | char(1) |
| **`pointofinterest`** | Intressepunktsnamn för mobiltjänster | varchar(255) |
| **`pointofinterestdistance`** | Avstånd för mobiltjänster till intressanta center | varchar(255) |
| **`post_`** kolumner | Innehåller det värde som används i rapporterna. Varje inläggskolumn fylls i efter serversidans logik, bearbetningsregler och VISTA-regler. Adobe rekommenderar att du i de flesta fall använder inläggskolumner. | Se respektive icke-postkolumn |
| **`product_list`** | The [`products`](/help/implement/vars/page-vars/products.md) sidvariabel. Hjälper till att fylla i flera dimensioner och mätvärden, inklusive [Kategori](/help/components/dimensions/category.md), [Produkt](/help/components/dimensions/product.md), [Enheter](/help/components/metrics/units.md)och [Intäkter](/help/components/metrics/revenue.md). | text |
| **`prop1`** - `prop75` | Anpassade trafikvariabler 1-75. Används i [Prop](/help/components/dimensions/prop.md) dimensioner. | varchar(100) |
| **`purchaseid`** | Unik identifierare för ett köp, enligt inställningen med [`purchaseID`](/help/implement/vars/page-vars/purchaseid.md) variabel. Används av `duplicate_purchase` kolumn. | char(20) |
| **`quarterly_visitor`** | En flagga som avgör om träffen är en ny kvartalsbesökare. | tinyint unsigned |
| **`ref_domain`** | The [Refererande domän](/help/components/dimensions/referring-domain.md) dimension. Baserat på `referrer` kolumn. | varchar(100) |
| **`ref_type`** | Ett numeriskt ID som representerar typen av hänvisning för träffen. Används i [Referenstyp](/help/components/dimensions/referrer-type.md) dimension. <br>1: Inuti din webbplats<br>2: Andra webbplatser <br>3: Sökmotorer <br>4: hårddisk <br>5: USENET <br>6: Typed/Bookmarked (ingen referent) <br>7: E-post <br>8: Inget JavaScript <br>9: Sociala nätverk | tinyint unsigned |
| **`referrer`** | The [Referent](/help/components/dimensions/referrer.md) dimension. Observera att while `referrer` använder datatypen varchar(255) `post_referrer` och datatypen varchar(244). | Varchar(255) |
| **`resolution`** | Ett numeriskt ID som representerar bildskärmens upplösning. Används i dimensionen [Bildskärmsupplösning](/help/components/dimensions/monitor-resolution.md) . Använder `resolution.tsv` uppslagstabell. | smallint unsigned |
| **`s_kwcid`** | Nyckelords-ID som används i Adobe Advertising-integreringar. | Varchar(255) |
| **`s_resolution`** | Värde för rå skärmupplösning. Samlas in med hjälp av JavaScript-funktionen `screen.width x screen.height`. | Röding(20) |
| **`search_engine`** | Ett numeriskt ID som representerar sökmotorn som hänvisade besökaren till din webbplats. Används i [Sökmotor](/help/components/dimensions/search-engine.md) dimensioner. Refererar till `search_engines.tsv` uppslagstabell. | smallint unsigned |
| **`search_page_num`** | Används av [Alla söksidrankning](/help/components/dimensions/all-search-page-rank.md) dimension. Anger vilken sida med sökresultat som din webbplats visade sig på innan användaren klickade igenom till din webbplats. | smallint unsigned |
| **`secondary_hit`** | En flagga som avgör om träffen är en sekundär träff. Den här flaggan kommer vanligtvis från taggar för flera programsviter och VISTA-regler som kopierar träffar. | tinyint unsigned |
| **`sourceid`** | SOURCE ID | int unsigned |
| **`state`** | State-variabel. | varchar(50) |
| **`stats_server`** | Inte till nytta. Adobes interna server som bearbetade träffen. | Röding(30) |
| **`t_time_info`** | Lokal tid för besökaren. Formatet är: `M/D/YYYY HH:MM:SS Month (0-11, 0=January) Timezone offset (in minutes)` | varchar(100) |
| **`tnt`** | Används i Adobe Target integreringar. Representerar alla tester som är kvalificerade för tillfället. Formatet är: `TargetCampaignID:TargetRecipeID:TargetType\|Event/Action`. | text |
| **`tnt_action`** | Används i Adobe Target integreringar. Representerar alla tester som träffen är kvalificerad för. | text |
| **`tnt_instances`** | Används i Adobe Target integreringar. Målförekomstvariabel. | text |
| **`transactionid`** | En unik identifierare där olika datapunkter kan överföras senare via datakällor. Samlas med [`transactionID`](/help/implement/vars/page-vars/transactionid.md) variabel. | text |
| **`truncated_hit`** | En flagga som anger att bildbegäran har trunkerats. Anger att en partiell träff togs emot. <br>Y: Träff trunkerades; partiell träff togs emot <br>N: Träff trunkerades inte, fullständig träff mottagen | char(1) |
| **`user_agent`** | Användaragentsträngen som skickas i HTTP-huvudet i bildbegäran. | text |
| **`user_hash`** | Inte till användning. Hash för rapportens Suite-ID. Använd `username` i stället. | int unsigned |
| **`user_server`** | Används i [Server](/help/components/dimensions/server.md) dimension. | varchar(100) |
| **`userid`** | Inte till användning. Det numeriska ID:t för rapportsvitens ID. Använd `username` i stället. | int unsigned |
| **`username`** | Rapportsvitens ID för träffen. | char(40) |
| **`va_closer_detail`** | The [Senaste beröringsdetalj](/help/components/dimensions/last-touch-detail.md) dimension. | varchar(255) |
| **`va_closer_id`** | Ett numeriskt ID som identifierar [Senaste beröringskanal](/help/components/dimensions/last-touch-channel.md) dimension. Sökningen efter detta ID finns i Marketing Channel Manager. | tinyint unsigned |
| **`va_finder_detail`** | The [Första beröringsdetalj](/help/components/dimensions/first-touch-detail.md) dimension. | varchar(255) |
| **`va_finder_id`** | Ett numeriskt ID som identifierar [Första beröringskanalen](/help/components/dimensions/first-touch-channel.md) dimension. Sökningen efter detta ID finns i Marketing Channel Manager. | Tinyint osignerad |
| **`va_instance_event`** | En flagga som identifierar Marketing Channel-instanser[](/help/components/metrics/instances.md). | Tinyint osignerad |
| **`va_new_engagement`** | En flagga som identifierar nya engagemang för](/help/components/metrics/new-engagements.md) marknadsföringskanalen[. | tinyint unsigned |
| **`video`** | Videoinnehåll | varchar(255) |
| **`videoad`** | Namn på videoannons | Varchar(255) |
| **`videoadinpod`** | Videoannons i poddposition | varchar(255) |
| **`videoadlength`** | Videoannons | heltal |
| **`videoadload`** | Videoannonser | varchar(255) |
| **`videoadname`** | Namn på videoannons | varchar(255) |
| **`videoadplayername`** | Namn på video- och videospelare | varchar(255) |
| **`videoadpod`** | Video och pod | varchar(255) |
| **`videoadvertiser`** | Annonsör av videoklipp | Varchar(255) |
| **`videoaudioalbum`** | Videoalbum med ljud | Varchar(255) |
| **`videoaudioartist`** | Videoljudartist | varchar(255) |
| **`videoaudioauthor`** | Videoljudförfattare | varchar(255) |
| **`videoaudiolabel`** | Etikett för videoljud | varchar(255) |
| **`videoaudiopublisher`** | Videoljudspublicering | varchar(255) |
| **`videoaudiostation`** | Videoljudstation | varchar(255) |
| **`videocampaign`** | Videokurs | varchar(255) |
| **`videochannel`** | Videokanal | varchar(255) |
| **`videochapter`** | Namn på videokapitel | varchar(255) |
| **`videocontenttype`** | Videoinnehållstyp. Ange automatiskt som Video för alla videovyer | varchar(255) |
| **`videodaypart`** | Video day part | varchar(255) |
| **`videoepisode`** | Videoavsnitt | varchar(255) |
| **`videofeedtype`** | Typ av videofeed | varchar(255) |
| **`videogenre`** | Videogenre | text |
| **`videolength`** | Videolängd | heltal |
| **`videomvpd`** | Video MVPD | varchar(255) |
| **`videoname`** | Videonamn | varchar(255) |
| **`videonetwork`** | Videonätverk | varchar(255) |
| **`videopath`** | Videosökväg | varchar(100) |
| **`videoplayername`** | Videospelarens namn | Varchar(255) |
| **`videotime`** | Tid för video | heltal |
| **`videoqoebitrateaverageevar`** | Genomsnittlig bithastighet för videokvalitet | varchar(255) |
| **`videoqoebitratechangecountevar`** | Antal ändringar av videokvalitet | Varchar(255) |
| **`videoqoebuffercountevar`** | Antal buffertar för videokvalitet | varchar(255) |
| **`videoqoebuffertimeevar`** | Bufferttid för videokvalitet | varchar(255) |
| **`videoqoedroppedframecountevar`** | Antal uteslutna bildrutor för videokvalitet | varchar(255) |
| **`videoqoeerrorcountevar`** | Antal fel för videokvalitet | varchar(255) |
| **`videoqoeextneralerrors`** | Externa fel i videokvalitet | text |
| **`videoqoeplayersdkerrors`** | SDK-fel för videokvalitet | text |
| **`videoqoetimetostartevar`** | Videokvalitetstid för att starta | Varchar(255) |
| **`videoseason`** | Video säsong | Varchar(255) |
| **`videosegment`** | Videosegment | varchar(255) |
| **`videoshow`** | Videoprogram | varchar(255) |
| **`videoshowtype`** | Videovisningstyp | varchar(255) |
| **`videostreamtype`** | Typ av videoström | varchar(255) |
| **`visid_high`** | Används med `visid_low` för att unikt identifiera en besökare. | bigint unsigned |
| **`visid_low`** | Används med `visid_high` för att unikt identifiera en besökare. | Bigint osignerad |
| **`visid_new`** | En flagga som avgör om träffen innehåller ett nyligen genererat besökar-ID. | char(1) |
| **`visid_timestamp`** | Om ett besökar-ID nyligen genereras, anger tidsstämpeln i UNIX®-tid när besökar-ID:t genererades. | int |
| **`visid_type`** | Ej för extern användning; används internt av Adobe för optimering av bearbetning. Ett numeriskt ID som representerar den metod som används för att identifiera besökaren.<br>`0`: Anpassat besökar-ID eller Okänt/ej tillämpligt<br>`1`: Reserv <br>`2`för IP- och användaragent: HTTP Mobile Subscriber Header <br>`3`: Äldre cookie-värde (`s_vi`) <br>`4`: Reservcookie-värde (`s_fid`) <br>`5`: Identity Service | Tinyint osignerad |
| **`visit_keywords`** | Dimensionen Sökord[](/help/components/dimensions/search-keyword.md). I den här kolumnen används en teckenbegränsning som inte är standard för varchar(244) för att hantera backend-logik som används av Adobe. | Varchar(244) |
| **`visit_num`** | The [Besöksnummer](/help/components/dimensions/visit-number.md) dimension. Börjar vid 1 och ökar stegvis varje gång ett nytt besök påbörjas per besökare. | int unsigned |
| **`visit_page_num`** | The [Träffdjup](/help/components/dimensions/hit-depth.md) dimension. Ökar med 1 för varje träff som besökaren skapar. Återställer varje besök. | int unsigned |
| **`visit_ref_domain`** | Baserat på `visit_referrer` kolumn. Den första refererande domänen för besöket. | varchar(100) |
| **`visit_ref_type`** | Ett numeriskt ID som representerar referenstypen för besökets första referent. Refererar till `referrer_type.tsv` uppslagstabell. | tinyint unsigned |
| **`visit_referrer`** | Den första referenten till besöket. | varchar(255) |
| **`visit_search_engine`** | Ett numeriskt ID som representerar besökets första sökmotor. Refererar till `search_engines.tsv` uppslagstabell. | smallint unsigned |
| **`visit_start_page_url`** | Besökets första URL. | varchar(255) |
| **`visit_start_pagename`** | Värdet för Sidnamn i den första träffen av besöket. | varchar(100) |
| **`visit_start_time_gmt`** | Tidsstämpel (i UNIX®-tid) för första besöket. | int |
| **`weekly_visitor`** | En flagga som avgör om träffen är en ny besökare varje vecka. | tinyint unsigned |
| **`yearly_visitor`** | En flagga som avgör om träffen är en ny årlig besökare. | tinyint unsigned |
| **`zip`** | Hjälper dig fylla i [Postnummer](/help/components/dimensions/zip-code.md) dimension. Se även `geo_zip`. | varchar(50) |

{style="table-layout:auto"}

## Oanvända eller indragna kolumner

Följande kolumnlista används inte och innehåller vanligtvis inga data. Kolumner som innehåller data stöds inte av aktuella datainsamlingsbibliotek och är inte tillgängliga i Analysis Workspace.

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
