---
title: cookieLifetime
description: Åsidosätt förfallodatumet för cookies som skapas i AppMeasurement.
exl-id: 2cd64301-9f12-4e77-abae-af431e4b499d
source-git-commit: 3986084eaab81842b6ea0dbabc7bdb78e39f887a
workflow-type: tm+mt
source-wordcount: '224'
ht-degree: 0%

---

# cookieLifetime

Cookies som anges av AppMeasurement har vanligtvis en förfallotid på två år. Använd variabeln `cookieLifetime` för att åsidosätta förfallodatumet för cookies som anges av AppMeasurement.

>[!NOTE]
>
>Denna variabel påverkar unika besökarantal och attribuering. Var försiktig när du anger den här variabeln.

## Cookie-livstid i Adobe Experience Platform-taggar

Cookie-livstid är en listruta under dragspelet [!UICONTROL Cookies] när du konfigurerar Adobe Analytics-tillägget.

1. Gå till `experience.adobe.com` och logga in när du uppmanas till det.
1. Välj [!UICONTROL Launch / Data Collection].
1. Klicka på [!UICONTROL Go to Launch / Data Collection] och välj sedan [!UICONTROL Tags].
1. Klicka på önskad egenskap.
1. Gå till fliken [!UICONTROL Extensions] och klicka sedan på knappen [!UICONTROL Configure] under Adobe Analytics.
1. Expandera dragspelsfliken [!UICONTROL Cookies] som visar listrutan [!UICONTROL Cookie Lifetime].

Den här listrutan innehåller följande värden:

* **Standard**: Cookie går ut efter 2 år.
* **Ingen**: AppMeasurement anger inte cookies.
* **Session**: Cookie förfaller i slutet av besökarens session.
* **Sekunder**: Cookie förfaller efter det angivna antalet sekunder. Om du till exempel ställer in den här listrutan på [!UICONTROL Seconds] och placerar `86400` i det anpassade fältet tvingas cookies att upphöra efter exakt 24 timmar.

## s.cookieLifetime i AppMeasurement and Data Collection custom code editor

Variabeln `s.cookieLifetime` är en sträng som bestämmer förfallodatumet för cookies som anges av AppMeasurement.

* Om värdet är `SESSION` upphör cookies som anges av AppMeasurement att gälla när webbläsarsessionen har slutförts.
* Om värdet är `NONE` försöker AppMeasurement inte ange cookies.
* Om värdet är en heltalssträng upphör cookies som anges av AppMeasurement att gälla efter att det angivna antalet sekunder har förflutit.

```js
// Expire cookies after each session
s.cookieLifetime = "SESSION";

// Expire cookies after exactly 24 hours
s.cookieLifetime = "86400";
```
