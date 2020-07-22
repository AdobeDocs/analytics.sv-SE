---
title: Besöksdjup
description: Besöksbaserad dimension som visar besökets djup.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '166'
ht-degree: 0%

---


# Besöksdjup

Dimensionen &#39;Besöksdjup&#39; visar antalet sidvisningar besökaren såg under hela besöket. Besöksdjupet ökar bara om träffen är en sidvy och [siddimensionen](page.md) inte är densamma som dimensionsobjektet för den sista sidvyn. Det är en besöksbaserad dimension, vilket innebär att den har samma värde för hela besöket. Variabeln är inställd för alla träffar på ett besök när besöket är avslutat.

## Fyll den här dimensionen med data

Den här dimensionen fungerar som den ska för alla implementeringar. Om en rapportsvit innehåller data fungerar den här dimensionen.

## Dimensionsobjekt

Dimensionsobjekten innehåller strängen `"Pages per visit"` följt av ett tal som representerar antalet sidor i besöket. Dimensionsobjektet för `"Pages per visit: 1"` representerar ett enkelsidigt besök, medan dimensionsobjektet `"Pages per visit: 8"` representerar ett besök med åtta sidvisningar (och ett valfritt antal anrop för länkspårning).

## Jämförelse med träffdjup

Se [Träff-djup](hit-depth.md) för en jämförelse mellan dimensioner.