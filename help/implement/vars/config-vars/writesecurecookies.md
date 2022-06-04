---
title: writeSecureCookies
description: Tillåter AppMeasurement att ange cookies med attributet Secure.
feature: Variables
exl-id: 0e03d621-5770-4c25-981d-e4af1431ec69
source-git-commit: 3f4d8df911c076a5ea41e7295038c0625a4d7c85
workflow-type: tm+mt
source-wordcount: '232'
ht-degree: 0%

---

# writeSecureCookies

The `writeSecureCookies` variabeln gör att AppMeasurement kan anges [Säkra cookies](https://en.wikipedia.org/wiki/Secure_cookie) för Analytics. Den här inställningen gäller både cookies för besökar-ID som anges av AppMeasurement och cookies som du anger med `Util.CookieWrite()` -metod. AppMeasurement 2.18.0 eller senare krävs.

`writeSecureCookies` gäller endast cookies som anges av AppMeasurement JavaScript (`s_fid`, `s_cc` och `s_sq`). Cookies angivna av `https` svar (`s_vi` och `s_ecid`) kan ställas in på&quot;säker&quot; genom att kontakta Adobe kundtjänst.

Läs mer om cookies i Analytics [här](https://experienceleague.adobe.com/docs/core-services/interface/administration/ec-cookies/cookies-analytics.html).

>[!WARNING]
>
>Om du aktiverar `writeSecureCookies` kontrollerar du att allt innehåll på din webbplats hanteras säkert via HTTPS. AppMeasurement fungerar inte om den här variabeln är aktiverad och du har osäkert innehåll på sidan.

## Skriv säkra cookies med taggar i Adobe Experience Platform

[!UICONTROL Write secure cookies] är en kryssruta under [!UICONTROL Cookies] när du konfigurerar Adobe Analytics-tillägget.

1. Logga in på [Användargränssnitt för datainsamling](https://experience.adobe.com/data-collection) med inloggningsuppgifterna för ditt AdobeID.
2. Klicka på önskad egenskap.
3. Gå till [!UICONTROL Extensions] klickar du på [!UICONTROL Configure] under Adobe Analytics.
4. Expandera [!UICONTROL Cookies] dragspelspanel, som visar [!UICONTROL Write secure cookies] kryssrutan.

## s.writeSecureCookies i AppMeasurement och anpassad kodredigerare

The `s.writeSecureCookies` variabeln är en boolesk variabel som avgör om AppMeasurement anger attributet Secure när en cookie skapas. Standardvärdet är `false`. Ange variabeln till `true` om allt innehåll på din webbplats är säkert och du vill att cookies som anges av AppMeasurement ska ha attributet Secure.

```js
s.writeSecureCookies = true;
```
