---
title: server
description: Fyll i dimensionen Servrar.
translation-type: tm+mt
source-git-commit: c7d596be4f70c820039725be6a5fddc8572156d9

---


# server

Variabeln lagrar vanligtvis webbplatsens värdnamn `server` . Det används ofta i rapportsviter som innehåller data från flera domäner. Den är funktionellt identisk med en prop.

## Server i Adobe Experience Platform Launch

Du kan ange server antingen när Analytics-tillägget (globala variabler) konfigureras eller enligt regler.

1. Logga in på [launch.adobe.com](https://launch.adobe.com) med inloggningsuppgifterna för ditt AdobeID.
2. Klicka på önskad egenskap.
3. Gå till [!UICONTROL Rules] fliken och klicka sedan på önskad regel (eller skapa en regel).
4. Under [!UICONTROL Actions]klickar du på en befintlig [!UICONTROL Adobe Analytics - Set Variables] åtgärd eller på +-ikonen.
5. Ställ in listrutan till Adobe Analytics och [!UICONTROL Extension] till [!UICONTROL Action Type] [!UICONTROL Set Variables].
6. Leta rätt på [!UICONTROL Server] avsnittet.

Du kan ställa in servern på valfritt strängvärde eller dataelement.

## s.server i den anpassade kodredigeraren AppMeasurement och Launch

Variabeln `s.server` är en sträng som vanligtvis innehåller värdnamnet för platsen. Den har ett maxvärde på 100 byte. längre värden trunkeras.

```js
// Set the server variable to a static string
s.server = "Example server";

// Automatically set the server variable to the site's hostname
s.server = window.location.hostname;
```
