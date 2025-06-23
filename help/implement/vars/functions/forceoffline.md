---
title: forceOffline
description: Ange onlinestatus för AppMeasurement manuellt.
feature: Appmeasurement Implementation
exl-id: 2e48bdf6-7de7-4976-86dd-ef3d558769c7
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '157'
ht-degree: 0%

---

# forceOffline

Med metoden `forceOffline()` kan du åsidosätta det automatiskt identifierade tillståndet för AppMeasurement.

>[!WARNING]
>
>Använd bara den här funktionen när [`trackOffline`](../config-vars/trackoffline.md) är aktiverad. Om den här funktionen används utanför spårning offline kan data gå förlorade.

AppMeasurement identifierar automatiskt enhetens onlineläge. Du kan använda metoden `forceOffline()` för att tvinga AppMeasurement att behandla träffar som om enheten var offline. Den här metoden tar inga argument och returnerar inget värde. Dess enda syfte är att åsidosätta onlinetillståndet i AppMeasurement.

## Tvinga offlineanvändning med SDK

SDK för webben stöder inte spårning offline.

## Tvinga offline med Adobe Analytics-tillägget

Det finns inget dedikerat fält i Adobe Analytics-tillägget som kan använda den här variabeln. Använd den anpassade kodredigeraren enligt AppMeasurement-syntax.

## s.forceOffline() i AppMeasurement och den anpassade kodredigeraren för Analytics-tillägget

Du kan anropa metoden `s.forceOffline()` var som helst i implementeringen efter att du har initierat Analytics-objektet.

```js
s.forceOffline();
```
