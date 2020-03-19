---
title: cookieDomain
description: Variabeln cookieDomain hjälper till att avgöra vilken domän cookies ska användas på.
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# cookieDomain

> [!IMPORTANT] Den här variabeln har tagits bort. Använd [`trackingServer`](trackingserver.md) istället.

Variabeln avgör vilken domän AppMeasurement anger cookies i. `cookieDomain` Du kan använda den här variabeln för att explicit ange cookie-domänen i stället för att använda [`cookieDomainPeriods`](cookiedomainperiods.md) -variabeln.

Den här variabeln behöver bara användas när **båda** följande villkor är uppfyllda:

* Om implementeringen använder cookies från första part. Den här variabeln krävs inte för implementeringar som använder ett [`trackingServer`](trackingserver.md) värde som innehåller `sc.omtrdc.net`.
* Om din domän har en punkt i suffixet. Du kan till exempel `example.co.uk` använda `cookieDomain` variabeln för att explicit ange att cookie-domänen är `example.co.uk` och inte `co.uk`.

Endast ett litet antal implementeringar har använts för variabeln, och till och med då kan alternativa variabler som `cookieDomain` [`cookieDomainPeriods`](cookiedomainperiods.md) kan användas i stället.

## Cookie-domän i Adobe Experience Platform Launch

Det finns inget dedikerat fält i Launch som kan använda den här variabeln. Använd den anpassade kodredigeraren efter AppMeasurement-syntax.

## s.cookieDomain i AppMeasurement och Launch custom code editor

Variabeln `cookieDomain` är en sträng och är inställd på den domän där du vill lagra cookies.

```js
s.cookieDomain = "stats.example.com";
```
