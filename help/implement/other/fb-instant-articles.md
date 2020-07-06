---
title: Implementera med Facebook Instant Articles
description: Implementera Adobe Analytics på Facebook Instant Article-sidor.
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '466'
ht-degree: 0%

---


# Implementera med Facebook Instant Articles

Med Direktartiklar på Facebook kan utgivaren skapa snabba, interaktiva artiklar på Facebook. Instant Articles kan läsa in innehåll upp till 10 gånger snabbare än mobilwebben.

Du kan bädda in Adobe Analytics på Facebook Instant Articles för att spåra besökares beteende. Eftersom utgivarens innehåll ligger inom Facebook-appen och inte på utgivarens webbplatser skiljer sig taggningsmetoden något från en vanlig Analytics-implementering.

## Arbetsflöde

Det övergripande arbetsflödet för att implementera Adobe Analytics är följande:

1. Skapa en `stats.html` sida. Kod den här sidan för att hämta frågesträngsparametrar från URL:en och tilldela varje parameter till en Analytics-variabel
1. Lägg sidan som värd `stats.html` på webbservern
1. Implementera Analytics på Facebook Instant Article genom att referera till `stats.html` filen i en iframe
1. Inkludera frågeparametrar i iframe- `src` attributet

### Steg 1: Skapa en `stats.html` sida

HTML-exempelkoden nedan kan användas för att hämta statistik från snabbartiklarna. Den här filen finns vanligtvis på en av företagets webbservrar. Varje gång en Instant Article läses in, läses filen in i en iframe, vilket utlöser att data skickas till Adobe.

```html
<html>
  <head>
    <title>Facebook Stats</title>
      <script language="javaScript" type="text/javascript" src="VisitorAPI.js"></script>
      <script language="javaScript" type="text/javascript" src="AppMeasurement.js"></script>
  </head>
  <body>
    <script>
      var v_orgId = "INSERT-ORG-ID-HERE";
      var s_account = "examplersid";
      var s_trackingServer = "example.sc.omtrdc.net";
      var visitor = Visitor.getInstance(v_orgId);
      visitor.trackingServer = s_trackingServer;

      var s = s_gi(s_account);
      s.account = s_account;
      s.trackingServer = s_trackingServer;
      s.visitor = visitor;

      s.pageName = s.Util.getQueryParam("pageName");
      s.pageURL = document.referrer; // The referrer to the utility page is the parent frame
      s.campaign = s.Util.getQueryParam("cmpId");
      s.eVar1 = "Facebook Instant Article";
      s.eVar2 = s.Util.getQueryParam("eVar2");

      s.t();
    </script>
  </body>
</html>
```

### Steg 2: Lägg sidan som värd `stats.html` på webbservern

Adobe rekommenderar att du publicerar din `stats.html` sida tillsammans med den senaste versionen av `AppMeasurement.js` och `VisitorAPI.js`. Arbeta med rätt tekniker i organisationen för att hantera filen på rätt plats.

### Steg 3: Referens `stats.html` på varje Facebook Instant Article-sida

När du skapar innehåll för Facebook Instant Article bäddar du in HTML-innehåll för analyser i en iframe. Exempel:

```html
<iframe class="no-margin" src="https://example.com/stats.html" height="0"></iframe>
```

### Steg 4: Ange anpassad variabel och händelsespårning

Anpassade variabler och händelser kan spåras i HTML-koden för analyser på två olika sätt:

* Inkludera variabelvärden och händelser direkt på `stats.html` sidan. Variabler som definieras här är bäst för värden som vanligtvis är desamma för alla snabbartiklar på Facebook.
* Inkludera variabelvärden som en del av en frågesträng som refererar till iframe. Med den här metoden kan du skicka variabelvärden från Facebook Instant Article till iframe-värdkoden för Analytics.

I följande exempel visas flera anpassade variabler som ingår i en frågesträng. Det JavaScript som finns i `stats.html` skulle sedan kontrollera frågesträngen med `s.Util.getQueryParam()`.

```html
<iframe class="no-margin" src="https://example.com/stats.html?eVar2=Dynamic%20article%20title&pageName=Example%20article%20name&cmpId=exampleID123" height="0"></iframe>
```

>[!NOTE]
>
>Refererardimensionen spåras inte automatiskt på grund av iframes-typen. Se till att du inkluderar den här dimensionen som en del av frågesträngen om du vill spåra den.

## Direktartiklar och sekretess för Facebook

Så länge Analytics HTML-sida finns på din webbserver, stöder Adobe din befintliga integritetspolicy för alla Facebook Instant Articles. Om en användare avstår från spårning på din primära webbplats avanmäler de sig också från spårning på alla dina Facebook Instant Articles. Verktygssidan har också stöd för Adobe Experience Cloud Identity Service så att ni kan integrera Facebook Instant Article-data med resten av Experience Cloud.
