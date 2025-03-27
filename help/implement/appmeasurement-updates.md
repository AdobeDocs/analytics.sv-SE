---
title: Versionsinformation om AppMeasurement för JavaScript
description: Versionsinformation för AppMeasurement för JavaScript.
feature: Appmeasurement Implementation
exl-id: 80b935f0-3ec5-4ffa-9858-f83ae9a6b763
role: Admin, Developer, Leader, User
source-git-commit: 886c6070936275cf1df269a951b87d041fcf7b8c
workflow-type: tm+mt
source-wordcount: '2726'
ht-degree: 3%

---

# Versionsinformation om AppMeasurement för JavaScript

>[!IMPORTANT]
>
>Från om med mars 2025 kommer den här artikeln inte längre att uppdateras. Du kan visa versionsinformation för och hämta den senaste versionen av AppMeasurement från [GitHub](https://github.com/adobe/appmeasurement/releases).


## Version 2.27.0

Releasedatum: **12 augusti 2024**

* Cookien `s_ac` skrivs nu med flaggan `secure` om `writeSecureCookies` har aktiverats.
* Korrigerade ett initieringsfel när biblioteket är inbäddat.
* Ett fel har korrigerats om `localStorage` eller `sessionStorage` har inaktiverats.
* Tips för High Entropy-användaragent ingår nu i länkspårningsanrop (`tl`) om `collectHighEntropyUserAgentHints` har aktiverats.

## Version 2.26.0

Releasedatum: **4 mars 2024**

* AppMeasurement känner automatiskt igen och använder rotdomänen för landskodens toppnivådomäner, som tidigare krävde särskilda cookie-domänkonfigurationer. Uppdatering kan få konsekvenser på grund av den här automatiska igenkänningen. Mer information finns i [`cookieDomainPeriods`](/help/implement/vars/config-vars/cookiedomainperiods.md).
* Distribution inkluderar Identity Service Library 5.5.0 och Data Integration Library 9.6.

## Version 2.25.0

Releasedatum: **12 september 2023**

* Den valfria metoden [`bufferRequests()`](vars/functions/bufferrequests.md) har lagts till för att förbättra tillförlitligheten vid hämtning av begäranden när en webbläsare inte stöder Beacon API eller avbryter begäranden när en sida tas bort.
* Lagt till skydd för att förhindra flera återanrop efter spåret för en enda begäran om spårning.

## Version 2.24.0

Releasedatum: **18 juli 2023**

* Den valfria konfigurationsvariabeln [`decodeLinkParameters`](vars/config-vars/decodelinkparameters.md) har lagts till för att avkoda länk-URL:er som innehåller dubbelbytetecken.
* Ytterligare felhantering har lagts till för webbläsare med felaktiga API:er för användaragenttips.
* Rubriken POST-innehållstyp har ändrats till `x-www-form-urlencoded` som standard.

## Version 2.23.0

Releasedatum: **23 september 2022**

* AppMeasurement har nu stöd för en samling klienttips för användaragenter med hög entropi som används i Chromium-webbläsare (Google Chrome och Microsoft Edge) för att tillhandahålla enhetsinformation. Du kan konfigurera klienttips via taggar eller använda konfigurationsvariabeln [`collectHighEntropyUserAgentHints`](vars/config-vars/collecthighentropyuseragenthints.md). Samling med hög entropi-tips är inaktiverad som standard. Läs mer om användaragenten [klienttips](/help/technotes/client-hints.md).

## Version 2.22.4

Releasedatum: **18 januari 2022**

* Anropet `s.tl()` för länkspårning verifierar nu att objektet som skickas till det innehåller ett `href`-attribut av typen `string`. Om det inte är en `string` ignorerar den attributet `href` utan att misslyckas. Detta scenario kan inträffa när du skickar `svg` objekt till länkspårningsanropet.

## Version 2.22.3

Releasedatum: **11 oktober 2021**

* Uppdaterade länkar i filer som pekar på dokumentation.

## Version 2.22.2

Releasedatum: **7 september 2021**

* Den här uppdateringen gör att `opt.dmp` och `opt.sell` alltid inkluderas när länkar spåras. Mer information finns i [Sekretessrapporteringen](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/privacy-reporting.md) i användarhandboken för Admin.

## Version 2.22.1

Releasedatum: **17 augusti 2021**

* Kunder som avanmäler sig kan ha sett att avanmälningsparametrarna på serversidan inte respekteras vid spårning av länkar. Korrigeringarna i den här versionen gör att avanmälningsflaggorna skickas om de finns när länkar spåras.

## Version 2.22.0

Releasedatum: **4 augusti 2020**

* Korrigera för saknad hänvisare när första träffen inte skickades på grund av användarens avanmälningsinställningar.

## Version 2.21.0

Releasedatum: **24 juni 2020**

* Ett problem har korrigerats där Activity Map linkExclusions-filtret inte alltid tillämpades för Firefox.

## Version 2.20.0

Releasedatum: **5 mars 2020**

* Ett säkerhetsrelaterat problem har korrigerats genom att Internet Explorer-identifieringen uppdaterades för att inaktivera JSLint-varning.

## Version 2.19.0

Releasedatum: **21 februari 2020**

* Uppdaterad målgruppshanteringsmodul till DIL 9.4. (AN-209341)

## Version 2.18.0

Releasedatum: **13 februari 2020**

* AppMeasurement kan nu tvinga cookies att inkludera attributet Secure genom att ange variabeln [`writeSecureCookies`](vars/config-vars/writesecurecookies.md). Kravet för den här variabeln är att hela klientwebbplatsen hanteras säkert (HTTPS). (AN-204604)

## Version 2.17.0

Releasedatum: **23 augusti 2019**

* Stöd för ändring av frågesträngar i Baidu har lagts till. (AN-182483)
* Korrigerade ett problem som orsakade inaktuella besökarvärden i träffar som placerades i kö i väntan på deltagande. (AN-184391)

## Version 2.16.0

Releasedatum: **15 augusti 2019**

* `sendBeacon`-stöd har implementerats i [!UICONTROL AppMeasurement] för avslutningslänkar. Om en träff använder `sendBeacon` och sidan tas bort är begäran fortfarande slutförd. Detta är mycket användbart för avslutslänkar eftersom det är mer sannolikt att träffen når datainsamlingsservrar. (AN-175142)
* ECID-/FID-värden cachelagras nu vid den första träffen trots att OptIn-inställningarna ändras. (AN-175142)
* Audience Management Module har uppdaterats till DIL 9.3. (AN-182704)
* Växeln i `s.ActivityMap.trackScrollReach` exponerades för att aktivera eller inaktivera rullningsspårning. (AN-182754)
* Uppgraderade AppMeasurement till att använda Visitor ID Service 4.4.0. (AN-182912)

## Version 2.15.0

Releasedatum: **15 juli 2019**

* Lagt till spårning av rullningsområde för ActivityMap i Activity Map-tillägget (AN-172949)
* DIL 9.2 har lagts till i AppMeasurement (AN-182472)

## Version 2.14.0

Releasedatum: **21 maj 2019**

* Problem med hanteringen av spårarparametrarnas tillstånd när flera träffar väntar har åtgärdats. (AN-176931, AN-176629, DTM-12758)
* Uppdaterat AppMeasurement med Visitor.js 4.3.0 (AN-180049)

## Version 2.13.0

Releasedatum: **10 april 2019**

* Åtgärda många rapporterade problem med clearVars. Problemet inträffar när träffar skickas ut innan spåraren är klar. När spåraren är klar kan biblioteket ange variabler som redan har rensats eller ändrats. (AN-176931, AN-176629, DTM-12758)

## Version 2.12.0

Releasedatum: **22 februari 2019**

* Uppdaterad målgruppshanteringsmodul till DIL 9.1. (AN-175255)
* GTM-säkerhetsprincipen tillåter inte Activity Map-modulen. (AN-174679)
* Förbättrade AppMeasurement för att efterleva avanmälan när identitetstjänsten inte har godkänts i avanmälan. (AN-175259)

## Version 2.11.0

Releasedatum: **11 februari 2019**

* Stöd för de nya funktionerna för avanmälningstjänster från Adobe i AppMeasurement har lagts till. (AN-163546)
* Stöd för lagring av länkspårningsdata i sessionslagring har lagts till. (AN-162272)
* Stöd för medieströmstyp för ljudanalys har lagts till. (AN-173265)

## Version 2.10.0

Releasedatum: **20 september 2018**

Den här versionen ser till att biblioteket [!DNL AppMeasurement] skickar cookies korrekt för alla anslutningstyper.

* [!DNL AppMeasurement] blockerar överföringar av cookies under POST. (AN-165538)
* Släpp stöd för XDomainRequest. (AN-165733)
* Minska standardlivstiden för cookies från [!DNL AppMeasurement] från fem till två år. (AN-158572)
* Ta bort mediemodulen från kodhanteraren ( [!DNL AppMeasurement]) (AN-166590)

## Version 2.9.0

Releasedatum: **24 maj 2018**

>[!NOTE]
>
>Besökar-API 3.0 eller senare krävs för kunder som använder ID-tjänsten [!DNL Experience Cloud]. Adobe rekommenderar att du uppgraderar till den senaste versionen av Visitor API när associerade kodbibliotek uppdateras ( [!DNL at.js], [!DNL AppMeasurement.js] osv.).

* [!DNL AppMeasurement] har uppdaterats för att använda det uppdaterade besökargränssnittet för att begära ID:n. (AN-151483)
* Ett problem har korrigerats där cookie för länkspårning fortsätter att skrivas efter att länkspårning har inaktiverats. (AN-156332)
* Korrigerade ett problem där `registerPreTrackCallback` och `registerPostTrackCallback` bryter återanropsfunktionens signatur vid flera anrop. (AN-158566)

## Version 2.8.2

Releasedatum: **12 april 2018**

* Uppdatera [!DNL AppMeasurement] om du vill använda det uppdaterade besökargränssnittet för att begära ID:n. (AN-151483)
* En cookie för länkspårning skrivs när länkspårning är inaktiverat. (AN-156332)
* Minska standardlivstiden för cookies från [!DNL AppMeasurement] från fem till två år. (AN-158572)

## Version 2.8.1

Releasedatum: **29 mars 2018**

Återpaketera Visitor API 3.1.0 (AN-159524), som innehåller snabbkorrigeringarna (CORE-11390, CORE-10634)

## Version 2.8.0

Releasedatum: **15 mars 2018**

Återpaketera Visitor API 3.1.0 (AN-159524), som innehåller snabbkorrigeringarna (CORE-11390, CORE-10634)

* Paket med VAPI v3.1 med [!DNL AppMeasurement] v2.8. (AN-158353)
* Reaktorn bygger datainsamlingens slutpunkt för att underlätta delning. (AN-156647)
* Lägg till timingstatistik för rundtur av begäranden i [!DNL AppMeasurement]. (AN-158343)

## Version 2.7.0

Releasedatum: **18 januari 2018**

* Släpper stöd för IE 6 till 9
* Inkludering av Visitor API v3.0.0
* DIL v7.00 ingår

## Version 2.6.0

Releasedatum: **9 november 2017**

Ett problem har korrigerats där [!DNL AppMeasurement]-biblioteket inte alltid ställer in rätt kontokombination när s_gl anropas. (AN-152153)

## Version 2.5.0

Releasedatum: **21 september 2017**

* Inkludering av [!DNL dil.js 6.12] ( [!DNL Audience Manager] modul)
* Inkludering av Visitor API 2.5.0.

## Version 2.4.0

Releasedatum: **17 augusti 2017**

* Inkludera dil.js v6.11
* Inkludera Visitor API 2.4.0

## Version 2.3.0

Releasedatum: **20 juli 2017**

* Korrigerat fel där `s.Util.getQueryParam` hämtade `#`
* Tillagd v6.10 av `dil.js` (AN-145701)

## Version 2.2.0

Releasedatum: **8 juni 2017**

* Stöd har lagts till för flera [!DNL AppMeasurement]-instansieringsorder. (AN-138237)
* Inkludering av version 2.2.0 Visitor API. (AN-144042)

## Version 2.1.0

Releasedatum: **20 april 2017**

* Inkluderade den senaste versionen av `dil.js` (AN-140396)
* Stöd har lagts till för parametern `adobe_mc_ref` som åsidosätter sidreferenten. (AN-131920)
* Återinkluderade besökar-API 2.1.0. (AN-140873)
* `mcorgid`-parametern har lagts till. (AN-139586)
* Tillagd cp-parameter (customerPerspective). (AN-140897)

## Version 2.0.0

Releasedatum: **9 mars 2017**

* Flyttad till en ny byggprocess som kräver en versionsnummeruppdatering till 2.0.0. (AN-137878)
* Flyttade mboxMCSDID-hantering till rätt avsnittsplats där spårningsanropet görs. (AN-138483)

## Version 1.8.0

Releasedatum: **19 januari 2017**

* Inkludera VisitorAPI 2.0.0
* Funktionsanrop och kontroller som görs om så att SDID förbrukas när avbrottskontrollen har slutförts. (AN-134364)
* `s.registerPreTrackCallback` och `s.registerPostTrackCallback` kopplingar har lagts till. (AN-134567)

## Version 1.7.0

Uppdaterat: **11 november 2016**

* Inkludera Visitor API 1.10.1.
* Uppdatera modulen [!DNL Audience Manager] med DIL 6.6 (Demdex Integration Library). (AN-132065)
* Inkludering av Visitor API 1.9.0. (AN-132072)
* Uppdatera [!DNL AppMeasurement] [!DNL Audience Manager] modul med DIL 6.5 och ytterligare konfigurationer (AN-129411)
* Inkludering av Visitor API 1.8.0 (AN-129887)

## Version 1.6.4

Uppdaterat: **18 augusti 2016**

* [!DNL AppMeasurement] har uppdaterats för att läsa och skriva AMCV-cookies. (AN-127098)
* Inkludering av Visitor API 1.7.0.

>[!NOTE]
>
>Se även följande versionsinformation för [!DNL JavaScript] version 1.6.3, som innehåller uppdaterade krav för tjänsten Experience Cloud ID.

## Version 1.6.3

Uppdaterat: **4 augusti 2016**

* Ett problem har korrigerats där [!DNL AppMeasurement] avslutade anslutningar för begäran för tidigt. (AN-126448)

>[!IMPORTANT]
>
>Version 1.6.0 av [!DNL Experience Cloud] ID-tjänsten *kräver* [!DNL AppMeasurement] för [!DNL JavaScript] version 1.6.3 eller senare. Om du vill uppgradera till version 1.6.0 av Experience Cloud ID-tjänsten måste du använda AppMeasurement 1.6.3 eller senare.

## Version 1.6.2

Releasedatum: **21 juli 2016**

* Inkludering av Visitor API 1.6.0.
* Korrigerade ett problem som fick [!DNL AppMeasurement] att anropa fel förvrängda metod i Visitor API. (AN-126006)
* Korrigerade ett problem som orsakade felet [!DNL JavaScript]: &quot;Attributet är endast giltigt på v:image&quot;. (AN-124009)

## Version 1.6.1

Releasedatum: **16 juni 2016**

* Inkludering av Visitor API 1.5.7.
* Hanteringen av länkklicksspårning i Firefox som inte utlöste complete-händelsen har åtgärdats.

## Version 1.6

Releasedatum: **21 april 2016**

* Activity Map-modulen [!DNL AppMeasurement] har integrerats i standardmodulen [!DNL AppMeasurement] så att du bara behöver referera till en [!DNL .js]-fil. Dessutom är Activity Map tracking aktiverat som standard. (AN-112689)
* Ett trunkeringsproblem som uppstod med ordningen för frågesträngsvariabler i [!DNL AppMeasurement] har korrigerats, så att *`pageURLRest`* är sist. (AN-114647)

## Version 1.5.4

Releasedatum: **17 mars 2016**

* Inkludering av besökar-API 1.5.4
* Stöd för avanmälan till Visitor API 1.5.4+

## Version 1.5.3

Releasedatum: **21 januari 2016**

* Hanteringen av modulen [!DNL Audience Manager] har korrigerats när POST används för att spåra anrop. (AN-115381)
* Flyttade resten av sidans URL (&quot;-g&quot;) till slutet av frågesträngen för spårningsbegäran. (AN-114647)

## Version 1.5.2

Releasedatum: **5 november 2015**

* Inkludering av Visitor API 1.5.3.
* Fast detection of IE11 for URL Truncation 2047 (AN-114914)

## Version 1.5.1

Releasedatum: **17 september 2015**

* Inkludering av besökar-API 1.5.2
* [!DNL Audience Manager]-modulen har uppdaterats för att använda Adobe Audience Manager DIL 6.2 - getCustomer-ID:n från VisitorAPI.js och skicka dem i /event-anropet till Adobe Audience Manager. (AN-104978)

## Version 1.5

Releasedatum: **18 juni 2015**

* Stöd för Visitor API 1.5, som använder metoden *`getCustomerIDs`* för att samla in kund-ID:n och autentiserade tillstånd, och skickar ID:n med datainsamlingsbegäranden.
* Korrigerade skapandet av en dubblett av måliframe i modulen **[!UICONTROL AudienceManagement]** (DIL 6.1)
* Åtgärdade det kända problemet som beskrivs i version 1.4.5.

## Version 1.4.5

Releasedatum: **21 maj 2015**

* Med början i iOS SDK version 4.5 kan du med ett nytt iOS-tillägg samla in användningsdata från dina Apple Watch-appar, Idag-widgetar, Photo Editing-widgetar och alla andra iOS-tilläggsappar.
* Med början i Android SDK version 4.5 kan du med ett nytt Android-tillägg samla in data från din Android app.
* Inkludering av Visitor API 1.4.
* AudienceManagement-modulen har uppdaterats för att använda DIL version 6.0.

>[!NOTE]
>
>**Känt fel**: I integreringar med Visitor API / [!DNL AppMeasurement] [!DNL Audience Manager] Module finns det två iFrame-målpubliceringsbegäranden som har gjorts i IE6-9: `//fast.<subdomain>.demdex.net/dest5.html` och `//fast.<subdomain>.demdex.net/dest4.html`. Det korrekta beteendet, som det visas i andra webbläsare, är att bara läsa in `//fast.<subdomain>.demdex.net/dest5.html`.

## Version 1.4.4

Releasedatum: **16 april 2015**

* Nu kan du inkludera anpassade kontextdatavariabler med livscykelvärden.
* `trackBeacon`- och `clearCurrentBeacon`-anropen är nu tillgängliga i PhoneGap.
* En mindre korrigering för att rensa ID:t för ljusserveranropsprofilen efter `trackLight`-anropet.

## Version 1.4.3

Releasedatum: **19 februari 2015**

* Hanteringen av fördröjda spårningsanrop är konsekvent, vilket åtgärdar problem med säkerhetskopierade variabler under fördröjningen, till exempel klickade objekt.
* Ändrad till att inte utföra automatisk spårning av referenser efter det första spårningsanropet, så att det andra, tredje, osv. spårningsanropet (vanligtvis länkspårning) inte dubbelräknar referenten när *`s.referrer`* ställdes in manuellt före det första spårningsanropet.
* Distributionszippen uppdaterades så att den innehöll Visitor API 1.3.5.

## Version 1.4.2

Releasedatum: **15 januari 2015**

* Korrigerad hantering av WebKit-förrenderingshantering för att förhindra spårning av förrenderade sidor som inte visas.
* Distributionszippen uppdaterades så att den innehöll Visitor API 1.3.4 och en uppdaterad **[!UICONTROL AudienceManagement]**-modul som innehåller DIL version 5.5.

## Version 1.4.1

Releasedatum: **18 september 2014**

* En `tagContainerMarker`-variabel har lagts till som tillåter implementeringen att ange upp till 4 tecken som har lagts till i versionssträngen tillsammans med en extra avgränsare för strecktecken. Detta används av dynamisk tagghantering.

  ```js
  // JavaScript
  s.tagContainerMarker = "D1.0";
  
  // Data Collection request
  //.../b/ss/myrsid/1/JS-1.4.1-D1.0/s43317392037311?...
  ```

  De fyra tecknen är begränsade till tecken som tillåts i URL-filsökvägar, t.ex. alfanumeriska tecken och punkter.

* På sidor som är dubbeltaggade med H-kod har en loop som kan inträffa vid automatisk länkspårning (hämtning och avslut) korrigerats med när fast länkspårning är aktiverat (standard i Webkit-webbläsare). Dessutom lades en allmän skyddsåtgärd till runt automatisk länkspårning för att förhindra liknande slingor. Den här skyddsfunktionen begränsar automatisk länkspårning av upprepade klickningar till objektet *same* till en gång var 10:e sekund. Skyddet gäller endast automatisk länkspårning, så manuella länkspårningsanrop (s.tl) är inte begränsade. Klickningar på olika objekt påverkas inte heller av den här skyddsfunktionen och spåras.
* Korrigerad hantering av klickade objekt när en fördröjning behövs.
* Korrigerade ett problem som orsakade ett dubbelsidigt antal sidor när s.t anropades från en länk-onclick-funktion, om Visitor-API:t inte har de värden som behövs ännu.
* Stöd för HTTP POST.

  >[!IMPORTANT]
  >
  >För att ett [!DNL Analytics]-anrop ska kunna använda metoden POST i stället för GET i [!DNL AppMeasurement] (en metod för att lösa [trunkerade URL:er i IE](https://helpx.adobe.com/analytics/kb/shortening-image-request-urls.html)) måste du använda den senaste implementeringen av Visitor ID-tjänsten för Experience Cloud.

## Version 1.4

Releasedatum: **21 augusti 2014**

* Spårning av webbläsarplugin-program (`p` frågeparameter) har tagits bort eftersom plugin-program inte längre rapporteras i version 15.
* Modulen **[!UICONTROL AudienceManagement]** har lagts till i hämtningszippen.
* Stöd för ytterligare eVars (76-250) och events (101-1000) har lagts till.

>[!NOTE]
>
>H-Code stöder inte ytterligare eVars och events.

## Version 1.3.2

Releasedatum: **19 juni 2014**

* Hanteringen av slutförda och väntande flaggor för Visitor-API-fält som det gamla [!DNL Analytics]-besökar-ID:t som orsakade fel har åtgärdats.
* Stöd för nya funktioner i besökar-ID-tjänst 1.3.

## Version 1.3.1

Releasedatum: **22 maj 2014**

* [!DNL AppMeasurement] för funktionen [!DNL JavaScript] `s_gi` kunde inte hitta instanser som skapats med H-koden `s_gi` korrekt. Observera att det här problemet endast påverkade vissa implementeringar av dubbel taggning där [!DNL AppMeasurement] för [!DNL JavaScript] och H-kod fanns på samma sida med separata instanser och `s_gi` användes för att hitta instanser per rapportserie.

## Version 1.3

Releasedatum: **17 april 2014**

* Stöd för [Experience Cloud Visitor ID-tjänsten](https://experienceleague.adobe.com/docs/id-service/using/home.html).

## Version 1.2.4

Releasedatum: **13 mars 2014**

* Felkorrigeringar för hjärtslagsvideo.

## Version 1.2.3

Releasedatum: **20 februari 2014**

* Felkorrigeringar för hjärtslagsvideo.

## Version 1.2.2

Releasedatum: **6 februari 2014**

* Ett kompatibilitetsproblem med DIL-modulen [!DNL Audience Manager] har korrigerats. [!DNL Audience Manager]-kunder måste även uppdatera till version 4.8 av DIL-modulen.

## Version 1.2.1

Releasedatum: **15 november 2013**

* Korrigerade sidhändelser som används för mätning av pulsslagvideo.

## Version 1.2

Releasedatum: **14 november 2013**

* Stöd för [Heartbeat-videomätning](https://experienceleague.adobe.com/docs/media-analytics/using/media-overview.html) har lagts till.
* `VisitorAPI.js` lades till för att stödja [besökar-ID-tjänsten](https://experienceleague.adobe.com/docs/id-service/using/home.html).

## Version 1.1.1

* Förhindrade ett anrop för länkspårning från att skickas från Opera-webbläsare för länkar som börjar med opera: (&quot;opera:&quot; liknar about:&quot; och &quot;chrome:&quot; i andra webbläsare).
* `alt=""` har lagts till i alla bildobjekt för att uppfylla kraven i Accessible Video and Communications Act.

## Version 1.1

Releasedatum: **18 september 2013**

* Korrigerat stöd för att placera biblioteket och sidkoden i taggen `head`.
* Modulen `onLoad` som saknas har lagts till.

## Version 1.0.3

Releasedatum: **15 augusti 2013**

* Stöd för driftsättning genom Adobe tagghantering har lagts till.
* Korrigerade ett problem som förhindrade att hierarkivariabler angavs för objektet [!DNL AppMeasurement].

## Version 1.0.2

Releasedatum: **18 juli 2013**

* Hash/fragment ignoreras nu av automatisk länkspårning. Tidigare spårades följande URL automatiskt eftersom hela `href` slutade i `.pdf`:

  ```js
  <a href="index.htm#anchor.pdf">Test Link</a>
  ```

  Nu ignoreras hash/fragment så länken spåras bara när filnamnet slutar i ett tillägg som matchar.

## Version 1.0.1

Releasedatum: **23 maj 2013**

Ett nytt [!DNL JavaScript] [!DNL AppMeasurement]-bibliotek är nu tillgängligt i Code Manager. Det här biblioteket har samma kärnfunktioner som [!DNL s_code.js], men är lättare och snabbare att använda på både mobila och stationära webbplatser.

* 3-7x snabbare än H.25-koden.
* Endast 21 kB okomprimerat och 8 kB gzippat (H.25-koden är 33 kB okomprimerad och 13 kB gzippad).
* Inbyggt stöd för att hämta frågeparametrar, läsa och skriva cookies och utföra avancerad länkspårning.
* Liten och snabb nog att användas med mobilsajter, och tillräckligt robust för att användas på hela datorwebben, så att du kan utnyttja ett bibliotek i alla webbmiljöer.
