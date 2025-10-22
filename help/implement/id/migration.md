---
title: Överväganden om migrering av Visiter ID-tjänst för Adobe Analytics
description: En översikt över hur Adobe Analytics interagerar med besökar-ID-tjänsten.
source-git-commit: f682f9c8533536e9b33f320f2a420055c6f4e397
workflow-type: tm+mt
source-wordcount: '617'
ht-degree: 0%

---

# Överväganden om migrering av Visiter ID-tjänst för Adobe Analytics

Om din organisation planerar att gå över till Visitor ID-tjänsten med en befintlig Analytics-implementering finns det några viktiga ämnen att tänka på. Dessa överväganden gör att ni kan behålla besökaridentifieringsintegriteten och förstå hur ID-tjänsten fungerar i närvaro av en befintlig Analytics-implementering.

>[!TIP]
>
>Den här sidan gäller endast befintliga implementeringar av AppMeasurement- eller Analytics-tillägg och lägger till Visitor ID-tjänsten eller uppgraderar till en Web SDK-implementering. Implementeringen använder med andra ord ett äldre analys-ID (`aid`) och går mot att använda ett Experience Cloud-ID (`mid`). Alla Web SDK-implementeringar använder redan ett Experience Cloud-ID (`mid`) som standard.

## Hur besökar-ID-tjänsten samverkar med äldre cookies för besökare i Analytics

Eftersom AppMeasurement har en egen metod för att identifiera besökare kan vissa besökare ha äldre Analytics-cookies när en organisation använder Visitor ID-tjänsten. Följande lista visar hur en besökare identifieras under olika omständigheter.

* **Det finns inga cookies för besökare**: ID-tjänsten tilldelar ett Experience Cloud-id (`mid`).
* **Det finns en `s_vi`-cookie**: ID-tjänsten skriver det befintliga gamla analys-ID:t (`aid`) till `AMCV`-cookien förutom ett Experience Cloud-ID (`mid`). Eftersom `aid` är högre i [åtgärdsordningen](overview.md) är det äldre analys-ID:t besökaridentifieraren tills `AMCV`-cookien förfaller eller rensas. När en respitperiod är aktiverad inkluderar ID-tjänsten både `mid` och `aid` i sitt svar.
* **Det finns en reservcookie**: ID-tjänsten skriver inte reservcookien (`fid`) till `AMCV`-cookien. I stället får besökarna ett Experience Cloud-ID (`mid`) som om de vore en ny besökare.

## Respitperiod för besökar-ID-tjänst

Om du har flera implementeringar som skickar data till samma rapportserie och du bara kan implementera tjänsten för besöks-ID för vissa implementeringar, rekommenderar Adobe att du konfigurerar en respitperiod. Om till exempel supportavsnittet på din plats hanteras av en separat taggningslösning, kan du ha använt Visitor ID-tjänsten på resten av din plats före supportavsnittet. Utan någon respitperiod får nya besökare som visar supportavsnittet ett gammalt besökar-ID för Analytics, vilket gör att två separata besökare räknas. Med en respitperiod utfärdar besökar-ID-tjänsten både ett Experience Cloud-ID (`mid`) och ett äldre Analytics-besökar-ID (`aid`) så att områden på webbplatsen utan ID-tjänsten fortsätter att identifiera besökare konsekvent.

Om du koordinerar distributionen av Visitor ID-tjänsten i alla delar av webbplatsen behöver du ingen respitperiod. Kontakta [Adobe kundtjänst](https://helpx.adobe.com/se/marketing-cloud/contact-support.html) om du vill konfigurera en respitperiod. Respitperioder kan konfigureras för upp till 180 dagar och kan förnyas. Adobe rekommenderar att du avbryter respitperioden när hela din egenskap har konfigurerats att använda ID-tjänsten.

## Spårning mellan domäner

I vissa implementeringar av äldre besökar-ID för Analytics kan&quot;användarvänliga cookies från tredje part&quot; användas, där två domäner delar samma besökares cookie på en gemensam domän som `data.example.com`. Eftersom egna cookies från tredje part fortfarande är cookies från tredje part, avvisar många moderna webbläsare dem, vilket gör att Analytics förlitar sig på ett reservID (`fid`) för besökaridentifiering. Genom att gå till ID-tjänsten kan alla domäner ange cookie-filen `AMCV` i en förstapartskontext, vilket ökar deras möjlighet att behålla ett besökar-ID.

Även om besökar-ID-tjänsten försöker ange en tredjeparts-cookie för korsdomänsspårning ( [`demdex` cookie &#x200B;](https://experienceleague.adobe.com/sv/docs/id-service/using/intro/cookies) ), avvisas den ofta av moderna webbläsare. Överväg att använda metoden [`appendVisitorIDsTo`](https://experienceleague.adobe.com/sv/docs/id-service/using/id-service-api/methods/appendvisitorid) för att skicka en besökares Experience Cloud-ID (`mid`) mellan domäner som du äger.

## Spårning på serversidan

Du kan anropa [`getMarketingCloudVisitorID`](https://experienceleague.adobe.com/sv/docs/id-service/using/id-service-api/methods/getmcvid) för att hämta Experience Cloud-id:t (`mid`) och [`getAnalyticsVisitorID`](https://experienceleague.adobe.com/sv/docs/id-service/using/id-service-api/methods/getanalyticsvisitorid) för att hämta det äldre analys-ID:t (`aid`). Adobe rekommenderar att du kontrollerar båda för att bevara logiken för besökaridentifiering.
