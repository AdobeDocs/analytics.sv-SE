---
title: trackingServerSecure
description: Bestäm var bildbegäranden ska skickas på HTTPS-sidor.
feature: Appmeasurement Implementation
exl-id: d5b112f9-f3f6-43ac-8ee5-d9ad8062e380
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '408'
ht-degree: 0%

---

# trackingServerSecure

Adobe samlar in data på er webbplats genom att ta emot en bildförfrågan som genererats av besökaren. Variabeln `trackingServerSecure` avgör var en bildbegäran skickas via HTTPS. Det avgör också var besökarnas cookies lagras. Om den här variabeln inte är korrekt definierad kan din implementering uppleva dataförlust.

>[!WARNING]
>
>Om du ändrar det här värdet söker AppMeasurement efter cookies på en annan plats. Unikt besökarantal kan tillfälligt öka i rapporteringen när besökarcookies anges på den nya platsen.

## Edge domain using the Web SDK extension

SDK använder [!UICONTROL Edge domain] för att hantera både spårningsservern och den säkra spårningsservern. Du kan ange det önskade [!UICONTROL Edge domain]-värdet när du konfigurerar Web SDK-tillägget.

1. Logga in på [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) med dina inloggningsuppgifter för AdobeID.
1. Klicka på den önskade taggegenskapen.
1. Gå till fliken [!UICONTROL Extensions] och klicka sedan på knappen **[!UICONTROL Configure]** under [!UICONTROL Adobe Experience Platform Web SDK].
1. Ange det önskade textfältet **[!UICONTROL Edge domain]**.

Mer information finns i [Konfigurera Adobe Experience Platform Web SDK-tillägget](https://experienceleague.adobe.com/docs/experience-platform/edge/extension/web-sdk-extension-configuration.html?lang=sv-SE) i dokumentationen för Web SDK.

>[!TIP]
>
>Om din organisation går över till Web SDK från en AppMeasurement- eller Analytics-tilläggsimplementering kan det här fältet använda samma värde som finns i `trackingServerSecure` (eller `trackingServer`).

## Edge domain implementerar Web SDK manuellt

Konfigurera SDK med [`edgeDomain`](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html?lang=sv-SE). Fältet är en sträng som avgör vilken domän som data ska skickas till.

```json
alloy("configure", {
  "edgeDomain": "data.example.com"
});
```

## SSL-spårningsserver som använder Adobe Analytics-tillägget

[!UICONTROL SSL Tracking Server] är ett fält under dragspelet [!UICONTROL General] när Adobe Analytics-tillägget konfigureras.

1. Logga in på [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) med dina inloggningsuppgifter för AdobeID.
2. Klicka på den önskade taggegenskapen.
3. Gå till fliken [!UICONTROL Extensions] och klicka sedan på knappen **[!UICONTROL Configure]** under Adobe Analytics.
4. Expandera dragspelsfliken [!UICONTROL General] som visar fältet [!UICONTROL SSL Tracking Server].

Om fältet lämnas tomt blir standardvärdet i variabeln [`trackingServer`](trackingserver.md).

## s.trackingServerSecure i AppMeasurement och den anpassade kodredigeraren för Analytics-tillägget

Variabeln `s.trackingServerSecure` är en sträng som innehåller platsen där bildbegäranden ska skickas. Det är nästan alltid en underdomän till din webbplats. Modern sekretesspraxis i webbläsare gör oftast cookies från tredje part otillförlitliga. Om variabeln är tom används värdet i variabeln `s.trackingServer`.

Värdet för den här variabeln är nästan alltid en förstapartsdomän, till exempel `data.example.com`. Mer information om cookie-processen finns i [Första part-cookies i Experience Cloud](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-first-party.html?lang=sv-SE) i användarhandboken för bastjänsterna.

Den person som initialt konfigurerar cookie-implementeringen från första part definierar också den domän och underdomän som används. Exempel:

```js
s.trackingServerSecure = "data.example.com";
```

CNAME-poster pekar vanligtvis på en underdomän på `data.adobedc.net`, `sc.adobedc.net` eller `2o7.net`.
