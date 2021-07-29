---
title: Distribuera Adobe Analytics till en dev-miljö
description: Lär dig hur du använder taggar för att distribuera Adobe Analytics till din utvecklingsmiljö.
exl-id: 324943db-cb0b-40b1-8884-56bb3f608278
source-git-commit: ea6812c8e596773abb8a05bbdb37bc641967c9b8
workflow-type: tm+mt
source-wordcount: '594'
ht-degree: 0%

---

# Distribuera en analysimplementering till en utvecklingsmiljö

När du har skapat och konfigurerat en taggegenskap är biblioteken klara att distribueras och koden implementeras på platsen.

>[!NOTE]
>Adobe Experience Platform Launch har omklassificerats som en serie datainsamlingstekniker i Experience Platform. Som ett resultat av detta har flera terminologiska förändringar införts i produktdokumentationen. Se följande [dokument](https://experienceleague.adobe.com/docs/experience-platform/tags/term-updates.html?lang=en) för en konsoliderad referens till terminologiska ändringar.

## Förutsättningar

[Skapa och konfigurera en taggegenskap för Adobe Analytics](create-analytics-property.md): Få tillgång till verktyget och skapa ett utrymme för er Analytics-implementering.

## Skapa adaptrar och miljöer

Taggar kan hantera många organisatoriska arbetsflöden när kod distribueras. Följ de här stegen för att skapa de komponenter som krävs för en Analytics-implementering. Som tagghanterare kan du arbeta inom organisationen för att skapa rätt arbetsflöde för att distribuera Adobe-lösningar.

1. Logga in på [användargränssnittet för datainsamling](https://experience.adobe.com/data-collection) med inloggningsuppgifterna för ditt Adobe-ID.
2. Klicka på den taggegenskap som du tänker implementera på webbplatsen.
3. Klicka på fliken Adaptrar och sedan på Lägg till adapter.
4. Ge den namnet&quot;Akamai&quot; och välj Akamai i listrutan. Klicka på Spara.
5. Gå till fliken Miljöer och klicka sedan på Skapa ny miljö.
6. Välj Utveckling, kalla det&quot;Dev Environment&quot; och välj sedan Akamai-adaptern i listrutan. Klicka på Skapa och sedan på Stäng.
7. Klicka på Lägg till miljö, välj Förproduktion, kalla den för Mellanlagringsmiljö och välj sedan Akamai-adaptern. Klicka på Skapa och sedan på Stäng.
8. Klicka på Lägg till miljö igen, välj Produktion, kalla den &quot;Produktionsmiljö&quot; och välj sedan Akamai-adaptern. Klicka på Skapa och sedan på Stäng.

## Bygg ett dev-bibliotek

Trots alla ändringar och konfigurationer som gjorts hittills har ingen kod publicerats. Om du skapar ett bibliotek som är ungefär översatt som en samling ändringar kan du publicera kod på webbplatsen.

1. Logga in på [användargränssnittet för datainsamling](https://experience.adobe.com/data-collection) med inloggningsuppgifterna för ditt Adobe-ID.
2. Klicka på den taggegenskap som du tänker implementera på webbplatsen.
3. Klicka på fliken Publicering och sedan på Lägg till nytt bibliotek.
4. Ge biblioteket namnet &#39;Inledande ändringar&#39; och välj en utvecklingsmiljö.
5. Klicka på Lägg till alla ändrade resurser, som automatiskt visar Adobe Analytics, identitetstjänsten och kärnan.
6. Klicka på Spara.
7. Gå tillbaka till arbetsflödesfönstret för publicering, klicka på listrutan bredvid det nya biblioteket och klicka på Skapa för utveckling. Efter några sekunder blir den gula punkten i biblioteket grön, vilket anger att bygget lyckades.
8. Gå till fliken Miljöer och klicka sedan på utvecklingsmiljön.
9. Under Install tags (Installera taggar) kopierar du kodblocken och skickar dem till din organisations webbplatsägare.

## Installera taggar i webbplatsens utvecklingsmiljö

Om du styr koden för webbplatsen implementerar du de två kodblocken på deras respektive platser (i taggen `<head>` och precis ovanför den avslutande `</body>`-taggen) på varje sida på webbplatsen. Den här koden placeras vanligtvis i platsens övergripande mall. En tom sida som bara innehåller implementeringskod ser ut så här:

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
   <script type="text/javascript">_satellite.pageBottom();</script>
</body>
</html>
```

## Felsökning

**Ett försök att skapa misslyckades.**

En vanlig orsak är att det redan finns element i andra bibliotek som har flyttats till staging eller produktion. När du skapar bibliotek ska du först se till att endast ändrade resurser läggs till i biblioteket.

## Dokumentation och ytterligare resurser

- [Snabbstartguide](https://experienceleague.adobe.com/docs/experience-platform/tags/get-started/quick-start.html?lang=en): Lär dig det grundläggande arbetsflödet för taggimplementering
- [Översikt över](https://experienceleague.adobe.com/docs/experience-platform/tags/publish/overview.html?lang=en) publicering: Läs mer om publicering och miljöer

## Nästa steg

[Validera er Analytics-implementering och publicera i produktionen](validate-publish-prod.md): Börja få ut mer av Adobe Analytics.
