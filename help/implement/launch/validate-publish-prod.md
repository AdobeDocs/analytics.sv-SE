---
title: Distribuera Adobe Analytics i en utvecklingsmiljö
description: Lär dig hur du använder Adobe Experience Platform Launch för att distribuera Adobe Analytics till din utvecklingsmiljö.
translation-type: tm+mt
source-git-commit: 2ffa989156dd9bc4f6ef9a216e8c06425cc39440

---


# Validera en utvecklingsimplementering och publicera till produktion

När ditt Adobe Experience Platform Launch-bibliotek väl är i produktion kan organisationen börja använda Adobe Analytics för att hämta grundläggande rapporter.

## Förutsättningar

[Distribuera er Analytics-implementering i er utvecklingsmiljö](deploy-dev.md): En Analytics-implementering måste publiceras i utvecklingsmiljön för att den här sidan ska kunna följas.

## Validera din dev-implementering med Experience Cloud-felsökaren

Experience Cloud-felsökaren är en Chrome-plugin som visar alla Experience Cloud-taggar som finns på en sida.

1. Öppna [Chrome Web Browser](https://www.google.com/chrome/) och gå till [Adobe Experience Cloud Debugger](https://chrome.google.com/webstore/detail/adobe-experience-cloud-de/ocdmogmohccmeicdhlhhgepeaijenapj) i Chrome Web Store för att installera tillägget.
2. Navigera till den utvecklingswebbplats som du har implementerat Launch på.
3. Klicka på felsökningsikonen för Adobe Experience Cloud i det övre högra hörnet av Chrome
4. Om allt är korrekt implementerat bör du se innehåll i Adobe Analytics, Adobe Experience Platform Launch och Adobe Experience Cloud Visitor ID-tjänsten:

![debugger][assets/debugger.png]

## Distribuera din dev-implementering till staging/prod

När du har validerat dina data kan du överföra implementeringen till den publicerade versionen av webbplatsen.

1. Gå till [Adobe Experience Platform Launch](https://launch.adobe.com) och logga in om du uppmanas till detta.
2. Klicka på den Launch-egenskap som du vill implementera på webbplatsen.
3. Klicka på fliken Publicering och leta upp biblioteket i utvecklingskolumnen.
4. Klicka på listrutan i biblioteket och välj sedan Skicka för godkännande. Klicka på Skicka i det modala fönstret.
5. Klicka på bibliotekets listruta igen (nu i kolumnen Skickat) och välj Skapa för mellanlagring.
6. Efter en stund blir det gula färgade ljuset i biblioteket grönt, vilket indikerar att bygget lyckades.
7. Klicka på bibliotekets listruta igen och välj Godkänn för publicering.
8. Klicka på bibliotekets listruta igen (nu i kolumnen Godkänd) och välj Skapa och publicera till produktion.
9. Gå till fliken Miljöer och klicka på Produktionsmiljö.
10. Kopiera produktionshuvudet + sidfotskoden och ge den till webbplatsägarna. Begär att de implementerar den här koden i din webbplats produktionsmiljö.

## Validera din produktionsimplementering

Bekräfta att du ser data i den publicerade versionen av din webbplats och påbörja den officiella datainsamlingen för Adobe Analytics.

1. När du har bekräftat från webbplatsägarna att de har överfört startkoden till produktion går du till webbplatsens hemsida i Chrome och öppnar felsökningsfunktionen för Adobe Experience Cloud.
2. Om allt fungerar bör du se data som liknar dina tester i din utvecklingsmiljö. Nu samlar ni in data på er webbplats och kan nu börja använda Adobe Analytics för rapportering.

## Felsökning

**Inga data visas i felsökaren.**

Öppna webbläsarens utvecklarkonsol (vanligtvis F12) när du är på din plats. Titta på sidans källkod och kontrollera att följande uppfylls:

* Det finns inga JavaScript-fel i konsolen. Samarbeta med webbplatsägarna i organisationen för att säkerställa att alla JS-fel åtgärdas.
* Huvudkoden är korrekt implementerad: Kontrollera att rubriktexten finns inuti `<head>` -taggen och att filen finns.
* AppMeasurement-biblioteket finns: Navigera direkt till JS-källan för att kontrollera att JS-filen innehåller kod. Om så inte är fallet kontrollerar du att alla miljöer har skapats och att biblioteket har publicerats i respektive miljö.
* Interfering plug-ins: Vissa Chrome-plugin-program kan förhindra att bildbegäranden utlöses. Inaktivera plugin-program som kan stoppa data från att skickas till Adobes servrar.

## Nästa steg

Nu när en grundläggande implementering har konfigurerats kan din roll i organisationen påverka vilken väg du vill lära dig mer om:

* [Skapa ett designdokument](../prepare/solution-design.md): Planera hur du vill använda anpassade variabler och inkludera dem sedan i implementeringen
* [Kom igång med Analysis Workspace](/help/analyze/analysis-workspace/home.md): Gör en djupdykning i Adobe Analytics med verktygets flaggskeppsfunktion.
