---
title: Implementera med AMP
description: Implementera Adobe Analytics på AMP-sidor.
feature: Implementation Basics
exl-id: 51a2662e-2a24-48f1-b17a-d1e1a57a394b
role: Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '917'
ht-degree: 0%

---

# Implementera med AMP

[AMP](https://amp.dev) är ett ramverk med öppen källkod som ger ett enkelt sätt att skapa snabba och smidiga webbsidor.

Eftersom Adobe Analytics använder ett JavaScript-bibliotek för att kompilera och skicka en bildbegäran, krävs justeringar i implementeringen för att skicka data till Adobe på sidor med AMP.

## Bestäm vilken metod som ska användas för att implementera Adobe Analytics på sidor med AMP

Adobe har skapat två metoder för att implementera Adobe Analytics på sidor med AMP. Båda använder `<amp-analytics>` HTML-tagg. Se [amp-analytics](https://amp.dev/documentation/components/amp-analytics) i AMP:s dokumentation för mer information.

* **Använd `"adobeanalytics"` mall**: Skapa Analytics-begäran direkt på sidan
* **Använd `"analytics_nativeConfig"` mall**: Använd en iframe som innehåller samma AppMeasurement kod som du distribuerar på din normala plats

I följande tabell jämförs dessa två metoder:

|   | **`"adobeanalytics"`mall** | **`"adobeanalytics_nativeConfig"`mall** |
|---|---|---|
| Besöks-/besöksantal i befintlig rapportserie | Hög uppblåsning | Minimal uppblåsning |
| Använd en separat rapportserie | Rekommenderas | Inte nödvändigt |
| Nya kontra återkommande besökare | Stöds inte | Stöds |
| Tjänst för besökar-ID | Stöds inte | Stöds |
| Video- och länkspårning | Delvis stöd | Stöds ännu inte |
| Svårighet att genomföra | Svårt | relativt enkelt |
| Adobe Experience Cloud-integreringar | Stöds inte | Delvis stöd |

Väg in proffsen och ikonerna så att du kan välja den bästa implementeringsmetoden för din organisation.

>[!WARNING]
>
>Använd inte båda `"adobeanalytics"` och `"adobeanalytics_nativeConfig"` -mallar på samma sida med AMP. Om du försöker göra det kan du generera fel i webbläsarkonsolen och dubbelräkna besökare.

## Metod 1: Använd `<amp-analytics>` -taggen med `"adobeanalytics"` mall

The `"adobeanalytics"` spårningsmallen använder `<amp-analytics>` HTML-tagg för att skapa en spårningsbegäran direkt. Du kan ange träffförfrågningar som startar vid specifika sidhändelser, som att sidan blir synlig eller vid ett klick. Klickhändelser kan anpassas för att tillämpas på vissa element-ID:n eller klasser genom att du anger en väljare. Du kan läsa in mallen genom att lägga till `type="adobeanalytics"` till taggen amp-analytics.

I följande kodexempel har två utlösare definierats: `pageLoad` och `click`. The `pageLoad` utlösaren aktiveras när dokumentet blir synligt och innehåller `pageName` variabeln enligt definitionen i `vars` -avsnitt. Den andra utlösaren `click` aktiveras när någon klickar på en knapp. The `eVar1` variabeln är inställd för den här händelsen med värdet `button clicked`.

```html
<amp-analytics type="adobeanalytics">
  <script type="application/json">
    {
      "requests": {
        "myClick": "${click}&v1=${eVar1}",
      },
      "vars": {
        "host": "example.data.adobedc.net",
        "reportSuites": "reportSuiteID1,reportSuiteID2",
        "pageName": "Adobe Analytics Using amp-analytics tag"
      },
      "triggers": {
        "pageLoad": {
          "on": "visible",
          "request": "pageview"
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

The `<amp-analytics>` -taggen har stöd för variabelersättningar så att AMP kan tillhandahålla datavärden som den känner till. Se [variabler som stöds i `amp-analytics`](https://github.com/ampproject/amphtml/blob/main/extensions/amp-analytics/analytics-vars.md) på GitHub om du vill ha mer information.

>[!NOTE]
>
>Bildbegäranden som skickas till Adobe med den här metoden innehåller inte data för många standardrapporter (till exempel webbläsare, skärmstorlek eller referent). Om du vill ta med den här informationen i träffar kontrollerar du att de ingår i frågesträngen för bildbegäran. Se [Frågeparametrar för datainsamling](../validate/query-parameters.md) om du vill ha en fullständig lista över bildförfrågningsparametrar och tillhörande variabler.

Adobe identifierar besökare med en inbyggd AMP-funktion och ställer in cookien `adobe_amp_id`. Detta besökar-ID är unikt för alla andra ID:n som angetts av Adobe Analytics. En unik besökare räknas för varje CDN som en besökare hämtar innehåll från, vilket kan generera ett unikt besökarantal. Vi rekommenderar att du använder en separat rapportserie för AMP-sidor eftersom AMP identifierar unika besökare. Adobe Experience Cloud ID-tjänsten stöds inte.

Den här lösningen kräver att spårningsservern som du anger finns i `host` egenskapen matchar spårningsservern på huvudwebbplatsen så att de befintliga sekretesspolicykontrollerna respekteras. I annat fall skapar du en separat integritetspolicy för sidor med AMP.

## Metod 2: Använd `<amp-analytics>` -taggen med `"adobeanalytics_nativeConfig"` mall

The `"adobeanalytics_nativeConfig"` -taggen är enklare att implementera eftersom den använder samma taggningsmetod som du använder på dina vanliga webbsidor. Lägg till följande i `amp-analytics` tagg:

```html
<amp-analytics type="adobeanalytics_nativeConfig">
  <script type="application/json">
    {
      "requests": {
        "base": "https://${host}",
        "iframeMessage": "${base}/stats.html?campaign=${queryParam(campaign)}&pageURL=${ampdocUrl}&ref=${documentReferrer}"
      },
      "vars": {
        "host": "example.data.adobedc.net"
      },
      "extraUrlParams": {
      "pageName": "Example AMP page",
      "v1": "eVar1 example value"
      }
    }
 </script>
</amp-analytics>
```

En HTML-sida på webbservrarna krävs också:

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
      var s_account = "examplersid1,examplersid2";
      var s_trackingServer = "example.data.adobedc.net";
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

Det här arbetssättet skickar data till en verktygswebbsida via frågesträngsparametrar som har lagts till i `iframeMessage` request-parameter. Dessa frågesträngsparametrar kan namnges precis som du vill, så länge som du `stats.html` sidan har konfigurerats för att samla in data från dem.

The `"adobeanalytics_nativeConfig"` -mallen lägger också till frågesträngsparametrar som baseras på variablerna som anges i `extraUrlParams` i `<amp-analytics>` -tagg. I exemplet ovan är `pageName` och `v1` parametrar ingår.

>[!IMPORTANT]
>
>Dina `stats.html` sidan måste finnas på en separat underdomän från den domän där AMP finns. AMP-ramverket tillåter inte iframes från samma underdomän som själva AMP-sidan finns på. Om din AMP till exempel finns på `amp.example.com`, är värd för `stats.html` sida på en separat underdomän som `ampmetrics.example.com`.

Om en användare väljer den här metoden och inte vill följa spårningen på din primära plats, avanmäls de också från spårning på alla AMP:er. Att använda den här verktygssidan innebär också att AMP kan stödja Adobe Experience Cloud ID-tjänsten. Det krävs ingen separat rapportserie.

Länkspårning och videospårning kan inte användas med den här metoden. The `iframeMessage` -taggen i AMP kan bara läsas in en gång per sida, så du kan inte skicka några andra bildbegäranden när bildrutan har lästs in. Den här metoden kräver också fler bearbetningsresurser som kan påverka rullningsprestanda. Den här metoden påverkar inte sidinläsningstiden eftersom alla resurser läses in asynkront.

## Vanliga frågor och svar

**Hur kan jag skilja AMP-besökare från andra i mina data?**

För alla AMP-sidor är [!UICONTROL JavaScript Version] dimension samlar in ett värde som liknar `AMP vX.X`. Du kan också ställa in en anpassad dimension på AMP så att du kan segmentera dessa besökare.

**Hur skiljer sig den här implementeringsmetoden från Facebook Instant Articles?**

Facebook Instant Articles har stöd för en liknande lösning som `"adobeanalytics_nativeConfig"` -metod. The `stats.html` sidan för den här metoden kan tillgodose era analysbehov för både AMP och FIA samtidigt. Mer information om hur du implementerar spårning för FIA finns i [Facebook Instant Articles](fb-instant-articles.md).
