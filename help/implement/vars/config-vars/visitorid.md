---
title: visitorID
description: Använd ett anpassat besökar-ID.
translation-type: tm+mt
source-git-commit: 979a95ca749a3e21c4ddf48ba2d2a95672938a20

---


# visitorID

Adobe använder flera olika metoder för att identifiera besökare på er webbplats. Variabeln `visitorID` åsidosätter alla andra metoder för besöksidentifiering.

> [!IMPORTANT] Adobe rekommenderar att du inte använder den här variabeln. Använd [Adobe Experience Cloud Identity Service](https://docs.adobe.com/content/help/en/id-service/using/home.html) i stället.

## Besökar-ID i Adobe Experience Platform Launch

[!UICONTROL Visitor ID] är ett fält under [!UICONTROL Cookies] dragspelet när du konfigurerar Adobe Analytics-tillägget.

1. Logga in på [launch.adobe.com](https://launch.adobe.com) med inloggningsuppgifterna för ditt AdobeID.
2. Klicka på önskad egenskap.
3. Gå till [!UICONTROL Extensions] fliken och klicka sedan på [!UICONTROL Configure] knappen under Adobe Analytics.
4. Expandera dragspelsfliken, som visar [!UICONTROL Cookies] [!UICONTROL Visitor ID] fältet.

Tilldela det här fältet till dataelementet som innehåller ditt anpassade besökar-ID. Ange inte det här fältet som ett statiskt värde.

## s.visitorID i AppMeasurement och Launch custom code editor

Variabeln `s.visitorID` är en sträng som innehåller en anpassad unik identifierare för besökaren. Giltiga värden är alfanumeriska tecken upp till 100 byte. Undvik att använda streck, blanksteg, understreck och symboler i den här variabeln.

> [!WARNING] Om du ställer in variabeln partway genom ett besök resulterar data i två olika unika besökare. `visitorID`

```js
s.visitorID = "abc123";
```
