---
title: charSet
description: Variabeln charSet avgör vilken kodning Adobe använder för att analysera din bildbegäran.
translation-type: tm+mt
source-git-commit: 70410af433f540764b71bd29a81ff9d8210cb95c
workflow-type: tm+mt
source-wordcount: '190'
ht-degree: 2%

---


# charSet

Variabeln charSet används av Adobe för att konvertera inkommande data till UTF-8 för lagring och rapportering från Analytics. De flesta webbplatser behöver inte ange den här variabeln.

Ange bara den här variabeln om du ser förvrängda värden ([mojibake](https://en.wikipedia.org/wiki/Mojibake)) i rapporter. Du kan ange den här variabeln sida för sida om webbplatsen använder olika kodningar på olika sidor.

## Teckenuppsättning i Adobe Experience Platform Launch

Teckenuppsättning är ett fält under [!UICONTROL General] dragspelet när Adobe Analytics-tillägget konfigureras.

1. Logga in på [launch.adobe.com](https://launch.adobe.com) med inloggningsuppgifterna för ditt AdobeID.
2. Klicka på önskad egenskap.
3. Gå till [!UICONTROL Extensions] fliken och klicka sedan på [!UICONTROL Configure] knappen under Adobe Analytics.
4. Expandera dragspelsfliken, som visar [!UICONTROL General] [!UICONTROL Character Set] fältet.

Du kan antingen använda en förinställd teckenuppsättning eller en anpassad teckenuppsättning. Undvik att ändra värdet från `UTF-8` om du inte ser förvrängda värden i rapporter.

## s.charSet i AppMeasurement and Launch custom code editor

Variabeln `charSet` är en sträng. Om du har blandat ihop värden i Adobe Analytics anger du den här variabeln till samma värde som HTML- `<meta charset="">` taggen på din webbplats.

```js
s.charSet = "UTF-8";
```
