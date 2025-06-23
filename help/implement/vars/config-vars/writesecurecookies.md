---
title: writeSecureCookies
description: Låter AppMeasurement ange cookies med attributet Secure.
feature: Appmeasurement Implementation
exl-id: 0e03d621-5770-4c25-981d-e4af1431ec69
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '253'
ht-degree: 0%

---

# writeSecureCookies

Variabeln `writeSecureCookies` gör att AppMeasurement kan ställa in [säkra cookies](https://en.wikipedia.org/wiki/Secure_cookie) för Analytics. Den här inställningen gäller både cookies för besökar-ID som har angetts av AppMeasurement och cookies som du har angett med metoden `Util.CookieWrite()`. AppMeasurement 2.18.0 eller senare krävs.

`writeSecureCookies` gäller endast cookies som har angetts av AppMeasurement JavaScript (`s_fid`, `s_cc` och `s_sq`). Cookies som anges av `https`-svar (`s_vi` och `s_ecid`) kan ställas in på &quot;secure&quot; genom att kontakta Adobe kundtjänst.

Läs mer om analyscookies [här](https://experienceleague.adobe.com/docs/core-services/interface/administration/ec-cookies/cookies-analytics.html).

>[!WARNING]
>
>Om du aktiverar variabeln `writeSecureCookies` måste du se till att allt innehåll på webbplatsen hanteras säkert via HTTPS. Datainsamlingen fungerar inte korrekt om variabeln är aktiverad och du har osäkert innehåll på sidan.

## Använd säkra cookies med SDK på webben

Om webbplatsen använder HTTPS-protokoll anges attributet Secure för alla cookies som anges av Web SDK.

## Skriv säkra cookies med Adobe Analytics-tillägget

[!UICONTROL Write secure cookies] är en kryssruta under dragspelet [!UICONTROL Cookies] när du konfigurerar Adobe Analytics-tillägget.

1. Logga in på [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) med dina inloggningsuppgifter för AdobeID.
2. Klicka på den önskade taggegenskapen.
3. Gå till fliken [!UICONTROL Extensions] och klicka sedan på knappen **[!UICONTROL Configure]** under Adobe Analytics.
4. Expandera dragspelsfliken [!UICONTROL Cookies], som visar kryssrutan [!UICONTROL Write secure cookies].

## s.writeSecureCookies i AppMeasurement och den anpassade kodredigeraren för Analytics-tillägget

Variabeln `s.writeSecureCookies` är en boolesk variabel som avgör om AppMeasurement ställer in attributet Secure när en cookie skapas. Dess standardvärde är `false`. Ange den här variabeln till `true` om allt innehåll på din webbplats är säkert och du vill att cookies som anges av AppMeasurement ska ha attributet Secure.

```js
s.writeSecureCookies = true;
```
