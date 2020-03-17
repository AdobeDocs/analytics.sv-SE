---
title: offlineHitLimit
description: Ange det maximala antalet träffar som ska köas för spårning offline.
translation-type: tm+mt
source-git-commit: 4a6cfa479559a644588613bd127c5b45ee8787e6

---


# offlineHitLimit

Spårning offline är ett valfritt sätt att samla in data i Adobe Analytics. Om en besökare kopplar från Internet men fortsätter att surfa på webbplatsen, lagras träffarna i en offlinekö tills enheten återansluter till Internet. Spårning offline används oftast för mobilprogram.

Variabeln sätter en övre gräns för hur många träffar enheten lagrar lokalt. `offlineHitLimit` Den här variabeln fungerar bara om `trackOffline` är `true`.

## Offline Hit Limit i Adobe Experience Platform Launch

Det finns inget dedikerat fält i Launch som kan använda den här variabeln. Använd den anpassade kodredigeraren efter AppMeasurement-syntax.

## s.offlineHitLimit i AppMeasurement and Launch custom code editor

Variabeln `s.offlineHitLimit` är ett heltal som representerar maximalt antal träffar som en enhet lagrar när de är offline. Om variabeln inte är definierad finns det ingen gräns för hur många träffar en enhet lagrar när den är offline.

```js
s.offlineHitLimit = 100;
```
