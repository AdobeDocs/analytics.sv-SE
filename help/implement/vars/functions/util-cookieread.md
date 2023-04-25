---
title: Util.cookieRead
description: Hämtar värdet för en cookie.
feature: Variables
exl-id: b05b628c-bae6-4dba-bc1d-6a1ab56e3660
source-git-commit: 6de20d2fbbab6ded6c92f0c6f3536671f4b2ae46
workflow-type: tm+mt
source-wordcount: '174'
ht-degree: 1%

---

# Util.cookieRead

Cookies kan lagra och hämta information över sidor på samma domän. Använd `Util.cookieRead()` metod för att hämta ett värde från en cookie.

## Läs cookies med Adobe Analytics-tillägget och Web SDK-tillägget

Du kan läsa cookies genom att ange värden i dataelement.

1. Logga in på [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) med inloggningsuppgifterna för ditt AdobeID.
2. Klicka på den önskade taggegenskapen.
3. Gå till [!UICONTROL Data Elements] och sedan klicka på det önskade dataelementet (eller skapa ett dataelement).
4. Ange [!UICONTROL Extension] nedrullningsbar lista till **[!UICONTROL Core]** och [!UICONTROL Data Element Type] till **[!UICONTROL Cookie]**.
5. Ange cookie-namnet i textfältet.

Cookie-värdet lagras i dataelementet. Du kan sedan referera till dataelementet i regler för att tilldela de önskade variablerna.

## s.Util.cookieRead() i AppMeasurement och den anpassade kodredigeraren i Analytics-tillägget

Ring `s.Util.cookieRead()` metod för att läsa ett önskat cookie-värde. Dess enda argument är en sträng, vilket är obligatoriskt. Den här metoden returnerar en sträng som innehåller cookie-värdet. Om cookies inte finns returneras en tom sträng.

```js
// Reads the value set in the cookie named 'example' and assigns the value to eVar1
s.eVar1 = s.Util.cookieRead("example");
```
