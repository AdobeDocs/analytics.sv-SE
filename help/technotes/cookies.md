---
title: Adobe Analytics och webbläsarcookies
description: Läs om hur Adobe Analytics hanterar cookies i en webbläsare.
translation-type: tm+mt
source-git-commit: 1ff9c892670e7b120bf727e556ff70f76c6751be
workflow-type: tm+mt
source-wordcount: '2285'
ht-degree: 0%

---


# Adobe Analytics och webbläsarcookies

För att ge stöd för beständig användaridentifiering i olika egenskaper och lösningar är Adobe Analytics responsivt på förändringar i hur webbläsare hanterar cookies. I följande vanliga frågor och svar visas information om hur beständig besökaridentifiering bevaras med ändringar i webbläsar-cookie.

## Hur förändrar webbläsarna hur de hanterar cookies?

I allmänhet blir de flesta webbläsare mer restriktiva när det gäller hur de lagrar cookies från tredje part. Detta kan påverka spårningen om cookien tas bort eller avvisas av webbläsaren. Webbläsaren Safari anger dessutom vissa begränsningar för vissa cookies från första part.

I följande lista visas några av de senaste ändringarna enligt webbläsare:

* Krom: Från och med Chrome 80 hanteras attributet på ett annat sätt för att hantera cookies från tredje part eller förfrågningar från flera webbplatser. `SameSite` I slutändan letar Chrome-utvecklare efter sätt att [ersätta cookies](https://blog.chromium.org/2020/01/building-more-private-web-path-towards.html?m=1) från tredje part helt och hållet.

* Firefox och Edge: Produktmeddelanden anger att efterföljande versioner av webbläsarna ska följa samma ändringar som i Chrome 80.

* Safari: Med [Safari 12.1](https://webkit.org/blog/category/privacy/)har beständiga cookies från första part som anges via API:t document.cookie, som ofta kallas cookies på klientsidan, en utgångsgräns på sju dagar.

## Vad är skillnaden mellan cookies från tredje part och cookies från första part?

### cookies från första part

cookies från första part skapas av kundwebbplatser (domänspecifika) och lagras i klientwebbläsare när användarna besöker kundens webbplatser. Alla webbläsare accepterar i allmänhet cookies från första part. I en cookie Analytics-implementering från en annan leverantör skapas cookie-filen för besökar-ID på en Adobe-nod när värdnamnet är avstämt med domänen med hjälp av en [CNAME](https://docs.adobe.com/content/help/en/id-service/using/reference/analytics-reference/cname.html). Cookien accepteras sedan av webbläsaren i en förstahandskontext. Mer information finns i [Om cookies](https://docs.adobe.com/content/help/en/core-services/interface/ec-cookies/cookies-first-party.html)från första part.

### cookies från tredje part

Tredjepartscookies skapas inte av webbplatser som användare besöker. Även om webbläsare för närvarande behandlar alla cookies från tredje part på samma sätt och lagrar dem på lämpligt sätt, kan cookies från tredje part bete sig på olika, viktiga sätt. Med en kunds implementering av cookies från tredje part i Analytics gör klienten bara anrop till Adobe, och inte till okända eller misstänkta tredjepartsdomäner. Det här är den aktuella metoden för att implementera Analytics för säker (HTTPS) och tillförlitlig spårning med beständiga identifierare. Den här metoden implementeras genom att filen AppMeasurement.js konfigureras. Mer information finns i [Cookies och Experience Platform Identity Service](https://docs.adobe.com/content/help/en/id-service/using/intro/cookies.html).

![Cookie-jämförelse](assets/cookies2.png)

## Hur lagrar och hanterar webbläsare för närvarande Analytics-cookies?

Beroende på implementeringen lagras Analytics-cookies på följande sätt:

### Implementeringar av cookies från tredje part

Webbläsare lagrar för närvarande Adobe [demdex.net](https://docs.adobe.com/content/help/en/audience-manager/user-guide/reference/demdex-calls.html) -ID:t som en cookie från tredje part. Denna cookie ger beständiga identifierare över domäner och möjliggör säkert (https) innehåll.

### Implementeringar av cookies från första part

Genom att konfigurera en CNAME kan din användare ta emot Adobe-cookies i en cookie-kontext för sina webbläsare. Detta kan vara ett praktiskt alternativ om en cookie-implementering från tredje part inte är optimal för dina användare.

## Vad är cookie-attributet SameSite och hur påverkar det Analytics?

I och med lanseringen av webbläsaren Chrome 80, och efterföljande versioner av Firefox och Edge-webbläsare, tillämpar attributet SameSite cookie specifikationen för tre olika värden för att styra beteendet för förfrågningar mellan webbplatser enligt följande:

* `None`: Med den här inställningen aktiveras åtkomst över flera webbplatser och cookies kan skickas i en tredjepartssituation. Om du vill ange det här attributet måste du även ange `Secure` och alla webbläsarbegäranden måste följa HTTPS. När du till exempel anger cookie-filen parar du värdena för attributet enligt följande: `Set-Cookie: example_session=test12; SameSite=None; Secure`. Om de inte är korrekt märkta kan cookies inte användas i de nyare webbläsarna och kommer att refuseras.

* `Lax`: Tillåter att begäranden mellan webbplatser skickas med cookies för samma plats endast för navigeringar på den översta nivån med *säkra* (skrivskyddade, t.ex. `GET`) HTTP-metoder.

* `Strict`: Samma webbplats-cookie skickas inte för någon begäran från tredje part. Cookien skickas bara om webbplatsen för cookien matchar webbplatsen i URL-fältet.

Standardbeteendet i de här webbläsarversionerna är att behandla cookies som inte har något angivet `SameSite` attribut på samma sätt som `SameSite=Lax`.

## Hur reagerar Adobe Analytics på dessa förändringar?

Alla Adobe cookie-uppdateringar hanteras via Adobe-servrar och Adobe har uppdaterat sina edge-servrar för att ange lämpliga cookie-attribut. Adobe har släppt uppdateringar på serversidan för att ange cookies från tredje part med lämpliga attribut. Inga JavaScript-uppdateringar krävs för dina webbplatser.

Den här uppgraderingen av edge-servrar i Adobe sker automatiskt när användare besöker en webbplats där cookien används. För de flesta Adobe-produkter har cookies rätt flaggor när Chrome 80 släpps. Undantaget är Adobe Analytics-implementeringar som använder datainsamling från tredje part och som inte använder Experience Cloud Identity Service (ECID). Dessa kunder kan uppleva en liten tillfällig ökning av antalet nya besökare som annars hade taggats som återkommande besökare.

För webbläsare som Google har identifierat som cookies som inte fungerar när `SameSite` är inställda på `None`lämnas `SameSite` istället olset.

I följande tabell sammanfattas cookies i Analytics:

![Cookie-tabell](assets/cookies1.png)

## Vilket är det bästa sättet att förbereda min webbplats för Chrome-, Firefox- och Edge-ändringar?

Analyskunder bör bekräfta att deras JavaScript-konfiguration använder HTTPS för sina anrop till Adobe-tjänster. ECID dirigerar om HTTP-anrop från tredje part till dess HTTPS-slutpunkt, vilket kan öka fördröjningen, men det innebär att du inte behöver ändra konfigurationen.

Adobe föreslår att du ser till att alla webbplatssidor hanteras med HTTPS.

### En CNAME för flera domäner

Om du har en CNAME-implementering som är inställd i samma domän som din webbplats, är detta en cookie-kontext för första part och du behöver inte göra några ändringar.

Om du däremot äger flera domäner och använder samma CNAME för datainsamling i alla dina domäner behandlas den som en cookie från tredje part i dessa andra domäner. Med Chrome 80 syns den inte längre på dessa andra domäner. För att beteendet ska bli mer likartat i alla webbläsare anges värdet för den här cookien explicit i Analytics (Analytics) `SameSite` `Lax`. Om du använder den här cookien i en användarvänlig tredjepartskontext måste du ange värdet för cookien, vilket även innebär att du alltid måste använda HTTPS. `SameSite=None` Kontakta Adobe kundtjänst om du vill ändra värdet för SameSite för dina säkra CNAME. Obs! Den här åtgärden krävs INTE för Analytics-kunder som använder ECID.

## Vilken inverkan har Safari-förändringarna (ITP 2.1) på Analytics?

Trots ändringar i Safari 12.1 samlas data från Adobe Experience Cloud-cookies fortfarande in. Även om det finns ett tak för cookies på sju dagar, förnyar besökarna din egendom inom den tiden cookien och behåller den från att löpa ut i ytterligare sju dagar. Fönster för att titta tillbaka och antalet besökare som kommer tillbaka kan minskas för Safari-trafik tills en Adobe-uppdatering blir tillgänglig.

På grund av det kortare utgångsdatumet på sju dagar kan kunderna se en ökning av unika besökare. Besök- och sidvisningsantalet ska inte påverkas. Om du har en fastighet som har säsongstrafik, t.ex. moms eller semesterhandel, kan du se större effekt eftersom besökaren inte kommer att vara ansluten mellan säsongerna.

Om du använder en CNAME sparar besökar-ID-tjänsten ECID i en cookie på serversidan. Detta gör att cookien kan behållas så länge den varar.

**Obs! ITP 2.1 gäller inte inbäddade webbläsare i mobilappar.**

### Berörda cookies från första part

Cookies som skapats genom `document.cookie` påverkas. Om du ställer in någon av dessa cookies via HTTP-svar (på serversidan) eller använder CNAME-certifiering påverkas inte ändringarna i ITP 2.1. Följande cookies och relaterade JavaScript-bibliotek från första part påverkas:

* AMCV-cookies som anges av ECID-tjänstbiblioteket (Experience Cloud ID)
* Analytics - gammal reservcookie `s_fid`

Analysera äldre `s_vi` cookie-filer som en cookie från tredje part, inklusive samlingsmål för adobedc.net, 2o7.net eller omtrdc.net, fortsätter att blockeras baserat på tidigare versioner av ITP.

Så här summerar du:

* Om du har en CNAME och använder besökar-ID-tjänsten påverkas inte implementeringen.

* Om du använder CNAME från en första part i den första partskontexten och inte använder besökar-ID-tjänsten påverkas inte implementeringen.

* Om du använder en cookie-domän från första part i tredjepartssammanhanget, eller med standarddomännamn från tredje part (t.ex. `adobedc.net`, `2o7.net`, `omtrdc.net`osv.), fortsätter Safari att blockera domänen som den har gjort.

* Om du använder ett anpassat besökar-ID beror detta på hur ditt besökar-ID lagras. Om du lagrar ditt ID i en cookie från en första part på klientsidan gäller sju dagars utgång. Om du använder något annat sätt för att lagra ditt anpassade ID måste du utvärdera om du påverkas.

### Minst påverkade datauppsättningar

Datauppsättningar med aktiva besökare som återvänder ofta påverkas minst av ändringarna. Om innehållet på din webbplats är sådant att kunderna återvänder dagligen eller minst ett par gånger i veckan, kommer cookies för dessa aktiva användare att förnyas innan de går ut. Sociala nätverk, nyheter och andra mediewebbplatser har oftast ett stort antal användare som kommer tillbaka ofta.

Kunder som använder `s_vi` som sitt primära besökar-ID och som är konfigurerade med datainsamling från första part med CNAME påverkas inte av ITP 2.1. Observera att i de fall där `s_vi` inte kan anges kan reservcookien användas, `s_fid` och kommer att ha sju dagars förfallotid.

Dessutom påverkas inte datauppsättningar som använder besökar-ID-tjänsten och som har en förstapartsdomän.

## Kommer Safari att påverka min verksamhet?

Adobe rekommenderar att man först mäter effekten i det egna företaget innan man gör några ändringar i datainsamlingen. Detta kan göras med metoderna nedan.

För att mäta påverkan på rapportering och testning är det viktigt att veta vilken typ av besöks- och cookie-spårning du har implementerat och hur mycket trafik du har från användare med Safari. Tänk på följande när du vill mäta effekten på ditt enskilda företag:

* Kontrollera vilka typer av cookies som dina Adobe-bibliotek ställer in.

* Öppna utvecklarkonsolen i din senaste Safari-webbläsare. Om du ser någon av de cookies som anges ovan i din förstapartsdomän kan du påverkas av dessa ändringar.

* Om du ser en `s_vi` `AMCV` cookie, men inte en cookie som har angetts i samband med en CNAME, använder du en CNAME för besöksidentifiering och din Analytics-användning påverkas inte av dessa ändringar. Om du ser både en `s_vi` cookie och en `AMCV` cookie som har angetts i samband med en CNAME-fil använder du nyligen eller för närvarande giltighetsperiod och en del av din Adobe Analytics-trafik kan påverkas.

* Använd Analytics för att mäta hur många besökare som inte kommer tillbaka inom sju dagar. Om besökarna återvänder upprepade gånger inom sju dagar kommer trafiken eventuellt inte att påverkas nämnvärt. Instruktioner om hur du använder Adobe Analytics för att komma underfund med detta finns i [Safari ITP 2.1 Impact on Adobe Experience Cloud and Experience Platform Customers](https://medium.com/adobetech/safari-itp-2-1-impact-on-adobe-experience-cloud-customers-9439cecb55ac).

* Mät hur stor procentandel av trafiken du har i webbläsarna från Safari för att avgöra om det är tillräckligt motiverat att göra några ändringar. Anvisningar om hur du använder Analytics för att ta reda på hur stor procentandel av Safari-trafiken till dina webbplatser finns i [Safari ITP 2.1 Impact on Adobe Experience Cloud and Experience Platform Customers](https://medium.com/adobetech/safari-itp-2-1-impact-on-adobe-experience-cloud-customers-9439cecb55ac).

## Vilka webbläsare använder jag mest?

Om du är intresserad av att lära dig mer om de webbläsare som besökarna använder kan du använda Dimensionen [Analytics](https://docs.adobe.com/content/help/en/analytics/components/variables/dimensions-reports/reports-browsers.html) Browser för att avgöra vilka webbläsare som används mest för webbplatserna. Du kan också använda Analytics-Dimensioner för att se vilka webbläsare som används mest beroende på geografisk region. Mer information finns i [GeoSegmentation](https://docs.adobe.com/content/help/en/analytics/components/variables/dimensions-reports/reports-geosegmentation.html).

Enligt [Starter](https://gs.statcounter.com/browser-market-share/all)var den globala marknadsandelen i slutet av 2019 följande för varje webbläsare:

* Krom: ~64 %
* Safari: ~17 %
* Firefox: ~4 %
* Kant: ~2 %

När marknadsandelen förändras kan du ta del av sådan [statistik](https://gs.statcounter.com/browser-market-share/all) för att se över er implementeringsstrategi.

## Hur fungerar jag bäst med ITP 2.1-förändringar i Safari på kort sikt?

Adobe’s CNAME och det hanterade certifikatprogrammet används för att hantera ITP-ändringar. Med Adobe Managed Certificate kan du utan extra kostnad implementera ett nytt förstahandscertifikat för cookies från en annan leverantör. Idag har Adobe flera CNAME-tjänster per lösning och vill på kort sikt utnyttja Analytics-certifieringsprogrammet.

Alla befintliga Analytics-kunder med en CNAME-konfiguration som även använder Experience Cloud ID Services för besökaridentifiering kan dra nytta av en framtida uppdatering av ECID-biblioteket. Denna ändring gör att CNAME-certifierade spårningsservrar kan behålla ECID och användas som referens för besöksidentifiering. Mer information finns i efterföljande versioner av ECID-biblioteket.

Adobe är medvetna om att inte alla ECID-bibliotekskunder använder CNAMES eller Analytics. Alla ECID-kunder erbjuds en CNAME-installation i syfte att utnyttja samma funktion.

Om du för närvarande inte utnyttjar CNAME för implementeringen kan du starta processen genom att prata med kundtjänst.

## Vad har Adobe för framtidsplaner för beständig besöksidentifiering?

Nya funktioner och implementeringar:

* CNAME-certifiering som självbetjäningsalternativ för alla Adobe-lösningar

* Flexibla metoder för insamling av besökar-ID, BYOI (Bring your own Identity) och API-första datainsamling

* Adobe Experience Platform identitetsdiagram

* Enhetlig metod för datainsamling i Adobe

Adobe strävar efter en mer exakt personalisering för konsumenter som vill ha en personaliserad upplevelse. Adobe strävar efter att erbjuda våra kunder funktioner för onlineidentitet som hjälper dem att anpassa sig efter kundernas valmöjligheter vad gäller integritet.

## Mer information

Mer information finns i:

* [Adobe Experience Cloud: Cookie-uppdateringar för Google Chrome](https://medium.com/adobetech/adobe-experience-cloud-cookie-updates-for-google-chrome-19ad67cf1598)

* [Safari ITP 2.1 Impact on Adobe Experience Cloud and Experience Platform Customers](https://medium.com/adobetech/safari-itp-2-1-impact-on-adobe-experience-cloud-customers-9439cecb55ac)
