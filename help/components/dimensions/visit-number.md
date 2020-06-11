---
title: Besöksnummer
description: Besökarens n:e besök.
translation-type: tm+mt
source-git-commit: 05ea2778cd5cd324c660fd0f1d2ac02373829f0f
workflow-type: tm+mt
source-wordcount: '162'
ht-degree: 0%

---


# Besöksnummer

Dimensionerna &#39;Besöksnummer&#39; som besöker besökaren just nu är aktiverad. När ett nytt besök börjar, ökar detta dimensionsvärde med 1. Den här dimensionen är användbar när du vill förstå hur engagerade besökare är när du återvänder till din webbplats. Det är en besöksbaserad dimension, vilket innebär att den innehåller samma värde för hela besöket och inte kan ändras. Det gäller besökarens livstid, oavsett projektets datumintervall.

## Fyll den här dimensionen med data

Den här dimensionen fungerar som den ska för alla implementeringar. Om en rapportsvit innehåller data fungerar den här dimensionen.

## Dimensionsvärden

Dimensionsvärdena inkluderar strängen `"Visit number"` följt av den numeriska representationen av besökarens besök. Om besökaren till exempel aldrig har besökt din webbplats tidigare tillhör deras första besök dimensionens värde `"Visit number 1"`. Om detta är besökarens trettonde besök på er webbplats tillhör de dimensionens värde `"Visit number 13"`.
