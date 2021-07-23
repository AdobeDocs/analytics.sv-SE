---
title: cookieDomain
description: Variabeln cookieDomain hjälper till att avgöra vilken domän cookies ska användas på.
exl-id: 7e8c26b8-d1a7-49f7-9c12-45fb1633c9d7
source-git-commit: 3986084eaab81842b6ea0dbabc7bdb78e39f887a
workflow-type: tm+mt
source-wordcount: '178'
ht-degree: 1%

---

# cookieDomain

>[!IMPORTANT]
>
>Den här variabeln har tagits bort. Använd [`trackingServer`](trackingserver.md) i stället.

Variabeln `cookieDomain` avgör vilken domän AppMeasurement anger cookies i. Du kan använda den här variabeln för att explicit ange cookie-domänen i stället för att använda variabeln [`cookieDomainPeriods`](cookiedomainperiods.md).

Den här variabeln behöver bara användas när **båda** av följande villkor uppfylls:

* Om implementeringen använder cookies från första part. Den här variabeln krävs inte för implementeringar som använder ett [`trackingServer`](trackingserver.md)-värde som innehåller `sc.adobedc.net`.
* Om din domän har en punkt i suffixet. `example.co.uk` kan till exempel använda variabeln `cookieDomain` för att explicit ange att cookie-domänen är `example.co.uk` och inte `co.uk`.

Endast ett litet antal implementeringar har använts för variabeln `cookieDomain`, och även då kan alternativa variabler som [`cookieDomainPeriods`](cookiedomainperiods.md) användas i stället.

## Cookie-domän i Adobe Experience Platform Data Collection

Det finns inget dedikerat fält i användargränssnittet för datainsamling som kan använda den här variabeln. Använd den anpassade kodredigeraren efter AppMeasurement-syntax.

## s.cookieDomain i AppMeasurement och anpassad kodredigerare

Variabeln `cookieDomain` är en sträng och ställs in på den domän där du vill lagra cookies.

```js
s.cookieDomain = "stats.example.com";
```
