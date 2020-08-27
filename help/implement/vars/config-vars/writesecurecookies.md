---
title: writeSecureCookies
description: Tillåter AppMeasurement att ange cookies med attributet Secure.
translation-type: tm+mt
source-git-commit: defb701d01747685a421b89a553f47efe40f1432
workflow-type: tm+mt
source-wordcount: '190'
ht-degree: 2%

---


# writeSecureCookies

Variabeln gör att AppMeasurement kan ange `writeSecureCookies` säkra cookies [](https://en.wikipedia.org/wiki/Secure_cookie) för Analytics. Den här inställningen gäller både cookies för besökar-ID som anges av AppMeasurement och cookies som du anger med `Util.CookieWrite()` metoden. AppMeasurement 2.18.0 eller senare krävs.

>[!IMPORTANT]
>
>Om du aktiverar `writeSecureCookies` variabeln måste du se till att allt innehåll på webbplatsen hanteras säkert via HTTPS. AppMeasurement fungerar inte om den här variabeln är aktiverad och du har osäkert innehåll på sidan.

## Skriv säkra cookies i Adobe Experience Platform Launch

[!UICONTROL Write secure cookies] är en kryssruta under [!UICONTROL Cookies] dragspelet när du konfigurerar Adobe Analytics-tillägget.

1. Logga in på [launch.adobe.com](https://launch.adobe.com) med inloggningsuppgifterna för ditt AdobeID.
2. Klicka på önskad egenskap.
3. Gå till [!UICONTROL Extensions] fliken och klicka sedan på [!UICONTROL Configure] knappen under Adobe Analytics.
4. Expandera dragspelsfliken så att [!UICONTROL Cookies] kryssrutan visas [!UICONTROL Write secure cookies] .

## s.writeSecureCookies i AppMeasurement and Launch custom code editor

Variabeln är en boolesk variabel som avgör om AppMeasurement anger attributet Secure när en cookie skapas. `s.writeSecureCookies` Dess standardvärde är `false`. Ange variabeln till `true` om allt innehåll på webbplatsen är säkert och du vill att cookies som anges av AppMeasurement ska ha attributet Secure.

```js
s.writeSecureCookies = true;
```
