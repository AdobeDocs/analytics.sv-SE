---
title: Util.cookieWrite
description: Skriver ett värde för en cookie.
feature: Variables
exl-id: 079dbe50-5568-467b-a67c-f44481a4a20b
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '131'
ht-degree: 2%

---

# Util.cookieWrite

Cookies kan lagra och hämta information över sidor på samma domän. Använd `Util.cookieWrite()` metod för att ange ett värde för en cookie. Du kan använda [`Util.cookieRead()`](util-cookieread.md) metod för att hämta värden som ställts in med `Util.cookieWrite()`.

## Ange cookies med Adobe Analytics-tillägget och Web SDK-tillägget

Adobe Experience Platform Data Collection ger inte möjlighet att ange cookies i gränssnittet.

## s.Util.cookieWrite() i AppMeasurement och den anpassade kodredigeraren för Analytics-tillägget

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
