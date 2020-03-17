---
title: Implementera Adobe Analytics
description: Implementera Adobe Analytics på er webbplats, på er egendom eller i er tillämpning.
translation-type: tm+mt
source-git-commit: 8a090574a6822a76366343ad5c657280bf7475eb

---


# Implementera Adobe Analytics

![Banderoll](../../assets/doc_banner_implement.png)

Adobe kräver kod på din webbplats eller i din app för att skicka data till Adobes datainsamlingsservrar. Följande steg visar hur en vanlig implementering fungerar.

1. När en besökare kommer till din webbplats görs en förfrågan till din webbserver.
2. Webbplatsens webbserver skickar sidkodsinformationen och sidan visas i webbläsaren.
3. Sidan läses in och JavaScript-koden för Analytics körs.
JavaScript-koden skickar en bildförfrågan från Adobes datainsamlingsservrar. Siddata som du definierade i implementeringen skickas som en del av en frågesträng i den här bildbegäran.

4. Adobe returnerar en genomskinlig pixelbild.
5. Adobe-servrar lagrar insamlade data i en *rapportserie*.
6. Rapportsvitens data fyller i de rapporter som du har åtkomst till i en webbläsare.

   JavaScript-koden körs snabbt och påverkar inte sidinläsningstiden märkbart. På så sätt kan du räkna sidor som visas när en besökare klickar på dem **[!UICONTROL Reload]** eller **[!UICONTROL Back]** kommer till en sida, eftersom JavaScript-skriptet körs även när sidan hämtas från cache.

Adobe Analytics kräver kod från er webbplats, mobilapp eller något annat program för att skicka data till datainsamlingsservrar. Det finns flera sätt att implementera koden, beroende på plattform och organisationens behov.

* **Adobe Experience Platform Launch**: Den standardiserade och rekommenderade metoden för att implementera Adobe Analytics. Placera en loader-tagg på varje sida och använd Launch-gränssnittet för att bestämma hur varje variabel definieras.
* **Dynamisk tagghantering**: Föregångaren till Launch. DTM använder ett liknande gränssnitt för att implementera Analytics, men är inte längre uppdaterat och inte lika flexibelt. Adobe rekommenderar att du använder Launch för att implementera Adobe Analytics.
* **Äldre JavaScript**: Den historiska manuella metoden för att implementera Adobe Analytics. Skapar konturer av variabler och inställningar som används i en implementering, vilket kan vara användbart för Launch-implementeringar med regler med anpassad kod.
* **Mobile SDK**: Dedikerade bibliotek för att enkelt skicka data till Adobe inifrån mobilappen.

## Implementeringsartiklar för nyckelanalyser

* [Adobe Debugger](validate/debugger.md)
* [Skapa en egenskap i Experience Platform Launch](launch/create-analytics-property.md)
* [AppMeasurement-uppdateringar](appmeasurement-updates.md)

## Fler användarhandböcker för Analytics

[Användarhandböcker för analys](/help/landing/home.md)

## Viktiga analysresurser

* [Kontakta kundtjänst](https://helpx.adobe.com/contact/enterprise-support.ec.html)
* [Analysforum](https://forums.adobe.com/community/experience-cloud/analytics-cloud/analytics)
* [Adobe Analytics-resurser](https://forums.adobe.com/message/10660755)
* [Experience League](https://landing.adobe.com/experience-league/)
