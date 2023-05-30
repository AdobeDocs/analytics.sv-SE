---
title: charSet
description: Variabeln charSet avgör vilken kodning Adobe använder för att analysera bildbegäran.
feature: Variables
exl-id: 2a2660c6-809d-4b33-a846-01e49dd99c7f
source-git-commit: ef82c34f97a0c8172f097b83b521860a1897c82c
workflow-type: tm+mt
source-wordcount: '224'
ht-degree: 0%

---

# charSet

The `charSet` variabeln används av Adobe för att konvertera inkommande data till UTF-8 för lagring och rapportering från Analytics. De flesta webbplatser behöver inte ange den här variabeln.

Ange bara den här variabeln om du ser förvrängda värden ([mojibake](https://en.wikipedia.org/wiki/Mojibake)) i rapporter. Du kan ange den här variabeln sida för sida om webbplatsen använder olika kodningar på olika sidor.

## Teckenuppsättning i Web SDK

Web SDK har för närvarande bara stöd för UTF-8, och har inga alternativ för att ändra kodning.

## Teckenuppsättning i Adobe Analytics-tillägget

Teckenuppsättning är ett fält under [!UICONTROL General] när du konfigurerar Adobe Analytics-tillägget i Adobe Experience Platform Data Collection.

1. Logga in på [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) med inloggningsuppgifterna för ditt AdobeID.
1. Klicka på den önskade taggegenskapen.
1. Gå till [!UICONTROL Extensions] klickar du på **[!UICONTROL Configure]** under Adobe Analytics.
1. Expandera [!UICONTROL General] dragspelspanel, som visar [!UICONTROL Character Set] fält.

Du kan antingen använda en förinställd teckenuppsättning eller en anpassad teckenuppsättning. Undvik att ändra värdet från `UTF-8` om du inte ser förvrängda värden i rapporter.

## s.charSet i AppMeasurement och den anpassade kodredigeraren för Analytics-tillägget

The `charSet` variabeln är en sträng. Om du har förvrängda värden i Adobe Analytics anger du variabeln till samma värde som `<meta charset="">` HTML-tagg på din webbplats.

```js
s.charSet = "UTF-8";
```
