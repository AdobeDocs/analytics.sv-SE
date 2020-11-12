---
title: Implementera Adobe Analytics
description: Implementera Adobe Analytics på din webbplats eller i en egenskap eller app.
translation-type: tm+mt
source-git-commit: 34ccd89d0ac4223af87b36a48e778fb678d5cd59
workflow-type: tm+mt
source-wordcount: '388'
ht-degree: 97%

---


# Implementera Adobe Analytics

![Banderoll](../../assets/doc_banner_implement.png)

Adobe kräver kod på din webbplats eller i din app för att kunna skicka data till Adobes datainsamlingsservrar. Följande steg visar hur en vanlig implementering fungerar.

1. När en besökare kommer till din webbplats, skickas en begäran till din webbserver.
2. Webbplatsens webbserver skickar sidkodsinformationen och sidan visas i webbläsaren.
3. Sidan läses in och Analytics JavaScript-kod körs.
JavaScript-koden skickar en bildbegäran till Adobes datainsamlingsservrar. Siddata som du har definierat under implementeringen skickas som en del av en frågesträng i den här bildbegäran.

4. Adobe returnerar en transparent pixelbild.
5. Adobe-servrarna lagrar insamlade data i en *rapportsvit*.
6. Rapportsvitens data fyller i de rapporter som du kan få åtkomst till i en webbläsare.

   JavaScript-koden körs snabbt och påverkar inte sidinläsningstiden märkbart. På så sätt kan du räkna de sidor som visas när en besökare klickar på **[!UICONTROL Reload]** eller **[!UICONTROL Back]** för att komma till en sida, eftersom JavaScript-skriptet körs även när sidan hämtas från cache.

Adobe Analytics kräver kod på din webbplats eller i din mobilapp eller annat program för att kunna skicka data till datainsamlingsservrar. Det finns flera metoder för att implementera den här koden, beroende på plattform och organisationens behov.

* **Adobe Experience Platform Launch:** Den standardiserade och rekommenderade metoden för att implementera Adobe Analytics. Placera en inläsartagg på varje sida och använd Launchs gränssnitt för att bestämma hur varje variabel ska definieras.
* **Dynamic Tag Management:** Föregångaren till Launch. DTM använder ett liknande gränssnitt för att implementera Analytics, men uppdateras inte längre och är inte lika flexibelt. Adobe rekommenderar att du använder Launch för att implementera Adobe Analytics.
* **Äldre JavaScript:** Den gamla, manuella metoden för att implementera Adobe Analytics. Beskriver variabler och inställningar som används i en implementering, vilket kan vara användbart för Launch-implementeringar som använder regler med anpassad kod.
* **SDK för mobila enheter:** Dedikerade bibliotek för att enkelt skicka data till Adobe från mobilappen.

## Viktiga artiklar om implementering av Analytics

* [Ta hand om en befintlig Adobe Analytics-implementering](/help/implement/prepare/existing-implementation.md)
* [Adobe Debugger](validate/debugger.md)
* [Skapa en egenskap i Experience Platform Launch](launch/create-analytics-property.md)
* [AppMeasurement-uppdateringar](appmeasurement-updates.md)

## Fler användarhandböcker för Analytics

[Användarhandböcker för Analytics](/help/landing/home.md)

## Viktiga Analytics-resurser

* [Kontakta kundtjänst](https://helpx.adobe.com/se/contact/enterprise-support.ec.html)
* [Analytics-forum](https://forums.adobe.com/community/experience-cloud/analytics-cloud/analytics)
* [Adobe Analytics-resurser](https://forums.adobe.com/message/10660755)
* [Experience League](https://landing.adobe.com/experience-league/)
