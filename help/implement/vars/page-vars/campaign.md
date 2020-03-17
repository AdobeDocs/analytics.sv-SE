---
title: kampanj
description: Fyll i dimensionen 'Spårningskod'.
translation-type: tm+mt
source-git-commit: c5a60bc9756af2742740dbc6a26a081f55ee3235

---


# kampanj

Variabeln är avsedd för att samla in spårningskoder på din webbplats. `campaign` I tidigare versioner av Adobe Analytics hade programmet en speciell behandling där det kunde användas som en uppdelning på de flesta dimensioner. I den aktuella versionen av Adobe Analytics fungerar den likadant som en eVar.

Den här variabeln fyller i dimensionen &#39;Tracking Code&#39;.

## Campaign i Adobe Experience Platform Launch

Du kan ange kampanj antingen när Analytics-tillägget (globala variabler) konfigureras eller under regler.

1. Logga in på [launch.adobe.com](https://launch.adobe.com) med inloggningsuppgifterna för ditt AdobeID.
2. Klicka på önskad egenskap.
3. Gå till [!UICONTROL Rules] fliken och klicka sedan på önskad regel (eller skapa en regel).
4. Under [!UICONTROL Actions]klickar du på en befintlig [!UICONTROL Adobe Analytics - Set Variables] åtgärd eller på +-ikonen.
5. Ställ in listrutan till Adobe Analytics och [!UICONTROL Extension] till [!UICONTROL Action Type] [!UICONTROL Set Variables].
6. Leta rätt på [!UICONTROL Campaign] avsnittet.

Du kan ställa in kampanjen på ett värde eller en frågesträngsparameter.

## s.campaign i AppMeasurement and Launch custom code editor

Variabeln är en sträng som vanligtvis innehåller en spårningskod som används i marknadsföringsaktiviteter. `s.campaign` Dess största längd är 255 byte. värden som är längre än 100 byte trunkeras automatiskt när de skickas till Adobe.

```js
// Set the campaign variable to a static value
s.campaign = "abc123";

// Collect the cid query string parameter value from the URL
// https://example.com?cid=abc123
s.campaign = s.Util.getQueryParam("cid");
```
