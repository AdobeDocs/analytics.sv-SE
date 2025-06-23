---
title: offlineThrottleDelay
description: Fastställer frekvensen för träffar när en enhet ansluts igen.
feature: Appmeasurement Implementation
exl-id: fa484638-bb1f-4df9-9ba1-e9763fa6ad27
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '195'
ht-degree: 0%

---

# offlineThrottleDelay

Spårning offline är ett valfritt sätt att samla in data i Adobe Analytics. Om en besökare kopplar från Internet men fortsätter att surfa på webbplatsen, lagras träffarna i en offlinekö tills enheten återansluter till Internet. Spårning offline används oftast för mobilprogram.

När en enhet ansluts igen skickas alla träffar som lagras på enheten till Adobe datainsamlingsservrar. Ett stort antal köade träffar kan påverka prestanda på äldre enheter. Använd variabeln `offlineThrottleDelay` för att fastställa hur ofta köade träffar skickas till Adobe.

## Fördröjning med strypning offline med Web SDK

SDK för webben stöder inte spårning offline.

## Fördröjning med offlinerastning med Adobe Analytics-tillägget

Det finns inget dedikerat fält i Adobe Analytics-tillägget som kan använda den här variabeln. Använd den anpassade kodredigeraren enligt AppMeasurement-syntax.

## s.offlineThrottleDelay i AppMeasurement och den anpassade kodredigeraren för Analytics-tillägget

Variabeln `s.offlineThrottleDelay` är ett heltal som representerar antalet millisekunder AppMeasurement väntar mellan köade träffar. Dess standardvärde är `0`, vilket innebär att alla träffar i kö skickas samtidigt. Om `trackOffline` är `false` händer ingenting.

```js
s.offlineThrottleDelay = 500;
```
