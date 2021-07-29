---
title: offlineThrottleDelay
description: Fastställer frekvensen för träffar när en enhet ansluts igen.
exl-id: fa484638-bb1f-4df9-9ba1-e9763fa6ad27
source-git-commit: 1a49c2a6d90fc670bd0646d6d40738a87b74b8eb
workflow-type: tm+mt
source-wordcount: '178'
ht-degree: 1%

---

# offlineThrottleDelay

Spårning offline är ett valfritt sätt att samla in data i Adobe Analytics. Om en besökare kopplar från Internet men fortsätter att surfa på webbplatsen, lagras träffarna i en offlinekö tills enheten återansluter till Internet. Spårning offline används oftast för mobilprogram.

När en enhet ansluts igen skickas alla träffar som lagras på enheten till datainsamlingsservrarna i Adobe. Ett stort antal köade träffar kan påverka prestanda på äldre enheter. Använd variabeln `offlineThrottleDelay` för att fastställa hur ofta köade träffar skickas till Adobe.

## Fördröjning för offlinebegränsning med hjälp av taggar i Adobe Experience Platform

Det finns inget dedikerat fält i användargränssnittet för datainsamling som kan använda den här variabeln. Använd den anpassade kodredigeraren efter AppMeasurement-syntax.

## s.offlineThrottleDelay i AppMeasurement och anpassad kodredigerare

Variabeln `s.offlineThrottleDelay` är ett heltal som representerar antalet millisekunder AppMeasurement väntar mellan köade träffar. Dess standardvärde är `0`, vilket innebär att alla träffar i kö skickas samtidigt. Om `trackOffline` är `false` händer ingenting.

```js
s.offlineThrottleDelay = 500;
```
