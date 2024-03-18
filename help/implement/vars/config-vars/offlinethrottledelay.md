---
title: offlineThrottleDelay
description: Fastställer frekvensen för träffar när en enhet ansluts igen.
feature: Variables
exl-id: fa484638-bb1f-4df9-9ba1-e9763fa6ad27
role: Admin, Developer
source-git-commit: 12347957a7a51dc1f8dfb46d489b59a450c2745a
workflow-type: tm+mt
source-wordcount: '195'
ht-degree: 0%

---

# offlineThrottleDelay

Spårning offline är ett valfritt sätt att samla in data i Adobe Analytics. Om en besökare kopplar från Internet men fortsätter att surfa på webbplatsen, lagras träffarna i en offlinekö tills enheten återansluter till Internet. Spårning offline används oftast för mobilprogram.

När en enhet ansluts igen skickas alla träffar som är lagrade på enheten till datainsamlingsservrarna i Adobe. Ett stort antal köade träffar kan påverka prestanda på äldre enheter. Använd `offlineThrottleDelay` variabel som anger hur ofta köade träffar skickas till Adobe.

## Fördröjning för offlinebegränsning med Web SDK

Web SDK stöder inte offlinespårning.

## Fördröjning med offlinerastning med Adobe Analytics-tillägget

Det finns inget dedikerat fält i Adobe Analytics-tillägget som kan använda den här variabeln. Använd den anpassade kodredigeraren enligt AppMeasurementen syntax.

## s.offlineThrottleDelay i AppMeasurementet och den anpassade kodredigeraren för Analytics-tillägget

The `s.offlineThrottleDelay` variabeln är ett heltal som representerar antalet millisekunder som AppMeasurementet väntar mellan skickade köade träffar. Standardvärdet är `0`, vilket innebär att alla träffar i kö skickas samtidigt. If `trackOffline` är `false`, gör den här variabeln ingenting.

```js
s.offlineThrottleDelay = 500;
```
