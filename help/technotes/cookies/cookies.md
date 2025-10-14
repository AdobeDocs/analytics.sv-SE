---
title: Adobe Analytics och webbläsarcookies
description: Läs om hur spårningsförebyggande åtgärder påverkar cookies från tredje part och från första part som anges av Adobe Analytics.
feature: Data Configuration and Collection
exl-id: c4a4751e-49fc-40c3-aa39-f0f0b20bda1b
role: Admin
source-git-commit: fcc165536d77284e002cb2ba6b7856be1fdb3e14
workflow-type: tm+mt
source-wordcount: '1908'
ht-degree: 0%

---

# Adobe Analytics och webbläsarcookies

I det här dokumentet förklaras hur de viktigaste åtgärderna för att spåra webbläsare påverkar cookies som angetts av Adobe Analytics från tredje part och från första part. Det innehåller information om Apple ITP-program (Intelligent Tracking Prevention) samt Chrome begränsningar för cookies från tredje part via attributet SameSite.

## Hur har webbläsarna begränsat användningen av cookies?

>[!NOTE]
>[Enhetsövergripande analys](/help/components/cda/overview.md#cda) och [Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-overview.html?lang=sv-SE#comparing-cja-to-traditional-adobe-analytics) kan sammanfogas med cookies med ett person-ID, till exempel ett hashas-inloggnings-ID, om ett sådant finns.

### Begränsningar för cookie-filer från tredje part

Cookies som används i en tredjepartskontext är ofta föråldrade. Firefox och Safari började som standard blockera cookies från tredje part från och med 2019 respektive 2020. Chrome planerar att upphöra med stödet för cookies från tredje part någon gång under 2023. När de gör det blir cookies från tredje part oanvändbara.

Dessutom tillåter Chrome för närvarande endast att cookies fungerar i ett tredjepartssammanhang om de har attributet &quot;SameSite&quot; inställt på Ingen och de är märkta som säkra, vilket innebär att de bara kan användas via HTTPS. Mer information finns i avsnittet [Vad är cookie-attributet SameSite och hur påverkar det Analytics?](#samesite-effect)

#### Vilka cookies från tredje part berörs av Adobe?

Besökar-ID-tjänsten använder cookien [demdex.net](https://experienceleague.adobe.com/docs/id-service/using/intro/cookies.html?lang=sv-SE) för att tillhandahålla en beständig identifierare för besökare i olika kunddomäner. Den äldre tjänsten för analys-ID, s_vi-cookie, anges som en cookie från tredje part för implementeringar som inte använder en anpassad CNAME-samlingsdomän.

I webbläsare där cookies från tredje part är blockerade är spårning över domäner inte tillgängligt.

### Begränsningar för cookie-filer från första part {#limitations-first-party-cookies}

Cookies från första part tillåts i alla större webbläsare. Apple begränsar dock livslängden för cookies från första part som Adobe har angett via sitt ITP (Intelligent Tracking Program). Detta påverkar både Safari och alla webbläsare på iOS och iPadOS.

Adobe cookies från första part är begränsade till 7-dagars utgång eller, för klickningar som Apple fastställer kommer från spårare, ett 24-timmars förfallodatum. Om en användare besöker webbplatsen och återkommer inom sju dagar med 7 dagars utgång, förlängs cookie-filens förfallodatum med ytterligare sju dagar. Men om en användare besöker er webbplats och återvänder på åtta dagar behandlas de som en ny användare vid det andra besöket.

För närvarande gäller ITP-principer för alla cookies från första part som anges av Adobe, oavsett om du använder tjänsten för besöks-ID eller det äldre analys-ID:t (&quot;s_vi&quot; cookie). I en punkt tillämpas dessa principer endast på cookies som ställs in på klientsidan och inte på cookies som ställs in på serversidan via en CNAME-implementering. I november 2020 uppdaterades dock ITP för att även gälla för CNAME-implementeringar.

#### Tidslinje för större ändringar av ITP-policyn {#ITP-timeline}

* Februari 2019 med [ITP 2.1](https://webkit.org/blog/8613/intelligent-tracking-prevention-2-1/): Cookies på klientsidan begränsades till ett sjudagars förfallodatum
* April 2019 med [ITP 2.2](https://webkit.org/blog/8828/intelligent-tracking-prevention-2-2/): Cookies på klientsidan var begränsade till 24 timmar för annonsklickningar när den refererande domänen var a) involverad i spårning av flera webbplatser och b) den slutliga URL:en innehöll en frågesträng och/eller en fragment-identifierare.
* November 2020 med [CNAME Cloaking and Bounce Tracking Defense](https://webkit.org/blog/11338/cname-cloaking-and-bounce-tracking-defense/): ITP-begränsningarna utökades till att omfatta CNAME-implementeringar.

ITP-reglerna utvecklas ofta. Information om de senaste profilerna finns i Apple [Spårningsskydd i Webkit](https://webkit.org/tracking-prevention).

#### Vilka Adobe-cookies påverkas?

Alla cookies från första part som har angetts av Adobe, och de relaterade JavaScript-biblioteken, påverkas av ITP-policyer:

* [&quot;AMCV&quot;-cookies](https://experienceleague.adobe.com/docs/id-service/using/intro/cookies.html?lang=sv-SE) har angetts av tjänstbiblioteket för Adobe Experience Cloud Visitor ID (ECID)
* Analysen av den gamla cookien [&#128279;](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-analytics.html?lang=sv-SE)&quot;s_vi&quot; när den har konfigurerats med datainsamling från första part med en CNAME
* Den gamla cookien [&#x200B; för Analytics &#x200B;](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-analytics.html?lang=sv-SE)&quot;s_fid&quot;, som är den reservcookie som används när s_vi inte kan anges

#### Vilken inverkan har ITP på Safari för analys?

Effekten av ITP-begränsningarna kan variera avsevärt beroende på hur användarna beter sig. Endast besökare som använder en webbläsare som påverkas av ITP (till exempel Safari) och som återvänder efter en sju dagars frånvaro påverkas. Om besökarna inte använder en ITP-webbläsare eller återvänder inom sju dagar påverkas de inte. Det är viktigt att granska era egna data i Analytics för att förstå hur stor påverkan denna begränsning har. Tips om hur du mäter effekten på dina webbplatser finns i [Hur kan jag avgöra om Safari påverkar min verksamhet?](#measure-itp-effect)

Om dessa begränsningar påverkar dina data kommer du att se:

1. Ökade besökarantal som återkommande besökare behandlas som nya besökare eftersom deras cookies har upphört att gälla. Alla mätvärden som baseras på besökarens mätvärden (t.ex. Försäljning per besökare) påverkas också.
2. Förändringar i attribuering. Attribution förlitar sig på att koppla konverteringshändelser till föregående aktiviteter av samma besökare. När en cookie upphör att gälla kopplas efterföljande händelser till en ny besökare. Den nya besökarens aktiviteter kan inte knytas till den tidigare besökarens aktiviteter.

>[!NOTE]
>
>ITP-tekniker gäller för närvarande inte inbäddade webbläsare i mobilappar.

## Vad är skillnaden mellan cookies från tredje part och cookies från första part?

### cookies från tredje part

Tredjepartscookies skapas inte av de webbplatser som användarna besöker.

Även om webbläsare för närvarande behandlar alla cookies från tredje part på samma sätt och lagrar dem så kan cookies från tredje part bete sig på olika sätt. Med en kunds Analytics-implementering av cookies från tredje part lagrar webbläsarna Adobe-ID:t [demdex.net](https://experienceleague.adobe.com/docs/audience-manager/user-guide/reference/demdex-calls.html?lang=sv-SE) som en cookie från tredje part, men klienten gör bara anrop till Adobe och inte för okända eller misstänkta tredjepartsdomäner. Denna cookie ger beständiga identifierare över domäner och möjliggör säkert (HTTPS) innehåll. Mer information finns i [Cookies och Experience Platform Identity Service](https://experienceleague.adobe.com/docs/id-service/using/intro/cookies.html?lang=sv-SE).

I Analytics-implementeringar används cookies från tredje part för domänövergripande spårning och för annonseringsanvändning, inklusive återannonsering. Med cookies från tredje part kan du identifiera besökare när de besöker olika domäner som du äger eller som annonser visas på webbplatser som du inte äger.<!--  Without these cookies, you cannot identify visitors as they visit different domains that you own or as they are shown ads on sites that you do not own unless your implementation can stitch other types of cookies and   -->

### cookies från första part

Första parts-cookies är domänspecifika och skapas av kundens webbplatser och lagras i klientwebbläsare när användarna besöker webbplatserna. Alla webbläsare accepterar i allmänhet cookies från första part, även om [Safari begränsar vissa typer av cookies från första part](#limitations-first-party-cookies).

I Analytics-implementeringar används cookies från första part för att identifiera användare när de finns på er webbplats och därför stöder alla analyser av användaraktiviteter. Du behöver inte cookies från tredje part för att förstå webbplatsaktiviteter.

Mer information finns i [Om cookies från första part](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-first-party.html?lang=sv-SE).

![Cookie-jämförelse](/help/technotes/assets/cookies2.png)

## Vad är cookie-attributet SameSite och hur påverkar det Analytics-cookies? {#samesite-effect}

I och med lanseringen av webbläsaren Chrome 80 i februari 2020 - och efterföljande versioner av webbläsarna Firefox och Edge - använder attributet SameSite cookie tre olika värden som styr om cookies kan användas i tredjepartssammanhang:

* `None`: Den här inställningen aktiverar åtkomst över flera webbplatser och gör att cookies kan skickas i en tredjepartskontext. Om du vill ange det här attributet måste du även ange `Secure` och alla webbläsarbegäranden måste följa HTTPS. När du till exempel anger cookie-filen parar du värdena för attributet enligt följande: `Set-Cookie: example_session=test12; SameSite=None; Secure`. Om de inte är korrekt märkta kan cookies inte användas i de nyare webbläsarna och de avvisas.

* `Lax`: Tillåter att korswebbplatsbegäranden endast skickas med cookies för toppnivånavigering med HTTP-metoder av typen *safe* (skrivskyddad, t.ex. `GET`).

* `Strict`: Cookie för samma webbplats skickas inte för webbplatsförfrågningar från tredje part. Cookien skickas bara om webbplatsen för cookien matchar webbplatsen i URL-fältet.

Standardbeteendet i de här webbläsarversionerna är att behandla cookies som inte har något angivet `SameSite`-attribut som är detsamma som `SameSite=Lax`.

### Hur hanterar Analytics samma webbplatsens cookie-attribut?

För kunder som använder besökar-ID-tjänsten har cookies egenskaperna `SameSite=None` och `secure` som standard, vilket gör att dessa cookies stöder användningsfall från tredje part.

För kunder som använder äldre Analytics-identifierare (`s_vi` och `s_fid`-cookies) ställs cookies in så att även tredjepartsanvändningsfall med standardsamlingsdomäner aktiveras: `adobedc.net`, `2o7.net` och `omtrdc.net`. För kunder som använder en CNAME-implementering anges `SameSite=Lax` av Analytics.

>[!NOTE]
>
>Om du äger flera domäner och använder samma CNAME för datainsamling i alla dina domäner behandlas cookien som en cookie från tredje part i dessa andra domäner. Om du använder de äldre analysidentifierarna kanske du vill uppdatera inställningen till `SameSite=None` så att dessa cookies kan delas mellan dina webbplatser. Mer information finns i [Ändra värdet för SameSite när du använder en CNAME för flera domäner](#samesite-one-cname) i nästa avsnitt.

För webbläsare som Google har identifierat som cookies som inte kan hanteras när `SameSite` är inställt på `None`, lämnas `SameSite` i stället orört.

I följande tabell sammanfattas samma webbplatsattribut för analyscookies:

![Cookie-tabell](/help/technotes/assets/cookies1.png)

### Hur uppfyller min webbplats kraven för attributet SameSite?

#### Hantera alla webbplatssidor med HTTPS

Bekräfta att din JavaScript-konfiguration använder HTTPS för alla samtal till Adobes tjänster.

Om webbplatsen använder Experience Cloud Visitor ID-tjänsten dirigerar tjänsten om HTTP-anrop från tredje part till HTTPS-slutpunkten, vilket kan öka fördröjningen men innebär att du inte behöver ändra konfigurationen.

#### Ändra värdet för SameSite när du använder en CNAME för flera domäner {#samesite-one-cname}

>[!NOTE]
>
>Följande information gäller endast webbplatser som inte använder tjänsten Experience Cloud Visitor ID.

Om du har en CNAME-implementering som är inställd i samma domän som din webbplats, skapas cookien i en förstahandskontext och du behöver inte göra några ändringar.

Om du däremot äger flera domäner och använder samma CNAME för datainsamling i alla dina domäner behandlas cookien som en cookie från tredje part i dessa andra domäner. Med Chrome 80 och senare är den inte längre synlig i dessa andra domäner. För att beteendet ska bli mer likartat i alla webbläsare har Analytics uttryckligen angett värdet `SameSite` för denna cookie till `Lax`. Om du använder den här cookien i en användarvänlig tredjepartskontext måste du ha cookien inställd med värdet `SameSite=None`, vilket även innebär att du alltid måste använda HTTPS. Om du inte redan har gjort det kontaktar du Adobe kundtjänst för att ändra värdet för SameSite för dina säkra CNAME.

## Hur kan jag avgöra om Safari påverkar min verksamhet? {#measure-itp-effect}

Adobe rekommenderar att man mäter effekten i det egna företaget innan man ändrar datainsamlingen. Du kan använda Analysis Workspace för att mäta effekten av förhindrande av ITP-spårning på ditt enskilda företag:

* Mät hur stor procentandel av trafiken du har via ITP-styrda webbläsare:

   1. Skapa ett segment för att se hur många besökare som använder en ITP-plattform.

      >[!NOTE]
      >
      >Vilka webbläsare som påverkas av ITP beror på om du använder en CNAME-implementering. Mer information finns i [Tidslinjen för större ändringar av ITP-principen](#ITP-timeline).

      ![Segment för ITP-besökare](/help/technotes/assets/itp-visitor-segment.png)

   2. Använd segmentet på antalet besök för att förstå den relativa användningen av Safari i din användarbas. Detta gör att du kan skapa en tabell som den här:

      ![Procent besök av ITP-besökare](/help/technotes/assets/visits-vs-safari-visits.png)

* Mät hur många besökare som använder webbläsare som inte är Safari och som inte kommer tillbaka inom sju dagar. Om besökare som inte är Safari återvänder upprepade gånger inom sju dagar, kommer din Safari-trafik kanske inte att påverkas nämnvärt.

   1. Skapa ett segment som följande för annan trafik än Safari.

      ![Segment för besökare som återvänder efter sju dagar](/help/technotes/assets/visits-after-seven-days.png)

   2. Använd segmentet på antalet besök för att förstå den relativa användningen av Safari i din användarbas. Detta gör att du kan skapa en tabell som den här:

      ![Procentandel besökare som återvänder efter sju dagar](/help/technotes/assets/percent-visits-after-seven-days.png)

### Sätt att justera data under rapportering

Om ditt företag påverkas av förhindrande av ITP-spårning kan du vidta följande åtgärder för att justera dina data under rapporteringen.

* Skapa ett segment för att filtrera ut ITP-användare.

  ![Segment för icke-ITP-besökare](/help/technotes/assets/non-itp-visitor-segment.png)

* Skapa ett beräknat mätvärde för att justera den kända besökarinflationen.

  ![Beräknat mått för att justera besökarinflationen](/help/technotes/assets/estimated-itp-visitors-metric.png)

>[!MORELIKETHIS]
>
>[Alternativ för att minska effekten av webbläsar-cookie-begränsningar](cookieless.md)
>&#x200B;>[Effekten av Apple nya App Tracking Transparency Framework på Adobe Analytics](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-discussions/the-impact-of-apple-s-new-app-tracking-transparency-framework-on/td-p/401833)
