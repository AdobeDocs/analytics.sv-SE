---
title: Slutet av livscykeln för fullständiga datakällor
description: Orsaker till slutet av livscykeln och jämförelser mellan API:t för inmatning av gruppdata och fullständiga datakällor för databearbetning.
exl-id: 24a44b7a-64fd-4a99-975f-4887f4638812
source-git-commit: 7cb2489c2deaf8e75c71589895314067a010caf8
workflow-type: tm+mt
source-wordcount: '1233'
ht-degree: 5%

---

# Slutet av livscykeln för fullständiga datakällor

I flera år har du kunnat skicka in data på träffnivå till Adobe Analytics med fullständig databehandling. Dessa data bearbetades på samma sätt som data som samlats in via våra JavaScript-bibliotek och SDK för mobilappar. 2020 släppte Adobe [API:t för datainmatning i grupp](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/bdia.md), som utför samma funktioner som fullständiga datakällor, men med ytterligare funktioner. Det här avsnittet innehåller information om ytterligare funktioner som tillhandahålls av API:t för inmatning av gruppdata och visar skillnader i filformat.

Från och med 25 mars 2021 kommer Adobe att förhindra att nya anslutningar för fullständiga datakällor skapas. Befintliga anslutningar stöds tills tjänsten är helt inaktuell den 31 juli 2021. Utöver vår standarddokumentation tillhandahåller vi en genomgång av de [steg som behövs för att skicka data via API:t för gruppdatainfogning](https://adobe.ly/aabdia).

## Varför upphör den här funktionen?

BDIA (Bulk Data Insertion API) ger ytterligare funktioner och täcker alla användningsfall som stöds av Fullständig bearbetning. Vi tror att du kommer att bli bättre om du använder API:t för datainfogning i grupp.

## Viktiga skillnader mellan fullständiga datakällor för databearbetning och API för inmatning av gruppdata

* Med datainfogning i grupp kan du skicka flera filer som kan bearbetas parallellt. Du kan använda besöksgrupper för att säkerställa besökarnas kontinuitet och eVar.
* Datavalidering och felhantering har funktioner för datavalidering och infogning av gruppdata, vilket eliminerar en del av det administrativa arbetet med att skicka träffdata.
* Datainfogning i grupp stöder flera alternativ för besökar-ID:n. Du kan skicka både Analytics ID och Marketing Cloud ID (mer information finns i [Identitetstjänst](https://experienceleague.adobe.com/docs/id-service/using/home.html)). Dessutom kan du använda ditt eget ID som [startvärde för att generera ett ECID](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/bdia.md#customer-id-and-experience-cloud-visitor-id-seeds).
* Datainfogning i grupp stöder list- och kontextdatavariabler.
* Datainfogning i grupp stöder inte Activity Map data.

## Viktiga skillnader i filformat och innehåll

* Det finns ytterligare obligatoriska fält för infogning av gruppdata. Mer information finns i [dokumentationen](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/bdia.md).
* För att säkerställa kontinuitet och attribuering för besökare måste rader i filer sorteras i kronologisk ordning vid infogning av massdata. Se [Besöksgrupper](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/bdia.md#visitor-groups) om du vill veta mer om ordningen för besöksaktiviteter mellan filer.
* Vid infogning av gruppdata måste filerna vara CSV-komprimerade i GZIP-format.
* BDIA använder&quot;tidsstämpel&quot; i stället för&quot;datum&quot;.

Mer information finns i följande jämförelse av fältvärden som är tillgängliga i BDIA (Bulk Data Insertion) och FPDS (Full Processing Data Sources).

## Jämförelse av fältvärden som är tillgängliga i BDIA och FPDS

| BDIA-variabel | Kolumnvariabel för fullständig bearbetning | Beskrivning |
| --- | --- | --- |
| aamlh | Stöds inte | Platstips för Adobe Audience Manager. |
| browserHeight | browserHeight | Webbläsarhöjd i pixlar (till exempel 768) |
| browserWidth | browserWidth | Webbläsarbredd i pixlar (till exempel 1024) |
| kampanj | kampanj | Kod för spårning av konverteringskampanj |
| kanal | kanal | Kanalsträng (till exempel Sport Section) |
| colorDepth | colorDepth | Bildskärmens färgdjup i bitar (t.ex. 24) |
| connectionType | connectionType | Besökarens anslutningstyp (LAN eller modem) |
| contextData.key | Stöds inte | Nyckelvärdepar anges i genom att rubriken&quot;contextData.product&quot; eller&quot;contextData.color&quot; namnges |
| cookiesEnabled | cookiesEnabled | `Y` eller  `N` om besökaren stöder cookies från första part |
| currencyCode | currencyCode | Valutakod för intäkt (till exempel `USD`) |
| customerID.[customerIDType].authState | Stöds inte | Besökarens autentiserade tillstånd. Värden som stöds är: 0, 1, 2, UNKNOWN, AUTHENTICATED, LOGGED_OUT eller &#39;&#39; (ej skiftlägeskänsligt). Två på varandra följande enkla citattecken (&#39;&#39;) gör att värdet utelämnas från frågesträngen, som översätts till 0 när träffen görs. Observera att de numeriska värden som stöds för authState anger följande: 0 = UNKNOWN, 1 = AUTHENTICATED, 2 = LOGGED_OUT. customerIDType kan vara vilken alfanumerisk sträng som helst, men ska betraktas som skiftlägeskänslig. |
| customerID.[customerIDType].id | Stöds inte | Kund-ID som ska användas. customerIDType kan vara vilken alfanumerisk sträng som helst, men ska betraktas som skiftlägeskänslig. |
| customerID.[customerIDType].isMCSeed | Stöds inte | Anger om detta är startvärdet för Marketing Cloud Visitor-ID:t. Värden som stöds är: 0, 1, TRUE, FALSE, &#39;&#39; (skiftlägesokänslig). Om du använder 0, FALSE eller två på varandra följande enkla citattecken (&#39;&#39;) utelämnas värdet från frågesträngen. customerIDType kan vara vilken alfanumerisk sträng som helst, men ska betraktas som skiftlägeskänslig. |
| eVarN | eVarN, dvs. `<eVar2>`..`<eVar>` | Konverteringsnamn för eVar. Du kan ha upp till 75 eVars ( eVar1 - eVar75 ) Du kan ange eVar namn (eVar12) eller ett eget namn (Ad Campaign 3). |
| händelser | händelser | [Händelsesträng](https://experienceleague.adobe.com/docs/analytics/implementation/vars/page-vars/events/event-serialization.html?lang=en#vars), formaterad med samma syntax som variabeln s.events. Till exempel: scAdd,event1,event7 |
| hierN | hierN, dvs. `<hier2>`..`</hier2>` | Hierarkinamn. Du kan ha upp till 5 hierarkier ( hier1 - hier5 ). Du kan ange standardnamnet för hierarkin `hier2` eller ett eget namn (Yankees). |
| homePage | homePage | Y eller N - är den aktuella sidan för besökarens hemsida. |
| ipaddress | Stöds inte | Besökarens IP-adress. |
| javaEnabled | javaEnabled | J eller N - har besökaren Java aktiverat. |
| javaScriptVersion | javaScriptVersion | JavaScript-version (till exempel 1.3). |
| språk | Stöds inte | Webbläsarens språk som stöds. Exempel, `en-us`. |
| linkName | linkName | Namn på länk. |
| linkType | linkType | Typ av länk. Värden som stöds är: `d: Download link`, `e: Exit link`, `o: Custom link`. |
| linkURL | linkURL | HREF of link. |
| list Exempelvis list2. | Stöds inte | En avgränsad lista med värden som skickas till en variabel och sedan rapporteras som enskilda radposter för rapportering |
| marketingCloudVisitorID | Stöds inte | Marketing Cloud ID. Se [Besökaridentifiering](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=en#id-service-api) och tjänsten Marketing Cloud Visitor ID |
| Stöds inte | charSet | Den teckenuppsättning som stöds för din webbplats. Exempel: UTF-8, ISO-8859-1 osv. |
| Stöds inte | clickAction | Objektidentifierare för besökarens klickkarta (oid) |
| Stöds inte | clickActionType | Objektidentifierartyp för klickkarta för besökare (oidt) |
| Stöds inte | clickContext | Sididentifierare för besökarens klickkarta (pid) |
| Stöds inte | clickContextType | Sididentifierartyp för klickkarta (pidt) för besökare |
| Stöds inte | clickSourceID | Källindex för besökarens klickkarta (oi) |
| Stöds inte | clickTag | Objekttaggsnamn för besökarens klickkarta (inte) |
| Stöds inte | scXmlVer | Marknadsföringen rapporterar XML-begärans versionsnummer (till exempel 1.0). |
| Stöds inte | tidszon | Besökarens tidszonsförskjutning från GMT i timmar (till exempel -8). |
| pageName | pageName | Sidans namn |
| pageType | pageType | Typ av sida (t.ex. &quot;Felsida&quot;). |
| pageURL | pageURL | Sidans URL (t.ex. https://www.example.com/index.html). |
| plugin-program | plugin-program | Semikolonavgränsad lista med namn på webbläsarplugin-program. |
| produkter | produkter | Lista över alla produkter på sidan. Separera produkter med kommatecken. Till exempel: Idrott;Kula;1;5.95,Leksaker; Överkant;1:1.99. |
| prop1 - prop75 | propN, dvs. `<prop2>`..`</prop2>` | Property#-sträng (till exempel Sport Section). |
| propN | propN | Egenskapsvärden för dina egenskaper. |
| purchaseID | purchaseID | Inköps-ID-nummer. |
| referent | referent | URL för sidreferenten. |
| reportSuiteID | s_account | Anger de rapportsviter där du vill skicka data. Du bör separera flera rapportpaket-ID:n med kommatecken. |
| upplösning | upplösning | Bildskärmsupplösning (till exempel 1 024 × 768). |
| server | server | Serversträng. |
| tillstånd | tillstånd | Conversion state string. |
| tidsstämpel | datum | Använd datumformatet ISO 8601 för datumformatet YYYY-MM-DDThh:mm:ss±UTC_offset (t.ex. 2021-09-01T12:00:00-07:00) eller Unix Time-format (antalet sekunder som gått sedan 1 januari 197) 0). |
| trackingServer | Stöds inte | Kan endast anges via kolumnrubrik. |
| transactionID | Stöds inte | Gemensamt värde som används för att knyta samman flerkanalsanvändaraktiviteter för rapportering. Mer information finns i [Användarhandbok för datakällor](https://experienceleague.adobe.com/docs/analytics/import/data-sources/datasrc-home.html?lang=en#data-sources). |
| userAgent | Stöds inte | Användaragentsträng |
| visitorID | visitorID | Besökarens analys-ID. Se [Besökaridentifiering](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=en). |
| zip | zip | Postnummer för konvertering. |
