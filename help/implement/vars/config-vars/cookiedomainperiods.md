---
title: cookieDomainPeriods
description: Hjälp AppMeasurement att förstå vilken domän cookies ska lagras i om din domän har en punkt i suffixet.
exl-id: c426d6a7-4521-4d50-bb7d-1664920618d8
source-git-commit: 1a49c2a6d90fc670bd0646d6d40738a87b74b8eb
workflow-type: tm+mt
source-wordcount: '285'
ht-degree: 0%

---

# cookieDomainPeriods

AppMeasurement bestämmer cookie-platsen genom att titta på domänen och domänsuffixet. För domäner som `example.com` ställer AppMeasurement in cookies på rätt plats. För andra domäner som `example.co.uk` kan AppMeasurement av misstag ange cookies på `co.uk`. De flesta webbläsare avvisar cookies som angetts i den här ogiltiga domänen, vilket orsakar problem med besökaridentifiering.

Variabeln `cookieDomainPeriods` hjälper AppMeasurement att avgöra var Analytics-cookies anges genom att anropa att domänsuffixet har en extra period. Den här variabeln tillåter AppMeasurement att anpassa den extra perioden i domänsuffixet och ange cookies på rätt plats.

* För domäner som `example.com` eller `www.example.com` behöver den här variabeln inte anges. Om det behövs kan du ställa in den här variabeln på `"2"`.
* För domäner som `example.co.uk` eller `www.example.co.jp` anger du den här variabeln till `"3"`.

>[!IMPORTANT]
>
>Ta inte underdomäner med i beräkningen för den här variabeln. Ange till exempel inte `cookieDomainPeriods` för exempel-URL:en `store.toys.example.com`. AppMeasurement identifierar som standard att cookies ska lagras på `example.com`, även på URL:er med många underdomäner.

## Domänperioder som använder taggar i Adobe Experience Platform

Domänperioder är ett fält under dragspelet [!UICONTROL Cookies] när du konfigurerar Adobe Analytics-tillägget.

1. Logga in på [användargränssnittet för datainsamling](https://experience.adobe.com/data-collection) med inloggningsuppgifterna för ditt Adobe-ID.
1. Klicka på önskad egenskap.
1. Gå till fliken [!UICONTROL Extensions] och klicka sedan på knappen [!UICONTROL Configure] under Adobe Analytics.
1. Expandera dragspelet [!UICONTROL Cookies], som visar fältet [!UICONTROL Domain Periods].

Ange det här fältet som `3` endast för domäner som innehåller en punkt i suffixet. Annars kan fältet lämnas tomt.

## s.cookieDomainPeriods i AppMeasurement och anpassad kodredigerare

Variabeln `cookieDomainPeriods` är en sträng som vanligtvis är inställd på `"3"`, endast i domäner som innehåller en punkt i suffixet. Dess standardvärde är `"2"`, som rymmer de flesta domäner.

```js
// Manually set cookieDomainPeriods for domains with a period in its suffix, such as www.example.co.uk
s.cookieDomainPeriods = "3";

// Detect if a URL has a domain suffix with an extra period, and set s.cookieDomainPeriods automatically
document.URL.indexOf(".co.") > 0 ? s.cookieDomainPeriods = "3" : s.cookieDomainPeriods = "2";
```
