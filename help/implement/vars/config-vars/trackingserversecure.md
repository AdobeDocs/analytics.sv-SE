---
title: trackingServerSecure
description: Bestäm var bildbegäranden ska skickas på HTTPS-sidor.
feature: Variables
exl-id: d5b112f9-f3f6-43ac-8ee5-d9ad8062e380
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '430'
ht-degree: 0%

---

# trackingServerSecure

Adobe samlar in data på er webbplats genom att ta emot en bildförfrågan som genererats av besökaren. The `trackingServerSecure` variabeln bestämmer var en bildbegäran skickas via HTTPS. Det avgör också var besökarnas cookies lagras. Om den här variabeln inte är korrekt definierad kan din implementering uppleva dataförlust.

>[!WARNING]
>
>Om du ändrar det här värdet får AppMeasurement att söka efter cookies på en annan plats. Unikt besökarantal kan tillfälligt öka i rapporteringen när besökarcookies anges på den nya platsen.

## Edge domain using the Web SDK extension

Web SDK använder [!UICONTROL Edge domain] för att hantera både spårningsserver och server för säker spårning. Du kan ställa in önskat [!UICONTROL Edge domain] när du konfigurerar Web SDK-tillägget.

1. Logga in på [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) med inloggningsuppgifterna för ditt AdobeID.
1. Klicka på den önskade taggegenskapen.
1. Gå till [!UICONTROL Extensions] klickar du på **[!UICONTROL Configure]** knapp under [!UICONTROL Adobe Experience Platform Web SDK].
1. Ange önskat **[!UICONTROL Edge domain]** textfält.

Se [Konfigurera Adobe Experience Platform Web SDK-tillägget](https://experienceleague.adobe.com/docs/experience-platform/edge/extension/web-sdk-extension-configuration.html) i Web SDK-dokumentationen om du vill ha mer information.

>[!TIP]
>
>Om organisationen går över till Web SDK från en AppMeasurement- eller Analytics-tilläggsimplementering kan det här fältet använda samma värde som i `trackingServerSecure` (eller `trackingServer`).

## Edge domain implementerar Web SDK manuellt

Konfigurera SDK med [`edgeDomain`](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html). Fältet är en sträng som avgör vilken domän som data ska skickas till.

```json
alloy("configure", {
  "edgeDomain": "data.example.com"
});
```

## SSL-spårningsserver som använder Adobe Analytics-tillägget

[!UICONTROL SSL Tracking Server] är ett fält under [!UICONTROL General] när du konfigurerar Adobe Analytics-tillägget.

1. Logga in på [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) med inloggningsuppgifterna för ditt AdobeID.
2. Klicka på den önskade taggegenskapen.
3. Gå till [!UICONTROL Extensions] klickar du på **[!UICONTROL Configure]** under Adobe Analytics.
4. Expandera [!UICONTROL General] dragspelspanel, som visar [!UICONTROL SSL Tracking Server] fält.

Om fältet lämnas tomt blir standardvärdet i [`trackingServer`](trackingserver.md) variabel.

## s.trackingServerSecure i AppMeasurement och den anpassade kodredigeraren i Analytics-tillägget

The `s.trackingServerSecure` variabeln är en sträng som innehåller platsen där bildbegäranden ska skickas. Det är nästan alltid en underdomän till din webbplats. Modern sekretesspraxis i webbläsare gör oftast cookies från tredje part otillförlitliga. Om variabeln är tom används värdet i `s.trackingServer` variabel.

Värdet för den här variabeln är nästan alltid en förstahandsdomän, som `data.example.com`. Se [Första parts-cookies i Experience Cloud](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-first-party.html) i användarhandboken för bastjänsterna för mer information om cookie-processen från första part.

Den person som initialt konfigurerar cookie-implementeringen från första part definierar också den domän och underdomän som används. Exempel:

```js
s.trackingServerSecure = "data.example.com";
```

CNAME-poster pekar vanligtvis på en underdomän på `data.adobedc.net`, `sc.adobedc.net` eller `2o7.net`.
