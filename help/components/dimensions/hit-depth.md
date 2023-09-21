---
title: Träffdjup
description: Antalet träffar på besöket.
feature: Dimensions
exl-id: 84c27e3f-4228-4455-95bf-0239928337b5
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '261'
ht-degree: 7%

---

# Träffdjup

Träffdjupet [dimension](overview.md) rapporterar hur långt in i ett besök en viss träff är. Denna dimension är värdefull när det gäller att förstå hur långt in i ett besök besökarna utför åtgärder på er webbplats. Träffdjupet räknar alla typer av träffar, inklusive sidvyer ([`t()`](/help/implement/vars/functions/t-method.md)) och länkspårningsträffar ([`tl()`](/help/implement/vars/functions/tl-method.md)).

## Fyll den här dimensionen med data

Den här dimensionen fungerar som den ska för alla implementeringar. Om en rapportsvit innehåller data fungerar den här dimensionen.

## Dimensioner

Dimensionen innehåller strängen `"Hit Depth"` följt av en siffra som visar antalet träffar på besöket. Dimensionsobjektet för `"Hit Depth 1"` representerar första träffen av besöket, medan dimensionsposten `"Hit Depth 8"` representerar besökets åttonde träff.

## Jämförelse av besöksdjup

Träffdjupet räknar alla typer av träffar, inklusive sidvisning och länkspårningsträffar. Besök endast djupsteg för sidvisningsträffar. _och_ den [Sida](page.md) dimensionsobjektet är inte detsamma som värdet på föregående sida. Besöksdjupet är också en besöksbaserad dimension, vilket innebär att det ger samma värde för alla träffar under besöket. I följande tabell visas ett exempel på ett besök och hur man ser träffdjup + besöksdjup:

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
