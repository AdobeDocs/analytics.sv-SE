---
description: Tillhandahåller rankade uppdelningsrapporter i Data warehouse, sorterade efter fallande måttvärde.
title: Sortera efter mätvärden
feature: Data Warehouse
exl-id: 6bd82951-c3b4-4ba2-8e4d-b7c9b351911b
source-git-commit: 4daa5c8bdbcb483f23a3b8f75dde9eeb48516db8
workflow-type: tm+mt
source-wordcount: '322'
ht-degree: 15%

---

# Sortera efter mätvärden

Tillhandahåller rankade uppdelningsrapporter i Data warehouse, sorterade efter fallande måttvärde.

Genom att sortera efter mätvärden blir det enklare för er att tolka Data warehouse-rapporter, och de här rapporterna blir enklare att jämföra med andra analytiska rapporter om uppdelning.

Nedan visas hur du kan ändra ordning på rader i en Data warehouse-rapport genom att aktivera alternativet &quot;Metrisk sortering&quot;.

Det finns fyra möjliga sätt att ordna Data warehouse-rapporter med &quot;Metrics Sort&quot;, baserat på hur datumgranularitet, rapportdimensioner eller mätvärden har konfigurerats och om &quot;Max rows&quot; har angetts:

* **Layout 1**: Radobjekt sorteras i ordlisteordning (standard). Om&quot;Max rows&quot; är inställt visas endast de första N raderna i rapporten.
* **Layout 2**: data warehouse använder en metrisk sortering över alla rader i rapporten. Tips i det första måttvärdet bryts av det andra måttet, sedan det tredje och så vidare. När alla mätvärden är bundna används standardordlisteordningen för uppdelningsradsobjekt.
* **Layout 3**: Som layout 2, med endast de översta N raderna (d.v.s. talet som anges i &quot;max rows&quot;) utdata i rapporten.
* **Layout 4**: Som layout 2, med undantag för att radobjekten för varje datumgranulationsperiod grupperas tillsammans och sorteras inom respektive tidsintervall.

Referera till kolumnen&quot;Rapportlayout&quot; i den här tabellen för att avgöra hur&quot;Metrisk sortering&quot; interagerar med andra rapportalternativ för Data warehouse.

| Sortera efter mätvärden? | Har statistik? | Har uppdelningar? | Datum för granularitet? | Ange maximalt antal rader? | Rapportlayout |
|---|---|---|---|---|---|
| Nej | Ja eller Nej | Ja eller Nej | Ja eller Nej | Ja eller Nej | 1 |
| Ja | Nej | Ja eller Nej | Ja eller Nej | Ja eller Nej | 1 |
| Ja | Ja | Nej | Nej | Ej tillämpligt | 1 |
| Ja | Ja | Nej | Ja eller Nej | Nej | 1 |
| Ja | Ja | Ja | Nej | Nej | 2 |
| Ja | Ja | Nej | Ja | Ja | 3 |
| Ja | Ja | Ja | Ja eller Nej | Ja | 3 |
| Ja | Ja | Ja | Ja | Nej | 4 |
