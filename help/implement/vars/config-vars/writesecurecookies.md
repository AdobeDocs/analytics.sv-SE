---
title: writeSecureCookies
description: Tillåter AppMeasurement att ange cookies med attributet Secure.
translation-type: tm+mt
source-git-commit: 7644f70dfec5380fc75be14605f1c4f74ee4a8c3

---


# writeSecureCookies

Variabeln gör att AppMeasurement kan ange `writeSecureCookies` säkra cookies [](https://en.wikipedia.org/wiki/Secure_cookie) för Analytics. Den här inställningen gäller både cookies för besökar-ID som anges av AppMeasurement och cookies som du anger med `Util.CookieWrite` metoden. AppMeasurement 2.18.0 eller senare krävs.

> [!IMPORTANT] Om du aktiverar `writeSecureCookies` variabeln måste du se till att allt innehåll på webbplatsen hanteras säkert via HTTPS. AppMeasurement fungerar inte om den här variabeln är aktiverad och du har osäkert innehåll på sidan.

## Skriv säkra cookies i Adobe Experience Platform Launch

Det finns inget dedikerat fält i Launch som kan använda den här variabeln. Använd den anpassade kodredigeraren efter AppMeasurement-syntax.

## s.writeSecureCookies i AppMeasurement and Launch custom code editor

Variabeln är en boolesk variabel som avgör om AppMeasurement anger attributet Secure när en cookie skapas. `s.writeSecureCookies` Dess standardvärde är `false`. Ange variabeln till `true` om allt innehåll på webbplatsen är säkert och du vill att cookies som anges av AppMeasurement ska ha attributet Secure.

```js
s.writeSecureCookies = true;
```
