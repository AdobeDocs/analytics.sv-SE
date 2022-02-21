---
title: Datakällor för transaktions-ID
description: Lär dig det allmänna arbetsflödet med att använda datakällor för transaktions-ID.
feature: Data Sources
exl-id: 5f26b15c-8d9c-46d5-860f-13fdfa21af2e
source-git-commit: 79294cfc6f86e5a41a39504099cd730f53668725
workflow-type: tm+mt
source-wordcount: '531'
ht-degree: 0%

---

# Datakällor för transaktions-ID

Med datakällor för transaktions-ID kan du inte bara visa online- och offlinedata sida vid sida, utan även binda samman data. Det kräver att [`transactionID`](/help/implement/vars/page-vars/transactionid.md) i er Analytics-implementering.

När du skickar en onlineträff som innehåller en `transactionID` värdet tar Adobe en ögonblicksbild av alla variabler som var eller var beständiga vid den tidpunkten. Om ett matchande transaktions-ID som överförts via datakällor hittas knyts offline- och onlinedata ihop.

För att kunna använda transaktioner måste onlineträffen med ett transaktions-ID ha skickats in och bearbetats innan några data i transaktionsdatakällan med det transaktions-ID:t skickas in. Onlinesatsen innehåller variabler (eVars o.s.v.), men inte händelser, som fanns i onlinesatsen som sparades med transaktions-ID-informationen.

När en träff på en transaktionsdatakälla skickas in, söker transaktions-ID:t på datakällans transaktion efter variablerna osv. (inte händelser) som associerades med den ursprungliga onlineträffen med detta transaktions-ID. Dessa variabler används i datakällans transaktionsträff, om det inte fanns något värde för en variabel som skickades i datakällans transaktionsträff.

## Exempel

Om en träff med transaktions-ID 1256 skickas in och utförs `evar1=blue`, `evar2=water` och `event1` är inställda och transaktionsdata för transaktions-ID 1256 sparas av med `evar1=blue`, `evar2=water`. Inga händelsevärden sparas som en del av transaktionsinformationen.

Låt oss nu anta att en transaktionstransaktion för en datakälla sedan skickas genom systemet med transaktions-ID 1256 och `evar1=yellow`, `evar3=mountain` och `event2` set. Systemet hittar sparade transaktionsdata och i datakällans transaktion träffar `evar2=water` (eftersom det var den ursprungliga träffen). Den ställs inte in `evar1=blue` (som det var i den ursprungliga träffen) eftersom det fanns ett värde för `evar1` (gul) har redan angetts för datakällans transaktion.  så datakälltransaktionen träffar på att `evar1=yellow`, `evar2=water` (från den ursprungliga onlineträffen) och `evar3=mountain`. Dessa tre eVar har `event2` set - händelsen från datakällans transaktionsträck.

Inga värden från datakällans transaktionsträff hämtas `event1` anges när transaktionsträffen för datakällan bearbetas.

## Totalt arbetsflöde för datakällor för transaktions-ID

Använd följande allmänna arbetsflöde för att börja använda datakällor för transaktions-ID:

1. Skapa en datakälla (kategorin Allmänt och typen Allmän datakälla (transaktions-ID)).
1. Följ guiden Konfigurera datakälla för att hämta en FTP-plats för att överföra data och hämta en mallfil för datakällor.
1. Uppdatera implementeringen så att den innehåller `transactionID` variabel.
1. Överföra en datakällfil till FTP-platsen med en `.fin` -fil.

## Exempel på överföringsfil och implementeringskod

Om du överförde följande datakällfil och implementerade följande kod på din plats, skulle du se data länkade i rapporter. Datakällfilen använder eVar1 och event1, medan onlineimplementeringen använder eVar2 och event2. Eftersom transaktions-ID:t matchar kan du se händelsedata2 för eVar1 och händelse1 för eVar2.

### Exempelfil

Hämta mallen, uppdatera värdena och överför den sedan till FTP-platsen för datakällorna:

| `#` | `Example eVar1 name` | `Example event 1 name` | `1` |
|---|---|---|---|
| `Date` | `Evar 1` | `Event 1` | `transactionID` |
| `01/01/2020/12/00/00` | `Example eVar1 value` | `1` | `1234` |

### Exempel på implementeringskod

En mer detaljerad förklaring om transaktions-ID finns på [`transactionID`](/help/implement/vars/page-vars/transactionid.md) I Implementera användarhandboken.

```js
var s = s_gi("examplersid");
s.eVar2 = "Example eVar2 value";
s.events = "event2";
s.transactionID = "1234";
s.t();
```
