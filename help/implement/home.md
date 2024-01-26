---
title: Implementera Adobe Analytics
description: Implementera Adobe Analytics på din webbplats eller i en egenskap eller app.
feature: Implementation Basics
exl-id: 2b629369-2d69-4dc6-861a-ff21a46d39e0
role: Admin, Developer, Leader, User
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '827'
ht-degree: 29%

---

# Implementera Adobe Analytics

![Banderoll](../../assets/doc_banner_implement.png)

Adobe kräver kod på din webbplats eller i din app för att kunna skicka data till Adobes datainsamlingsservrar. Följande steg visar hur en vanlig implementering fungerar.

1. När en besökare kommer till din webbplats, skickas en begäran till din webbserver.
2. Webbplatsens webbserver skickar sidkodsinformationen och sidan visas i webbläsaren.
3. Sidan läses in och Analytics JavaScript-kod körs.
JavaScript-koden skickar en bildbegäran till Adobe datainsamlingsservrar. Siddata som du har definierat under implementeringen skickas som en del av en frågesträng i den här bildbegäran.

4. Adobe returnerar en transparent pixelbild.
5. Adobe-servrar lagrar insamlade data i en eller flera *rapportsviter*.
6. Rapportsvitens data fyller i de rapporter som du kan få åtkomst till i en webbläsare.

JavaScript-koden körs snabbt och påverkar inte sidinläsningstiden märkbart. På så sätt kan du räkna de sidor som visas när en besökare klickar på **[!UICONTROL Reload]** eller **[!UICONTROL Back]** för att komma till en sida, eftersom JavaScript-skriptet körs även när sidan hämtas från cache.

Adobe Analytics kräver kod på din webbplats eller i din mobilapp eller annat program för att kunna skicka data till datainsamlingsservrar. Det finns flera metoder för att implementera den här koden, beroende på plattform och organisationens behov.

## Implementeringsmetoder för webbplatser

För **webbplats**, finns följande implementeringsmetoder:

* **Web SDK-tillägg**: Den standardiserade och rekommenderade metoden för att implementera Adobe Analytics för nya kunder. Lägg till **Adobe Experience Platform Web SDK-tillägg** i Adobe Experience Platform Data Collection **Taggar** placerar du sedan en loader-tagg på varje sida. Taggen skickar data till Adobe Experience Platform **Edge Network**, som vidarebefordrar dessa data till Adobe Analytics.
  ![Web SDK-tillägg](./assets/websdk-extension-implementation.png)
Se [Så här implementerar du Adobe Analytics med tillägget Adobe Experience Platform Web SDK.](./aep-edge/overview.md) för mer information.

* **Web SDK**: Du kan läsa in Web SDK-bibliotek manuellt på din webbplats om du inte vill använda Adobe Experience Platform Data Collection. Referera till Web SDK-biblioteket (`alloy.js`) på varje sida och skicka önskade spårningsanrop till Adobe Experience Platform **Edge Network** i ett format som passar er. Edge Network vidarebefordrar dessa data till Adobe Analytics.
  ![Web SDK](./assets/websdk-implementation.png)
Se [Implementera Adobe Analytics med Adobe Experience Platform Web SDK](./aep-edge/overview.md) för mer information.

* **Analystillägg**: Lägg till **Adobe Analytics-tillägg** i Adobe Experience Platform Data Collection **Taggar**placerar du sedan en loader-tagg på varje sida. Taggen skickar data direkt till Adobe Analytics. Använd den här implementeringsmetoden om du vill att taggar ska vara praktiska, men inte använda Edge Network-infrastrukturen.
  ![Adobe Analytics-tillägg](./assets/analytics-extension-implementation.png)
Se [Implementera Adobe Analytics med Analytics-tillägget](launch/overview.md) för mer information.

* **Äldre JavaScript:** Den gamla, manuella metoden för att implementera Adobe Analytics. Referera till AppMeasurementet (`AppMeasurement.js`) på varje sida och sedan ange variabler och inställningar i JavaScript.
  ![Implementera Adobe Analytics med äldre JavaScript](./assets/appmeasurement-implementation.png)
Den här implementeringsmetoden kan vara användbar för implementeringar med anpassad kod och är idealisk för implementeringstyper som inte finns någon annanstans, till exempel för [AMP-sidor](other/amp.md).

Följande beslutsflöde kan hjälpa dig att välja en implementeringsmetod:

![Ett beslutsträd för att välja en implementeringsmetod, vilket beskrivs i detta avsnitt.](./assets/decision-tree.png)


>[!TIP]
>
>Kontakta kontoteamet på Adobe för råd och bästa praxis för implementering baserat på din nuvarande situation.

## Implementeringsmetoder för mobilappar

För **mobilapp**, finns följande implementeringsmetoder:

* **Mobile SDK-tillägg**: Den standardiserade och rekommenderade metoden för att implementera Adobe Analytics i din mobilapp. Använd dedikerade bibliotek för att enkelt skicka data till Adobe inifrån mobilappen. Lägg till **Adobe Experience Platform Mobile SDK-tillägg** i Adobe Experience Platform Data Collection **Taggar** implementera sedan Mobile SDK-biblioteket i din app. Du kan använda SDK för att importera bibliotek, registrera tillägg och läsa in taggkonfigurationen. Skicka data till Adobe Experience Platform **Edge Network**; Edge vidarebefordrar sedan dessa data till Adobe Analytics.
  ![Mobile SDK-tillägg](./assets/mobilesdk-extension.png)

  Se [Implementera Adobe Analytics med Adobe Experience Platform Mobile SDK](../implement/aep-edge/mobile-sdk/overview.md) för mer information.

* **Analystillägg**: Lägg till **Adobe Analytics-tillägg** i Adobe Experience Platform Data Collection **Taggar**och implementera SDK-biblioteket för mobiler i din app. Du kan använda SDK för att importera bibliotek, registrera tillägg och läsa in taggkonfigurationen. Implementeringsmetoden skickar data direkt till Adobe Analytics. Vi rekommenderar om du vill ha Adobe Experience Platform Data Collection, men inte vill använda Adobe Experience Platform Edge-nätverksinfrastruktur.
  ![Analystillägg](./assets/mobilesdk-analytics-extension.png)

  Se [Implementera Adobe Analytics med Analytics-tillägget](../implement/aep-edge/mobile-sdk/overview.md) för mer information.


>[!CAUTION]
>
>Stöd för version 4 Mobile SDK upphörde den 31 augusti 2021. Mer information finns i [Vanliga frågor om att supporten ska upphöra för SDK:er för version 4 för mobila enheter](https://developer.adobe.com/client-sdks/resources/upgrade-platform-sdks/v4-faq/).

## Viktiga artiklar om implementering av Analytics

* [Ta hand om en befintlig Adobe Analytics-implementering](/help/implement/prepare/existing-implementation.md)
* [Adobe Debugger](validate/debugger.md)
* [Skapa en taggegenskap i Experience Platform](launch/create-analytics-property.md)
* [AppMeasurement](appmeasurement-updates.md)

## Fler användarhandböcker för Analytics

[Användarhandböcker för Analytics](https://experienceleague.adobe.com/docs/analytics.html)

## Viktiga Analytics-resurser

* [Kontakta kundtjänst](https://experienceleague.adobe.com/?support-solution=Analytics&amp;lang=sv#support)
* [Analytics-forum](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics/ct-p/adobe-analytics-community)
* [Adobe Analytics-resurser](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-discussions/adobe-analytics-resources/m-p/276666)
