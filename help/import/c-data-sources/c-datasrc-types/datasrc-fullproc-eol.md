---
title: Slutet av livscykeln för fullständiga datakällor
description: Orsaker till slutet av livscykeln och jämförelser mellan API:t för inmatning av gruppdata och fullständiga datakällor för databearbetning.
translation-type: tm+mt
source-git-commit: 2e077db74b7719f49aec513fc99dad33a4d5b831
workflow-type: tm+mt
source-wordcount: '732'
ht-degree: 3%

---


# Slutet av livscykeln för fullständiga datakällor

I flera år har du kunnat skicka in data på träffnivå till Adobe Analytics med fullständig databehandling. Dessa data bearbetades på samma sätt som data som samlats in via våra JavaScript-bibliotek och SDK för mobilappar. 2020 släppte Adobe [API:t för datainmatning i grupp](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/bdia.md), som utför samma funktioner som fullständiga datakällor, men med ytterligare funktioner. Det här avsnittet innehåller information om ytterligare funktioner som tillhandahålls av API:t för inmatning av gruppdata och visar skillnader i filformat.

Från och med 25 mars 2021 kommer Adobe att förhindra att nya anslutningar för fullständiga datakällor skapas. Befintliga anslutningar stöds tills tjänsten är helt inaktuell. Utbyggnaden kommer att äga rum 2021, men ett visst datum har ännu inte fastställts.

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

| BDIA, FPDS, båda | BDIA-variabel | Kolumnvariabel för fullständig bearbetning | Beskrivning |
| --- | --- | --- | --- |
| BDIA | aamlh | Stöds inte | Platstips för Adobe Audience Manager. Se giltiga ID-värden i tabellen nedan AAM region. |
| Båda | browserHeight | browserHeight | Webbläsarhöjd i pixlar (till exempel 768) |
| Båda | browserWidth | browserWidth | Webbläsarbredd i pixlar (till exempel 1024) |
| Båda | kampanj | kampanj | Kod för spårning av konverteringskampanj |
| Båda | kanal | kanal | Kanalsträng (till exempel Sport Section) |
| Båda | colorDepth | colorDepth | Bildskärmens färgdjup i bitar (t.ex. 24) |
| Båda | connectionType | connectionType | Besökarens anslutningstyp (LAN eller modem) |
| BDIA | contextData.key | Stöds inte | Nyckelvärdepar anges i genom att rubriken&quot;contextData.product&quot; eller&quot;contextData.color&quot; namnges |
| Båda | cookiesEnabled | cookiesEnabled | `Y` eller  `N` om besökaren stöder cookies från första part |
| Båda | currencyCode | currencyCode | Valutakod för intäkt (till exempel `USD`) |
| BDIA | customerID.[customerIDType].authState | Stöds inte | Besökarens autentiserade tillstånd. Värden som stöds är: 0, 1, 2, UNKNOWN, AUTHENTICATED, LOGGED_OUT eller &#39;&#39; (ej skiftlägeskänsligt). Två på varandra följande enkla citattecken (&#39;&#39;) gör att värdet utelämnas från frågesträngen, som översätts till 0 när träffen görs. Observera att de numeriska värden som stöds för authState anger följande: 0 = UNKNOWN, 1 = AUTHENTICATED, 2 = LOGGED_OUT. customerIDType kan vara vilken alfanumerisk sträng som helst, men ska betraktas som skiftlägeskänslig. |
| BDIA | customerID.[customerIDType].id | Stöds inte | Kund-ID som ska användas. customerIDType kan vara vilken alfanumerisk sträng som helst, men ska betraktas som skiftlägeskänslig. |
| BDIA | customerID.[customerIDType].isMCSeed | Stöds inte | Anger om detta är startvärdet för Marketing Cloud Visitor-ID:t. Värden som stöds är: 0, 1, TRUE, FALSE, &#39;&#39; (skiftlägesokänslig). Om du använder 0, FALSE eller två på varandra följande enkla citattecken (&#39;&#39;) utelämnas värdet från frågesträngen. customerIDType kan vara vilken alfanumerisk sträng som helst, men ska betraktas som skiftlägeskänslig. |
