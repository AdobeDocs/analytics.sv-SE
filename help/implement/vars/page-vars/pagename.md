---
title: pageName
description: Namnet på sidan på webbplatsen.
translation-type: tm+mt
source-git-commit: c7d596be4f70c820039725be6a5fddc8572156d9

---


# pageName

Variabeln lagrar vanligtvis namnet på en viss sida `pageName` . Det är praktiskt att avgöra vilka enskilda sidor som är mest populära. Den här variabeln fyller i dimensionen &quot;Sidnamn&quot;.

> [!NOTE] Den här dimensionen tas alltid bort från länkspårningsanrop. Om du vill se sidnamnet där en länk spårades bör du överväga att kopiera variabeln till en eVar.

Om den här variabeln inte definieras för ett visst sidspårningsanrop används `pageURL` variabeln i stället.

## Sidnamn i Adobe Experience Platform Launch

Du kan ange sidnamn antingen när du konfigurerar Analytics-tillägget (globala variabler) eller under regler.

1. Logga in på [launch.adobe.com](https://launch.adobe.com) med inloggningsuppgifterna för ditt AdobeID.
2. Klicka på önskad egenskap.
3. Gå till [!UICONTROL Rules] fliken och klicka sedan på önskad regel (eller skapa en regel).
4. Under [!UICONTROL Actions]klickar du på en befintlig [!UICONTROL Adobe Analytics - Set Variables] åtgärd eller på +-ikonen.
5. Ställ in listrutan till Adobe Analytics och [!UICONTROL Extension] till [!UICONTROL Action Type] [!UICONTROL Set Variables].
6. Leta rätt på [!UICONTROL Page name] avsnittet.

Du kan ange sidnamn till valfritt strängvärde, inklusive dataelement.

## s.pageName i AppMeasurement and Launch custom code editor

Variabeln är en sträng som vanligtvis innehåller sidans namn. `s.pageName` Den har ett maxvärde på 100 byte. längre värden trunkeras. Den här trunkeringen innehåller instanser där den återgår till `pageURL` om variabeln är tom.

```js
// Set page name to a static value
s.pageName = "Example page name";

// Set page name to the page's title
s.pageName = window.document.title;
```
