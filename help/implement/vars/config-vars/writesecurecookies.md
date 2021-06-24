---
title: writeSecureCookies
description: Tillåter AppMeasurement att ange cookies med attributet Secure.
exl-id: 0e03d621-5770-4c25-981d-e4af1431ec69
source-git-commit: b93cd06c2a8867f4848dc317e426b73dcfbb5dfd
workflow-type: tm+mt
source-wordcount: '228'
ht-degree: 1%

---

# writeSecureCookies

Variabeln `writeSecureCookies` gör att AppMeasurement kan ställa in [säkra cookies](https://en.wikipedia.org/wiki/Secure_cookie) för Analytics. Den här inställningen gäller både cookies för besökar-ID som anges av AppMeasurement och cookies som du anger med metoden `Util.CookieWrite()`. AppMeasurement 2.18.0 eller senare krävs.

`writeSecureCookies` gäller endast för cookies som anges av AppMeasurement JavaScript (`s_fid`och  `s_cc`   `s_sq`). Cookies som ställs in med `https`-svar (`s_vi` och `s_ecid`) kan ställas in på secure genom att kontakta Adobe kundtjänst.

Läs mer om Analytics-cookies [här](https://experienceleague.adobe.com/docs/core-services/interface/administration/ec-cookies/cookies-analytics.html).

>[!IMPORTANT]
>
>Om du aktiverar variabeln `writeSecureCookies` kontrollerar du att allt innehåll på platsen hanteras säkert via HTTPS. AppMeasurement fungerar inte om den här variabeln är aktiverad och du har osäkert innehåll på sidan.

## Skriv säkra cookies i Adobe Experience Platform Launch

[!UICONTROL Write secure cookies] är en kryssruta under  [!UICONTROL Cookies] dragspelet när du konfigurerar Adobe Analytics-tillägget.

1. Logga in på [launch.adobe.com](https://launch.adobe.com) med inloggningsuppgifterna för ditt Adobe-ID.
2. Klicka på önskad egenskap.
3. Gå till fliken [!UICONTROL Extensions] och klicka sedan på knappen [!UICONTROL Configure] under Adobe Analytics.
4. Expandera dragspelet [!UICONTROL Cookies], som visar kryssrutan [!UICONTROL Write secure cookies].

## s.writeSecureCookies i AppMeasurement and Launch custom code editor

Variabeln `s.writeSecureCookies` är en boolesk variabel som avgör om AppMeasurement anger attributet Secure när en cookie skapas. Dess standardvärde är `false`. Ange den här variabeln till `true` om allt innehåll på webbplatsen är säkert och du vill att cookies som anges av AppMeasurement ska ha attributet Secure.

```js
s.writeSecureCookies = true;
```
