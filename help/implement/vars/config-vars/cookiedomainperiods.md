---
title: cookieDomainPeriods
description: Hjälp AppMeasurementet att förstå vilken domän cookies ska lagras i om domänen har en punkt i suffixet.
feature: Variables
exl-id: c426d6a7-4521-4d50-bb7d-1664920618d8
role: Admin, Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '306'
ht-degree: 0%

---


# cookieDomainPeriods

AppMeasurementet avgör dess cookie-plats genom att titta på domänen och domänsuffixet. För domäner som `example.com`, ställer AppMeasurementet in cookies på rätt plats. För andra domäner som `example.co.uk`, kan AppMeasurementet av misstag ange cookies på `co.uk`. De flesta webbläsare avvisar cookies som angetts i den här ogiltiga domänen, vilket orsakar problem med besökaridentifiering.

The `cookieDomainPeriods` variabeln hjälper AppMeasurementet att avgöra var Analytics-cookies anges genom att anropa att domänsuffixet har en extra period. Den här variabeln gör att AppMeasurementet kan ta emot den extra perioden i domänsuffixet och ange cookies på rätt plats.

* För domäner som `example.com` eller `www.example.com`behöver den här variabeln inte anges. Om det behövs kan du ange variabeln till `"2"`.
* För domäner som `example.co.uk` eller `www.example.co.jp`, ange variabeln till `"3"`.

>[!IMPORTANT]
>
>Ta inte underdomäner med i beräkningen för variabeln. Ange till exempel inte `cookieDomainPeriods` på exempelwebbadressen `store.toys.example.com`. AppMeasurementet känner som standard igen att cookies ska lagras på `example.com`, även på URL:er med många underdomäner.

## Domänperioder som använder Web SDK

Web SDK kan identifiera rätt cookie-lagringsdomän utan den här variabeln.

## Domänperioder som använder Adobe Analytics-tillägget

Domänperioder är ett fält under [!UICONTROL Cookies] när du konfigurerar Adobe Analytics-tillägget.

1. Logga in på [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) med inloggningsuppgifterna för ditt AdobeID.
1. Klicka på den önskade taggegenskapen.
1. Gå till [!UICONTROL Extensions] klickar du på **[!UICONTROL Configure]** under Adobe Analytics.
1. Expandera [!UICONTROL Cookies] dragspelspanel, som visar [!UICONTROL Domain Periods] fält.

Ange att fältet ska `3` endast på domäner som innehåller en punkt i suffixet. Annars kan fältet lämnas tomt.

## s.cookieDomainPeriods i AppMeasurementet och den anpassade kodredigeraren för Analytics-tillägget

The `cookieDomainPeriods` variabeln är en sträng som vanligtvis är inställd på `"3"`, endast i domäner som innehåller en punkt i suffixet. Standardvärdet är `"2"`, som rymmer de flesta domäner.

```js
// Manually set cookieDomainPeriods for domains with a period in its suffix, such as www.example.co.uk
s.cookieDomainPeriods = "3";

// Detect if a URL has a domain suffix with an extra period, and set s.cookieDomainPeriods automatically
document.URL.indexOf(".co.") > 0 ? s.cookieDomainPeriods = "3" : s.cookieDomainPeriods = "2";
```
