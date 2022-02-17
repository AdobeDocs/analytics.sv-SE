---
title: Util.cookieWrite
description: Skriver ett värde för en cookie.
feature: Variables
exl-id: 079dbe50-5568-467b-a67c-f44481a4a20b
source-git-commit: b3c74782ef6183fa63674b98e4c0fc39fc09441b
workflow-type: tm+mt
source-wordcount: '131'
ht-degree: 2%

---

# Util.cookieWrite

Cookies kan lagra och hämta information över sidor på samma domän. Använd `Util.cookieWrite()` metod för att ange ett värde för en cookie. Du kan använda [`Util.cookieRead()`](util-cookieread.md) metod för att hämta värden som ställts in med `Util.cookieWrite()`.

## Ange cookies med hjälp av taggar i Adobe Experience Platform

Gränssnittet för datainsamling ger inte möjlighet att ange cookies i gränssnittet. Använd den anpassade kodredigeraren efter AppMeasurement-syntax.

## s.Util.cookieWrite() i AppMeasurement och anpassad kodredigerare

Ring `s.Util.cookieWrite()` metod för att ange ett önskat värde för en cookie.

```js
s.Util.cookieWrite("example_cookie","Example cookie value")
```

Det finns ett valfritt tredje argument som avgör när cookien upphör att gälla. Cookies anges med `s.Util.cookieWrite()` förfaller som standard i slutet av webbläsarsessionen.

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
