---
title: clearVars
description: Tar bort följande värden från instansobjektet. Den här funktionen tar bort elementen (anger dem som "undefined").
exl-id: 8ecb2b2d-7b66-4232-b0ea-b8c6cdcc1515
source-git-commit: 1a49c2a6d90fc670bd0646d6d40738a87b74b8eb
workflow-type: tm+mt
source-wordcount: '165'
ht-degree: 1%

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

## Rensa variabler med taggar i Adobe Experience Platform

Ange åtgärden Rensa variabler när du konfigurerar en regel.

1. Logga in på [användargränssnittet för datainsamling](https://experience.adobe.com/data-collection) med inloggningsuppgifterna för ditt Adobe-ID.
2. Klicka på önskad egenskap.
3. Gå till fliken [!UICONTROL Rules] och klicka sedan på önskad regel (eller skapa en regel).
4. Klicka på plustecknet under [!UICONTROL Actions]
5. Ange listrutan [!UICONTROL Extension] till Adobe Analytics och [!UICONTROL Action Type] till [!UICONTROL Clear Variables].

## s.clearVars() i AppMeasurement och anpassad kodredigerare

Du kan anropa metoden `s.clearVars()` var som helst i implementeringen efter att du har initierat objektinstansen för Analytics.

```js
s.clearVars();
```
