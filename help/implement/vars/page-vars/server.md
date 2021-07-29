---
title: server
description: Fyll i dimensionen Servrar.
exl-id: 7904c3c2-9a91-497e-89d0-9eed9ae7a902
source-git-commit: 1a49c2a6d90fc670bd0646d6d40738a87b74b8eb
workflow-type: tm+mt
source-wordcount: '151'
ht-degree: 1%

---

# server

Variabeln `server` lagrar vanligtvis webbplatsens värdnamn. Det används ofta i rapportsviter som innehåller data från flera domäner. Den är funktionellt identisk med en prop.

## Server som använder taggar i Adobe Experience Platform

Du kan ange server antingen när Analytics-tillägget (globala variabler) konfigureras eller enligt regler.

1. Logga in på [användargränssnittet för datainsamling](https://experience.adobe.com/data-collection) med inloggningsuppgifterna för ditt Adobe-ID.
2. Klicka på önskad egenskap.
3. Gå till fliken [!UICONTROL Rules] och klicka sedan på önskad regel (eller skapa en regel).
4. Klicka på en befintlig [!UICONTROL Adobe Analytics - Set Variables]-åtgärd under [!UICONTROL Actions] eller klicka på +-ikonen.
5. Ange listrutan [!UICONTROL Extension] till Adobe Analytics och [!UICONTROL Action Type] till [!UICONTROL Set Variables].
6. Gå till avsnittet [!UICONTROL Server].

Du kan ställa in servern på valfritt strängvärde eller dataelement.

## s.server i AppMeasurement och anpassad kodredigerare

Variabeln `s.server` är en sträng som vanligtvis innehåller värdnamnet för platsen. Den har ett maxvärde på 100 byte. längre värden trunkeras.

```js
// Set the server variable to a static string
s.server = "Example server";

// Automatically set the server variable to the site's hostname
s.server = window.location.hostname;
```
