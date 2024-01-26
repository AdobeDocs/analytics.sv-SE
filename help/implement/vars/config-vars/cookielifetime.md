---
title: cookieLifetime
description: Åsidosätt förfallodatumet för cookies som skapas i AppMeasurementet.
feature: Variables
exl-id: 2cd64301-9f12-4e77-abae-af431e4b499d
role: Admin, Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '257'
ht-degree: 0%

---

# cookieLifetime

Cookies som anges med AppMeasurement har vanligtvis en utgångstid på 2 år. Använd `cookieLifetime` variabel som åsidosätter förfallodatumet för cookies som anges av AppMeasurementet.

>[!NOTE]
>
>Denna variabel påverkar unika besökarantal och attribuering. Var försiktig när du anger den här variabeln.

## Cookie-livstid med Web SDK

Web SDK erbjuder ännu inte någon anpassning av livstiden för cookies som anges i den.

## Cookie-livstid med Adobe Analytics-tillägget

Cookie-livstid är en listruta under [!UICONTROL Cookies] när du konfigurerar Adobe Analytics-tillägget.

1. Logga in på [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) med inloggningsuppgifterna för ditt AdobeID.
1. Klicka på den önskade taggegenskapen.
1. Gå till [!UICONTROL Extensions] klickar du på **[!UICONTROL Configure]** under Adobe Analytics.
1. Expandera [!UICONTROL Cookies] dragspelspanel, som visar [!UICONTROL Cookie Lifetime] listruta.

Den här listrutan innehåller följande värden:

* **Standard**: Cookie går ut efter 2 år.
* **Ingen**: AppMeasurementet anger inte cookies.
* **Session**: Cookie förfaller i slutet av besökarens session.
* **Sekunder**: Cookie upphör att gälla efter det angivna antalet sekunder. Om du till exempel anger den här nedrullningsbara listan som [!UICONTROL Seconds] och montera `86400` i det anpassade fältet tvingar cookies att upphöra efter exakt 24 timmar.

## s.cookieLivstid i AppMeasurementet och den anpassade kodredigeraren för Analytics-tillägget

The `s.cookieLifetime` variabeln är en sträng som bestämmer förfallodatumet för cookies som anges av AppMeasurementet.

* Om inställt på `SESSION`, upphör cookies som anges med AppMeasurement att gälla när webbläsarsessionen har slutförts.
* Om inställt på `NONE`, försöker AppMeasurementet inte ange cookies.
* Om värdet är en heltalssträng upphör cookies som anges med AppMeasurement att gälla efter att det angivna antalet sekunder har förflutit.

```js
// Expire cookies after each session
s.cookieLifetime = "SESSION";

// Expire cookies after exactly 24 hours
s.cookieLifetime = "86400";
```
