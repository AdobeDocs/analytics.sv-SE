---
title: forceOffline
description: Ange onlinetillståndet för AppMeasurement manuellt.
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '138'
ht-degree: 1%

---


# forceOffline

Med den här `forceOffline()` metoden kan du åsidosätta det automatiskt identifierade tillståndet för AppMeasurement.

>[!IMPORTANT]
>
>Använd bara den här funktionen när den [`trackOffline`](../config-vars/trackoffline.md) är aktiverad. Om den här funktionen används utanför spårning offline kan data gå förlorade.

AppMeasurement identifierar automatiskt enhetens onlineläge. Du kan använda metoden för att tvinga AppMeasurement att behandla träffar som om enheten var offline. `forceOffline()` Den här metoden tar inga argument och returnerar inget värde. Dess enda syfte är att åsidosätta onlinetillståndet i AppMeasurement.

## Tvinga offlineläge i Adobe Experience Platform Launch

Det finns inget dedikerat fält i Launch som kan använda den här variabeln. Använd den anpassade kodredigeraren efter AppMeasurement-syntax.

## s.forceOffline() i den anpassade kodredigeraren AppMeasurement och Launch

Du kan anropa metoden var som helst i implementeringen när du har initierat Analytics-objektet. `s.forceOffline()`

```js
s.forceOffline();
```
