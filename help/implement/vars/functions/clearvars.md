---
title: clearVars
description: Rensa värden från instansobjektet.
feature: Appmeasurement Implementation
exl-id: 8ecb2b2d-7b66-4232-b0ea-b8c6cdcc1515
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '179'
ht-degree: 0%

---

# clearVars

Vissa implementeringar, till exempel på enkelsidiga program, kräver flera träffar som skickas på samma sidinläsning. Använd metoden `clearVars()` för att rensa variabelvärden så att de inte kvarstår för efterföljande träffar.

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

När du skickar data till Adobe via Web SDK rensas alla XDM-data automatiskt.

## Rensa variabler med Adobe Analytics-tillägget

Ange åtgärden Rensa variabler när du konfigurerar en regel.

1. Logga in på [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) med dina inloggningsuppgifter för AdobeID.
2. Klicka på den önskade taggegenskapen.
3. Gå till fliken [!UICONTROL Rules] och klicka sedan på önskad regel (eller skapa en regel).
4. Klicka på plustecknet under [!UICONTROL Actions]
5. Ange Adobe Analytics i listrutan [!UICONTROL Extension] och [!UICONTROL Action Type] till [!UICONTROL Clear Variables].

## s.clearVars() i AppMeasurement och den anpassade kodredigeraren för Analytics-tillägget

Du kan anropa metoden `s.clearVars()` var som helst i implementeringen efter att du har initierat objektinstansen för Analytics.

```js
s.clearVars();
```
