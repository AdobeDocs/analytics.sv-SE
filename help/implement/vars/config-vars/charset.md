---
title: charSet
description: Variabeln charSet avgör vilken kodning Adobe använder för att analysera bildbegäran.
feature: Variables
exl-id: 2a2660c6-809d-4b33-a846-01e49dd99c7f
source-git-commit: b3c74782ef6183fa63674b98e4c0fc39fc09441b
workflow-type: tm+mt
source-wordcount: '192'
ht-degree: 1%

---

# charSet

Variabeln charSet används av Adobe för att konvertera inkommande data till UTF-8 för lagring och rapportering från Analytics. De flesta webbplatser behöver inte ange den här variabeln.

Ange bara den här variabeln om du ser förvrängda värden ([mojibake](https://en.wikipedia.org/wiki/Mojibake)) i rapporter. Du kan ange den här variabeln sida för sida om webbplatsen använder olika kodningar på olika sidor.

## Teckenuppsättning i Adobe Experience Platform

Teckenuppsättning är ett fält under [!UICONTROL General] när du konfigurerar Adobe Analytics-tillägget.

1. Logga in på [Användargränssnitt för datainsamling](https://experience.adobe.com/data-collection) med inloggningsuppgifterna för ditt AdobeID.
1. Klicka på önskad egenskap.
1. Gå till [!UICONTROL Extensions] klickar du på [!UICONTROL Configure] under Adobe Analytics.
1. Expandera [!UICONTROL General] dragspelspanel, som visar [!UICONTROL Character Set] fält.

Du kan antingen använda en förinställd teckenuppsättning eller en anpassad teckenuppsättning. Undvik att ändra värdet från `UTF-8` om du inte ser förvrängda värden i rapporter.

## s.charSet i AppMeasurement och anpassad kodredigerare

The `charSet` variabeln är en sträng. Om du har förvrängda värden i Adobe Analytics anger du variabeln till samma värde som `<meta charset="">` HTML-tagg på din webbplats.

```js
s.charSet = "UTF-8";
```
