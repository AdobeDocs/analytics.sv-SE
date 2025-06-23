---
title: cookieDomain
description: (Borttaget) Hjälper till att avgöra vilken domän som cookies ska anges på.
feature: Appmeasurement Implementation
exl-id: 7e8c26b8-d1a7-49f7-9c12-45fb1633c9d7
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '197'
ht-degree: 0%

---

# cookieDomain

>[!IMPORTANT]
>Den här variabeln har tagits bort. Använd [`trackingServer`](trackingserver.md) i stället.

Variabeln `cookieDomain` avgör vilken domän AppMeasurement anger cookies i. Du kan använda den här variabeln för att explicit ange cookie-domänen i stället för att använda variabeln [`cookieDomainPeriods`](cookiedomainperiods.md).

Den här variabeln behöver bara användas när **båda** av följande villkor uppfylls:

* Om implementeringen använder cookies från första part. Den här variabeln krävs inte för implementeringar som använder ett [`trackingServer`](trackingserver.md)-värde som innehåller `sc.adobedc.net`.
* Om din domän har en punkt i suffixet. `example.co.uk` kan till exempel använda variabeln `cookieDomain` för att explicit ange att cookie-domänen är `example.co.uk` och inte `co.uk`.

Endast ett litet antal implementeringar har använts för variabeln `cookieDomain`, och även då kan alternativa variabler som [`cookieDomainPeriods`](cookiedomainperiods.md) användas i stället.

## Cookie-domän med SDK på webben

SDK kan identifiera rätt cookie-lagringsdomän utan den här variabeln.

## Cookie-domän med Adobe Analytics-tillägg

Det finns inget dedikerat fält i Adobe Analytics-tillägget som kan använda den här variabeln. Använd den anpassade kodredigeraren enligt AppMeasurement-syntax.

## s.cookieDomain i AppMeasurement och den anpassade kodredigeraren för Analytics-tillägget

Variabeln `cookieDomain` är en sträng och är inställd på domänen som du vill lagra cookies i.

```js
s.cookieDomain = "stats.example.com";
```
