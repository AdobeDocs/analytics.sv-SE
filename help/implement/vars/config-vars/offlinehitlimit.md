---
title: offlineHitLimit
description: Ange det maximala antalet träffar som ska köas för spårning offline.
feature: Variables
exl-id: de6478b3-b95f-4edc-8427-7b915a46b3ba
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '160'
ht-degree: 1%

---

# offlineHitLimit

Spårning offline är ett valfritt sätt att samla in data i Adobe Analytics. Om en besökare kopplar från Internet men fortsätter att surfa på webbplatsen, lagras träffarna i en offlinekö tills enheten återansluter till Internet. Spårning offline används oftast för mobilprogram.

The `offlineHitLimit` variabeln sätter en övre gräns för hur många träffar enheten lagrar lokalt. Den här variabeln fungerar bara om [`trackOffline`](trackoffline.md) är aktiverat.

## Offline Hit Limit med Adobe Analytics-tillägget

Det finns inget dedikerat fält i Adobe Analytics-tillägget som kan använda den här variabeln. Använd den anpassade kodredigeraren efter AppMeasurement-syntax.

## s.offlineHitLimit i AppMeasurement och den anpassade kodredigeraren i Analytics-tillägget

The `s.offlineHitLimit` variabeln är ett heltal som representerar maximalt antal träffar som en enhet lagrar när de är offline. Om variabeln inte är definierad finns det ingen gräns för hur många träffar en enhet lagrar när den är offline.

```js
s.offlineHitLimit = 100;
```
