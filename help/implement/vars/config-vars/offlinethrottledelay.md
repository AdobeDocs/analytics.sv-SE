---
title: offlineThrottleDelay
description: Fastställer frekvensen för träffar när en enhet ansluts igen.
feature: Variables
exl-id: fa484638-bb1f-4df9-9ba1-e9763fa6ad27
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '180'
ht-degree: 1%

---

# offlineThrottleDelay

Spårning offline är ett valfritt sätt att samla in data i Adobe Analytics. Om en besökare kopplar från Internet men fortsätter att surfa på webbplatsen, lagras träffarna i en offlinekö tills enheten återansluter till Internet. Spårning offline används oftast för mobilprogram.

När en enhet ansluts igen skickas alla träffar som lagras på enheten till datainsamlingsservrarna i Adobe. Ett stort antal köade träffar kan påverka prestanda på äldre enheter. Använd `offlineThrottleDelay` variabel som anger hur ofta köade träffar skickas till Adobe.

## Fördröjning för offlinebegränsning med Adobe Analytics-tillägget

Det finns inget dedikerat fält i Adobe Analytics-tillägget som kan använda den här variabeln. Använd den anpassade kodredigeraren efter AppMeasurement-syntax.

## s.offlineThrottleDelay i AppMeasurement och den anpassade kodredigeraren i Analytics-tillägget

The `s.offlineThrottleDelay` variabeln är ett heltal som representerar antalet millisekunder AppMeasurement väntar mellan köade träffar. Standardvärdet är `0`, vilket innebär att alla träffar i kö skickas samtidigt. If `trackOffline` är `false`, gör den här variabeln ingenting.

```js
s.offlineThrottleDelay = 500;
```
