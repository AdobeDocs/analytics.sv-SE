---
title: Besöksnummer
description: Besökarens sjätte besök.
feature: Dimensions
exl-id: daef34b3-c270-476d-a45c-a20be6138c6b
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '163'
ht-degree: 0%

---

# Besöksnummer

Besöksnumret [dimension](overview.md) rapporterar vilket besök besökaren är på. När ett nytt besök startar, ökar dimensionsposten med 1. Den här dimensionen är användbar när du vill förstå hur engagerade besökare är när du återvänder till din webbplats. Det är en besöksbaserad dimension, vilket innebär att den innehåller samma värde för hela besöket och inte kan ändras. Det gäller besökarens livstid, oavsett projektets datumintervall.

## Fyll den här dimensionen med data

Den här dimensionen fungerar som den ska för alla implementeringar. Om en rapportsvit innehåller data fungerar den här dimensionen.

## Dimensioner

Dimensionen innehåller strängen `"Visit number"` följt av den numeriska representationen av besökarens besök. Om besökaren till exempel aldrig har besökt din webbplats tidigare tillhör deras första besök dimensionsobjektet `"Visit number 1"`. Om det här är besökarens trettonde besök på webbplatsen tillhör de dimensionsobjektet `"Visit number 13"`.
