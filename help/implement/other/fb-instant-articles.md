---
title: Implementera med Facebook Instant Articles
description: Implementera Adobe Analytics på Facebook Instant Article-sidor.
feature: Implementation Basics
exl-id: 2189f70d-32f0-4137-9d53-7acab0f15e6c
source-git-commit: b3c74782ef6183fa63674b98e4c0fc39fc09441b
workflow-type: tm+mt
source-wordcount: '466'
ht-degree: 0%

---

# Implementera med Facebook Instant Articles

Med facebook Instant Articles kan utgivaren skapa snabba, interaktiva artiklar på Facebook. Instant Articles kan läsa in innehåll upp till 10 gånger snabbare än mobilwebben.

Du kan bädda in Adobe Analytics i Facebook Instant Articles för att spåra besökares beteende. Eftersom utgivarens innehåll finns i Facebook-appen och inte på utgivarens webbplatser skiljer sig taggningsmetoden något från en vanlig Analytics-implementering.

## Arbetsflöde

Det övergripande arbetsflödet för att implementera Adobe Analytics är följande:

1. Skapa en `stats.html` sida. Kod den här sidan för att hämta frågesträngsparametrar från URL:en och tilldela varje parameter till en Analytics-variabel
1. Värd för `stats.html` sida på webbservern
1. Implementera analyser på Facebook Instant Article genom att referera till `stats.html` fil i en iframe
1. Inkludera frågeparametrar i iframe `src` attribute

### Steg 1: Skapa en `stats.html` page

Exemplet HTML nedan kan användas för att hämta statistik från snabbartiklarna. Den här filen finns vanligtvis på en av företagets webbservrar. Varje gång en snabbartikel läses in, läses filen in i en iframe, vilket utlöser att data skickas till Adobe.

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
      var s_account = "examplersid1,examplersid2";
      var s_trackingServer = "example.data.adobedc.net";
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

### Steg 2: Värd för `stats.html` sida på webbservern

Adobe rekommenderar att du är värd för `stats.html` sida vid sida med den senaste versionen av `AppMeasurement.js` och `VisitorAPI.js`. Arbeta med rätt tekniker i organisationen för att hantera filen på rätt plats.

### Steg 3: Referens `stats.html` på varje Facebook Instant Article-sida

När du skapar Facebook Instant Article-innehåll bäddar du in HTML-innehåll för analyser i en iframe. Exempel:

```html
<iframe class="no-margin" src="https://example.com/stats.html" height="0"></iframe>
```

### Steg 4: Ange anpassad variabel och händelsespårning

Anpassade variabler och händelser kan spåras i HTML med hjälp av två olika metoder:

* Inkludera variabelvärden och händelser direkt i `stats.html` sida. Variabler som definieras här är bäst för värden som vanligtvis är desamma för alla Facebook Instant Articles.
* Inkludera variabelvärden som en del av en frågesträng som refererar till iframe. Med den här metoden kan du skicka variabelvärden från Facebook Instant Article till koden för iframe-värdanalys.

I följande exempel visas flera anpassade variabler som ingår i en frågesträng. Det JavaScript som finns i `stats.html` skulle sedan kontrollera frågesträngen med `s.Util.getQueryParam()`.

```html
<iframe class="no-margin" src="https://example.com/stats.html?eVar2=Dynamic%20article%20title&pageName=Example%20article%20name&cmpId=exampleID123" height="0"></iframe>
```

>[!NOTE]
>
>Refererardimensionen spåras inte automatiskt på grund av iframes-typen. Se till att du inkluderar den här dimensionen som en del av frågesträngen om du vill spåra den.

## Facebook Instant Articles och sekretess

Så länge Analytics HTML-sidan finns på webbservern stöder Adobe er befintliga integritetspolicy i alla Facebook Instant Articles. Om en användare väljer att inte följa detta på din primära webbplats avanmäler de sig också från spårning av alla dina Facebook Instant Articles. Verktygssidan har också stöd för Adobe Experience Cloud Identity Service så att du kan integrera Facebook Instant Article-data med resten av Experience Cloud.
