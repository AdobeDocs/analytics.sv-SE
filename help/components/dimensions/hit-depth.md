---
title: Träffdjup
description: Antalet träffar på besöket.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '261'
ht-degree: 7%

---


# Träffdjup

Dimensionen &#39;Träff&#39; visar hur långt in i ett besök en viss träff är. Denna dimension är värdefull när det gäller att förstå hur långt in i ett besök besökarna utför åtgärder på er webbplats. Träffdjupet räknar alla typer av träffar, inklusive sidvisningar ([`t()`](/help/implement/vars/functions/t-method.md)) och länkspårningsträffar ([`tl()`](/help/implement/vars/functions/tl-method.md)).

## Fyll den här dimensionen med data

Den här dimensionen fungerar som den ska för alla implementeringar. Om en rapportsvit innehåller data fungerar den här dimensionen.

## Dimensionsobjekt

Dimensionsobjekten inkluderar strängen `"Hit Depth"` följt av ett tal som representerar antalet träffar i besöket. Dimensionsposten för `"Hit Depth 1"` representerar den första träffen av besöket, medan dimensionsposten `"Hit Depth 8"` representerar den åttonde träffen av besöket.

## Jämförelse av besöksdjup

Träffdjup räknar alla typer av träffar, inklusive sidvy och länkspårningsträffar. Besök endast djupsteg för sidvisningträffar _och_ dimensionsobjektet för [sidan](page.md) är inte detsamma som värdet på föregående sida. Besöksdjupet är också en besöksbaserad dimension, vilket innebär att det ger samma värde för alla träffar under besöket. I följande tabell visas ett exempel på ett besök och hur man ser träffdjup + besöksdjup:

| Sidsekvens | Träffdjup | Räknas med besöksdjup? | Besöksdjup |
| --- | --- | --- | --- |
| Startsida | 1 | Ja | 4 |
| Produktsida | 2 | Ja | 4 |
| Startsida | 3 | Ja | 4 |
| Klicka på den anpassade länken | 4 | Nej (anpassad länk) | 4 |
| Klicka på den anpassade länken | 5 | Nej (anpassad länk) | 4 |
| Produktsida | 6 | Ja | 4 |
| Klicka på den anpassade länken | 7 | Nej (anpassad länk) | 4 |
| Produktsida | 8 | Nej (samma som föregående sida) | 4 |
