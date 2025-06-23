---
title: Util.cookieWrite
description: Skriver ett värde för en cookie.
feature: Appmeasurement Implementation
exl-id: 079dbe50-5568-467b-a67c-f44481a4a20b
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '131'
ht-degree: 0%

---

# Util.cookieWrite

Cookies kan lagra och hämta information över sidor på samma domän. Använd metoden `Util.cookieWrite()` för att ange ett värde för en cookie. Du kan använda metoden [`Util.cookieRead()`](util-cookieread.md) för att hämta värden som angetts med `Util.cookieWrite()`.

## Ange cookies med Adobe Analytics och Web SDK-tillägget

Adobe Experience Platform Data Collection ger inte möjlighet att ange cookies i gränssnittet.

## s.Util.cookieWrite() i AppMeasurement och den anpassade kodredigeraren för Analytics-tillägget

Anropa metoden `s.Util.cookieWrite()` för att ange en cookie till önskat värde.

```js
s.Util.cookieWrite("example_cookie","Example cookie value")
```

Det finns ett valfritt tredje argument som avgör när cookien upphör att gälla. Cookies som angetts med `s.Util.cookieWrite()` förfaller som standard i slutet av webbläsarsessionen.

```js
// Set a cookie with an expiration 6 months from now
var cookieDate = new Date();
cookieDate.setMonth(cookieDate.getMonth() + 6);
s.Util.cookieWrite("example_cookie","Example 6-month cookie",cookieDate);
```

## Exempel

Du kan instansiera en variabel när du har skrivit en cookie. Variabeln är boolesk.

```js
var success = s.Util.cookieWrite("example_cookie","Example cookie value");
if (success) {
  console.log("Cookie written successfully");
} else {
  console.log("Cookie write failed");
}
```
