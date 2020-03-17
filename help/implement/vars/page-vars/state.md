---
title: Läge
description: Fyll i rapporten om besökarstatus i Rapporter och analyser.
translation-type: tm+mt
source-git-commit: f75c6759feb6576017733f1aac5bff2e21d4b0af

---


# läge

> [!IMPORTANT] Den här variabeln har tagits bort och är inte en tillgänglig dimension i Analysis Workspace. Använd dimensionen &#39;USA&#39; i stället, som AppMeasurement automatiskt samlar in baserat på besökarens plats.

I tidigare versioner av Adobe Analytics användes variabeln när besökare fyllde i leveransinformation på `state` butikssajter. Den är funktionellt identisk med en prop, men är inte tillgänglig i Analysis Workspace.

## Tillstånd i Adobe Experience Platform Launch

Du kan ange tillstånd antingen när Analytics-tillägget (globala variabler) konfigureras eller under regler.

1. Logga in på [launch.adobe.com](https://launch.adobe.com) med inloggningsuppgifterna för ditt AdobeID.
2. Klicka på önskad egenskap.
3. Gå till [!UICONTROL Rules] fliken och klicka sedan på önskad regel (eller skapa en regel).
4. Under [!UICONTROL Actions]klickar du på en befintlig [!UICONTROL Adobe Analytics - Set Variables] åtgärd eller på +-ikonen.
5. Ställ in listrutan till Adobe Analytics och [!UICONTROL Extension] till [!UICONTROL Action Type] [!UICONTROL Set Variables].
6. Leta rätt på [!UICONTROL State] avsnittet.

Du kan ange tillstånd till valfritt strängvärde eller dataelement.

## s.state in AppMeasurement and Launch custom code editor

Variabeln `s.state` är en sträng som vanligtvis innehåller besökarens delstat eller provins. Fulla lägesnamn eller tvåbokstavskoder är båda giltiga. Den får innehålla högst 50 byte. längre värden trunkeras. Dess standardvärde är en tom sträng.

```js
s.state = "Utah";
```
