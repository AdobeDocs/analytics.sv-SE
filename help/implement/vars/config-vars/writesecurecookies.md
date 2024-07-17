---
title: writeSecureCookies
description: Tillåter AppMeasurementet att ange cookies med attributet Secure.
feature: Variables
exl-id: 0e03d621-5770-4c25-981d-e4af1431ec69
role: Admin, Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '253'
ht-degree: 0%

---

# writeSecureCookies

Variabeln `writeSecureCookies` gör att AppMeasurementet kan ange [säkra cookies](https://en.wikipedia.org/wiki/Secure_cookie) för Analytics. Den här inställningen gäller både cookies för besökar-ID som anges av AppMeasurementet och cookies som du anger med metoden `Util.CookieWrite()`. AppMeasurement 2.18.0 eller senare krävs.

`writeSecureCookies` gäller endast cookies som anges av AppMeasurementet JavaScript (`s_fid`, `s_cc` och `s_sq`). Cookies som anges av `https`-svar (`s_vi` och `s_ecid`) kan anges till &quot;secure&quot; genom att kontakta Adobe kundtjänst.

Läs mer om analyscookies [här](https://experienceleague.adobe.com/docs/core-services/interface/administration/ec-cookies/cookies-analytics.html).

>[!WARNING]
>
>Om du aktiverar variabeln `writeSecureCookies` måste du se till att allt innehåll på webbplatsen hanteras säkert via HTTPS. Datainsamlingen fungerar inte korrekt om variabeln är aktiverad och du har osäkert innehåll på sidan.

## Använd säkra cookies med Web SDK

Om webbplatsen använder HTTPS-protokoll anges attributet Secure för alla cookies som anges av Web SDK.

## Skriv säkra cookies med Adobe Analytics-tillägget

[!UICONTROL Write secure cookies] är en kryssruta under dragspelet [!UICONTROL Cookies] när du konfigurerar Adobe Analytics-tillägget.

1. Logga in på [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) med dina inloggningsuppgifter för AdobeID.
2. Klicka på den önskade taggegenskapen.
3. Gå till fliken [!UICONTROL Extensions] och klicka sedan på knappen **[!UICONTROL Configure]** under Adobe Analytics.
4. Expandera dragspelsfliken [!UICONTROL Cookies], som visar kryssrutan [!UICONTROL Write secure cookies].

## s.writeSecureCookies i AppMeasurementet och den anpassade kodredigeraren för Analytics-tillägget

Variabeln `s.writeSecureCookies` är en boolesk variabel som avgör om AppMeasurementet ställer in attributet Secure när en cookie skapas. Dess standardvärde är `false`. Ange den här variabeln till `true` om allt innehåll på din webbplats är säkert och du vill att cookies som anges av AppMeasurementet ska ha attributet Secure.

```js
s.writeSecureCookies = true;
```
