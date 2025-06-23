---
title: fpcookieDomainPeriods
description: Hjälp AppMeasurement att förstå vilken domän cookies ska lagras i om din domän har en punkt i suffixet.
feature: Appmeasurement Implementation
exl-id: e994a188-1dab-4bf0-912b-cd2f6a1032e0
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '281'
ht-degree: 0%

---

# fpCookieDomainPeriods

Variabeln `fpCookieDomainPeriods` hjälper AppMeasurement att avgöra var Analytics-cookies anges genom att anropa att domänsuffixet har en extra period. Med den här variabeln kan AppMeasurement ta emot den extra perioden i domänsuffixet och ange cookies på rätt plats. Det ärver värdet för [`cookieDomainPeriods`](cookiedomainperiods.md), men det är fortfarande en bra metod att ange om du använder en cookie-implementering från en annan leverantör.

* För domäner som `example.com` eller `www.example.com` behöver variabeln inte anges. Om det behövs kan du ange variabeln till `"2"`.
* För domäner som `example.co.uk` eller `www.example.co.jp` anger du den här variabeln till `"3"`.

>[!IMPORTANT]
>
>Ta inte underdomäner med i beräkningen för variabeln. Ange till exempel inte `fpCookieDomainPeriods` för exempel-URL:en `store.toys.example.com`. AppMeasurement identifierar som standard att cookies ska lagras på `example.com`, även på URL:er med många underdomäner.

## Första parts domänperioder som använder Web SDK

SDK kan identifiera rätt cookie-lagringsdomän utan den här variabeln.

## Första parts domänperioder som använder Adobe Analytics-tillägget

Första parts domänperioder är ett fält under dragspelet [!UICONTROL Cookies] när Adobe Analytics-tillägget konfigureras.

1. Logga in på [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) med dina inloggningsuppgifter för AdobeID.
2. Klicka på den önskade taggegenskapen.
3. Gå till fliken [!UICONTROL Extensions] och klicka sedan på knappen **[!UICONTROL Configure]** under Adobe Analytics.
4. Expandera dragspelsfliken [!UICONTROL Cookies] som visar fältet [!UICONTROL First-party Domain Periods].

Ange det här fältet som `3` endast för domäner som innehåller en punkt i suffixet. Annars kan fältet lämnas tomt.

## s.fpCookieDomainPeriods i AppMeasurement och den anpassade kodredigeraren för Analytics-tillägget

Variabeln `fpCookieDomainPeriods` är en sträng som vanligtvis är inställd på `"3"`, endast i domäner som innehåller en punkt i suffixet. Dess standardvärde är `"2"`, som rymmer de flesta domäner.

```js
// Manually set fpCookieDomainPeriods for domains with a period in its suffix, such as www.example.co.uk
s.fpCookieDomainPeriods = "3";

// Detect if a URL has a domain suffix with an extra period, and set s.fpCookieDomainPeriods automatically
document.URL.indexOf(".co.") > 0 ? s.fpCookieDomainPeriods = "3" : s.fpCookieDomainPeriods = "2";
```
