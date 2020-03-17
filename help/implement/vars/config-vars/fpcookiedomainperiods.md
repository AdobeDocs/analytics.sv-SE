---
title: cookieDomainPeriods
description: Hjälp AppMeasurement att förstå vilken domän cookies ska lagras i om din domän har en punkt i suffixet.
translation-type: tm+mt
source-git-commit: 04b97e93a95691132680d4da197dc62eb2b9fdd1

---


# fpCookieDomainPeriods

Variabeln hjälper AppMeasurement att avgöra var Analytics-cookies anges genom att anropa att domänsuffixet har en extra period. `fpCookieDomainPeriods` Den här variabeln tillåter AppMeasurement att anpassa den extra perioden i domänsuffixet och ange cookies på rätt plats. Den ärver värdet av `cookieDomainPeriods`, men är ändå en bra metod att ange om du använder en cookie-implementering från en annan leverantör.

* För domäner som `example.com` eller `www.example.com`behöver variabeln inte anges. Om det behövs kan du ange variabeln till `"2"`.
* För domäner som `example.co.uk` eller `www.example.co.jp`anger du den här variabeln som `"3"`.

> [!IMPORTANT] Ta inte underdomäner med i beräkningen för den här variabeln. Ange till exempel inte `fpCookieDomainPeriods` på exempel-URL `store.toys.example.com`. AppMeasurement identifierar som standard att cookies ska lagras på `example.com`, även på URL:er med många underdomäner.

## Första parts domänperioder i Adobe Experience Platform Launch

Första parts domänperioder är ett fält under [!UICONTROL Cookies] dragspelet när Adobe Analytics-tillägget konfigureras.

1. Logga in på [launch.adobe.com](https://launch.adobe.com) med inloggningsuppgifterna för ditt AdobeID.
2. Klicka på önskad egenskap.
3. Gå till [!UICONTROL Extensions] fliken och klicka sedan på [!UICONTROL Configure] knappen under Adobe Analytics.
4. Expandera dragspelsfliken, som visar [!UICONTROL Cookies] [!UICONTROL First-party Domain Periods] fältet.

Ange det här fältet som `3` endast för domäner som innehåller en punkt i suffixet. Annars kan fältet lämnas tomt.

## s.fpCookieDomainPeriods i AppMeasurement och Launch, anpassad kodredigerare

Variabeln `fpCookieDomainPeriods` är en sträng som vanligtvis är inställd på `"3"`endast i domäner som innehåller en punkt i suffixet. Dess standardvärde är `"2"`, vilket ger plats för de flesta domäner.

```js
// Manually set fpCookieDomainPeriods for domains with a period in its suffix, such as www.example.co.uk
s.fpCookieDomainPeriods = "3";

// Detect if a URL has a domain suffix with an extra period, and set s.fpCookieDomainPeriods automatically
document.URL.indexOf(".co.") > 0 ? s.fpCookieDomainPeriods = "3" : s.fpCookieDomainPeriods = "2";
```
