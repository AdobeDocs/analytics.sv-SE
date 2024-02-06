---
title: Adobe Analytics och webbläsarcookies
description: Läs om hur spårningsförebyggande åtgärder påverkar cookies från tredje part och från första part som anges av Adobe Analytics.
feature: Data Configuration and Collection
exl-id: c4a4751e-49fc-40c3-aa39-f0f0b20bda1b
role: Admin
source-git-commit: d3d5b01fe17f88d07a748fac814d2161682837c2
workflow-type: tm+mt
source-wordcount: '1914'
ht-degree: 0%

---

# Adobe Analytics och webbläsarcookies

I det här dokumentet förklaras hur de viktigaste åtgärderna för att spåra webbläsare påverkar cookies som angetts av Adobe Analytics från tredje part och från första part. Det innehåller information om Apple ITP-program (Intelligent Tracking Prevention) samt Chrome:s begränsningar för cookies från tredje part via attributet SameSite.

## Hur har webbläsarna begränsat användningen av cookies?

>[!NOTE]
>[Enhetsövergripande analys](https://experienceleague.adobe.com/docs/analytics/components/cda/overview.html#cda) och [Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-overview.html#comparing-cja-to-traditional-adobe-analytics) kan sammanfogas mellan cookies med ett person-ID, t.ex. ett hashade inloggnings-ID, om ett sådant finns.

### Begränsningar för cookie-filer från tredje part

Cookies som används i en tredjepartskontext är ofta föråldrade. Firefox och Safari började som standard blockera cookies från tredje part från och med 2019 respektive 2020. Chrome har meddelat att man under 2023 kommer att upphöra med stödet för cookies från tredje part. När de gör det blir cookies från tredje part oanvändbara.

Dessutom tillåter Chrome för närvarande endast att cookies fungerar i en tredjepartskontext om de har attributet &quot;SameSite&quot; inställt på Ingen och de är märkta som säkra, vilket innebär att de bara kan användas via HTTPS. Mer information finns i avsnittet[Vad är cookie-attributet SameSite och hur påverkar det Analytics?](#samesite-effect)&quot;

#### Vilka cookies från tredje part berörs av Adobe?

Tjänsten för besökar-ID använder &quot;[demdex.net](https://experienceleague.adobe.com/docs/id-service/using/intro/cookies.html)&quot; cookie för att ge en beständig identifierare för besökare i olika kunddomäner. Den äldre tjänsten för analys-ID, s_vi-cookie, anges som en cookie från tredje part för implementeringar som inte använder en anpassad CNAME-samlingsdomän.

I webbläsare där cookies från tredje part är blockerade är spårning över domäner inte tillgängligt.

### Begränsningar för cookie-filer från första part {#limitations-first-party-cookies}

Cookies från första part tillåts i alla större webbläsare. Apple begränsar dock livslängden för cookies från första part som Adobe ställer in via sitt Intelligent Tracking Program (ITP). Detta påverkar både Safari och alla webbläsare på iOS och iPadOS.

Adobe-cookies från första part är begränsade till ett 7-dagars upphörande eller, för klickningar som Apple bestämmer kommer från spårare, ett 24-timmars upphörande. Om en användare besöker webbplatsen och återkommer inom sju dagar med 7 dagars utgång, förlängs cookie-filens förfallodatum med ytterligare sju dagar. Men om en användare besöker er webbplats och återvänder på åtta dagar behandlas de som en ny användare vid det andra besöket.

För närvarande gäller ITP-principer för alla cookies från första part som anges av Adobe, oavsett om du använder tjänsten för besöks-ID eller det äldre analys-ID:t (&quot;s_vi&quot; cookie). I en punkt tillämpas dessa principer endast på cookies som ställs in på klientsidan och inte på cookies som ställs in på serversidan via en CNAME-implementering. I november 2020 uppdaterades dock ITP för att även gälla för CNAME-implementeringar.

#### Tidslinje för större ändringar av ITP-policyn {#ITP-timeline}

* Februari 2019 med [ITP 2.1](https://webkit.org/blog/8613/intelligent-tracking-prevention-2-1/): Cookies på klientsidan var begränsade till ett sjudagars förfallodatum
* April 2019 med [ITP 2.2](https://webkit.org/blog/8828/intelligent-tracking-prevention-2-2/): Klientsidans cookies var begränsade till 24 timmar för annonsklickningar när den refererande domänen var a) involverad i spårning av webbplatser och b) den slutliga URL:en innehöll en frågesträng och/eller en fragment-ID.
* November 2020 med [CNAME Dolda och studsspårningsförsvar](https://webkit.org/blog/11338/cname-cloaking-and-bounce-tracking-defense/): ITP-begränsningarna utökades till CNAME-implementeringar.

ITP-reglerna utvecklas ofta. Information om de senaste policyerna finns i Apple [Spårningsskydd i Webkit](https://webkit.org/tracking-prevention).

#### Vilka cookies från första part i Adobe påverkas?

Alla cookies från första part som anges av Adobe, och de relaterade JavaScript-biblioteken, påverkas av ITP-principer:

* [&quot;AMCV&quot;-cookies](https://experienceleague.adobe.com/docs/id-service/using/intro/cookies.html) anges av tjänstbiblioteket för Adobe Experience Cloud Visitor ID (ECID)
* Analytics-bakgrunden [&quot;s_vi&quot;-cookie](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-analytics.html) när den är konfigurerad med datainsamling från första part med en CNAME
* Analytics-bakgrunden [&quot;s_fid&quot;-cookie](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-analytics.html), vilket är den reservcookie som används när &quot;s_vi&quot; inte kan anges

#### Vilken inverkan har ITP på Safari för analys?

Effekten av ITP-begränsningarna kan variera avsevärt beroende på hur användarna beter sig. Endast besökare som använder en webbläsare som påverkas av ITP (till exempel Safari) och som återvänder efter en sju dagars frånvaro påverkas. Om besökarna inte använder en ITP-webbläsare eller återvänder inom sju dagar påverkas de inte. Det är viktigt att granska era egna data i Analytics för att förstå hur stor påverkan denna begränsning har. Tips om hur du mäter effekten på dina webbplatser finns i &quot;[Hur kan jag avgöra om Safari påverkar min verksamhet?](#measure-itp-effect)&quot;

Om dessa begränsningar påverkar dina data kommer du att se:

1. Ökade besökarantal som återkommande besökare behandlas som nya besökare eftersom deras cookies har upphört att gälla. Alla mätvärden som baseras på besökarens mätvärden (t.ex. Försäljning per besökare) påverkas också.
2. Förändringar i attribuering. Attribution förlitar sig på att koppla konverteringshändelser till föregående aktiviteter av samma besökare. När en cookie upphör att gälla kopplas efterföljande händelser till en ny besökare. Den nya besökarens aktiviteter kan inte knytas till den tidigare besökarens aktiviteter.

>[!NOTE]
>
>ITP-tekniker gäller för närvarande inte inbäddade webbläsare i mobilappar.

## Vad är skillnaden mellan cookies från tredje part och cookies från första part?

### cookies från tredje part

Tredjepartscookies skapas inte av de webbplatser som användarna besöker.

Även om webbläsare för närvarande behandlar alla cookies från tredje part på samma sätt och lagrar dem så kan cookies från tredje part bete sig på olika sätt. Med en kunds Analytics-implementering av cookies från tredje part lagrar webbläsarna Adobe [demdex.net](https://experienceleague.adobe.com/docs/audience-manager/user-guide/reference/demdex-calls.html) ID som en cookie från tredje part, men klienten gör bara anrop till Adobe och inte för okända eller misstänkta tredjepartsdomäner. Denna cookie ger beständiga identifierare över domäner och möjliggör säkert (HTTPS) innehåll. Mer information finns i [Cookies och Experience Platform Identity Service](https://experienceleague.adobe.com/docs/id-service/using/intro/cookies.html).

I Analytics-implementeringar används cookies från tredje part för domänövergripande spårning och för annonseringsanvändning, inklusive återannonsering. Med cookies från tredje part kan du identifiera besökare när de besöker olika domäner som du äger eller som de visas på annonser på webbplatser som du inte äger.<!--  Without these cookies, you cannot identify visitors as they visit different domains that you own or as they are shown ads on sites that you do not own unless your implementation can stitch other types of cookies and   -->

### cookies från första part

Första parts-cookies är domänspecifika och skapas av kundens webbplatser och lagras i klientwebbläsare när användarna besöker webbplatserna. Alla webbläsare accepterar i allmänhet cookies från första part, även om [Safari begränsar vissa typer av cookies från första part](#limitations-first-party-cookies).

I Analytics-implementeringar används cookies från första part för att identifiera användare när de finns på er webbplats och därför stöder alla analyser av användaraktiviteter. Du behöver inte cookies från tredje part för att förstå webbplatsaktiviteter.

Mer information finns i [Om cookies från första part](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-first-party.html).

![Cookie-jämförelse](/help/technotes/assets/cookies2.png)

## Vad är cookie-attributet SameSite och hur påverkar det Analytics-cookies? {#samesite-effect}

I och med att webbläsaren Chrome 80 släpptes i februari 2020 - och i efterföljande versioner av Firefox- och Edge-webbläsare - tillämpar attributet SameSite cookie specifikationen för tre olika värden som styr om cookies kan användas i ett tredjepartssammanhang:

* `None`: Den här inställningen aktiverar åtkomst över webbplatser och gör att cookies kan skickas i en tredjepartssituation. Om du vill ange det här attributet måste du också ange `Secure` och alla webbläsarbegäranden måste följa HTTPS. När du till exempel anger cookie-filen parar du värdena för attributet enligt följande: `Set-Cookie: example_session=test12; SameSite=None; Secure`. Om de inte är korrekt märkta kan cookies inte användas i de nyare webbläsarna och de avvisas.

* `Lax`: Tillåter att begäranden mellan webbplatser skickas med cookies för samma webbplats endast för navigering på den översta nivån med *säker* (skrivskyddad, till exempel `GET`) HTTP-metoder.

* `Strict`: En cookie för samma webbplats skickas inte för webbplatsförfrågningar från tredje part. Cookien skickas bara om webbplatsen för cookien matchar webbplatsen i URL-fältet.

Standardbeteendet i de här webbläsarversionerna är att hantera cookies som inte har någon angiven `SameSite` samma attribut som `SameSite=Lax`.

### Hur hanterar Analytics samma webbplatsens cookie-attribut?

För kunder som använder Visitor ID-tjänsten har cookies egenskaperna `SameSite=None` och `secure` anges som standard, vilket gör att dessa cookies kan användas med stöd för tredjepartsanvändning.

För kunder som använder äldre Analytics-identifierare (&quot;s_vi&quot; och&quot;s_fid&quot;-cookies) ställs cookies in på att aktivera användningsfall från tredje part med standardsamlingsdomäner: adobedc.net, 2o7.net och omtrdc.net. För kunder som använder en CNAME-implementering anges i Analytics `SameSite=Lax`.

>[!NOTE]
>
>Om du äger flera domäner och använder samma CNAME för datainsamling i alla dina domäner behandlas cookien som en cookie från tredje part i dessa andra domäner. Om du använder de äldre analysidentifierarna kanske du vill uppdatera inställningen till `SameSite=None` så att dessa cookies kan delas på alla dina webbplatser. Se &quot;[Ändra värdet för SameSite när du använder en CNAME för flera domäner](#samesite-one-cname)&quot; i nästa avsnitt om du vill ha mer information.

För webbläsare som Google har identifierat som cookies som inte hanterar när `SameSite` är inställd på `None`, `SameSite` i stället lämnas orörd.

I följande tabell sammanfattas samma webbplatsattribut för analyscookies:

![Cookie-tabell](/help/technotes/assets/cookies1.png)

### Hur uppfyller min webbplats kraven för attributet SameSite?

#### Hantera alla webbplatssidor med HTTPS

Kontrollera att din JavaScript-konfiguration använder HTTPS för alla anrop till Adobe-tjänster.

Om webbplatsen använder Experience Cloud Visitor ID-tjänsten dirigerar tjänsten om HTTP-anrop från tredje part till HTTPS-slutpunkten, vilket kan öka fördröjningen men innebär att du inte behöver ändra konfigurationen.

#### Ändra värdet för SameSite när du använder en CNAME för flera domäner {#samesite-one-cname}

>[!NOTE]
>
>Följande information gäller endast webbplatser som inte använder tjänsten Experience Cloud Visitor ID.

Om du har en CNAME-implementering som är inställd i samma domän som din webbplats, skapas cookien i en förstahandskontext och du behöver inte göra några ändringar.

Om du däremot äger flera domäner och använder samma CNAME för datainsamling i alla dina domäner behandlas cookien som en cookie från tredje part i dessa andra domäner. Med Chrome 80 och senare är den inte längre synlig i dessa andra domäner. För att beteendet ska bli mer likartat i alla webbläsare har Analytics uttryckligen angett `SameSite` värdet för denna cookie till `Lax`. Om du använder den här cookien i en användarvänlig tredjepartskontext måste du ha cookien inställd med `SameSite=None` , vilket innebär att du alltid måste använda HTTPS. Om du inte redan har gjort det kontaktar du kundtjänst på Adobe för att ändra värdet för SameSite för dina säkra CNAME.

## Hur kan jag avgöra om Safari påverkar min verksamhet? {#measure-itp-effect}

Adobe rekommenderar att kunderna mäter effekten i sitt eget företag innan de ändrar datainsamlingen. Du kan använda Analysis Workspace för att mäta effekten av förhindrande av ITP-spårning på ditt enskilda företag:

* Mät hur stor procentandel av trafiken du har via ITP-styrda webbläsare:

   1. Skapa ett segment för att se hur många besökare som använder en ITP-plattform.

      >[!NOTE]
      >
      >Vilka webbläsare som påverkas av ITP beror på om du använder en CNAME-implementering. Se &quot;[Tidslinje för större ändringar av ITP-policyn](#ITP-timeline)&quot; för mer information.

      ![Segment för ITP-besökare](/help/technotes/assets/itp-visitor-segment.png)

   2. Använd segmentet på antalet besök för att förstå den relativa användningen av Safari i din användarbas. Detta gör att du kan skapa en tabell som den här:

      ![Procent besök av ITP-besökare](/help/technotes/assets/visits-vs-safari-visits.png)

* Mät hur många besökare som använder webbläsare som inte är Safari och som inte kommer tillbaka inom sju dagar. Om besökare som inte är Safari återvänder upprepade gånger inom sju dagar, kommer din Safari-trafik kanske inte att påverkas nämnvärt.

   1. Skapa ett segment som följande för annan trafik än Safari.

      ![Segment för besökare som återvänder efter sju dagar](/help/technotes/assets/visits-after-seven-days.png)

   2. Använd segmentet på antalet besök för att förstå den relativa användningen av Safari i din användarbas. Detta gör att du kan skapa en tabell som den här:

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
>[Effekten av Apple nya App Tracking Transparency Framework på Adobe Analytics](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-discussions/the-impact-of-apple-s-new-app-tracking-transparency-framework-on/td-p/401833)
