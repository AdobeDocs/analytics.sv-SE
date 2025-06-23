---
title: cookieLifetime
description: Åsidosätt förfallodatumet för cookies som skapas i AppMeasurement.
feature: Appmeasurement Implementation
exl-id: 2cd64301-9f12-4e77-abae-af431e4b499d
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '257'
ht-degree: 0%

---

# cookieLifetime

Cookies som anges av AppMeasurement har vanligtvis en giltighetstid på två år. Använd variabeln `cookieLifetime` för att åsidosätta förfallodatumet för cookies som angetts av AppMeasurement.

>[!NOTE]
>
>Denna variabel påverkar unika besökarantal och attribuering. Var försiktig när du anger den här variabeln.

## Cookie-livstid med SDK på webben

Web SDK erbjuder ännu inte någon anpassning efter livstiden för cookies som den anger.

## Cookie-livstid med Adobe Analytics-tillägget

Cookie-livstid är en nedrullningsbar lista under dragspelsfliken [!UICONTROL Cookies] när du konfigurerar Adobe Analytics-tillägget.

1. Logga in på [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) med dina inloggningsuppgifter för AdobeID.
1. Klicka på den önskade taggegenskapen.
1. Gå till fliken [!UICONTROL Extensions] och klicka sedan på knappen **[!UICONTROL Configure]** under Adobe Analytics.
1. Expandera dragspelsfliken [!UICONTROL Cookies] som visar listrutan [!UICONTROL Cookie Lifetime].

Den här listrutan innehåller följande värden:

* **Standard**: Cookie upphör att gälla efter 2 år.
* **Ingen**: AppMeasurement anger inte cookies.
* **Session**: Cookie förfaller i slutet av besökarsessionen.
* **Sekunder**: Cookie förfaller efter det angivna antalet sekunder. Om du till exempel ställer in den här nedrullningsbara listan på [!UICONTROL Seconds] och placerar `86400` i det anpassade fältet tvingas cookies att förfalla efter exakt 24 timmar.

## s.cookieLifetime i AppMeasurement och den anpassade kodredigeraren för Analytics-tillägget

Variabeln `s.cookieLifetime` är en sträng som bestämmer förfallodatumet för cookies som anges av AppMeasurement.

* Om värdet är `SESSION` upphör cookies som angetts av AppMeasurement att gälla när webbläsarsessionen har slutförts.
* Om värdet är `NONE` försöker AppMeasurement inte ange cookies.
* Om den anges som en heltalssträng upphör cookies som anges av AppMeasurement att gälla efter det angivna antalet sekunder.

```js
// Expire cookies after each session
s.cookieLifetime = "SESSION";

// Expire cookies after exactly 24 hours
s.cookieLifetime = "86400";
```
