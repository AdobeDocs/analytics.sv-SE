---
title: Dag i månaden
description: Den numeriska dagen i månaden, oavsett vilken månad.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '138'
ht-degree: 0%

---


# Dag i månaden

Dimensionen Dag i månaden rapporterar den numeriska dagen i en viss månad som en dimensionspost. Om du till exempel har en rapport som sträcker sig från 1 januari till 31 mars grupperas den första i varje månad till samma dimensionsobjekt. Den här rapporten är värdefull om du vill att en rapport ska delas upp efter dag, men inte vill ha ett statiskt datum som dimensionsobjekt. Det är särskilt värdefullt som en dimension i schemalagda rapporter, eftersom den här dimensionen följer det valda datumintervallet.

## Fyll den här dimensionen med data

Den här dimensionen fungerar som den ska för alla implementeringar. Om en rapportsvit innehåller data fungerar den här dimensionen.

## Dimensionsobjekt

Dimensionsobjekten är siffrorna `1` - `31`som representerar dagen i månaden då träffen inträffade.
