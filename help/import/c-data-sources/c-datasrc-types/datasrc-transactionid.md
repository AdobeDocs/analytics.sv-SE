---
title: Datakällor för transaktions-ID
description: Lär dig det allmänna arbetsflödet med att använda datakällor för transaktions-ID.
exl-id: 5f26b15c-8d9c-46d5-860f-13fdfa21af2e
source-git-commit: 1ee6a1e69a277f0d3c0ffd1defca0d4cb098cc6c
workflow-type: tm+mt
source-wordcount: '270'
ht-degree: 0%

---

# Datakällor för transaktions-ID

Med datakällor för transaktions-ID kan du inte bara visa online- och offlinedata sida vid sida, utan även binda samman data. Det kräver att variabeln [`transactionID`](/help/implement/vars/page-vars/transactionid.md) används i din Analytics-implementering.

När du skickar en onlineträff som innehåller ett `transactionID`-värde tar Adobe en ögonblicksbild av alla variabler som angetts eller sparats vid den tidpunkten. Om ett matchande transaktions-ID som överförts via datakällor hittas knyts offline- och onlinedata ihop. Det spelar ingen roll vilken datakälla som ses först.

## Totalt arbetsflöde för datakällor för transaktions-ID

Använd följande allmänna arbetsflöde för att börja använda datakällor för transaktions-ID:

1. Skapa en datakälla (kategorin Allmänt och typen Allmän datakälla (transaktions-ID)).
1. Följ guiden Konfigurera datakälla för att hämta en FTP-plats för att överföra data och hämta en mallfil för datakällor.
1. Uppdatera implementeringen så att den innehåller variabeln `transactionID`.
1. Överför en datakällfil till FTP-platsen med en `.fin`-fil.

## Exempel på överföringsfil och implementeringskod

Om du överförde följande datakällfil och implementerade följande kod på din plats, skulle du se data länkade i rapporter. Datakällfilen använder eVar1 och event1, medan onlineimplementeringen använder eVar2 och event2. Eftersom transaktions-ID:t matchar kan du se händelsedata2 för eVar1 och händelse1 för eVar2.

### Exempelfil

Hämta mallen, uppdatera värdena och överför den sedan till FTP-platsen för datakällorna:

| `#` | `Example eVar1 name` | `Example event 1 name` | `1` |
|---|---|---|---|
| `Date` | `Evar 1` | `Event 1` | `transactionID` |
| `01/01/2020/12/00/00` | `Example eVar1 value` | `1` | `1234` |

### Exempel på implementeringskod

En mer detaljerad förklaring om transaktions-ID finns i [`transactionID`](/help/implement/vars/page-vars/transactionid.md) I användarhandboken för implementering.

```js
var s = s_gi("examplersid");
s.eVar2 = "Example eVar2 value";
s.events = "event2";
s.transactionID = "1234";
s.t();
```
