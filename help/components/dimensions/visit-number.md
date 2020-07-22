---
title: Besöksnummer
description: Besökarens n:e besök.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '162'
ht-degree: 0%

---


# Besöksnummer

Dimensionerna &#39;Besöksnummer&#39; som besöker besökaren just nu är aktiverad. När ett nytt besök startar, ökar dimensionsposten med 1. Den här dimensionen är användbar när du vill förstå hur engagerade besökare är när du återvänder till din webbplats. Det är en besöksbaserad dimension, vilket innebär att den innehåller samma värde för hela besöket och inte kan ändras. Det gäller besökarens livstid, oavsett projektets datumintervall.

## Fyll den här dimensionen med data

Den här dimensionen fungerar som den ska för alla implementeringar. Om en rapportsvit innehåller data fungerar den här dimensionen.

## Dimensionsobjekt

Dimensionsobjekten inkluderar strängen `"Visit number"` följt av den numeriska representationen av besökarens besök. Om besökaren till exempel aldrig har besökt din webbplats tidigare tillhör deras första besök dimensionsposten `"Visit number 1"`. Om detta är besökarens trettonde besök på er webbplats tillhör de dimensionsposten `"Visit number 13"`.
