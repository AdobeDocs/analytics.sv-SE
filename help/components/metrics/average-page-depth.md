---
title: Genomsnittligt siddjup
description: Hur många sidor i genomsnitt dimensionen finns på.
translation-type: tm+mt
source-git-commit: 54aeaa35fea8f725c87030936fa24f415064e333
workflow-type: tm+mt
source-wordcount: '370'
ht-degree: 0%

---


# Genomsnittligt siddjup

Mätvärdet för genomsnittlig siddjup visar hur långt i ett visst besök dimensionsvärdet finns. På din hemsida visas till exempel vanligtvis ett mindre siddjup än på din inköpsbekräftelsesida, som vanligtvis skulle vara längre fram vid ett besök. Det här måttet är användbart när du vill förstå hur många sidor i ett givet dimensionsvärde som ligger i genomsnitt. Du kan använda den här informationen för att optimera vissa sidor mot nya besökare om sidan i genomsnitt har ett lågt djup.

>[TIP] Använd detta mätvärde tillsammans med andra mätvärden (till exempel [Besök](visits.md)) för att få bättre insikter. Om du bara använder det här måttet får du dimensionsvärden som innehåller avvikande siddjup, vilket vanligtvis inte är värdefullt.

## Hur det här måttet beräknas

Den första sidan av ett besök har siddjupet `0`. Nästa sida har siddjupet 1 och ökar sidvisningen till slutet av besöket. Det här måttet ökar bara med anrop till sidvyn ([`t()`](/help/implement/vars/functions/t-method.md)) och inte med anrop till länkspårning ([`tl()`](/help/implement/vars/functions/tl-method.md)).

För ett givet dimensionsvärde lägger du till alla siddjup för det dimensionsvärdet och dividerar det med besök. Resultatet är det genomsnittliga siddjupet, avrundat till närmaste heltal. Dimensionsvärden med ett genomsnittligt siddjup på `0` innebär att de ofta fanns på besökets första sida.

Här följer ett exempel:

```text
Page1 > Page2 > Page2 > Page3 > Page4 > Page2
```

Om vi ville ha ett genomsnittligt siddjup för dimensionsvärdet `Page2`skulle det beräknas så här:

```text
If 'Count repeat instances' is enabled:
(1 + 2 + 5) / 3 = 2.67, rounded up to 3

If 'Count repeat instances' is disabled:
(1 + 4) / 2 = 2.5, rounded up to 3
```

>[!TIP] Om du vill visa genomsnittligt siddjup med en decimal, skapar du ett beräknat mått med det här måttet som det enda elementet i formeln. Öka antalet decimaler i det beräknade måttet till önskad decimal.

## Procent över 100 %

Det här måttet innehåller ofta procenttal över 100 %. Nämnaren är hela dimensionens genomsnittliga siddjup och täljaren är dimensionvärdets genomsnittliga siddjup. Om medelvärdet för hela dimensionens siddjup är lägre än medelvärdet för ett givet dimensionsvärde, visas procentvärden över 100 %. Om du sorterar rankade rapporter efter det här måttet visas ett genomsnittligt siddjup som vanligen inte är värdefullt. Adobe rekommenderar sortering efter andra mätvärden, till exempel [Besök](visits.md), i rankade rapporter.