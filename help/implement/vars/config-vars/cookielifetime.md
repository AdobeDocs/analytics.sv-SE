---
title: cookieLifetime
description: Åsidosätt förfallodatumet för cookies som skapas i AppMeasurement.
feature: Variables
exl-id: 2cd64301-9f12-4e77-abae-af431e4b499d
source-git-commit: b3c74782ef6183fa63674b98e4c0fc39fc09441b
workflow-type: tm+mt
source-wordcount: '226'
ht-degree: 0%

---

# cookieLifetime

Cookies som anges av AppMeasurement har vanligtvis en förfallotid på två år. Använd `cookieLifetime` variabel som åsidosätter förfallodatumet för cookies som anges av AppMeasurement.

>[!NOTE]
>
>Denna variabel påverkar unika besökarantal och attribuering. Var försiktig när du anger den här variabeln.

## Cookie-livstid med taggar i Adobe Experience Platform

Cookie-livstid är en listruta under [!UICONTROL Cookies] när du konfigurerar Adobe Analytics-tillägget.

1. Logga in på [Användargränssnitt för datainsamling](https://experience.adobe.com/data-collection) med inloggningsuppgifterna för ditt AdobeID.
1. Klicka på önskad egenskap.
1. Gå till [!UICONTROL Extensions] klickar du på [!UICONTROL Configure] under Adobe Analytics.
1. Expandera [!UICONTROL Cookies] dragspelspanel, som visar [!UICONTROL Cookie Lifetime] listruta.

Den här listrutan innehåller följande värden:

* **Standard**: Cookie går ut efter 2 år.
* **Ingen**: AppMeasurement anger inte cookies.
* **Session**: Cookie förfaller i slutet av besökarens session.
* **Sekunder**: Cookie förfaller efter det angivna antalet sekunder. Om du till exempel anger den här listrutan som [!UICONTROL Seconds] och montera `86400` i det anpassade fältet tvingar cookies att upphöra efter exakt 24 timmar.

## s.cookieLifetime i AppMeasurement och anpassad kodredigerare

The `s.cookieLifetime` variabeln är en sträng som bestämmer förfallodatumet för cookies som anges av AppMeasurement.

* Om inställt på `SESSION`, upphör cookies som anges av AppMeasurement att gälla när webbläsarsessionen har slutförts.
* Om inställt på `NONE`, försöker AppMeasurement inte ange cookies.
* Om värdet är en heltalssträng upphör cookies som anges av AppMeasurement att gälla efter att det angivna antalet sekunder har förflutit.

```js
// Expire cookies after each session
s.cookieLifetime = "SESSION";

// Expire cookies after exactly 24 hours
s.cookieLifetime = "86400";
```
