---
title: charSet
description: Variabeln charSet avgör vilken kodning Adobe använder för att analysera bildbegäran.
feature: Variables
exl-id: 2a2660c6-809d-4b33-a846-01e49dd99c7f
role: Admin, Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '221'
ht-degree: 0%

---

# charSet

Variabeln `charSet` används av Adobe för att konvertera inkommande data till UTF-8 för lagring och rapportering från Analytics. De flesta webbplatser behöver inte ange den här variabeln.

Ange bara den här variabeln om du ser förvrängda värden ([mojibake](https://en.wikipedia.org/wiki/Mojibake)) i rapporter. Du kan ange den här variabeln sida för sida om webbplatsen använder olika kodningar på olika sidor.

## Teckenuppsättning i Web SDK

Web SDK har för närvarande bara stöd för UTF-8, och har inga alternativ för att ändra kodning.

## Teckenuppsättning i Adobe Analytics-tillägget

Teckenuppsättning är ett fält under dragspelet [!UICONTROL General] när du konfigurerar Adobe Analytics-tillägget i Adobe Experience Platform Data Collection.

1. Logga in på [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) med dina inloggningsuppgifter för AdobeID.
1. Klicka på den önskade taggegenskapen.
1. Gå till fliken [!UICONTROL Extensions] och klicka sedan på knappen **[!UICONTROL Configure]** under Adobe Analytics.
1. Expandera dragspelsfliken [!UICONTROL General] som visar fältet [!UICONTROL Character Set].

Du kan antingen använda en förinställd teckenuppsättning eller en anpassad teckenuppsättning. Ändra inte värdet från `UTF-8` om du inte ser förvrängda värden i rapporter.

## s.charSet i AppMeasurementet och den anpassade kodredigeraren för Analytics-tillägget

Variabeln `charSet` är en sträng. Om du har förvrängt värden i Adobe Analytics anger du den här variabeln till samma värde som taggen `<meta charset="">` HTML på din webbplats.

```js
s.charSet = "UTF-8";
```
