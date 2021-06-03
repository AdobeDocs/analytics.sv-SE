---
title: trackingServerSecure
description: Bestäm var bildbegäranden ska skickas på HTTPS-sidor.
exl-id: d5b112f9-f3f6-43ac-8ee5-d9ad8062e380
source-git-commit: f669af03a502d8a24cea3047b96ec7cba7c59e6f
workflow-type: tm+mt
source-wordcount: '276'
ht-degree: 2%

---

# trackingServerSecure

Adobe samlar in data på er webbplats genom att ta emot en bildförfrågan som genererats av besökaren. Variabeln `trackingServerSecure` avgör var en bildbegäran skickas via HTTPS. Det avgör också var besökarnas cookies lagras. Om den här variabeln inte är korrekt definierad kan din implementering uppleva dataförlust.

>[!IMPORTANT]
>
>Om du ändrar det här värdet får AppMeasurement att söka efter cookies på en annan plats. Unikt besökarantal kan tillfälligt öka i rapporteringen när besökarcookies anges på den nya platsen.

## SSL-spårningsserver i Adobe Experience Platform Launch

[!UICONTROL SSL Tracking Server] är ett fält under  [!UICONTROL General] dragspelet när du konfigurerar Adobe Analytics-tillägget.

1. Logga in på [launch.adobe.com](https://launch.adobe.com) med inloggningsuppgifterna för ditt Adobe-ID.
2. Klicka på önskad egenskap.
3. Gå till fliken [!UICONTROL Extensions] och klicka sedan på knappen [!UICONTROL Configure] under Adobe Analytics.
4. Expandera dragspelet [!UICONTROL General], som visar fältet [!UICONTROL SSL Tracking Server].

Om fältet lämnas tomt blir standardvärdet i variabeln [`trackingServer`](trackingserver.md).

## s.trackingServerSecure in AppMeasurement and Launch custom code editor

Variabeln `s.trackingServerSecure` är en sträng som innehåller platsen där bildbegäranden ska skickas. Det är nästan alltid en underdomän till din webbplats. Modern sekretesspraxis i webbläsare gör oftast cookies från tredje part otillförlitliga. Om variabeln är tom används värdet i variabeln `s.trackingServer`.

Värdet för den här variabeln är nästan alltid en förstapartsdomän, till exempel `data.example.com`. Se [cookies från första part i Experience Cloud](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-first-party.html) i användarhandboken för bastjänsterna för mer information om cookie-processen från första part.

Den person som initialt konfigurerar cookie-implementeringen från första part definierar också den domän och underdomän som används. Exempel:

```js
s.trackingServerSecure = "data.example.com";
```

CNAME-poster pekar vanligtvis på en underdomän på `data.adobedc.net`, `sc.adobedc.net` eller `2o7.net`.
