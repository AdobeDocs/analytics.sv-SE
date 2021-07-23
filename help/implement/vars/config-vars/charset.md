---
title: charSet
description: Variabeln charSet avgör vilken kodning Adobe använder för att analysera bildbegäran.
exl-id: 2a2660c6-809d-4b33-a846-01e49dd99c7f
source-git-commit: 3986084eaab81842b6ea0dbabc7bdb78e39f887a
workflow-type: tm+mt
source-wordcount: '189'
ht-degree: 1%

---

# charSet

Variabeln charSet används av Adobe för att konvertera inkommande data till UTF-8 för lagring och rapportering från Analytics. De flesta webbplatser behöver inte ange den här variabeln.

Ange bara den här variabeln om du ser förvrängda värden ([mojibake](https://en.wikipedia.org/wiki/Mojibake)) i rapporter. Du kan ange den här variabeln sida för sida om webbplatsen använder olika kodningar på olika sidor.

## Teckenuppsättning i Adobe Experience Platform

Teckenuppsättning är ett fält under dragspelet [!UICONTROL General] när du konfigurerar Adobe Analytics-tillägget.

1. Gå till `experience.adobe.com` och logga in när du uppmanas till det.
1. Välj [!UICONTROL Launch / Data Collection].
1. Klicka på [!UICONTROL Go to Launch / Data Collection] och välj sedan [!UICONTROL Tags].
1. Klicka på önskad egenskap.
1. Gå till fliken [!UICONTROL Extensions] och klicka sedan på knappen [!UICONTROL Configure] under Adobe Analytics.
1. Expandera dragspelet [!UICONTROL General], som visar fältet [!UICONTROL Character Set].

Du kan antingen använda en förinställd teckenuppsättning eller en anpassad teckenuppsättning. Undvik att ändra värdet från `UTF-8` om du inte ser förvrängda värden i rapporter.

## s.charSet i AppMeasurement och anpassad kodredigerare

Variabeln `charSet` är en sträng. Om du har förvrängda värden i Adobe Analytics anger du den här variabeln till samma värde som HTML-taggen `<meta charset="">` på din webbplats.

```js
s.charSet = "UTF-8";
```
