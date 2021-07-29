---
title: offlineHitLimit
description: Ange det maximala antalet träffar som ska köas för spårning offline.
exl-id: de6478b3-b95f-4edc-8427-7b915a46b3ba
source-git-commit: 1a49c2a6d90fc670bd0646d6d40738a87b74b8eb
workflow-type: tm+mt
source-wordcount: '158'
ht-degree: 1%

---

# offlineHitLimit

Spårning offline är ett valfritt sätt att samla in data i Adobe Analytics. Om en besökare kopplar från Internet men fortsätter att surfa på webbplatsen, lagras träffarna i en offlinekö tills enheten återansluter till Internet. Spårning offline används oftast för mobilprogram.

Variabeln `offlineHitLimit` sätter en gräns för hur många träffar enheten lagrar lokalt. Den här variabeln fungerar bara om [`trackOffline`](trackoffline.md) är aktiverat.

## Offline Hit Limit med taggar i Adobe Experience Platform

Det finns inget dedikerat fält i användargränssnittet för datainsamling som kan använda den här variabeln. Använd den anpassade kodredigeraren efter AppMeasurement-syntax.

## s.offlineHitLimit i AppMeasurement och anpassad kodredigerare

Variabeln `s.offlineHitLimit` är ett heltal som representerar det maximala antalet träffar som en enhet lagrar när de är offline. Om variabeln inte är definierad finns det ingen gräns för hur många träffar en enhet lagrar när den är offline.

```js
s.offlineHitLimit = 100;
```
