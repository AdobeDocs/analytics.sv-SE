---
title: Implementera med AMP
description: Implementera Adobe Analytics på AMP-sidor.
translation-type: tm+mt
source-git-commit: 9d2007bead6a4963022f8ea884169802b1c002ff

---


# Implementera med AMP

[AMP](https://amp.dev) är ett HTML-ramverk med öppen källkod som ger ett enkelt sätt att skapa snabba och smidiga webbsidor.

Eftersom Adobe Analytics använder ett JavaScript-bibliotek för att kompilera och skicka en bildbegäran, krävs justeringar i implementeringen för att skicka data till Adobe på sidor med AMP.

## Bestäm vilken metod Adobe Analytics ska implementeras på sidor med AMP

Adobe har skapat två metoder för att implementera Adobe Analytics på sidor med AMP. Båda använder `<amp-analytics>` HTML-taggen. Mer information finns i taggen [](https://github.com/ampproject/amphtml/tree/master/extensions/amp-analytics) amp-analytics på GitHub-projektet för ampproject.

* **Använd`"adobeanalytics"`spårningsmallen**: Skapa Analytics-begäran direkt på sidan
* **Använd`"analytics_nativeConfig"`spårningsmallen**: Använd en iframe som innehåller samma AppMeasurement-kod som du distribuerar på din normala webbplats

I följande tabell jämförs dessa två metoder:

|  | **adobeanalytics-mall** | **mallen&quot;adobeanalytics_nativeConfig&quot;** |
|---|---|---|
| Besöks-/besöksantal i befintlig rapportserie | Hög uppblåsning | Minimal uppblåsning |
| Använd en separat rapportserie | Rekommenderas | Inte nödvändigt |
| Nya kontra återkommande besökare | Stöds inte | Stöds |
| Tjänst för besökar-ID | Stöds inte | Stöds |
| Video- och länkspårning | Delvis stöd | Stöds ännu inte |
| Svårighet att genomföra | Något svårt | relativt enkelt |
| Integreringar med Adobe Experience Cloud | Stöds inte | Delvis stöd |

Väg in proffsen och ikonerna i organisationen för att avgöra vilken metod du vill använda. Se [AMP-exempel](https://github.com/Adobe-Marketing-Cloud/mobile-services/tree/master/samples/mobile-web) på Adobes GitHub-databas för exempelkod.

> [!WARNING] Använd inte både `"adobeanalytics"` - och `"adobeanalytics_nativeConfig"` -mallarna på samma sida med AMP. Om du försöker göra det kan du generera fel i webbläsarkonsolen och dubbelräkna besökare.

## Metod 1: Använd taggen amp-analytics med mallen&quot;adobeanalytics&quot;

Spårningsmallen använder `"adobeanalytics"` `<amp-analytics>` HTML-taggen för att skapa en spårningsbegäran direkt. Du kan ange träffförfrågningar som startar vid specifika sidhändelser, som att sidan blir synlig eller vid ett klick. Klickhändelser kan anpassas för att tillämpas på vissa element-ID:n eller klasser genom att du anger en väljare. Du kan läsa in mallen genom `type="adobeanalytics"` att lägga till den i taggen amp-analytics.

I följande kodexempel har två utlösare definierats: `pageLoad` och `click`. Utlösaren aktiveras när dokumentet blir synligt och innehåller den `pageLoad` variabel som definieras i `pageName` `vars` avsnittet. Den andra utlösaren `click` utlöses när någon klickar på en knapp. `eVar1` är inställd för den här händelsen med värdet `button clicked`.

```html
<amp-analytics type="adobeanalytics">
  <script type="application/json">
    {
      "requests": {
        "myClick": "${click}&v1=${eVar1}",
      },
      "vars": {
        "host": "example.sc.omtrdc.net",
        "reportSuites": "reportSuiteID",
        "pageName": "Adobe Analytics Using amp-analytics tag"
      },
      "triggers": {
        "pageLoad": {
          "on": "visible",
          "request": "pageView"
        },
        "click": {
          "on": "click",
          "selector": "button",
          "request": "myClick",
          "vars": {
            "eVar1": "button clicked"
          }
        }
      }
    }
  </script>
</amp-analytics>
```

I `click` utlösaren kan du ange en väljare som ser till att när någon klickar på det specifika DOM-elementet (i det här fallet en knapp), utlöses `buttonClick` begäran och ställs in automatiskt för att ange den här träffen som ett länkspårningsanrop.

Dessutom har stöd för ett antal variabelersättningar så att AMP kan tillhandahålla datavärden som man känner till. `amp-analytics` Mer information finns i [variabler som stöds i](https://github.com/ampproject/amphtml/blob/master/extensions/amp-analytics/analytics-vars.md) amp-analytics på GitHub.

> [!NOTE] Bildbegäranden som skickas till Adobe med den här metoden innehåller inte data för många standardrapporter (till exempel webbläsare, skärmstorlek eller referent). Om du vill ta med den här informationen i träffar kontrollerar du att de ingår i frågesträngen för bildbegäran. Mer information finns i [Frågeparametrar](../validate/query-parameters.md) för datainsamling.

Adobe identifierar besökare med en inbyggd AMP-funktion och ställer in cookien `adobe_amp_id`. Detta besökar-ID är unikt för alla andra ID:n som anges av Adobe Analytics (till exempel `s_vi` cookie). Adobe Experience Cloud ID Service stöds inte med den här implementeringsmetoden.

> [!NOTE] AMP använder CDN:er för att leverera innehåll. Den är uppbyggd för att räkna olika unika besökare för varje CDN som en besökare hämtar innehåll från, vilket kan generera ett unikt antal besökare.

Vi rekommenderar att du använder en separat rapportserie för AMP-sidor på grund av hur AMP identifierar unika besökare.

Den här lösningen kräver att den spårningsserver som du anger i egenskapen `host` matchar spårningsservern på huvudplatsen, så att de befintliga sekretesspolicykontrollerna respekteras. I annat fall skapar du en separat integritetspolicy för sidor med AMP.

## Metod 2: Använd taggen amp-analytics med mallen&quot;adobeanalytics_nativeConfig&quot;

Taggen är enklare att implementera eftersom den använder samma taggmetod som du använder på dina vanliga webbsidor. `"adobeanalytics_nativeConfig"` Lägg till följande i din `amp-analytics` tagg:

```html
<amp-analytics type="adobeanalytics_nativeConfig">
  <script type="application/json">
    {
      "requests": {
        "base": "https://${host}",
        "iframeMessage": "${base}/stats.html?campaign=${queryParam(campaign)}&pageURL=${ampdocUrl}&ref=${documentReferrer}"
      },
      "vars": {
        "host": "example.sc.omtrdc.net"
      },
      "extraUrlParams": {
      "pageName": "Example AMP page",
      "v1": "eVar1 example value"
      }
    }
 </script>
</amp-analytics>
```

En HTML-sida på dina webbservrar krävs också:

```html
<html>
  <head>
    <title>Stats Example</title>
    <script language="JavaScript" type="text/javascript" src="VisitorAPI.js"></script>
    <script language="JavaScript" type="text/javascript" src="AppMeasurement.js"></script>
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
      s.visitorNamespace = s_visitorNamespace;
      s.visitor = visitor;
      s.pageName = s.Util.getQueryParam("pageName");
      s.eVar1 = s.Util.getQueryParam("v1");
      s.campaign = s.Util.getQueryParam("campaign");
      s.pageURL = s.Util.getQueryParam("pageURL");
      s.referrer = s.Util.getQueryParam("ref");
      s.t();
    </script>
  </body>
</html>
```

Den här metoden skickar data till en verktygswebbsida via frågesträngsparametrar som har lagts till i parametern request `iframeMessage` . Dessa frågesträngsparametrar kan namnges precis som du vill, förutsatt att din `stats.html` sida har konfigurerats för att samla in data från dem.

I mallen läggs också frågesträngsparametrar till baserat på de variabler som listas i avsnittet i `"adobeanalytics_nativeConfig"` `extraUrlParams` taggen amp-analytics. I ovanstående exempel inkluderas parametrarna `pageName` och `v1` .

> [!IMPORTANT] Din `stats.html` sida måste ligga på en separat underdomän från den domän som AMP-servern finns på. AMP-ramverket tillåter inte iframes från samma underdomän som själva AMP-sidan finns på. Om din AMP till exempel ligger på `amp.example.com`en värdserver, kan du lägga din `stats.html` sida på en separat underdomän, till exempel `ampmetrics.example.com`.

Om en användare väljer den här metoden och inte vill följa spårningen på din primära plats, avanmäls de också från spårning på alla AMP:er. Att använda den här verktygssidan innebär också att AMP kan stödja Adobe Experience Cloud ID-tjänsten. Det krävs ingen separat rapportserie.

Länkspårning och videospårning kan inte användas med den här metoden. Taggen `iframeMessage` i AMP kan bara läsas in en gång per sida, så du kan inte skicka några andra bildbegäranden när bildrutan har lästs in. Den här metoden kräver också fler bearbetningsresurser som kan påverka rullningsprestanda. Den här metoden påverkar inte sidinläsningstiden eftersom alla resurser läses in asynkront.

## Vanliga frågor

**Är videospårning tillgängligt för båda metoderna?**

Nej. AMP-standarden stöder bara utlösare för &quot;visible&quot;, &quot;click&quot; och &quot;timer&quot;. Den stöder ännu inte explicita utlösare för videospårning som `amp-analytics` -taggen kan lyssna på. Mallen kan dessutom bara läsas in en gång, så efterföljande bildbegäranden efter att en sida har lästs in är inte möjliga. `"adobeanalytics_nativeConfig"`

**Hur kan jag skilja AMP-besökare från andra i mina data?**

För alla AMP-sidor samlar [!UICONTROL JavaScript Version] dimensionen in ett värde som liknar `AMP vX.X`. Du kan också ställa in en anpassad dimension på AMP så att du kan segmentera dessa besökare.

**Hur skiljer sig den här implementeringsmetoden från Facebook Instant Articles?**

Direktartiklar på Facebook stöder en lösning som liknar `"adobeanalytics_nativeConfig"` metoden. Sidan `stats.html` för den här metoden kan tillgodose analysbehoven för både AMP och FIA samtidigt. Mer information om hur du implementerar spårning på FIA finns i [Direktartiklar](fb-instant-articles.md)på Facebook.
