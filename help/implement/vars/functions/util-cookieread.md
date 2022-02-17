---
title: Util.cookieRead
description: Hämtar värdet för en cookie.
feature: Variables
exl-id: b05b628c-bae6-4dba-bc1d-6a1ab56e3660
source-git-commit: b3c74782ef6183fa63674b98e4c0fc39fc09441b
workflow-type: tm+mt
source-wordcount: '163'
ht-degree: 1%

---

# Util.cookieRead

Cookies kan lagra och hämta information över sidor på samma domän. Använd `Util.cookieRead()` metod för att hämta ett värde från en cookie.

## Läs cookies med taggar i Adobe Experience Platform

Du kan läsa cookies genom att ange värden i dataelement.

1. Logga in på [Användargränssnitt för datainsamling](https://experience.adobe.com/data-collection) med inloggningsuppgifterna för ditt AdobeID.
2. Klicka på önskad egenskap.
3. Gå till [!UICONTROL Data Elements] och sedan klicka på det önskade dataelementet (eller skapa ett dataelement).
4. Ange [!UICONTROL Extension] listruta till [!UICONTROL Core]och [!UICONTROL Data Element Type] till [!UICONTROL Cookie].
5. Ange cookie-namnet i textfältet.

Cookie-värdet lagras i dataelementet. Du kan sedan referera till dataelementet i regler för att tilldela Analytics-variabler.

## s.Util.cookieRead() i AppMeasurement och en anpassad kodredigerare

Ring `s.Util.cookieRead()` metod för att läsa ett önskat cookie-värde. Dess enda argument är en sträng, vilket är obligatoriskt. Den här metoden returnerar en sträng som innehåller cookie-värdet. Om cookies inte finns returneras en tom sträng.

```js
// Reads the value set in the cookie named 'example' and assigns the value to eVar1
s.eVar1 = s.Util.cookieRead("example");
```
