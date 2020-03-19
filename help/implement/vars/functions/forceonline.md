---
title: forceOnline
description: Ange onlinetillståndet för AppMeasurement manuellt.
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# forceOnline

Med den här `forceOnline()` metoden kan du åsidosätta det automatiskt identifierade tillståndet för AppMeasurement.

> [!IMPORTANT] Använd bara den här metoden när [`trackOffline`](../config-vars/trackoffline.md) är aktiverad. Om den här funktionen används utanför spårning offline kan data gå förlorade.

AppMeasurement identifierar automatiskt enhetens onlineläge. Du kan använda metoden för att tvinga AppMeasurement att behandla träffar som om enheten var online. `forceOnline()` Den här metoden tar inga argument och returnerar inget värde. Dess enda syfte är att åsidosätta onlinetillståndet i AppMeasurement.

## Force Online in Adobe Experience Platform Launch

Det finns inget dedikerat fält i Launch som kan använda den här variabeln. Använd den anpassade kodredigeraren efter AppMeasurement-syntax.

## s.forceOnline() i AppMeasurement och Launch, anpassad kodredigerare

Du kan anropa metoden var som helst i implementeringen efter att du har initierat Analytics-objektet. `s.forceOnline()`

```js
s.forceOnline();
```
