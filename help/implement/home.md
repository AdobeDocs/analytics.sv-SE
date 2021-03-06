---
title: Implementera Adobe Analytics
description: Implementera Adobe Analytics på din webbplats eller i en egenskap eller app.
feature: Implementation Basics
exl-id: 2b629369-2d69-4dc6-861a-ff21a46d39e0
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '428'
ht-degree: 64%

---

# Implementera Adobe Analytics

![Banderoll](../../assets/doc_banner_implement.png)

Här är en videoöversikt över Adobe Analytics:

>[!VIDEO](https://video.tv.adobe.com/v/27429/?quality=12)

Adobe kräver kod på din webbplats eller i din app för att kunna skicka data till Adobes datainsamlingsservrar. Följande steg visar hur en vanlig implementering fungerar.

1. När en besökare kommer till din webbplats, skickas en begäran till din webbserver.
2. Webbplatsens webbserver skickar sidkodsinformationen och sidan visas i webbläsaren.
3. Sidan läses in och Analytics JavaScript-kod körs.
JavaScript-koden skickar en bildbegäran till Adobes datainsamlingsservrar. Siddata som du har definierat under implementeringen skickas som en del av en frågesträng i den här bildbegäran.

4. Adobe returnerar en transparent pixelbild.
5. Adobe-servrar lagrar insamlade data i en eller flera *rapportsviter*.
6. Rapportsvitens data fyller i de rapporter som du kan få åtkomst till i en webbläsare.

   JavaScript-koden körs snabbt och påverkar inte sidinläsningstiden märkbart. På så sätt kan du räkna de sidor som visas när en besökare klickar på **[!UICONTROL Reload]** eller **[!UICONTROL Back]** för att komma till en sida, eftersom JavaScript-skriptet körs även när sidan hämtas från cache.

Adobe Analytics kräver kod på din webbplats eller i din mobilapp eller annat program för att kunna skicka data till datainsamlingsservrar. Det finns flera metoder för att implementera den här koden, beroende på plattform och organisationens behov.

* **Web SDK**: Den standardiserade och rekommenderade metoden för att implementera Adobe Analytics. Installera Web SDK-tillägget i Adobe Experience Platform Data Collection, använd en loader-tagg på varje sida och skicka data till Adobe Experience Platform Edge i ett format som passar din organisation. Experience Edge vidarebefordrar inkommande data till Adobe Analytics i rätt format.
* **Adobe Analytics-tillägg**: Installera Adobe Analytics-tillägget i Adobe Experience Platform Data Collection. Placera en loader-tagg på varje sida och använd Analytics-tillägget för att bestämma hur varje variabel definieras.
* **Äldre JavaScript:** Den gamla, manuella metoden för att implementera Adobe Analytics. Skapar konturer av variabler och inställningar som används i en implementering, vilket kan vara användbart för tadimplementeringar med regler med anpassad kod.
* **SDK för mobila enheter:** Dedikerade bibliotek för att enkelt skicka data till Adobe från mobilappen.

## Viktiga artiklar om implementering av Analytics

* [Ta hand om en befintlig Adobe Analytics-implementering](/help/implement/prepare/existing-implementation.md)
* [Adobe Debugger](validate/debugger.md)
* [Skapa en taggegenskap i Experience Platform](launch/create-analytics-property.md)
* [AppMeasurement-uppdateringar](appmeasurement-updates.md)

## Fler användarhandböcker för Analytics

[Användarhandböcker för Analytics](https://experienceleague.adobe.com/docs/analytics.html)

## Viktiga Analytics-resurser

* [Kontakta kundtjänst](https://experienceleague.adobe.com/?support-solution=Analytics#support)
* [Analytics-forum](https://forums.adobe.com/community/experience-cloud/analytics-cloud/analytics)
* [Adobe Analytics-resurser](https://forums.adobe.com/message/10660755)
* [Experience League](https://landing.adobe.com/experience-league/)
