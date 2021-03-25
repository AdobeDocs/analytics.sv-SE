---
title: clearVars
description: Rensa variabelvärden från spårningsobjektet.
translation-type: tm+mt
source-git-commit: f19be69832b0a2b723d825472e0eec1e44f89440
workflow-type: tm+mt
source-wordcount: '151'
ht-degree: 2%

---


# clearVars

Vissa implementeringar, till exempel på enkelsidiga program, kräver flera träffar som skickas på samma sidinläsning. Använd metoden `clearVars()` för att rensa variabelvärden så att de inte kvarstår för efterföljande träffar.

Den här metoden tar inga argument och returnerar inget värde. Dess enda syfte är att rensa variabelvärden från förekomstobjektet. Den här metoden ställer in följande element på `undefined`:

* `prop1` - `prop75`
* `eVar` -  `eVar250`
* `hier1` -  `hier5`
* `list1` -  `list3`
* `events`
* `products`
* `channel`
* `purchaseID`
* `transactionID`
* `state`
* `zip`
* `campaign`

## Rensa variabler i Adobe Experience Platform Launch

Ange åtgärden Rensa variabler när du konfigurerar en regel.

1. Logga in på [launch.adobe.com](https://launch.adobe.com) med inloggningsuppgifterna för ditt Adobe-ID.
2. Klicka på önskad egenskap.
3. Gå till fliken [!UICONTROL Rules] och klicka sedan på önskad regel (eller skapa en regel).
4. Klicka på plustecknet under [!UICONTROL Actions]
5. Ange listrutan [!UICONTROL Extension] till Adobe Analytics och [!UICONTROL Action Type] till [!UICONTROL Clear Variables].

## s.clearVars() i AppMeasurement och Launch, anpassad kodredigerare

Du kan anropa metoden `s.clearVars()` var som helst i implementeringen efter att du har initierat objektinstansen för Analytics.

```js
s.clearVars();
```
