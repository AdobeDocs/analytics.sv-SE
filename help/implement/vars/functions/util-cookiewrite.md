---
title: Util.cookieWrite
description: Skriver ett värde för en cookie.
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# Util.cookieWrite

Cookies kan lagra och hämta information över sidor på samma domän. Använd `Util.cookieWrite()` metoden för att ange ett värde för en cookie. Du kan använda metoden [`Util.cookieRead()`](util-cookieread.md) för att hämta värden som angetts med `Util.cookieWrite()`.

## Ange cookies i Adobe Experience Platform Launch

Launch ger inte möjlighet att ange cookies i gränssnittet. Använd den anpassade kodredigeraren efter AppMeasurement-syntax.

## s.Util.cookieWrite() i AppMeasurement och Launch, anpassad kodredigerare

Anropa `s.Util.cookieWrite()` metoden för att ange ett önskat värde för en cookie.

```js
s.Util.cookieWrite("example_cookie","Example cookie value")
```

Det finns ett valfritt tredje argument som avgör när cookien upphör att gälla. Cookies som anges med `s.Util.cookieWrite()` upphör som standard i slutet av webbläsarsessionen.

```js
// Set a cookie with an expiration 6 months from now
var cookieDate = new Date();
cookieDate.setMonth(cookieDate.getMonth() + 6);
s.Util.cookieWrite("example_cookie","Example 6-month cookie",cookieDate);
```

## Exempel

Du kan instansiera en variabel när du har skrivit en cookie. Den här variabeln är boolesk.

```js
var success = s.Util.cookieWrite("example_cookie","Example cookie value");
if (success) {
  console.log("Cookie written successfully");
} else {
  console.log("Cookie write failed");
}
```
