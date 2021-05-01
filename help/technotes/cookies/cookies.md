---
title: Adobe Analytics och webbläsarcookies
description: Läs om hur spårningsförebyggande åtgärder påverkar cookies från tredje part och från första part som anges av Adobe Analytics.
translation-type: tm+mt
source-git-commit: 07c76cea1f6fd64957fd4fd20bc5187976f3c14c
workflow-type: tm+mt
source-wordcount: '1887'
ht-degree: 0%

---


# Adobe Analytics och webbläsarcookies

I det här dokumentet förklaras hur de viktigaste åtgärderna för att spåra webbläsare påverkar cookies som angetts av Adobe Analytics från tredje part och från första part. Det innehåller information om Apples ITP-program (Intelligent Tracking Prevention) samt Chrome:s begränsningar för cookies från tredje part via attributet SameSite.

## Hur har webbläsarna begränsat användningen av cookies?

### Begränsningar för cookies från tredje part

Cookies som används i en tredjepartskontext är ofta föråldrade. Firefox och Safari började som standard blockera cookies från tredje part från och med 2019 respektive 2020. Chrome har meddelat att man under 2022 kommer att upphöra med stödet för cookies från tredje part. När de gör det blir cookies från tredje part oanvändbara.

Dessutom tillåter Chrome för närvarande endast att cookies fungerar i en tredjepartskontext om de har attributet &quot;SameSite&quot; inställt på Ingen och de är märkta som säkra, vilket innebär att de bara kan användas via HTTPS. Mer information finns i avsnittet &quot;[Vad är cookie-attributet SameSite och hur påverkar det Analytics?](#samesite-effect)&quot;

#### Vilka cookies från tredje part berörs av Adobe?

Besökar-ID-tjänsten använder cookien [`demdex.net`](https://experienceleague.adobe.com/docs/id-service/using/intro/cookies.html) för att tillhandahålla en beständig identifierare för besökare i olika kunddomäner. I webbläsare där cookies från tredje part är blockerade är spårning över domäner inte tillgängligt.

### Begränsningar för cookie-filer från första part {#limitations-first-party-cookies}

Cookies från första part tillåts i alla större webbläsare. Apple begränsar dock livslängden för cookies från första part som anges av Adobe via deras ITP (Intelligent Tracking Program). Detta inkluderar Safari på MacOS och alla webbläsare på iOS och iPadOS.

Adobe-cookies från första part är begränsade till en 7-dagars utgång eller en 24-timmars förfallotid för klickningar som Apple bestämmer kommer från spårare. Om en användare besöker din webbplats och sedan återkommer inom dessa sju dagar, kommer cookie-filens utgångsdatum att förlängas med ytterligare sju dagar. Om en användare besöker din webbplats och sedan återvänder på åtta dagar behandlas de som en ny användare vid det andra besöket.

För närvarande gäller ITP-principer för alla cookies från första part som anges av Adobe, oavsett om du använder tjänsten för besöks-ID eller det äldre analys-ID:t (&quot;s_vi&quot; cookie). I en punkt tillämpas dessa principer endast på cookies som ställs in på klientsidan och inte på cookies som ställs in på serversidan via en CNAME-implementering. I november 2020 uppdaterades dock ITP för att även gälla för CNAME-implementeringar.

#### Tidslinje för större ändringar av ITP-policyn

* Februari 2019 med [ITP 2.1](https://webkit.org/blog/8613/intelligent-tracking-prevention-2-1/): Kakor på klientsidan var begränsade till sju dagars upphörande
* April 2019 med [ITP 2.2](https://webkit.org/blog/8828/intelligent-tracking-prevention-2-2/): Klientsidans cookies var begränsade till 24 timmar för annonsklickningar när den refererande domänen var a) involverad i spårning av webbplatser och b) den slutliga URL:en innehöll en frågesträng och/eller en fragment-ID.
* November 2020 med [CNAME Cloaking and Bounce Tracking Defense](https://webkit.org/blog/11338/cname-cloaking-and-bounce-tracking-defense/): ITP-begränsningarna utökades till CNAME-implementeringar.

ITP-reglerna utvecklas ofta. Information om de senaste profilerna finns i [Spårningsskydd i Webkit](https://webkit.org/tracking-prevention).

#### Vilka cookies från första part i Adobe påverkas?

Alla cookies från första part som anges av Adobe, och de relaterade JavaScript-biblioteken, påverkas av ITP-principer:

* [`AMCV` cookieset ](https://experienceleague.adobe.com/docs/id-service/using/intro/cookies.html) av tjänstbiblioteket för Adobe Experience Cloud Visitor ID (ECID)
* Analysen har äldre [`s_vi`-cookie](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-analytics.html) när den har konfigurerats med datainsamling från första part med en CNAME
* Den gamla cookien [`s_fid` i Analytics, som är den reservcookie som används när `s_vi` inte kan anges](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-analytics.html)

#### Vilken inverkan har ITP på Safari för analys?

Effekten av ITP-begränsningarna varierar avsevärt beroende på hur användarna beter sig. Endast besökare som använder en webbläsare som påverkas av ITP (det vill säga Safari) och återvänder efter en sju dagars frånvaro påverkas. Om besökarna inte använder en ITP-webbläsare eller återvänder inom sju dagar påverkas de inte. Det är viktigt att granska era egna data i Analytics för att förstå hur stor påverkan denna begränsning har. Tips om hur du mäter effekten på dina webbplatser finns i &quot;[Hur kan jag avgöra om Safari påverkar min verksamhet?](#measure-itp-effect)&quot;

Om dessa begränsningar påverkar dina data kommer du att se:

1. Ökade besökarantal som återkommande besökare behandlas som nya besökare eftersom deras cookies har upphört att gälla. Alla mätvärden som baseras på besökarens mätvärden (t.ex. Försäljning per besökare) påverkas också.
2. Förändringar i attribuering. Konverteringshändelser är knutna till föregående aktiviteter av samma besökare. När en cookie upphör att gälla kopplas framtida händelser till en ny besökare, och konverteringar kan inte knytas tillbaka till den ursprungliga besökaren.

>[!NOTE]
>
>ITP-tekniker gäller för närvarande inte inbäddade webbläsare i mobilappar.

## Vad är skillnaden mellan cookies från tredje part och cookies från första part?

### cookies från tredje part

Tredjepartscookies skapas inte av de webbplatser som användarna besöker.

Även om webbläsare för närvarande behandlar alla cookies från tredje part på samma sätt och lagrar dem på lämpligt sätt, kan cookies från tredje part bete sig på olika sätt. Med en kunds Analytics-implementering av cookies från tredje part lagrar webbläsarna Adobe-ID:t [demdex.net](https://experienceleague.adobe.com/docs/audience-manager/user-guide/reference/demdex-calls.html) som en cookie från tredje part, men klienten gör bara anrop till Adobe och inte för okända eller misstänkta tredjepartsdomäner. Denna cookie ger beständiga identifierare över domäner och möjliggör säkert (HTTPS) innehåll. Mer information finns i [Cookies och Experience Platform Identity Service](https://experienceleague.adobe.com/docs/id-service/using/intro/cookies.html).

I Analytics-implementeringar används cookies från tredje part för domänövergripande spårning och för annonseringsanvändning, inklusive återannonsering. Med cookies från tredje part kan du identifiera besökare när de besöker olika domäner som du äger eller som annonser visas på webbplatser som du inte äger.<!--  Without these cookies, you cannot identify visitors as they visit different domains that you own or as they are shown ads on sites that you do not own unless your implementation can stitch other types of cookies and   -->

### cookies från första part

Första parts-cookies är domänspecifika och skapas av kundens webbplatser och lagras i klientwebbläsare när användarna besöker webbplatserna. Alla webbläsare accepterar i allmänhet cookies från första part, även om [Safari begränsar vissa typer av cookies från första part](#limitations-first-party-cookies).

I Analytics-implementeringar används cookies från första part för att identifiera användare när de finns på er webbplats och därför stöder alla analyser av användaraktiviteter. Du behöver inte cookies från tredje part för att förstå webbplatsaktiviteter.

Mer information finns i [Om cookies från första part](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-first-party.html).

![Cookie-jämförelse](/help/technotes/assets/cookies2.png)

## Vad är cookie-attributet SameSite och hur påverkar det Analytics-cookies? {#samesite-effect}

I och med att webbläsaren Chrome 80 släpptes i februari 2020 - och i efterföljande versioner av Firefox- och Edge-webbläsare - tillämpar attributet SameSite cookie specifikationen för tre olika värden för att styra beteendet för begäran mellan webbplatser:

* `None`: Med den här inställningen aktiveras åtkomst över flera webbplatser och cookies kan skickas i en tredjepartssituation. Om du vill ange det här attributet måste du även ange `Secure` och alla webbläsarbegäranden måste följa HTTPS. När du till exempel anger cookie-filen parar du värdena för attributet enligt följande: `Set-Cookie: example_session=test12; SameSite=None; Secure`. Om de inte är korrekt märkta kan cookies inte användas i de nyare webbläsarna och de avvisas.

* `Lax`: Tillåter att begäranden mellan webbplatser skickas med cookies för samma plats endast för navigering på den översta nivån med  *säkra*  (skrivskyddade, t.ex.  `GET`) HTTP-metoder.

* `Strict`: Samma webbplats-cookie skickas inte för någon begäran från tredje part. Cookien skickas bara om webbplatsen för cookien matchar webbplatsen i URL-fältet.

Standardbeteendet i de här webbläsarversionerna är att behandla cookies som inte har något angivet `SameSite`-attribut som är samma som `SameSite=Lax`.

### Hur hanterar Analytics samma webbplatsens cookie-attribut?

Alla Adobe cookie-uppdateringar hanteras via Adobe-servrar och Adobe edge-servrar anger lämpliga cookie-attribut. Alla cookies från tredje part uppdaterades på serversidan med lämpliga attribut. Inga JavaScript-uppdateringar krävs för dina webbplatser.

Den här uppgraderingen av edge-servrar i Adobe skedde automatiskt när användare besökte en webbplats där cookien användes. För de flesta Adobe-produkter hade cookies rätt flaggor när Chrome 80 släpptes 2020. Undantaget var Adobe Analytics-implementeringar som använder datainsamling från tredje part och som inte använder tjänsten Experience Cloud Visitor ID. För den typen av implementering måste du be kundtjänst ändra flaggorna; Mer information finns i &quot;[Ändra värdet för SameSite när du använder en CNAME för flera domäner](#samesite-one-cname)&quot; i nästa avsnitt. Tills flaggan ändras kan kunderna uppleva en liten, tillfällig ökning av antalet nya besökare som annars skulle taggas som återkommande besökare.

För webbläsare som Google har identifierat som cookies som inte kan hanteras när `SameSite` är inställt på `None`, är `SameSite` i stället okonfigurerat.

I följande tabell sammanfattas samma webbplatsattribut för analyscookies:

![Cookie-tabell](/help/technotes/assets/cookies1.png)

### Hur uppfyller min webbplats kraven för attributet SameSite?

#### Hantera alla webbplatssidor med HTTPS

Bekräfta att din JavaScript-konfiguration använder HTTPS för alla anrop till Adobe-tjänster.

Om webbplatsen använder Experience Cloud Visitor ID-tjänsten dirigerar tjänsten om HTTP-anrop från tredje part till HTTPS-slutpunkten, vilket kan öka fördröjningen men innebär att du inte behöver ändra konfigurationen.

#### Ändra värdet för SameSite när du använder en CNAME för flera domäner {#samesite-one-cname}

>[!NOTE]
>
>Följande information gäller endast webbplatser som inte använder tjänsten Experience Cloud Visitor ID.

Om du har en CNAME-implementering som är inställd i samma domän som din webbplats, skapas cookien i en förstahandskontext och du behöver inte göra några ändringar.

Om du däremot äger flera domäner och använder samma CNAME för datainsamling i alla dina domäner behandlas cookien som en cookie från tredje part i dessa andra domäner. Med Chrome 80 och senare är den inte längre synlig i dessa andra domäner. För att beteendet ska bli mer likartat i alla webbläsare har Analytics uttryckligen angett `SameSite`-värdet för denna cookie till `Lax`. Om du använder den här cookien i en användarvänlig tredjepartskontext måste du ha cookien inställd med `SameSite=None`-värdet, vilket även innebär att du alltid måste använda HTTPS. Om du inte redan har gjort det kontaktar du kundtjänst på Adobe för att ändra värdet för SameSite för dina säkra CNAME.

## Hur kan jag avgöra om Safari påverkar min verksamhet? {#measure-itp-effect}

Adobe rekommenderar att kunderna mäter effekten i sitt eget företag innan de ändrar datainsamlingen. Du kan använda Analysis Workspace för att mäta effekten av förhindrande av ITP-spårning på ditt enskilda företag:

* Mät hur stor procentandel av trafiken du har via ITP-styrda webbläsare:

   1. Skapa ett segment för att se hur många besökare som använder en ITP-plattform.

      ![Segment för ITP-besökare](/help/technotes/assets/itp-visitor-segment.png)

   2. Använd segmentet på antalet besök för att förstå den relativa användningen av Safari i din användarbas. Då kan du skapa en tabell så här:

      ![Procent besök av ITP-besökare](/help/technotes/assets/visits-vs-safari-visits.png)

* Mät hur många besökare som använder webbläsare som inte är Safari och som inte kommer tillbaka inom sju dagar. Om besökare som inte är Safari återvänder upprepade gånger inom sju dagar, kommer din Safari-trafik kanske inte att påverkas nämnvärt.

   1. Skapa ett segment som följande för annan trafik än Safari.

      ![Segment för besökare som återvänder efter sju dagar](/help/technotes/assets/visits-after-seven-days.png)

   2. Använd segmentet på antalet besök för att förstå den relativa användningen av Safari i din användarbas. Då kan du skapa en tabell så här:

      ![Andel besökare som återvänder efter sju dagar](/help/technotes/assets/percent-visits-after-seven-days.png)

### Sätt att justera data under rapportering

Om ditt företag påverkas av förhindrande av ITP-spårning kan du vidta följande åtgärder för att justera dina data under rapporteringen.

* Skapa ett segment för att filtrera ut ITP-användare.

   ![Segment för icke-ITP-besökare](/help/technotes/assets/non-itp-visitor-segment.png)

* Skapa ett beräknat mätvärde för att justera den kända besökarinflationen.

   ![Beräknade mätvärden som justeras för besökarinflationen](/help/technotes/assets/estimated-itp-visitors-metric.png)

>[!MORELIKETHIS]
>
>[Alternativ för att minska effekten av webbläsar-cookie-begränsningar](cookieless.md)
>[The Impact of Apple&#39;s New App Tracking Transparency Framework on Adobe Analytics](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-discussions/the-impact-of-apple-s-new-app-tracking-transparency-framework-on/td-p/401833)
