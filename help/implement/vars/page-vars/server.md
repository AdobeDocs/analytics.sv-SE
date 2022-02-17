---
title: server
description: Fyll i dimensionen Servrar.
feature: Variables
exl-id: 7904c3c2-9a91-497e-89d0-9eed9ae7a902
source-git-commit: b3c74782ef6183fa63674b98e4c0fc39fc09441b
workflow-type: tm+mt
source-wordcount: '151'
ht-degree: 1%

---

# server

The `server` variabeln lagrar vanligtvis webbplatsens värdnamn. Det används ofta i rapportsviter som innehåller data från flera domäner. Den är funktionellt identisk med en prop.

## Server som använder taggar i Adobe Experience Platform

Du kan ange server antingen när Analytics-tillägget (globala variabler) konfigureras eller enligt regler.

1. Logga in på [Användargränssnitt för datainsamling](https://experience.adobe.com/data-collection) med inloggningsuppgifterna för ditt AdobeID.
2. Klicka på önskad egenskap.
3. Gå till [!UICONTROL Rules] och sedan klicka på önskad regel (eller skapa en regel).
4. Under [!UICONTROL Actions]klickar du på en befintlig [!UICONTROL Adobe Analytics - Set Variables] eller klicka på +-ikonen.
5. Ange [!UICONTROL Extension] till Adobe Analytics och [!UICONTROL Action Type] till [!UICONTROL Set Variables].
6. Leta reda på [!UICONTROL Server] -avsnitt.

Du kan ställa in servern på valfritt strängvärde eller dataelement.

## s.server i AppMeasurement och anpassad kodredigerare

The `s.server` variabeln är en sträng som vanligtvis innehåller värdnamnet för platsen. Den har ett maxvärde på 100 byte. längre värden trunkeras.

```js
// Set the server variable to a static string
s.server = "Example server";

// Automatically set the server variable to the site's hostname
s.server = window.location.hostname;
```
