---
title: Besöksdjup
description: Besöksbaserad dimension som visar besökets djup.
feature: Dimensions
exl-id: 3e9aca08-2255-46ca-9949-77334ee7120e
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '167'
ht-degree: 0%

---

# Besöksdjup

Besöksdjupet [dimension](overview.md) visar antalet sidvisningar besökaren såg under hela besöket. Besöksdjupet ökar bara om träffen är en sidvy och dimensionen [Sida](page.md) inte är densamma som dimensionsobjektet för den sista sidvyn. Det är en besöksbaserad dimension, vilket innebär att den har samma värde för hela besöket. Variabeln är inställd för alla träffar på ett besök när besöket är avslutat.

## Fyll den här dimensionen med data

Den här dimensionen fungerar som den ska för alla implementeringar. Om en rapportsvit innehåller data fungerar den här dimensionen.

## Dimensioner

Dimensionen innehåller strängen `"Pages per visit"` följt av ett tal som representerar antalet sidor i besöket. Dimensionsobjektet för `"Pages per visit: 1"` representerar ett enkelsidigt besök, medan dimensionsobjektet `"Pages per visit: 8"` representerar ett besök med åtta sidvyer (och ett valfritt antal länkspårningsanrop).

## Jämförelse med träffdjup

Se [Träff-djup](hit-depth.md) för en jämförelse mellan dimensioner.
