---
title: cookieLifetime
description: Åsidosätt förfallodatumet för cookies som skapas i AppMeasurement.
translation-type: tm+mt
source-git-commit: 979a95ca749a3e21c4ddf48ba2d2a95672938a20

---


# cookieLifetime

Cookies som anges av AppMeasurement har vanligtvis en förfallotid på två år. Använd variabeln för att åsidosätta förfallodatumet för cookies som anges av AppMeasurement. `cookieLifetime`

> [!NOTE] Denna variabel påverkar unika besökarantal och attribuering. Var försiktig när du anger den här variabeln.

## Cookie-livstid i Adobe Experience Platform Launch

Cookie-livstid är en listruta under [!UICONTROL Cookies] dragspelsfliken när du konfigurerar Adobe Analytics-tillägget.

1. Logga in på [launch.adobe.com](https://launch.adobe.com) med inloggningsuppgifterna för ditt AdobeID.
2. Klicka på önskad egenskap.
3. Gå till [!UICONTROL Extensions] fliken och klicka sedan på [!UICONTROL Configure] knappen under Adobe Analytics.
4. Expandera dragspelsfliken, som visar [!UICONTROL Cookies] [!UICONTROL Cookie Lifetime] listrutan.

Den här listrutan innehåller följande värden:

* **Standard**: Cookie går ut efter 2 år.
* **Ingen**: AppMeasurement anger inte cookies.
* **Session**: Cookie förfaller i slutet av besökarens session.
* **Sekunder**: Cookie förfaller efter det angivna antalet sekunder. Om du till exempel ställer in den här listrutan på [!UICONTROL Seconds] och placerar den `86400` i det anpassade fältet tvingas cookies att upphöra efter exakt 24 timmar.

## s.cookieLifetime i AppMeasurement and Launch custom code editor

Variabeln är en sträng som bestämmer förfallodatumet för cookies som anges av AppMeasurement. `s.cookieLifetime`

* Om detta anges `SESSION`upphör cookies som anges av AppMeasurement att gälla när webbläsarsessionen har slutförts.
* Om det anges `NONE`försöker AppMeasurement inte att ange cookies.
* Om värdet är en heltalssträng upphör cookies som anges av AppMeasurement att gälla efter att det angivna antalet sekunder har förflutit.

```js
// Expire cookies after each session
s.cookieLifetime = "SESSION";

// Expire cookies after exactly 24 hours
s.cookieLifetime = "86400";

