---
description: Tillhandahåller rankade uppdelningsrapporter i Data Warehouse, sorterade efter fallande måttvärde.
title: Sortera efter mätvärden
feature: Data Warehouse
exl-id: 6bd82951-c3b4-4ba2-8e4d-b7c9b351911b
source-git-commit: 42c95198a4d4389308c78c312b5bb37572350cc1
workflow-type: tm+mt
source-wordcount: '322'
ht-degree: 14%

---

# Sortera efter mått

Tillhandahåller rankade uppdelningsrapporter i Data Warehouse, sorterade efter fallande måttvärde.

Sortering efter mätvärden gör det enklare för er att tolka Data Warehouse-rapporter, och de här rapporterna blir enklare att jämföra med andra analytiska rapporter.

Nedan visas hur du kan ändra ordning på rader i en Data Warehouse genom att aktivera alternativet &quot;Metrisk sortering&quot;.

Det finns fyra möjliga sätt att organisera Data Warehouse-rapporter med &quot;Metrics Sort&quot;, baserat på hur datumgranularitet, rapporteringsmått eller mätvärden har konfigurerats och om &quot;Max rows&quot; har angetts:

* **Layout 1**: Radobjekt sorteras i ordlisteordning (standard). Om&quot;Max rows&quot; är inställt visas endast de första N raderna i rapporten.
* **Layout 2**: Data Warehouse använder en måttsortering över alla rader i rapporten. Tips i det första måttvärdet bryts av det andra måttet, sedan det tredje och så vidare. När alla mätvärden är bundna används standardordlisteordningen för uppdelningsradsobjekt.
* **Layout 3**: Som layout 2, med endast de översta N raderna (d.v.s. talet i&quot;max rows&quot;) som utdata i rapporten.
* **Layout 4**: Som layout 2, med undantag för att radobjekten för varje datumgranularitetsperiod grupperas tillsammans och sorteras inom respektive tidsintervall.

Referera till kolumnen&quot;Rapportlayout&quot; i den här tabellen för att avgöra hur&quot;Metrisk sortering&quot; interagerar med andra rapportalternativ för Data Warehouse.

| Sortera efter mätvärden? | Har statistik? | Har uppdelningar? | Datum för granularitet? | Max rader? | Rapportlayout |
|---|---|---|---|---|---|
| Nej | Ja eller Nej | Ja eller Nej | Ja eller Nej | Ja eller Nej | 1 |
| Ja | Nej | Ja eller Nej | Ja eller Nej | Ja eller Nej | 1 |
| Ja | Ja | Nej | Nej | Ej tillämpligt | 1 |
| Ja | Ja | Nej | Ja eller Nej | Nej | 1 |
| Ja | Ja | Ja | Nej | Nej | 2 |
| Ja | Ja | Nej | Ja | Ja | 3 |
| Ja | Ja | Ja | Ja eller Nej | Ja | 3 |
| Ja | Ja | Ja | Ja | Nej | 4 |
