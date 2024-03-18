---
title: server
description: Fyll i dimensionen Servrar.
feature: Variables
exl-id: 7904c3c2-9a91-497e-89d0-9eed9ae7a902
role: Admin, Developer
source-git-commit: 5ef92db2f5edb5fded497dddedd56abd49d8a019
workflow-type: tm+mt
source-wordcount: '171'
ht-degree: 0%

---

# server

The `server` variabeln lagrar vanligtvis webbplatsens värdnamn. Det används ofta i rapportsviter som innehåller data från flera domäner. Den är funktionellt identisk med en prop.

## Server som använder Web SDK

Servern är mappad till följande variabler:

* [XDM-objekt](/help/implement/aep-edge/xdm-var-mapping.md): `xdm.web.webPageDetails.server`
* [Dataobjekt](/help/implement/aep-edge/data-var-mapping.md): `data.__adobe.analytics.server`

## Server som använder Adobe Analytics-tillägget

Du kan ange server antingen när Analytics-tillägget (globala variabler) konfigureras eller enligt regler.

1. Logga in på [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) med inloggningsuppgifterna för ditt AdobeID.
2. Klicka på den önskade taggegenskapen.
3. Gå till [!UICONTROL Rules] och sedan klicka på önskad regel (eller skapa en regel).
4. Under [!UICONTROL Actions]klickar du på en befintlig [!UICONTROL Adobe Analytics - Set Variables] eller klicka på +-ikonen.
5. Ange [!UICONTROL Extension] nedrullningsbar lista till Adobe Analytics och [!UICONTROL Action Type] till [!UICONTROL Set Variables].
6. Leta reda på [!UICONTROL Server] -avsnitt.

Du kan ställa in servern på valfritt strängvärde eller dataelement.

## s.server i AppMeasurementet och den anpassade kodredigeraren för Analytics-tillägget

The `s.server` variabeln är en sträng som vanligtvis innehåller värdnamnet för platsen. Det har ett maxvärde på 100 byte. Ju längre värde, desto trunkeras.

```js
// Set the server variable to a static string
s.server = "Example server";

// Automatically set the server variable to the site's hostname
s.server = window.location.hostname;
```
