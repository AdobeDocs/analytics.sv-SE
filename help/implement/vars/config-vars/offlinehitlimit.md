---
title: offlineHitLimit
description: Ange det maximala antalet träffar som ska köas för spårning offline.
feature: Appmeasurement Implementation
exl-id: de6478b3-b95f-4edc-8427-7b915a46b3ba
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '193'
ht-degree: 0%

---

# offlineHitLimit

Spårning offline är ett valfritt sätt att samla in data i Adobe Analytics. Om en besökare kopplar från Internet men fortsätter att surfa på webbplatsen, lagras träffarna i en offlinekö tills enheten återansluter till Internet. Spårning offline används oftast för mobilprogram.

Variabeln `offlineHitLimit` sätter ett tak för antalet träffar som enheten lagrar lokalt. Den här variabeln fungerar bara om [`trackOffline`](trackoffline.md) har aktiverats.

## Offline-träffgräns med Web SDK

SDK för webben stöder inte spårning offline.

## Offline-träffgräns med Adobe Analytics-tillägget

Det finns inget dedikerat fält i Adobe Analytics-tillägget som kan använda den här variabeln. Använd den anpassade kodredigeraren enligt AppMeasurement-syntax.

## s.offlineHitLimit i AppMeasurement och den anpassade kodredigeraren för Analytics-tillägget

Variabeln `s.offlineHitLimit` är ett heltal som representerar maximalt antal träffar som en enhet lagrar när de är offline. Om den här variabeln inte definieras blir standardvärdet `10`. Du kan ange det till valfritt heltalsvärde. När du anger höga värden bör du tänka på lokala lagringshöljen i besökarens webbläsare. Den här gränsen är vanligtvis 5-10 MB.

```js
s.offlineHitLimit = 100;
```
