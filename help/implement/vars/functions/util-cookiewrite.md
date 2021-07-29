---
title: Util.cookieWrite
description: Skriver ett värde för en cookie.
exl-id: 079dbe50-5568-467b-a67c-f44481a4a20b
source-git-commit: 1a49c2a6d90fc670bd0646d6d40738a87b74b8eb
workflow-type: tm+mt
source-wordcount: '131'
ht-degree: 2%

---

# Util.cookieWrite

Cookies kan lagra och hämta information över sidor på samma domän. Använd metoden `Util.cookieWrite()` för att ange ett värde för en cookie. Du kan använda metoden [`Util.cookieRead()`](util-cookieread.md) för att hämta värden som angetts med `Util.cookieWrite()`.

## Ange cookies med hjälp av taggar i Adobe Experience Platform

Gränssnittet för datainsamling ger inte möjlighet att ange cookies i gränssnittet. Använd den anpassade kodredigeraren efter AppMeasurement-syntax.

## s.Util.cookieWrite() i AppMeasurement och anpassad kodredigerare

Anropa metoden `s.Util.cookieWrite()` om du vill ange ett värde för en cookie.

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
