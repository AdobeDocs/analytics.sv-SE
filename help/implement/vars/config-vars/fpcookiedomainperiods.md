---
title: fpcookieDomainPeriods
description: Hjälp AppMeasurementet att förstå vilken domän cookies ska lagras i om domänen har en punkt i suffixet.
feature: Variables
exl-id: e994a188-1dab-4bf0-912b-cd2f6a1032e0
role: Admin, Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '281'
ht-degree: 0%

---

# fpCookieDomainPeriods

The `fpCookieDomainPeriods` variabeln hjälper AppMeasurementet att avgöra var Analytics-cookies anges genom att anropa att domänsuffixet har en extra period. Den här variabeln gör att AppMeasurementet kan ta emot den extra perioden i domänsuffixet och ange cookies på rätt plats. Det ärver värdet för [`cookieDomainPeriods`](cookiedomainperiods.md), men det är ändå en bra metod att ange om du använder en cookie-implementering från en annan leverantör.

* För domäner som `example.com` eller `www.example.com`behöver den här variabeln inte anges. Om det behövs kan du ange variabeln till `"2"`.
* För domäner som `example.co.uk` eller `www.example.co.jp`, ange variabeln till `"3"`.

>[!IMPORTANT]
>
>Ta inte underdomäner med i beräkningen för variabeln. Ange till exempel inte `fpCookieDomainPeriods` på exempelwebbadressen `store.toys.example.com`. AppMeasurementet känner som standard igen att cookies ska lagras på `example.com`, även på URL:er med många underdomäner.

## Första parts domänperioder med Web SDK

Web SDK kan identifiera rätt cookie-lagringsdomän utan den här variabeln.

## Första parts domänperioder som använder Adobe Analytics-tillägget

Första parts domänperioder är ett fält under [!UICONTROL Cookies] när du konfigurerar Adobe Analytics-tillägget.

1. Logga in på [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) med inloggningsuppgifterna för ditt AdobeID.
2. Klicka på den önskade taggegenskapen.
3. Gå till [!UICONTROL Extensions] klickar du på **[!UICONTROL Configure]** under Adobe Analytics.
4. Expandera [!UICONTROL Cookies] dragspelspanel, som visar [!UICONTROL First-party Domain Periods] fält.

Ange att fältet ska `3` endast på domäner som innehåller en punkt i suffixet. Annars kan fältet lämnas tomt.

## s.fpCookieDomainPeriods i AppMeasurementet och den anpassade kodredigeraren för Analytics-tillägget

The `fpCookieDomainPeriods` variabeln är en sträng som vanligtvis är inställd på `"3"`, endast i domäner som innehåller en punkt i suffixet. Standardvärdet är `"2"`, som rymmer de flesta domäner.

```js
// Manually set fpCookieDomainPeriods for domains with a period in its suffix, such as www.example.co.uk
s.fpCookieDomainPeriods = "3";

// Detect if a URL has a domain suffix with an extra period, and set s.fpCookieDomainPeriods automatically
document.URL.indexOf(".co.") > 0 ? s.fpCookieDomainPeriods = "3" : s.fpCookieDomainPeriods = "2";
```
