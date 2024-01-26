---
title: Distribuera Adobe Analytics i en utvecklingsmiljö
description: Lär dig hur du använder taggar för att distribuera Adobe Analytics till din utvecklingsmiljö.
feature: Tags
exl-id: 324943db-cb0b-40b1-8884-56bb3f608278
role: Admin, Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '551'
ht-degree: 0%

---

# Distribuera en analysimplementering till en utvecklingsmiljö

När du har skapat och konfigurerat en taggegenskap är biblioteken klara att distribueras och koden implementeras på platsen.

## Förutsättningar

[Skapa och konfigurera en taggegenskap för Adobe Analytics](create-analytics-property.md): Använd verktyget och skapa ett utrymme för er Analytics-implementering.

## Skapa adaptrar och miljöer

Taggar kan hantera många organisatoriska arbetsflöden när kod distribueras. Följ de här stegen för att skapa de komponenter som krävs för en Analytics-implementering. Som tagghanterare kan du arbeta inom organisationen för att skapa rätt arbetsflöde för att distribuera Adobe-lösningar.

1. Logga in på [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) med inloggningsuppgifterna för ditt AdobeID.
2. Klicka på den taggegenskap som du tänker implementera på webbplatsen.
3. Klicka **[!UICONTROL Hosts]** och sedan klicka **[!UICONTROL Add Host]**.
4. Ge den ett namn `"Adobe managed"`och markera **[!UICONTROL Managed by Adobe]** i typlistan. Klicka på Spara.
5. Navigera till **[!UICONTROL Environments]** och sedan klicka **[!UICONTROL Add Environment]**.
6. Välj **[!UICONTROL Development]**, namnge `"Dev Environment"`väljer du sedan den Adobe-hanterade värden i listrutan. Klicka på **[!UICONTROL Save]**.
7. Ett modalt fönster med instruktioner för webbinstallation visas. Vi återgår till det här fönstret vid ett senare tillfälle. **[!UICONTROL Close]** för tillfället.
8. Klicka **[!UICONTROL Add Environment]**, markera **[!UICONTROL Staging]**, namnge `"Staging Environment"`väljer du sedan den Adobe-hanterade värden. Klicka **[!UICONTROL Create]** stänger du installationsinstruktionens modala fönster.
9. Klicka **[!UICONTROL Add Environment]** igen, välj **[!UICONTROL Production]**, namnge `"Production Environment"`väljer du sedan den Adobe-hanterade värden. Klicka **[!UICONTROL Create]** stänger du installationsinstruktionens modala fönster.

## Bygg ett dev-bibliotek

Trots alla ändringar och konfigurationer som gjorts hittills har ingen kod publicerats. Om du skapar ett bibliotek som är ungefär översatt som en samling ändringar kan du publicera kod på webbplatsen.

1. Logga in på [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) med inloggningsuppgifterna för ditt AdobeID.
2. Klicka på den taggegenskap som du tänker implementera på webbplatsen.
3. Klicka på **[!UICONTROL Publishing Flow]** tabbtangenten och klicka sedan på **[!UICONTROL Add Library]**. Se [Översikt över publicering](https://experienceleague.adobe.com/docs/experience-platform/tags/publish/overview.html) i taggdokumentationen för mer information om den här sidan.
4. Namnge biblioteket `'Initial changes'`och väljer utvecklingsmiljö.
5. Klicka **[!UICONTROL Add All Changed Resources]**, som automatiskt listar Adobe Analytics, identitetstjänst och kärna.
6. Klicka på **[!UICONTROL Save]**.
7. Gå tillbaka till arbetsflödesfönstret, klicka på listrutan bredvid det nya biblioteket och klicka på **[!UICONTROL Build for Development]**. Efter några sekunder blir den gula punkten i biblioteket grön, vilket anger att bygget lyckades.
8. Navigera till **[!UICONTROL Environments]** klickar du sedan på installationsikonen till höger om utvecklingsmiljön. Den här åtgärden öppnar det modala fönstret för instruktioner för webbinstallation igen.
9. Kopiera kodblocken och skicka dem till din organisations webbplatsägare.

## Installera taggar i webbplatsens utvecklingsmiljö

Om du kontrollerar koden för webbplatsen implementerar du varje kodblock på respektive plats:

* Huvudtaggen tillhör `<head>` -tagg på din webbplats.
* Om du väljer att läsa in taggar synkront måste du även inkludera ett andra kodblock precis under stängningen `</body>` -tagg på din webbplats. Du kan välja att läsa in bibliotekstaggar synkront genom att aktivera **[!UICONTROL Load Library Asynchronously]** i Web Install Instructions.

Taggkoden placeras vanligtvis i platsens övergripande mall. En tom sida som bara innehåller implementeringskod ser ut så här:

```html
<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8">
  <title>Example page</title>
  <script src="//assets.adobedtm.com/launch-xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx-development.min.js"></script>
</head>
<body>
   <p>This is a test page.</p>
   <!-- Only include this extra code if you load tags synchronously -->
   <script type="text/javascript">_satellite.pageBottom();</script>
</body>
</html>
```

## Felsökning

**Ett försök att skapa misslyckades.**

En vanlig orsak är att det redan finns element i andra bibliotek som har flyttats till staging eller produktion. När du skapar bibliotek ska du först se till att endast ändrade resurser läggs till i biblioteket.

## Nästa steg

[Validera er Analytics-implementering och publicera till produktion](validate-publish-prod.md): Börja få ut mer av Adobe Analytics.
