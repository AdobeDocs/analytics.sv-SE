---
title: Util.cookieRead
description: Hämtar värdet för en cookie.
translation-type: tm+mt
source-git-commit: d1db8da65faac1bf09fa2a290a2645092b542a35

---


# Util.cookieRead

Cookies kan lagra och hämta information över sidor på samma domän. Använd `Util.cookieRead` metoden för att hämta ett värde från en cookie.

## Läs cookies i Adobe Experience Platform Launch

Du kan läsa cookies genom att ange värden i dataelement.

1. Logga in på [launch.adobe.com](https://launch.adobe.com) med inloggningsuppgifterna för ditt AdobeID.
2. Klicka på önskad egenskap.
3. Gå till [!UICONTROL Data Elements] fliken och klicka sedan på det önskade dataelementet (eller skapa ett dataelement).
4. Ställ in [!UICONTROL Extension] listrutan till [!UICONTROL Core]och [!UICONTROL Data Element Type] till [!UICONTROL Cookie].
5. Ange cookie-namnet i textfältet.

Cookie-värdet lagras i dataelementet. Du kan sedan referera till dataelementet i regler för att tilldela Analytics-variabler.

## s.Util.cookieRead() i AppMeasurement och Launch, anpassad kodredigerare

Anropa `s.Util.cookieRead()` metoden för att läsa ett önskat cookie-värde. Dess enda argument är en sträng, vilket är obligatoriskt. Den här metoden returnerar en sträng som innehåller cookie-värdet. Om cookies inte finns returneras en tom sträng.

```js
// Reads the value set in the cookie named 'example' and assigns the value to eVar1
s.eVar1 = s.Util.cookieRead("example");
```
