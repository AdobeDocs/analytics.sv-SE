---
title: charSet
description: Variabeln charSet avgör vilken kodning Adobe använder för att analysera din bildbegäran.
translation-type: tm+mt
source-git-commit: f769da139d9890fd736a9b277934b11aa131e166

---


# charSet

Variabeln charSet används av Adobe för att konvertera inkommande data till UTF-8 för lagring och rapportering från Analytics. Om din webbplats använder en annan teckenuppsättning än UTF-8 tillåter den här variabeln att dina data kodas korrekt av Adobe. Den här variabeln kan ställas in sida för sida om webbplatsen använder olika kodningar på olika sidor.

## Teckenuppsättning i Adobe Experience Platform Launch

Teckenuppsättning är ett fält under [!UICONTROL General] dragspelet när Adobe Analytics-tillägget konfigureras.

1. Logga in på [launch.adobe.com](https://launch.adobe.com) med inloggningsuppgifterna för ditt AdobeID.
2. Klicka på önskad egenskap.
3. Gå till [!UICONTROL Extensions] fliken och klicka sedan på [!UICONTROL Configure] knappen under Adobe Analytics.
4. Expandera dragspelsfliken, som visar [!UICONTROL General] [!UICONTROL Character Set] fältet.

Du kan antingen använda en förinställd teckenuppsättning eller en anpassad teckenuppsättning. Detta värde bör matcha teckenkodningen på din webbplats. De flesta webbplatser använder `UTF-8`.

## s.charSet i AppMeasurement and Launch custom code editor

Variabeln `charSet` är en sträng. Ange den här variabeln till samma värde som HTML- `<meta charset="">` taggen på din plats.

```js
s.charSet = "UTF-8";
```
