---
title: forceOnline
description: Ange onlinestatus för AppMeasurement manuellt.
feature: Appmeasurement Implementation
exl-id: 318408bf-bec6-49aa-a762-9d2eebab233e
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '157'
ht-degree: 0%

---

# forceOnline

Med metoden `forceOnline()` kan du åsidosätta det automatiskt identifierade tillståndet för AppMeasurement.

>[!WARNING]
>
>Använd bara den här metoden när [`trackOffline`](../config-vars/trackoffline.md) är aktiverad. Om den här funktionen används utanför spårning offline kan data gå förlorade.

AppMeasurement identifierar automatiskt enhetens onlineläge. Du kan använda metoden `forceOnline()` för att tvinga AppMeasurement att behandla träffar som om enheten var online. Den här metoden tar inga argument och returnerar inget värde. Dess enda syfte är att åsidosätta onlinetillståndet i AppMeasurement.

## Tvinga online med Web SDK

SDK för webben stöder inte spårning offline.

## Tvinga online med Adobe Analytics-tillägget

Det finns inget dedikerat fält i Adobe Analytics-tillägget som kan använda den här variabeln. Använd den anpassade kodredigeraren enligt AppMeasurement-syntax.

## s.forceOnline() i AppMeasurement och den anpassade kodredigeraren för Analytics-tillägget

Du kan anropa metoden `s.forceOnline()` var som helst i implementeringen efter att du har initierat Analytics-objektet.

```js
s.forceOnline();
```
