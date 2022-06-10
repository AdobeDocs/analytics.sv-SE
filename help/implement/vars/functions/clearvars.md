---
title: clearVars
description: Tar bort följande värden från instansobjektet. Den här funktionen tar bort elementen (anger dem som "undefined").
feature: Variables
exl-id: 8ecb2b2d-7b66-4232-b0ea-b8c6cdcc1515
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '191'
ht-degree: 1%

---

# clearVars

Vissa implementeringar, till exempel på enkelsidiga program, kräver flera träffar som skickas på samma sidinläsning. Använd `clearVars()` metod för att rensa variabelvärden så att de inte kvarstår för efterföljande träffar.

Den här metoden tar inga argument och returnerar inget värde. Dess enda syfte är att rensa variabelvärden från förekomstobjektet. Den här metoden ställer in följande element på `undefined`:

* `prop1` - `prop75`
* `eVar` - `eVar250`
* `hier1` - `hier5`
* `list1` - `list3`
* `events`
* `products`
* `channel`
* `purchaseID`
* `transactionID`
* `state`
* `zip`
* `campaign`

## Rensa variabler med Web SDK

När du skickar data till Adobe med Web SDK rensas alla XDM-data automatiskt.

## Rensa variabler med Adobe Analytics-tillägget

Ange åtgärden Rensa variabler när du konfigurerar en regel.

1. Logga in på [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) med inloggningsuppgifterna för ditt AdobeID.
2. Klicka på den önskade taggegenskapen.
3. Gå till [!UICONTROL Rules] och sedan klicka på önskad regel (eller skapa en regel).
4. Under [!UICONTROL Actions]klickar du på plustecknet (+)
5. Ange [!UICONTROL Extension] till Adobe Analytics och [!UICONTROL Action Type] till [!UICONTROL Clear Variables].

## s.clearVars() i AppMeasurement och den anpassade kodredigeraren i Analytics-tillägget

Du kan ringa `s.clearVars()` var som helst i implementeringen efter att du har initierat objektinstansen i Analytics.

```js
s.clearVars();
```
