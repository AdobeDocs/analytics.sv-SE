---
title: Util.cookieRead
description: Hämtar värdet för en cookie.
exl-id: b05b628c-bae6-4dba-bc1d-6a1ab56e3660
source-git-commit: 1a49c2a6d90fc670bd0646d6d40738a87b74b8eb
workflow-type: tm+mt
source-wordcount: '163'
ht-degree: 1%

---

# Util.cookieRead

Cookies kan lagra och hämta information över sidor på samma domän. Använd metoden `Util.cookieRead()` för att hämta ett värde från en cookie.

## Läs cookies med taggar i Adobe Experience Platform

Du kan läsa cookies genom att ange värden i dataelement.

1. Logga in på [användargränssnittet för datainsamling](https://experience.adobe.com/data-collection) med inloggningsuppgifterna för ditt Adobe-ID.
2. Klicka på önskad egenskap.
3. Gå till fliken [!UICONTROL Data Elements] och klicka sedan på det önskade dataelementet (eller skapa ett dataelement).
4. Ställ in listrutan [!UICONTROL Extension] till [!UICONTROL Core] och [!UICONTROL Data Element Type] till [!UICONTROL Cookie].
5. Ange cookie-namnet i textfältet.

Cookie-värdet lagras i dataelementet. Du kan sedan referera till dataelementet i regler för att tilldela Analytics-variabler.

## s.Util.cookieRead() i AppMeasurement och en anpassad kodredigerare

Anropa metoden `s.Util.cookieRead()` om du vill läsa ett önskat cookie-värde. Dess enda argument är en sträng, vilket är obligatoriskt. Den här metoden returnerar en sträng som innehåller cookie-värdet. Om cookies inte finns returneras en tom sträng.

```js
// Reads the value set in the cookie named 'example' and assigns the value to eVar1
s.eVar1 = s.Util.cookieRead("example");
```
