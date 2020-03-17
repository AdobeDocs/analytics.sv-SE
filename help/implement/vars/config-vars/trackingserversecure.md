---
title: trackingServerSecure
description: Bestäm var bildbegäranden ska skickas på HTTPS-sidor.
translation-type: tm+mt
source-git-commit: 979a95ca749a3e21c4ddf48ba2d2a95672938a20

---


# trackingServerSecure

Adobe samlar in data på er webbplats genom att ta emot en bildförfrågan som genererats av besökaren. Variabeln avgör `trackingServerSecure` var en bildbegäran skickas via HTTPS. Det avgör också var besökarnas cookies lagras. Om den här variabeln inte är korrekt definierad kan din implementering uppleva dataförlust.

> [!IMPORTANT] Om du ändrar det här värdet får AppMeasurement att söka efter cookies på en annan plats. Unikt besökarantal kan tillfälligt öka i rapporteringen när besökarcookies anges på den nya platsen.

## SSL Tracking Server i Adobe Experience Platform Launch

[!UICONTROL SSL Tracking Server] är ett fält under [!UICONTROL General] dragspelet när du konfigurerar Adobe Analytics-tillägget.

1. Logga in på [launch.adobe.com](https://launch.adobe.com) med inloggningsuppgifterna för ditt AdobeID.
2. Klicka på önskad egenskap.
3. Gå till [!UICONTROL Extensions] fliken och klicka sedan på [!UICONTROL Configure] knappen under Adobe Analytics.
4. Expandera dragspelsfliken, som visar [!UICONTROL General] [!UICONTROL SSL Tracking Server] fältet.

Om fältet lämnas tomt blir standardvärdet i `trackingServer` variabeln.

## s.trackingServerSecure in AppMeasurement and Launch custom code editor

Variabeln `s.trackingServerSecure` är en sträng som innehåller platsen där bildbegäranden ska skickas. Det är nästan alltid en underdomän till din webbplats. Modern sekretesspraxis i webbläsare gör oftast cookies från tredje part otillförlitliga. Om variabeln är tom används värdet i `s.trackingServer` variabeln.

Värdet för den här variabeln är nästan alltid en förstahandsdomän, till exempel `data.example.com`. Mer information om cookie-processen från första [part finns i Experience Cloud](https://docs.adobe.com/content/help/en/core-services/interface/ec-cookies/cookies-first-party.html) i användarhandboken för bastjänsterna.

Den person som initialt konfigurerar cookie-implementeringen från första part definierar också den domän och underdomän som används. Exempel:

```js
s.trackingServerSecure = "data.example.com";
```

CNAME-poster pekar vanligtvis på en underdomän på `ssl.d1.sc.omtrdc.net`.
