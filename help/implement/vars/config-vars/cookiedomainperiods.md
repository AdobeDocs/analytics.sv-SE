---
title: cookieDomainPeriods
description: Hjälp AppMeasurement att förstå vilken domän cookies ska lagras i om din domän har en punkt i suffixet.
translation-type: tm+mt
source-git-commit: 04b97e93a95691132680d4da197dc62eb2b9fdd1

---


# cookieDomainPeriods

AppMeasurement bestämmer cookie-platsen genom att titta på domänen och domänsuffixet. För domäner som `example.com`AppMeasurement anges cookies på rätt plats. För andra domäner som `example.co.uk`AppMeasurement kan dock cookies av misstag anges `co.uk`. De flesta webbläsare avvisar cookies som angetts i den här ogiltiga domänen, vilket orsakar problem med besökaridentifiering.

Variabeln hjälper AppMeasurement att avgöra var Analytics-cookies anges genom att anropa att domänsuffixet har en extra period. `cookieDomainPeriods` Den här variabeln tillåter AppMeasurement att anpassa den extra perioden i domänsuffixet och ange cookies på rätt plats.

* För domäner som `example.com` eller `www.example.com`behöver variabeln inte anges. Om det behövs kan du ange variabeln till `"2"`.
* För domäner som `example.co.uk` eller `www.example.co.jp`anger du den här variabeln som `"3"`.

> [!IMPORTANT] Ta inte underdomäner med i beräkningen för den här variabeln. Ange till exempel inte `cookieDomainPeriods` på exempel-URL `store.toys.example.com`. AppMeasurement identifierar som standard att cookies ska lagras på `example.com`, även på URL:er med många underdomäner.

## Domänperioder i Adobe Experience Platform Launch

Domänperioder är ett fält under [!UICONTROL Cookies] dragspelet när Adobe Analytics-tillägget konfigureras.

1. Logga in på [launch.adobe.com](https://launch.adobe.com) med inloggningsuppgifterna för ditt AdobeID.
2. Klicka på önskad egenskap.
3. Gå till [!UICONTROL Extensions] fliken och klicka sedan på [!UICONTROL Configure] knappen under Adobe Analytics.
4. Expandera dragspelsfliken, som visar [!UICONTROL Cookies] [!UICONTROL Domain Periods] fältet.

Ange det här fältet som `3` endast för domäner som innehåller en punkt i suffixet. Annars kan fältet lämnas tomt.

## s.cookieDomainPeriods i AppMeasurement and Launch custom code editor

Variabeln `cookieDomainPeriods` är en sträng som vanligtvis är inställd på `"3"`endast i domäner som innehåller en punkt i suffixet. Dess standardvärde är `"2"`, vilket ger plats för de flesta domäner.

```js
// Manually set cookieDomainPeriods for domains with a period in its suffix, such as www.example.co.uk
s.cookieDomainPeriods = "3";

// Detect if a URL has a domain suffix with an extra period, and set s.cookieDomainPeriods automatically
document.URL.indexOf(".co.") > 0 ? s.cookieDomainPeriods = "3" : s.cookieDomainPeriods = "2";
```
