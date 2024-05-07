---
title: Sena träffar
description: Lär dig hur dataflöden behandlar sena träffar.
feature: Data Feeds
exl-id: c99a702b-2aaa-47a6-958a-1e5ab66961ba
source-git-commit: 6b8366b451be1612331f517ee80fd57744deafdc
workflow-type: tm+mt
source-wordcount: '351'
ht-degree: 0%

---

# Sena träffar

Historiska data kan komma när ett datafeedjobb har avslutat bearbetningen för en viss timme eller dag, till exempel genom tidsstämplade träffar eller datakällor. Sena träffar är en anpassning av backend-funktionen som tillhandahålls av Adobe för att hjälpa till att inkludera dessa data i dataflöden.

## Hur sent det är att komma in på jobbet

När en dataström normalt bearbetar data, tittar den bara på data i sitt rapportfönster (vanligtvis den senaste timmen eller dagen). Om data kommer efter att en feed har bearbetat det rapportfönstret, inkluderas dessa data aldrig i någon datafeed.

När sena träffar har aktiverats ändras bearbetningsmetoden så att den inkluderar dessa data. Varje gång en datafeed bearbetar data tittar den på eventuella sena träffar som har inträffat och grupperar dem i nästa datafeedfil som skickas till FTP-platsen.

## Aktivera sena träffar

Sena träffar kan aktiveras manuellt av Adobe på enskilda dataflöden. Innan du gör det bör du tänka på följande:

* Data för olika dagar visas ofta i dataflöden när sena träffar har aktiverats. Se till att den plattform du använder för att importera dataflöden kan innehålla data från olika dagar inom samma fil.
* Sena träffar ökar bearbetningstiden. Vanligtvis är fördröjningen mindre än en timme, men den kan vara flera timmar eller mer om rapportsviten tar emot ett stort antal sena träffar. Adobe rekommenderar att du inte aktiverar den här inställningen om det är av största vikt att dataflödena kommer i rätt tid.
* Om en dataflödesfil bearbetas på nytt inkluderas de träffar som togs med i originalfilen i den bearbetade filen när bearbetningen görs inom de första fem dagarna. Efter 5 dagar inkluderas inte sena träffar i den bearbetade filen.

Om du vill aktivera sena träffar för ett befintligt återkommande dataflöde ska du be en användare som stöds att kontakta Kundtjänst och inkludera följande:

* Observera att du vill aktivera sena träffar för en viss datafeed
* Rapportsvit-ID
* Namn på datafeed
