---
title: Versionsinformation om AppMeasurement for JavaScript
description: Cumulative release notes for AppMeasurement for JavaScript.
feature: Appmeasurement Implementation
exl-id: 80b935f0-3ec5-4ffa-9858-f83ae9a6b763
source-git-commit: 25eccb2b9fe3827e62b0ae98d9bebf7a97b239f5
workflow-type: tm+mt
source-wordcount: '2315'
ht-degree: 2%

---

# Versionsinformation om AppMeasurement for JavaScript

Ackumulerade versionsinformation för [!DNL AppMeasurement] för JavaScript.

<!-- https://wiki.corp.adobe.com/display/omtrcache/AppMeasurement+Change+Log -->

Du kan hämta den senaste versionen av AppMeasurement i [Kodhanteraren](/help/admin/admin/code-manager-admin.md).

## Version 2.23.0

Releasedatum: **23 september 2022**

* AppMeasurement har nu stöd för en samling klienttips för användaragenter med hög entropi som används i Chromium-webbläsare (Google Chrome och Microsoft Edge) för att tillhandahålla enhetsinformation. Du kan konfigurera klienttips via taggar eller använda flaggan &quot;collectHighEntropyUserAgentHints&quot;. Samling med hög entropi-tips är som standard inaktiverad. Läs mer om User-Agent [klienttips](/help/technotes/client-hints.md).


## Version 2.22.4

Releasedatum: **18 januari 2022**

* Länkspårningsanrop `s.tl()` verifierar nu att objektet som skickas till det innehåller en `href` type-attribut `string`. Om det inte är en `string`så ignoreras de `href` i stället för att misslyckas. Detta kan inträffa om det skickas `svg` till länkspårningsanropet.

## Version 2.22.3

Releasedatum: **11 oktober 2021**

* Uppdaterade filer som refererar till hjälpdokumentationen för att peka på de aktuella hjälpplatserna.

## Version 2.22.2

Releasedatum: **7 september 2021**

* Den här uppdateringen orsakar `opt.dmp` och `opt.sell` att alltid inkluderas när länkar spåras. Här är en [fullständig förteckning över variabler för samtycke](https://experienceleague.adobe.com/docs/analytics/admin/data-governance/consent-variables.html).

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

* AppMeasurement kan nu tvinga cookies att inkludera attributet Secure genom att ställa in [`writeSecureCookies`](vars/config-vars/writesecurecookies.md) variabel. Kravet för den här variabeln är att hela klientwebbplatsen hanteras säkert (HTTPS). (AN-204604)

## Version 2.17.0

Releasedatum: **23 augusti 2019**

* Stöd för ändring av frågesträngar i Baidu har lagts till. (AN-182483)
* Korrigerade ett problem som orsakade inaktuella besökarvärden i träffar som placerades i kö i väntan på deltagande. (AN-184391)

## Version 2.16.0

Releasedatum: **15 augusti 2019**

* Implementerat `sendBeacon` stöd i [!UICONTROL AppMeasurement] för att avsluta länkar. Om en träff använder `sendBeacon` och sidan tas bort är begäran fortfarande slutförd. Detta är mycket användbart för avslutslänkar eftersom det är mer sannolikt att träffen når datainsamlingsservrar. (AN-175142)
* ECID-/FID-värden cachelagras nu vid den första träffen trots att OptIn-inställningarna ändras. (AN-175142)
* Audience Management Module har uppdaterats till DIL 9.3. (AN-182704)
* Exponerad växling in `s.ActivityMap.trackScrollReach` för att aktivera eller inaktivera spårning av rullningsräckvidd. (AN-182754)
* Uppgraderade AppMeasurement till att använda Visitor ID Service 4.4.0. (AN-182912)

## Version 2.15.0

Releasedatum: **15 juli 2019**

* Lagt till spårning av rullningsområde för ActivityMap i tillägget Activity Map (AN-172949)
* DIL 9.2 har lagts till i AppMeasurement (AN-182472)

## Version 2.14.0

Releasedatum: **21 maj 2019**

* Problem med hanteringen av spårarparametrarnas tillstånd när flera träffar väntar har åtgärdats. (AN-176931, AN-176629, DTM-12758)
* Uppdaterad AppMeasurement med Visitor.js 4.3.0 (AN-180049)

## Version 2.13.0

Releasedatum: **10 april 2019**

* Åtgärda många rapporterade problem med clearVars. Problemet inträffar när träffar skickas ut innan spåraren är klar. När spåraren är klar kan biblioteket ange variabler som redan har rensats eller ändrats. (AN-176931, AN-176629, DTM-12758).

## Version 2.12.0

Releasedatum: **22 februari 2019**

* Uppdaterad målgruppshanteringsmodul till DIL 9.1. (AN-175255)
* GTM-säkerhetsprincipen tillåter inte Activity Map-modulen. (AN-174679)
* Förbättrad AppMeasurement för att efterleva avanmälan när identitetstjänsten inte har godkänts i avanmälan. (AN-175259)

## Version 2.11.0

Releasedatum: **11 februari 2019**

* Stöd har lagts till för de nya Adobe-funktionerna för anmälningstjänster i AppMeasurement. (AN-163546)
* Stöd för lagring av länkspårningsdata i sessionslagring har lagts till. (AN-162272)
* Stöd för medieströmstyp för ljudanalys har lagts till. (AN-173265)

## Version 2.10.0

Releasedatum: **20 september 2018**

Den här versionen ser till att [!DNL AppMeasurement] biblioteket skickar cookies korrekt för alla anslutningstyper.

* [!DNL AppMeasurement] blockerar överföringar av cookies under POST. (AN-165538)
* Släpp stöd för XDomainRequest. (AN-165733)
* Minska [!DNL AppMeasurement] standardlivslängd för cookie från fem till två år. (AN-158572)
* Ta bort mediemodulen från kodhanteraren ( [!DNL AppMeasurement]) (AN-166590)

## Version 2.9.0

Releasedatum: **24 maj 2018**

>[!NOTE]
>
>Besöks-API 3.0 eller högre krävs för kunder som använder [!DNL Experience Cloud] ID-tjänst. Adobe rekommenderar att du uppgraderar till den senaste versionen av Visitor API när associerade kodbibliotek uppdateras ( [!DNL at.js], [!DNL AppMeasurement.js]och så vidare.)

* Uppdaterat [!DNL AppMeasurement] om du vill använda det uppdaterade besökargränssnittet för att begära ID:n. (AN-151483)
* Ett problem har korrigerats där cookie för länkspårning fortsätter att skrivas efter att länkspårning har inaktiverats. (AN-156332)
* Ett problem där `registerPreTrackCallback` och `registerPostTrackCallback` återanropsfunktionens signatur bryts vid flera anrop. (AN-158566)

## Version 2.8.2

Releasedatum: **12 april 2018**

* Uppdatera [!DNL AppMeasurement] om du vill använda det uppdaterade besökargränssnittet för att begära ID:n. (AN-151483)
* En cookie för länkspårning skrivs när länkspårning är inaktiverat. (AN-156332)
* Minska [!DNL AppMeasurement] standardlivslängd för cookie från fem till två år. (AN-158572)

## Version 2.8.1

Releasedatum: **29 mars 2018**

Paketera om Visitor API 3.1.0 (AN-159524), som innehåller snabbkorrigeringarna: (CORE-11390, CORE-10634)

## Version 2.8.0

Releasedatum: **15 mars 2018**

Paketera om Visitor API 3.1.0 (AN-159524), som innehåller snabbkorrigeringarna: (CORE-11390, CORE-10634)

* Paket med VAPI v3.1 med [!DNL AppMeasurement] v2.8. (AN-158353)
* Reaktorn bygger datainsamlingens slutpunkt för att underlätta delning. (AN-156647)
* Lägg till timingstatistik för rundtur av begäranden i [!DNL AppMeasurement]. (AN-158343)

## Version 2.7.0

Releasedatum: **18 januari 2018**

* Släpper stöd för IE 6 till 9
* Inkludering av Visitor API v3.0.0
* Inkludering av DIL v7.00

## Version 2.6.0

Releasedatum: **9 november 2017**

Ett problem där [!DNL AppMeasurement] biblioteket anger inte alltid rätt kontokombination när s_gl anropas. (AN-152153)

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

* Korrigerat fel där `s.Util.getQueryParam` fångad `#`
* Lagt till v6.10 av `dil.js` (AN-145701)

## Version 2.2.0

Releasedatum: **8 juni 2017**

* Stöd för flera [!DNL AppMeasurement] instansieringsordning. (AN-138237)
* Inkludering av version 2.2.0 Visitor API. (AN-144042)

## Version 2.1.0

Releasedatum: **20 april 2017**

* Den senaste versionen av `dil.js` (AN-140396)
* Stöd för `adobe_mc_ref` parameter som åsidosätter sidreferenten. (AN-131920)
* Återinkluderade besökar-API 2.1.0. (AN-140873)
* Tillagd `mcorgid` parameter. (AN-139586)
* Tillagd cp-parameter (customerPerspective). (AN-140897)

## Version 2.0.0

Releasedatum: **9 mars 2017**

* Flyttad till en ny byggprocess som kräver en versionsnummeruppdatering till 2.0.0. (AN-137878)
* Flyttade mboxMCSDID-hantering till rätt avsnittsplats där spårningsanropet görs. (AN-138483)

## Version 1.8.0

Releasedatum: **19 januari 2017**

* Inkludera VisitorAPI 2.0.0
* Funktionsanrop och kontroller som görs om så att SDID förbrukas när avbrottskontrollen har slutförts. (AN-134364)
* Tillagd `s.registerPreTrackCallback` och `s.registerPostTrackCallback` krokar. (AN-134567)

## Version 1.7.0

Uppdaterat: **11 november 2016**

* Inkludera Visitor API 1.10.1.
* Uppdatera [!DNL Audience Manager] modul med Demdex Integration Library (DIL) 6.6. (AN-132065)
* Inkludering av Visitor API 1.9.0. (AN-132072)
* Uppdatera [!DNL AppMeasurement] [!DNL Audience Manager] Modul med DIL 6.5 och ytterligare konfigurationer (AN-129411)
* Inkludering av Visitor API 1.8.0 (AN-129887)

## Version 1.6.4

Uppdaterades: **18 augusti 2016**

* Uppdaterat [!DNL AppMeasurement] läsa och skriva AMCV-cookies. (AN-127098)
* Inkludering av Visitor API 1.7.0.

>[!NOTE]
>
>Se även följande versionsinformation för [!DNL JavaScript] version 1.6.3, som innehåller uppdaterade krav för tjänsten Experience Cloud ID.

## Version 1.6.3

Uppdaterades: **4 augusti 2016**

* Ett problem där [!DNL AppMeasurement] anslutningar för begäranden som avslutades i förtid. (AN-126448)

>[!IMPORTANT]
>
>Version 1.6.0 av [!DNL Experience Cloud] ID-tjänst *kräver* [!DNL AppMeasurement] for [!DNL JavaScript] version 1.6.3 eller senare. Om du vill uppgradera till version 1.6.0 av Experience Cloud ID-tjänsten måste du använda AppMeasurement 1.6.3 eller senare.

## Version 1.6.2

Releasedatum: **21 juli 2016**

* Inkludering av Visitor API 1.6.0.
* Korrigerat ett problem som orsakade [!DNL AppMeasurement] för att anropa fel dolda metod i besökar-API:t. (AN-126006)
* Ett problem som orsakade [!DNL JavaScript] fel: &quot;Attributet är endast giltigt på v:image&quot;. (AN-124009)

## Version 1.6.1

Releasedatum: **16 juni 2016**

* Inkludering av Visitor API 1.5.7.
* Hanteringen av länkklicksspårning i Firefox som inte utlöste complete-händelsen har åtgärdats.

## Version 1.6

Releasedatum: **21 april 2016**

* The [!DNL AppMeasurement] Modulen Activity Map har integrerats i [!DNL AppMeasurement] standardmodul, så att du bara behöver referera till en [!DNL .js] -fil. Spårning av Activity Map aktiveras som standard. (AN-112689)
* Ett trunkeringsproblem som uppstod med ordningen för frågesträngsvariabler i har korrigerats [!DNL AppMeasurement]så att *`pageURLRest`* är sist. (AN-114647)

## Version 1.5.4

Releasedatum: **17 mars 2016**

* Inkludering av besökar-API 1.5.4
* Stöd för avanmälan till Visitor API 1.5.4+

## Version 1.5.3

Releasedatum: **21 januari 2016**

* Fast hantering av [!DNL Audience Manager] när POST används för att spåra anrop. (AN-115381)
* Flyttade resten av sidans URL (&quot;-g&quot;) till slutet av frågesträngen för spårningsbegäran. (AN-114647)

## Version 1.5.2

Releasedatum: **5 november 2015**

* Inkludering av Visitor API 1.5.3.
* Fast detection of IE11 for URL Truncation 2047 (AN-114914)

## Version 1.5.1

Releasedatum: **17 september 2015**

* Inkludering av besökar-API 1.5.2
* Uppdaterat [!DNL Audience Manager] för att använda AAM DIL 6.2 - getCustomer ID:n från VisitorAPI.js och skicka dem i /event-anrop till AAM. (AN-104978)

## Version 1.5

Releasedatum: **18 juni 2015**

* Stöd för Visitor API 1.5, som använder *`getCustomerIDs`* metod för att samla in kund-ID:n och autentiserade tillstånd och skickar ID:n med datainsamlingsbegäranden.
* Korrigerat skapandet av en dubblett av mål-iframe i **[!UICONTROL AudienceManagement]** modul (DIL 6.1)
* Åtgärdade det kända problemet som beskrivs i version 1.4.5.

## Version 1.4.5

Releasedatum: **21 maj 2015**

* Med början i iOS SDK version 4.5 kan du med ett nytt iOS-tillägg samla in användningsdata från dina Apple Watch-appar, Today-widgetar, fotoredigeringswidgetar och alla andra iOS-tilläggsappar. Se [Implementering av iOS-tillägg](https://experienceleague.adobe.com/docs/mobile-services/ios/ios-ext/ios-ext.html) i användarhandboken för mobiltjänster.
* Från och med Android SDK version 4.5 kan du med ett nytt Android-tillägg samla in data från Android-appen. Se [Android-bärare](https://experienceleague.adobe.com/docs/mobile-services/android/wearables-android/android-wearable.html) i användarhandboken för mobiltjänster.
* Inkludering av Visitor API 1.4.
* AudienceManagement-modulen har uppdaterats för att använda DIL version 6.0.

>[!NOTE]
>
>**Känt fel**: I besökar-API:t / [!DNL AppMeasurement] [!DNL Audience Manager] Modulintegrationer, det finns två iFrame-målpubliceringsbegäranden i IE6-9: `//fast.<subdomain>.demdex.net/dest5.html` och  `//fast.<subdomain>.demdex.net/dest4.html`. Det korrekta beteendet, som det visas i andra webbläsare, är att bara läsa in `//fast.<subdomain>.demdex.net/dest5.html`.

## Version 1.4.4

Releasedatum: **16 april 2015**

* Nu kan du inkludera anpassade kontextdatavariabler med livscykelvärden.
* The `trackBeacon` och `clearCurrentBeacon` nu är samtal tillgängliga i PhoneGap.
* En mindre korrigering för att rensa anropsprofil-ID för ljusterservern efter `trackLight` ring.

## Version 1.4.3

Releasedatum: **19 februari 2015**

* Hanteringen av fördröjda spårningsanrop är konsekvent, vilket åtgärdar problem med säkerhetskopierade variabler under fördröjningen, till exempel klickade objekt.
* Ändrad till att inte utföra automatisk spårning av referenser efter det första spårningsanropet, så att det andra, tredje osv. spårningsanropet (vanligtvis länkspårning) inte dubbelräknar referenten när *`s.referrer`* har angetts manuellt före det första spårningsanropet.
* Distributionszippen uppdaterades så att den innehöll Visitor API 1.3.5.

## Version 1.4.2

Releasedatum: **15 januari 2015**

* Korrigerad hantering av WebKit-förrenderingshantering för att förhindra spårning av förrenderade sidor som inte visas.
* Distributionszippen uppdaterades så att den innehöll Visitor API 1.3.4 och en uppdaterad **[!UICONTROL AudienceManagement]** som innehåller DIL version 5.5.

## Version 1.4.1

Releasedatum: **18 september 2014**

* Lagt till en `tagContainerMarker` variabel som gör att implementeringen kan ange upp till 4 tecken som läggs till i versionssträngen tillsammans med en extra streckteckenavgränsare. Detta används av dynamisk tagghantering.

   ```js
   // JavaScript
   s.tagContainerMarker = "D1.0";
   
   // Data Collection request
   //.../b/ss/myrsid/1/JS-1.4.1-D1.0/s43317392037311?...
   ```

   De fyra tecknen är begränsade till tecken som tillåts i URL-filsökvägar, t.ex. alfanumeriska tecken och punkter.

* På sidor som är dubbeltaggade med H-kod har en loop som kan inträffa vid automatisk länkspårning (hämtning och avslut) korrigerats med när fast länkspårning är aktiverat (standard i Webkit-webbläsare). Dessutom lades en allmän skyddsåtgärd till runt automatisk länkspårning för att förhindra liknande slingor. Skyddet begränsar automatisk länkspårning av upprepade klickningar till *samma* till en gång var 10:e sekund. Skyddet gäller endast automatisk länkspårning, så manuella länkspårningsanrop (s.tl) är inte begränsade. Klickningar på olika objekt påverkas inte heller av den här skyddsfunktionen och spåras.
* Korrigerad hantering av klickade objekt när en fördröjning behövs.
* Korrigerade ett problem som orsakade ett dubbelsidigt antal sidor när s.t anropades från en länk-onclick-funktion, om Visitor-API:t inte har de värden som behövs ännu.
* Stöd för HTTP-POST.

   >[!IMPORTANT]
   >
   >För [!DNL Analytics] anrop till att använda metoden POST i stället för metoden GET i [!DNL AppMeasurement] (en lösningsmetod [trunkerade URL:er i IE](https://helpx.adobe.com/analytics/kb/shortening-image-request-urls.html)) måste du använda den senaste implementeringen av Visitor ID-tjänsten för Experience Cloud.

## Version 1.4

Releasedatum: **21 augusti 2014**

* Spårning av webbläsarplugin-program har tagits bort (`p` frågeparameter) eftersom plugin-program inte längre rapporteras i version 15.
* Tillägg av **[!UICONTROL AudienceManagement]** Modul i den nedladdningsbara zippen.
* Stöd för ytterligare eVars (76-250) och events (101-1000) har lagts till.

>[!NOTE]
>
>H-Code stöder inte ytterligare eVars och events.

## Version 1.3.2

Releasedatum: **19 juni 2014**

* Korrigerad hantering av slutförda och väntande flaggor för Visitor API-fält som det äldre [!DNL Analytics] Besökar-ID som orsakade fel.
* Stöd för nya funktioner i besökar-ID-tjänst 1.3.

## Version 1.3.1

Releasedatum: **22 maj 2014**

* [!DNL AppMeasurement] for [!DNL JavaScript] `s_gi` funktionen hittade inte instanser som skapats med H-kod korrekt `s_gi`. Observera att den här utgåvan endast påverkade vissa implementeringar av dubbel taggning där [!DNL AppMeasurement] for [!DNL JavaScript] och H-koden fanns på samma sida med olika instanser, och `s_gi` används för att hitta instanser via rapportsviten.

## Version 1.3

Releasedatum: **17 april 2014**

* Stöd för [Experience Cloud Visitor-ID-tjänst](https://experienceleague.adobe.com/docs/id-service/using/home.html).

## Version 1.2.4

Releasedatum: **13 mars 2014**

* Felkorrigeringar för hjärtslagsvideo.

## Version 1.2.3

Releasedatum: **20 februari 2014**

* Felkorrigeringar för hjärtslagsvideo.

## Version 1.2.2

Releasedatum: **6 februari 2014**

* Ett kompatibilitetsproblem med [!DNL Audience Manager] Modulen DIL. [!DNL Audience Manager] man måste också uppdatera till version 4.8 i modulen DIL.

## Version 1.2.1

Releasedatum: **15 november 2013**

* Korrigerade sidhändelser som används för mätning av pulsslagvideo.

## Version 1.2

Releasedatum: **14 november 2013**

* Stöd för [Heartaktmätning av video](https://experienceleague.adobe.com/docs/media-analytics/using/media-overview.html).
* `VisitorAPI.js` lades till i stödet [Tjänst för besökar-ID](https://experienceleague.adobe.com/docs/id-service/using/home.html).

## Version 1.1.1

* Förhindrade ett anrop för länkspårning från att skickas från Opera-webbläsare för länkar som börjar med opera: (&quot;opera:&quot; liknar about:&quot; och &quot;chrome:&quot; i andra webbläsare).
* Tillagd `alt=""` till alla Image-objekt för att uppfylla kraven i Accessible Video and Communications Act.

## Version 1.1

Releasedatum: **18 september 2013**

* Fast stöd för montering av bibliotek och sidkod i `head` -tagg.
* Tillagd modul saknas `onLoad` support.

## Version 1.0.3

Releasedatum: **15 augusti 2013**

* Stöd för driftsättning via tagghantering i Adobe har lagts till.
* Ett problem som gjorde att hierarkivariabler inte kunde anges på [!DNL AppMeasurement] -objekt.

## Version 1.0.2

Releasedatum: **18 juli 2013**

* Hash/fragment ignoreras nu av automatisk länkspårning. Tidigare spårades följande URL automatiskt eftersom hela `href` slutar i `.pdf`:

   ```js
   <a href="index.htm#anchor.pdf">Test Link</a>
   ```

   Nu ignoreras hash/fragment så länken spåras bara när filnamnet slutar i ett tillägg som matchar.

## Version 1.0.1

Releasedatum: **23 maj 2013**

En ny [!DNL JavaScript] [!DNL AppMeasurement] biblioteket är nu tillgängligt i Code Manager. Det här biblioteket har samma kärnfunktioner som [!DNL s_code.js], men är lättare och snabbare att använda på både mobila och stationära webbplatser.

* 3-7x snabbare än H.25-koden.
* Endast 21 kB okomprimerat och 8 kB gzippat (H.25-koden är 33 kB okomprimerad och 13 kB gzippad).
* Inbyggt stöd för att hämta frågeparametrar, läsa och skriva cookies och utföra avancerad länkspårning.
* Liten och snabb nog att användas med mobilsajter, och tillräckligt robust för att användas på hela datorwebben, så att du kan utnyttja ett bibliotek i alla webbmiljöer.
