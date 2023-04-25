---
title: Validera en utvecklingsimplementering och publicera till produktion
description: Lär dig hur du använder Adobe Experience Platform-taggar för att distribuera Adobe Analytics till din produktionsmiljö.
feature: Launch Implementation
exl-id: 2f5bcfee-d75e-4dac-bea9-91c6cc545173
source-git-commit: 78cfb1f3c4d45fc983982a8da11b66f2b2c9ecbc
workflow-type: tm+mt
source-wordcount: '612'
ht-degree: 2%

---

# Validera en utvecklingsimplementering och publicera till produktion

När taggbiblioteket är i produktion kan ni börja använda Adobe Analytics för att hämta in grundläggande rapporter.

## Förutsättningar

[Distribuera er Analytics-implementering i er utvecklingsmiljö](deploy-dev.md): En Analytics-implementering måste publiceras i utvecklingsmiljön för att den här sidan ska kunna följas.

## Validera din dev-implementering med felsökningsfunktionen i Experience Cloud

Felsökaren Experience Cloud är ett tillägg som visar alla Experience Cloud-taggar som finns på en sida.

1. Installera tillägget för antingen [Krom](https://chrome.google.com/webstore/detail/adobe-experience-platform/bfnnokhpnncpkdmbokanobigaccjkpob) eller [Firefox](https://addons.mozilla.org/sv-SE/firefox/addon/adobe-experience-platform-dbg/).
2. Navigera till den utvecklingswebbplats där du har implementerat taggar.
3. Klicka på Adobe Experience Cloud felsökningsikon i webbläsaren.
4. Om allt är korrekt implementerat bör du se innehåll i Adobe Analytics, taggar och tjänsten Adobe Experience Cloud Visitor ID.

## Distribuera din dev-implementering till staging/prod

När du har verifierat att du ser data kan du överföra implementeringen till den publicerade versionen av webbplatsen.

1. Logga in på [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) med inloggningsuppgifterna för ditt AdobeID.
1. Klicka på den taggegenskap som du tänker implementera på webbplatsen.
1. Klicka på **[!UICONTROL Publishing]** och leta upp ditt bibliotek i utvecklingskolumnen.
1. Klicka på listrutan i biblioteket och välj **[!UICONTROL Submit for Approval]**. Klicka **[!UICONTROL Submit]** i modalfönstret.
1. Klicka på bibliotekets listruta igen (nu i kolumnen Skickat) och välj **[!UICONTROL Build for Staging]**.
1. Efter en stund blir det gula färgade ljuset i biblioteket grönt, vilket indikerar att bygget lyckades.
1. Klicka på bibliotekets listruta igen och välj **[!UICONTROL Approve for Publishing]**.
1. Klicka på bibliotekets listruta igen (nu i [!UICONTROL Approved] kolumn) och markera **[!UICONTROL Build and Publish to Production]**.
1. Gå till fliken Miljö och klicka **[!UICONTROL Production Environment]**.
1. Kopiera produktionsinstallationskoden och skicka den till webbplatsägarna. Begär att de implementerar den här koden i din webbplats produktionsmiljö.

## Validera din produktionsimplementering

Bekräfta att du ser data i den publicerade versionen av din webbplats och börja samla in data för Adobe Analytics.

1. När du har bekräftat för webbplatsägarna att de har överfört taggkoden till produktion går du till webbplatsens hemsida i Chrome och öppnar [!UICONTROL Adobe Experience Cloud debugger].
2. Om allt fungerar bör du se data som liknar dina tester i din utvecklingsmiljö. Nu samlar du in data på webbplatsen och kan börja använda Adobe Analytics för rapportering.

## Felsökning

**Inga data visas i felsökaren.**

Öppna webbläsarens utvecklarkonsol (vanligtvis F12) när du är på din plats. Titta på sidans källkod och kontrollera att följande uppfylls:

* Det finns inga JavaScript-fel i konsolen. Samarbeta med webbplatsägarna i organisationen för att säkerställa att alla JS-fel åtgärdas.
* Huvudkoden är korrekt implementerad: Kontrollera att rubriktexten finns inuti `<head>` och att filen finns.
* AppMeasurement-biblioteket finns: Navigera direkt till JS-källan för att kontrollera att JS-filen innehåller kod. Om så inte är fallet kontrollerar du att alla miljöer har skapats och att biblioteket har publicerats i respektive miljö.
* Interfering extensions: Vissa tillägg, till exempel annonsblockerare, kan förhindra att bildbegäranden utlöses. Inaktivera tillägg som kan stoppa data från att skickas till Adobe.

## Nästa steg

Nu när en grundläggande implementering är klar kan din roll i organisationen påverka vilken väg du vill lära dig mer om:

* [Skapa ett dokument för lösningsdesign](../prepare/solution-design.md): Planera hur du vill använda anpassade variabler och inkludera dem sedan i implementeringen
* [Kom igång med Analysis Workspace](/help/analyze/analysis-workspace/home.md): Gör en djupdykning i Adobe Analytics med verktygets flaggskeppsfunktion.
