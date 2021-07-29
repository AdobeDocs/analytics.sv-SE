---
title: cookieDomainPeriods
description: Hjälp AppMeasurement att förstå vilken domän cookies ska lagras i om din domän har en punkt i suffixet.
exl-id: e994a188-1dab-4bf0-912b-cd2f6a1032e0
source-git-commit: 1a49c2a6d90fc670bd0646d6d40738a87b74b8eb
workflow-type: tm+mt
source-wordcount: '259'
ht-degree: 0%

---

# fpCookieDomainPeriods

Variabeln `fpCookieDomainPeriods` hjälper AppMeasurement att avgöra var Analytics-cookies anges genom att anropa att domänsuffixet har en extra period. Den här variabeln tillåter AppMeasurement att anpassa den extra perioden i domänsuffixet och ange cookies på rätt plats. Den ärver värdet [`cookieDomainPeriods`](cookiedomainperiods.md), men är ändå en bra metod att ange om du använder en cookie-implementering från en annan leverantör.

* För domäner som `example.com` eller `www.example.com` behöver den här variabeln inte anges. Om det behövs kan du ställa in den här variabeln på `"2"`.
* För domäner som `example.co.uk` eller `www.example.co.jp` anger du den här variabeln till `"3"`.

>[!IMPORTANT]
>
>Ta inte underdomäner med i beräkningen för den här variabeln. Ange till exempel inte `fpCookieDomainPeriods` för exempel-URL:en `store.toys.example.com`. AppMeasurement identifierar som standard att cookies ska lagras på `example.com`, även på URL:er med många underdomäner.

## Första parts domänperioder som använder taggar i Adobe Experience Platform

Första parts domänperioder är ett fält under dragspelet [!UICONTROL Cookies] när tillägget Adobe Analytics konfigureras.

1. Logga in på [användargränssnittet för datainsamling](https://experience.adobe.com/data-collection) med inloggningsuppgifterna för ditt Adobe-ID.
2. Klicka på önskad egenskap.
3. Gå till fliken [!UICONTROL Extensions] och klicka sedan på knappen [!UICONTROL Configure] under Adobe Analytics.
4. Expandera dragspelet [!UICONTROL Cookies], som visar fältet [!UICONTROL First-party Domain Periods].

Ange det här fältet som `3` endast för domäner som innehåller en punkt i suffixet. Annars kan fältet lämnas tomt.

## s.fpCookieDomainPeriods i AppMeasurement och anpassad kodredigerare

Variabeln `fpCookieDomainPeriods` är en sträng som vanligtvis är inställd på `"3"`, endast i domäner som innehåller en punkt i suffixet. Dess standardvärde är `"2"`, som rymmer de flesta domäner.

```js
// Manually set fpCookieDomainPeriods for domains with a period in its suffix, such as www.example.co.uk
s.fpCookieDomainPeriods = "3";

// Detect if a URL has a domain suffix with an extra period, and set s.fpCookieDomainPeriods automatically
document.URL.indexOf(".co.") > 0 ? s.fpCookieDomainPeriods = "3" : s.fpCookieDomainPeriods = "2";
```
