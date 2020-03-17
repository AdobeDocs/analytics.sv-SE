---
title: hänvisare
description: Åsidosätt den automatiskt insamlade referenten för en träff.
translation-type: tm+mt
source-git-commit: c7d596be4f70c820039725be6a5fddc8572156d9

---


# hänvisare

Variabeln `referrer` åsidosätter den automatiskt insamlade referenten i rapporter. Den här variabeln är användbar i situationer där referenten kan förloras, till exempel vid omdirigeringar eller när besökaren tillfälligt vidarebefordras till en betalningsbehandlare. Den här variabeln används för att fylla i dimensionerna Referer och Refererande domän.

## Referent i Adobe Experience Platform Launch

Du kan ange referent antingen när Analytics-tillägget (globala variabler) konfigureras eller under regler.

1. Logga in på [launch.adobe.com](https://launch.adobe.com) med inloggningsuppgifterna för ditt AdobeID.
2. Klicka på önskad egenskap.
3. Gå till [!UICONTROL Rules] fliken och klicka sedan på önskad regel (eller skapa en regel).
4. Under [!UICONTROL Actions]klickar du på en befintlig [!UICONTROL Adobe Analytics - Set Variables] åtgärd eller på +-ikonen.
5. Ställ in listrutan till Adobe Analytics och [!UICONTROL Extension] till [!UICONTROL Action Type] [!UICONTROL Set Variables].
6. Leta rätt på [!UICONTROL Referrer] avsnittet.

Du kan ställa in referenten på valfritt strängvärde, inklusive dataelement.

## s.referrer i AppMeasurement och Launch, anpassad kodredigerare

Variabeln `s.referrer` är en sträng som innehåller URL:en för föregående sida. Denna variabel kan lagra högst 255 byte. värden som är större än 255 byte trunkeras. AppMeasurement anger automatiskt variabeln till `document.referrer`; du behöver inte ange den här variabeln om du inte vill åsidosätta det automatiskt insamlade värdet.

```js
s.referrer = "https://example.com";
```

Undvik att ställa in den här variabeln på värden som inte är URL-adresser.

## Exempel

Många organisationer hanterar implementeringar kring omdirigeringar. Du kan använda [`getQueryParam`](../functions/util-getqueryparam.md) verktyget för att hämta en referens från URL-adressen om webbplatsen har plats för den. Kontrollera att du URL-kodar alla värden som ingår i frågesträngen.

```js
// Example if the URL is https://example.com?r=https%3A%2F%2Fexample.org
s.referrer = s.Util.getQueryParam("r");
```
