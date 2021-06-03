---
title: Distribuera Adobe Analytics till en dev-miljö
description: Lär dig hur du använder Adobe Experience Platform Launch för att distribuera Adobe Analytics till din utvecklingsmiljö.
exl-id: 324943db-cb0b-40b1-8884-56bb3f608278
source-git-commit: f669af03a502d8a24cea3047b96ec7cba7c59e6f
workflow-type: tm+mt
source-wordcount: '544'
ht-degree: 1%

---

# Distribuera en analysimplementering till en utvecklingsmiljö

När en egenskap har skapats och konfigurerats i Launch är biblioteken klara att distribueras och koden implementeras på din webbplats.

## Förutsättningar

[Skapa och konfigurera en egenskap för Adobe Analytics i Launch](create-analytics-property.md): Få tillgång till verktyget och skapa ett utrymme för er Analytics-implementering.

## Skapa adaptrar och miljöer

Launch innehåller många organisatoriska arbetsflöden för att distribuera kod. Följ de här stegen för att skapa de komponenter som krävs för en Analytics-implementering. Som Launch-administratör kan du arbeta inom organisationen för att skapa rätt arbetsflöde för att distribuera Adobe-lösningar.

1. Gå till [Adobe Experience Platform Launch](https://launch.adobe.com) och logga in om du uppmanas till det.
2. Klicka på den Launch-egenskap som du vill implementera på webbplatsen.
3. Klicka på fliken Adaptrar och sedan på Lägg till adapter.
4. Ge den namnet&quot;Akamai&quot; och välj Akamai i listrutan. Klicka på Spara.
5. Gå till fliken Miljöer och klicka sedan på Skapa ny miljö.
6. Välj Utveckling, kalla det&quot;Dev Environment&quot; och välj sedan Akamai-adaptern i listrutan. Klicka på Skapa och sedan på Stäng.
7. Klicka på Lägg till miljö, välj Förproduktion, kalla den för Mellanlagringsmiljö och välj sedan Akamai-adaptern. Klicka på Skapa och sedan på Stäng.
8. Klicka på Lägg till miljö igen, välj Produktion, kalla den &quot;Produktionsmiljö&quot; och välj sedan Akamai-adaptern. Klicka på Skapa och sedan på Stäng.

## Bygg ett dev-bibliotek

Trots alla ändringar och konfigurationer som gjorts hittills har ingen kod publicerats. Om du skapar ett bibliotek som är ungefär översatt som en samling ändringar kan du publicera kod på webbplatsen.

1. Gå till [Adobe Experience Platform Launch](https://launch.adobe.com) och logga in om du uppmanas till det.
2. Klicka på den Launch-egenskap som du vill implementera på webbplatsen.
3. Klicka på fliken Publicering och sedan på Lägg till nytt bibliotek.
4. Ge biblioteket namnet &#39;Inledande ändringar&#39; och välj en utvecklingsmiljö.
5. Klicka på Lägg till alla ändrade resurser, som automatiskt visar Adobe Analytics, identitetstjänsten och kärnan.
6. Klicka på Spara.
7. Gå tillbaka till arbetsflödesfönstret för publicering, klicka på listrutan bredvid det nya biblioteket och klicka på Skapa för utveckling. Efter några sekunder blir den gula punkten i biblioteket grön, vilket anger att bygget lyckades.
8. Gå till fliken Miljöer och klicka sedan på utvecklingsmiljön.
9. Under Install Launch kopierar du kodblocken och skickar dem till din organisations webbplatsägare.

## Installera Launch i webbplatsens utvecklingsmiljö

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

- [Komma igång med Launch](https://experienceleague.adobe.com/docs/launch/using/intro/get-started/quick-start.html): Lär dig det grundläggande arbetsflödet i Launch
- [Starta publicering](https://experienceleague.adobe.com/docs/launch/using/reference/publish/overview.html): Läs mer om publicering och miljöer

## Nästa steg

[Validera er Analytics-implementering och publicera i produktionen](validate-publish-prod.md): Börja få ut mer av Adobe Analytics.
