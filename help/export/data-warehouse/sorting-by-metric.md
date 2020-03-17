---
description: Tillhandahåller rankade uppdelningsrapporter i datalagret, sorterade efter fallande måttvärde.
title: Sortera efter mått
uuid: 07da2607-b3fd-463b-90d4-6884a93c7e25
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Sortera efter mått

Tillhandahåller rankade uppdelningsrapporter i datalagret, sorterade efter fallande måttvärde.

Sortering efter mätvärden gör det enklare för er att tolka datalagerrapporter, och de här rapporterna blir enklare att jämföra med andra analytiska rapporter om uppdelningar.

Nedan visas hur du kan ändra ordning på rader i en datalagerrapport genom att aktivera alternativet &quot;Metrisk sortering&quot;.

Det finns fyra möjliga sätt att ordna datalagerrapporter med &quot;Metrics Sort&quot;, baserat på hur datumgranularitet, rapportdimensioner eller mått har konfigurerats och om &quot;Max rows&quot; har angetts:

* **Layout 1**: Radobjekt sorteras i ordlisteordning (standard). Om&quot;Max rows&quot; är inställt visas endast de första N raderna i rapporten.
* **Layout 2**: Datalagret använder en måttsortering över alla rader i rapporten. Tips i det första måttvärdet bryts av det andra måttet, sedan det tredje och så vidare. När alla mätvärden är bundna används standardordlisteordningen för uppdelningsradsobjekt.
* **Layout 3**: Som layout 2, med endast de översta N raderna (d.v.s. talet som anges i &quot;max rows&quot;) utdata i rapporten.
* **Layout 4**: Som layout 2, med undantag för att radobjekten för varje datumgranulationsperiod grupperas tillsammans och sorteras inom respektive tidsintervall.

Referera till kolumnen&quot;Rapportlayout&quot; i den här tabellen för att bestämma hur&quot;Metrisk sortering&quot; interagerar med andra rapporteringsalternativ för datalager.

| Sortera efter mått? | Har statistik? | Har uppdelningar? | Datum för granularitet? | Ange maximalt antal rader? | Rapportlayout |
|---|---|---|---|---|---|
| Nej | Ja eller Nej | Ja eller Nej | Ja eller Nej | Ja eller Nej | 1 |
| Ja | Nej | Ja eller Nej | Ja eller Nej | Ja eller Nej | 1 |
| Ja | Ja | Nej | Nej | Ej tillämpligt | 1 |
| Ja | Ja | Nej | Ja eller Nej | Nej | 1 |
| Ja | Ja | Ja | Nej | Nej | 2 |
| Ja | Ja | Nej | Ja | Ja | 3 |
| Ja | Ja | Ja | Ja eller Nej | Ja | 3 |
| Ja | Ja | Ja | Ja | Nej | 4 |

