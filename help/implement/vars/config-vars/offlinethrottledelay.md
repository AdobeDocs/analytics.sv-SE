---
title: offlineThrottleDelay
description: Fastställer frekvensen för träffar när en enhet ansluts igen.
translation-type: tm+mt
source-git-commit: f313fd0c9ffda054a18ad1d457a74602b08e51fa

---


# offlineThrottleDelay

Spårning offline är ett valfritt sätt att samla in data i Adobe Analytics. Om en besökare kopplar från Internet men fortsätter att surfa på webbplatsen, lagras träffarna i en offlinekö tills enheten återansluter till Internet. Spårning offline används oftast för mobilprogram.

När en enhet ansluts igen skickas alla träffar som lagras på enheten till Adobes datainsamlingsservrar. Ett stort antal köade träffar kan påverka prestanda på äldre enheter. Använd variabeln `offlineThrottleDelay` för att fastställa hur ofta köade träffar skickas till Adobe.

## Fördröjning för offlinebegränsning i Adobe Experience Platform Launch

Det finns inget dedikerat fält i Launch som kan använda den här variabeln. Använd den anpassade kodredigeraren efter AppMeasurement-syntax.

## s.offlineThrottleDelay i AppMeasurement and Launch custom code editor

Variabeln är ett heltal som representerar antalet millisekunder AppMeasurement väntar mellan köade träffar. `s.offlineThrottleDelay` Dess standardvärde är `0`, vilket innebär att alla träffar i kö skickas samtidigt. Om `trackOffline` det är `false`så händer ingenting.

```js
s.offlineThrottleDelay = 500;
```
