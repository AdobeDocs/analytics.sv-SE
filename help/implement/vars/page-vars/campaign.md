---
title: kampanj
description: Fyll i dimensionen 'Spårningskod'.
exl-id: 2278d2b8-8d60-4634-a176-f027a237bc12
source-git-commit: 1a49c2a6d90fc670bd0646d6d40738a87b74b8eb
workflow-type: tm+mt
source-wordcount: '183'
ht-degree: 1%

---

# kampanj

Variabeln `campaign` är dedikerad till att samla in spårningskoder på din webbplats. I tidigare versioner av Adobe Analytics hade programmet en speciell behandling där det kunde användas som en uppdelning på de flesta dimensioner. I den aktuella versionen av Adobe Analytics fungerar den likadant som en eVar.

Den här variabeln fyller i dimensionen &#39;Tracking Code&#39;.

## Campaign using tags in Adobe Experience Platform

Du kan ange kampanj antingen när Analytics-tillägget (globala variabler) konfigureras eller under regler.

1. Logga in på [användargränssnittet för datainsamling](https://experience.adobe.com/data-collection) med inloggningsuppgifterna för ditt Adobe-ID.
2. Klicka på önskad egenskap.
3. Gå till fliken [!UICONTROL Rules] och klicka sedan på önskad regel (eller skapa en regel).
4. Klicka på en befintlig [!UICONTROL Adobe Analytics - Set Variables]-åtgärd under [!UICONTROL Actions] eller klicka på +-ikonen.
5. Ange listrutan [!UICONTROL Extension] till Adobe Analytics och [!UICONTROL Action Type] till [!UICONTROL Set Variables].
6. Gå till avsnittet [!UICONTROL Campaign].

Du kan ställa in kampanjen på ett värde eller en frågesträngsparameter.

## s.campaign i AppMeasurement och anpassad kodredigerare

Variabeln `s.campaign` är en sträng som vanligtvis innehåller en spårningskod som används i marknadsföringsaktiviteter. Dess största längd är 255 byte. värden som är längre än 255 byte trunkeras automatiskt när de skickas till Adobe.

```js
// Set the campaign variable to a static value
s.campaign = "abc123";

// Collect the cid query string parameter value from the URL
// https://example.com?cid=abc123
s.campaign = s.Util.getQueryParam("cid");
```
