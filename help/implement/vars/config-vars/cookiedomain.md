---
title: cookieDomain
description: Variabeln cookieDomain hjälper till att avgöra vilken domän cookies ska användas på.
feature: Variables
exl-id: 7e8c26b8-d1a7-49f7-9c12-45fb1633c9d7
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '199'
ht-degree: 1%

---

# cookieDomain

>[!IMPORTANT]
>
>Den här variabeln har tagits bort. Använd [`trackingServer`](trackingserver.md) i stället.

The `cookieDomain` variabeln bestämmer den domän där AppMeasurement anger cookies. Du kan använda den här variabeln för att explicit ange cookie-domänen i stället för att använda [`cookieDomainPeriods`](cookiedomainperiods.md) variabel.

Den här variabeln behöver bara användas när **båda** av följande villkor är uppfyllda:

* Om implementeringen använder cookies från första part. Den här variabeln krävs inte för implementeringar som använder en [`trackingServer`](trackingserver.md) värde som innehåller `sc.adobedc.net`.
* Om din domän har en punkt i suffixet. Till exempel: `example.co.uk` kan använda `cookieDomain` variabel för att explicit ange att cookie-domänen är `example.co.uk` och inte `co.uk`.

Endast ett litet antal implementeringar har använts för `cookieDomain` variabel, och till och med då, alternativa variabler som [`cookieDomainPeriods`](cookiedomainperiods.md) kan användas i stället.

## Cookie-domän med Web SDK

Web SDK kan identifiera rätt cookie-lagringsdomän utan den här variabeln.

## Cookie-domän med Adobe Analytics-tillägg

Det finns inget dedikerat fält i Adobe Analytics-tillägget som kan använda den här variabeln. Använd den anpassade kodredigeraren efter AppMeasurement-syntax.

## s.cookieDomain i AppMeasurement och den anpassade kodredigeraren i Analytics-tillägget

The `cookieDomain` variabeln är en sträng och ställs in på den domän där du vill lagra cookies.

```js
s.cookieDomain = "stats.example.com";
```
