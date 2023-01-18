---
title: Implementera Adobe Analytics
description: Implementera Adobe Analytics på din webbplats eller i en egenskap eller app.
feature: Implementation Basics
exl-id: 2b629369-2d69-4dc6-861a-ff21a46d39e0
source-git-commit: d2c291f7db465034ffadc4a2c1caf9639caf2a1d
workflow-type: tm+mt
source-wordcount: '409'
ht-degree: 44%

---

# Implementera Adobe Analytics

![Banderoll](../../assets/doc_banner_implement.png)

Här är en videoöversikt över Adobe Analytics:

>[!VIDEO](https://video.tv.adobe.com/v/27429/?quality=12)

Adobe kräver kod på din webbplats eller i din app för att kunna skicka data till Adobes datainsamlingsservrar. Följande steg visar hur en vanlig implementering fungerar.

1. När en besökare kommer till din webbplats, skickas en begäran till din webbserver.
2. Webbplatsens webbserver skickar sidkodsinformationen och sidan visas i webbläsaren.
3. Sidan läses in och Analytics JavaScript-kod körs.
4. JavaScript-koden skickar en 1x1-pixelbildbegäran till datainsamlingsservrar för Adobe. Siddata som du har definierat under implementeringen skickas som en del av en frågesträng i den här bildbegäran.
5. Adobe datainsamlingsservrar returnerar den begärda bilden.
6. Adobe-servrar tolkar och lagrar insamlade data i en rapportserie.
7. Rapportsvitens data fyller i de rapporter som du kan få åtkomst till i en webbläsare.


Adobe erbjuder flera metoder för att implementera koden, beroende på plattform och organisationens behov.

* **Web SDK-tillägg**: Den aktuella, standardiserade och rekommenderade metoden för att implementera Adobe Analytics. Installera Web SDK-tillägget i Adobe Experience Platform Data Collection, använd en loader-tagg på varje sida och skicka data till Adobe Experience Platform Edge i ett format som passar din organisation. Experience Edge vidarebefordrar inkommande data till Adobe Analytics i rätt format.
* **Web SDK**: Du kan läsa in Web SDK-bibliotek manuellt på webbplatsen om du inte vill använda taggar. Referera till Web SDK-biblioteket på varje sida och skicka önskade spårningsanrop till Adobe Experience Edge.
* **Adobe Analytics-tillägg**: Installera Adobe Analytics-tillägget i Adobe Experience Platform Data Collection. Placera en loader-tagg på varje sida och använd Analytics-tillägget för att bestämma hur varje variabel definieras.
* **Äldre JavaScript:** Den gamla, manuella metoden för att implementera Adobe Analytics. Skapar konturer av variabler och inställningar som används i en implementering, vilket kan vara användbart för implementeringar med regler med anpassad kod.
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
