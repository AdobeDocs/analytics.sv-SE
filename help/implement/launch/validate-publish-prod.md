---
title: Validera en utvecklingsimplementering och publicera till produktion
description: Lär dig hur du använder Adobe Experience Platform-taggar för att distribuera Adobe Analytics till din produktionsmiljö.
feature: Tags
exl-id: 2f5bcfee-d75e-4dac-bea9-91c6cc545173
role: Admin, Developer
source-git-commit: e35210582e94037cf286b98e7e0a6b06040a8c6f
workflow-type: tm+mt
source-wordcount: '599'
ht-degree: 0%

---

# Validera en utvecklingsimplementering och publicera till produktion

När taggbiblioteket är i produktion kan ni börja använda Adobe Analytics för att hämta in grundläggande rapporter.

## Förutsättningar

[Distribuera din Analytics-implementering till din utvecklingsmiljö](deploy-dev.md): En Analytics-implementering måste publiceras till din utvecklingsmiljö för att du ska kunna följa den här sidan.

## Validera din dev-implementering med felsökningsfunktionen i Experience Cloud

Felsökaren Experience Cloud är ett tillägg som visar alla Experience Cloud-taggar som finns på en sida.

1. Installera tillägget för [Chrome](https://chromewebstore.google.com/detail/adobe-experience-platform/bfnnokhpnncpkdmbokanobigaccjkpob) eller Firefox.
2. Navigera till den utvecklingswebbplats där du har implementerat taggar.
3. Klicka på Adobe Experience Cloud felsökningsikon i webbläsaren.
4. Om allt är korrekt implementerat bör du se innehåll i Adobe Analytics, taggar och tjänsten Adobe Experience Cloud Visitor ID.

## Distribuera din dev-implementering till staging/prod

När du har verifierat att du ser data kan du överföra implementeringen till den publicerade versionen av webbplatsen.

1. Logga in på [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) med dina inloggningsuppgifter för AdobeID.
1. Klicka på den taggegenskap som du tänker implementera på webbplatsen.
1. Klicka på fliken **[!UICONTROL Publishing]** och leta upp ditt bibliotek i utvecklingskolumnen.
1. Klicka på listrutan i biblioteket och välj sedan **[!UICONTROL Submit for Approval]**. Klicka på **[!UICONTROL Submit]** i det modala fönstret.
1. Klicka på bibliotekets nedrullningsbara lista igen (nu i kolumnen Skickat) och välj **[!UICONTROL Build for Staging]**.
1. Efter en stund blir det gula färgade ljuset i biblioteket grönt, vilket indikerar att bygget lyckades.
1. Klicka på bibliotekets listruta igen och välj **[!UICONTROL Approve for Publishing]**.
1. Klicka på bibliotekets nedrullningsbara lista igen (nu i kolumnen [!UICONTROL Approved]) och välj **[!UICONTROL Build and Publish to Production]**.
1. Gå till fliken Miljöer och klicka på **[!UICONTROL Production Environment]**.
1. Kopiera produktionsinstallationskoden och skicka den till webbplatsägarna. Begär att de implementerar den här koden i din webbplats produktionsmiljö.

## Validera din produktionsimplementering

Bekräfta att du ser data i den publicerade versionen av din webbplats och börja samla in data för Adobe Analytics.

1. När du har bekräftat för webbplatsägarna att de har överfört taggkoden till produktion går du till webbplatsens hemsida i Chrome och öppnar [!UICONTROL Adobe Experience Cloud debugger].
2. Om allt fungerar bör du se data som liknar dina tester i din utvecklingsmiljö. Nu samlar du in data på webbplatsen och kan börja använda Adobe Analytics för rapportering.

## Felsökning

**Inga data visas i felsökaren.**

Öppna webbläsarens utvecklarkonsol (vanligtvis F12) när du är på din plats. Titta på sidans källkod och kontrollera att följande uppfylls:

* Konsolen innehåller inga JavaScript-fel. Samarbeta med webbplatsägarna i organisationen för att säkerställa att alla JS-fel åtgärdas.
* Huvudkoden är korrekt implementerad: Kontrollera att rubriktoden finns inuti taggen `<head>` och att filen finns.
* AppMeasurementen finns: Navigera direkt till JS-källan och kontrollera att JS-filen innehåller kod. Om så inte är fallet kontrollerar du att alla miljöer har skapats och att biblioteket har publicerats i respektive miljö.
* Interfering extensions: Vissa tillägg, t.ex. annonsblockerare, kan förhindra att bildbegäranden utlöses. Inaktivera tillägg som kan stoppa data från att skickas till Adobe.

## Nästa steg

Nu när en grundläggande implementering är klar kan din roll i organisationen påverka vilken väg du vill lära dig mer om:

* [Skapa ett lösningsdesigndokument](../prepare/solution-design.md): Skapa en plan för hur du vill använda anpassade variabler och ta sedan med dem i implementeringen
* [Kom igång med Analysis Workspace](/help/analyze/analysis-workspace/home.md): Gå direkt till Adobe Analytics med verktygets flaggfunktion.
