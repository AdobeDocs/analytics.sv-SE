---
title: clearVars
description: Tar bort följande värden från instansobjektet. Den här funktionen tar bort elementen (anger dem som "undefined").
translation-type: tm+mt
source-git-commit: d1db8da65faac1bf09fa2a290a2645092b542a35

---


# clearVars

Vissa implementeringar, till exempel på enkelsidiga program, kräver flera träffar som skickas på samma sidinläsning. Använd `clearVars` metoden för att rensa variabelvärden så att de inte kvarstår för efterföljande träffar.

Den här metoden tar inga argument och returnerar inget värde. Dess enda syfte är att rensa variabelvärden från förekomstobjektet. Den här metoden ställer in följande element till `undefined`:

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

## Rensa variabler i Adobe Experience Platform Launch

Ange åtgärden Rensa variabler när du konfigurerar en regel.

1. Logga in på [launch.adobe.com](https://launch.adobe.com) med inloggningsuppgifterna för ditt AdobeID.
2. Klicka på önskad egenskap.
3. Gå till [!UICONTROL Rules] fliken och klicka sedan på önskad regel (eller skapa en regel).
4. Klicka på ikonen + [!UICONTROL Actions]under
5. Ställ in listrutan till Adobe Analytics och [!UICONTROL Extension] till [!UICONTROL Action Type] [!UICONTROL Clear Variables].

## s.clearVars() i AppMeasurement och Launch, anpassad kodredigerare

Du kan anropa metoden var som helst i implementeringen efter att du har initierat objektinstansen i Analytics. `s.clearVars()`

```js
s.clearVars();
```
