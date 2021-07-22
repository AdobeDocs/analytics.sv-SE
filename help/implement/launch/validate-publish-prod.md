---
title: Validera en utvecklingsimplementering och publicera till produktion
description: Lär dig hur du använder Adobe Experience Platform-taggar för att distribuera Adobe Analytics till din produktionsmiljö.
exl-id: 2f5bcfee-d75e-4dac-bea9-91c6cc545173
source-git-commit: 5368e808a862a3e320f5d079433db96ab79b45c8
workflow-type: tm+mt
source-wordcount: '669'
ht-degree: 0%

---

# Validera en utvecklingsimplementering och publicera till produktion

När taggbiblioteket är i produktion kan ni börja använda Adobe Analytics för att hämta in grundläggande rapporter.

>[!NOTE]
>Adobe Experience Platform Launch har omklassificerats som en serie datainsamlingstekniker i Experience Platform. Som ett resultat av detta har flera terminologiska förändringar införts i produktdokumentationen. Se följande [dokument](https://experienceleague.adobe.com/docs/experience-platform/tags/term-updates.html?lang=en) för en konsoliderad referens till terminologiska ändringar.

## Förutsättningar

[Distribuera er Analytics-implementering i er utvecklingsmiljö](deploy-dev.md): En Analytics-implementering måste publiceras i utvecklingsmiljön för att den här sidan ska kunna följas.

## Validera din dev-implementering med felsökningsfunktionen i Experience Cloud

Felsökaren Experience Cloud är en Chrome-plugin som visar alla Experience Cloud-taggar som finns på en sida.

1. Öppna [Chrome Web Browser](https://www.google.com/chrome/) och gå till [Adobe Experience Cloud Debugger](https://chrome.google.com/webstore/detail/adobe-experience-cloud-de/ocdmogmohccmeicdhlhhgepeaijenapj) på Chrome Web Store för att installera tillägget.
2. Navigera till den utvecklingswebbplats där du har implementerat taggar.
3. Klicka på felsökningsikonen för Adobe Experience Cloud i det övre högra hörnet av Chrome
4. Om allt är korrekt implementerat bör du se innehåll i Adobe Analytics, taggar och tjänsten Adobe Experience Cloud Visitor ID:

![debugger][assets/debugger.png]

## Distribuera din dev-implementering till staging/prod

När du har validerat dina data kan du överföra implementeringen till den publicerade versionen av webbplatsen.

1. Gå till [experience.adobe.com](https://experience.adobe.com) och logga in när du uppmanas till det.
1. Välj **[!UICONTROL Launch / Data Collection]**.
1. Klicka på **[!UICONTROL Go to Launch / Data Collection]** och välj sedan **[!UICONTROL Tags]**.
1. Klicka på den taggegenskap som du tänker implementera på webbplatsen.
1. Klicka på fliken **[!UICONTROL Publishing]** och leta upp ditt bibliotek i utvecklingskolumnen.
1. Klicka på listrutan i biblioteket och välj **[!UICONTROL Submit for Approval]**. Klicka på **[!UICONTROL Submit]** i det modala fönstret.
1. Klicka på bibliotekets listruta igen (nu i kolumnen Skickat) och välj **[!UICONTROL Build for Staging]**.
1. Efter en stund blir det gula färgade ljuset i biblioteket grönt, vilket indikerar att bygget lyckades.
1. Klicka på bibliotekets listruta igen och välj **[!UICONTROL Approve for Publishing]**.
1. Klicka på bibliotekets listruta igen (nu i kolumnen [!UICONTROL Approved]) och välj **[!UICONTROL Build and Publish to Production]**.
1. Gå till fliken Miljöer och klicka på **[!UICONTROL Production Environment]**.
1. Kopiera produktionshuvudet + sidfotskoden och ge den till webbplatsägarna. Begär att de implementerar den här koden i din webbplats produktionsmiljö.

## Validera din produktionsimplementering

Bekräfta att du ser data i den publicerade versionen av din webbplats och börja samla in data för Adobe Analytics.

1. När du har bekräftat för webbplatsägarna att de har överfört taggkoden till produktion går du till webbplatsens hemsida i Chrome och öppnar [!UICONTROL Adobe Experience Cloud debugger].
2. Om allt fungerar bör du se data som liknar dina tester i din utvecklingsmiljö. Nu samlar du in data på webbplatsen och kan börja använda Adobe Analytics för rapportering.

## Felsökning

**Inga data visas i felsökaren.**

Öppna webbläsarens utvecklarkonsol (vanligtvis F12) när du är på din plats. Titta på sidans källkod och kontrollera att följande uppfylls:

* Det finns inga JavaScript-fel i konsolen. Samarbeta med webbplatsägarna i organisationen för att säkerställa att alla JS-fel åtgärdas.
* Huvudkoden är korrekt implementerad: Kontrollera att rubrikkoden finns inuti taggen `<head>` och att filen finns.
* AppMeasurement-biblioteket finns: Navigera direkt till JS-källan för att kontrollera att JS-filen innehåller kod. Om så inte är fallet kontrollerar du att alla miljöer har skapats och att biblioteket har publicerats i respektive miljö.
* Interfering plug-ins: Vissa Chrome-plugin-program kan förhindra att bildbegäranden utlöses. Inaktivera plugin-program som kan förhindra att data skickas till Adobe-servrar.

## Nästa steg

Nu när en grundläggande implementering är klar kan din roll i organisationen påverka vilken väg du vill lära dig mer om:

* [Skapa ett designdokument](../prepare/solution-design.md): Planera hur du vill använda anpassade variabler och inkludera dem sedan i implementeringen
* [Kom igång med Analysis Workspace](/help/analyze/analysis-workspace/home.md): Gör en djupdykning i Adobe Analytics med verktygets flaggskeppsfunktion.
