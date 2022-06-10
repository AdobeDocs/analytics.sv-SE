---
title: cookieDomainPeriods
description: Hjälp AppMeasurement att förstå vilken domän cookies ska lagras i om din domän har en punkt i suffixet.
feature: Variables
exl-id: c426d6a7-4521-4d50-bb7d-1664920618d8
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '308'
ht-degree: 0%

---


# cookieDomainPeriods

AppMeasurement bestämmer cookie-platsen genom att titta på domänen och domänsuffixet. För domäner som `example.com`, AppMeasurement ställer in cookies på rätt plats. För andra domäner som `example.co.uk`kan AppMeasurement av misstag ange cookies på `co.uk`. De flesta webbläsare avvisar cookies som angetts i den här ogiltiga domänen, vilket orsakar problem med besökaridentifiering.

The `cookieDomainPeriods` variabeln hjälper AppMeasurement att avgöra var Analytics-cookies anges genom att anropa att domänsuffixet har en extra period. Den här variabeln tillåter AppMeasurement att anpassa den extra perioden i domänsuffixet och ange cookies på rätt plats.

* För domäner som `example.com` eller `www.example.com`behöver den här variabeln inte anges. Om det behövs kan du ange variabeln till `"2"`.
* För domäner som `example.co.uk` eller `www.example.co.jp`, ange variabeln till `"3"`.

>[!IMPORTANT]
>
>Ta inte underdomäner med i beräkningen för den här variabeln. Ange till exempel inte `cookieDomainPeriods` på exempelwebbadressen `store.toys.example.com`. AppMeasurement känner som standard igen att cookies ska lagras på `example.com`, även på URL:er med många underdomäner.

## Domänperioder som använder Web SDK

Web SDK kan identifiera rätt cookie-lagringsdomän utan den här variabeln.

## Domänperioder som använder Adobe Analytics-tillägget

Domänperioder är ett fält under [!UICONTROL Cookies] när du konfigurerar Adobe Analytics-tillägget.

1. Logga in på [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) med inloggningsuppgifterna för ditt AdobeID.
1. Klicka på den önskade taggegenskapen.
1. Gå till [!UICONTROL Extensions] klickar du på **[!UICONTROL Configure]** under Adobe Analytics.
1. Expandera [!UICONTROL Cookies] dragspelspanel, som visar [!UICONTROL Domain Periods] fält.

Ange att det här fältet ska `3` endast på domäner som innehåller en punkt i suffixet. Annars kan fältet lämnas tomt.

## s.cookieDomainPeriods i AppMeasurement och den anpassade kodredigeraren i Analytics-tillägget

The `cookieDomainPeriods` variabeln är en sträng som vanligtvis är inställd på `"3"`, endast i domäner som innehåller en punkt i suffixet. Standardvärdet är `"2"`, som rymmer de flesta domäner.

```js
// Manually set cookieDomainPeriods for domains with a period in its suffix, such as www.example.co.uk
s.cookieDomainPeriods = "3";

// Detect if a URL has a domain suffix with an extra period, and set s.cookieDomainPeriods automatically
document.URL.indexOf(".co.") > 0 ? s.cookieDomainPeriods = "3" : s.cookieDomainPeriods = "2";
```
