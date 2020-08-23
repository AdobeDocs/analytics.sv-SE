---
title: Genomsnittligt siddjup
description: Hur många sidor i genomsnitt dimensionen finns på.
translation-type: tm+mt
source-git-commit: 226bbce18750825d459056ac2a87549614eb3c2c
workflow-type: tm+mt
source-wordcount: '369'
ht-degree: 0%

---


# Genomsnittligt siddjup

Måttet för genomsnittlig siddjup visar hur långt i ett visst besök dimensionsobjektet finns. På din hemsida visas till exempel vanligtvis ett mindre siddjup än på din inköpsbekräftelsesida, som vanligtvis skulle vara längre fram vid ett besök. Det här måttet är användbart när du vill veta hur många sidor i en given dimensionspost som finns i genomsnitt. Du kan använda den här informationen för att optimera vissa sidor mot nya besökare om sidan i genomsnitt har ett lågt djup.

>[!TIP]
>
>Använd det här måttet tillsammans med andra mätvärden (till exempel [Besök](visits.md)) för att få bättre insikter. Om du bara använder det här måttet får du dimensionsobjekt som innehåller avvikande siddjup, vilket vanligtvis inte är värdefullt.

## Hur det här måttet beräknas

Den första sidan av ett besök har siddjupet `0`. Nästa sida har siddjupet 1 och ökar sidvisningen till slutet av besöket. Det här måttet ökar bara med anrop till sidvyn ([`t()`](/help/implement/vars/functions/t-method.md)) och inte med anrop till länkspårning ([`tl()`](/help/implement/vars/functions/tl-method.md)).

För en given dimensionsuppgift lägger du till alla siddjup för den dimensionsobjektet och dividerar den med besök. Resultatet är det genomsnittliga siddjupet, avrundat till närmaste heltal. Dimensioner med ett genomsnittligt siddjup `0` innebär att de ofta fanns på besökets första sida.

Här följer ett exempel:

```text
Page1 > Page2 > Page2 > Page3 > Page4 > Page2
```

Om vi ville ha ett genomsnittligt siddjup för dimensionsobjektet `Page2`skulle det beräknas så här:

```text
If 'Count repeat instances' is enabled:
(1 + 2 + 5) / 3 = 2.67, rounded up to 3

If 'Count repeat instances' is disabled:
(1 + 4) / 2 = 2.5, rounded up to 3
```

>[!TIP]
>
>Om du vill visa genomsnittligt siddjup med en decimal, skapar du ett beräknat mått med det här måttet som det enda elementet i formeln. Öka antalet decimaler i det beräknade måttet till önskad decimal.

## Procent över 100 %

Det här måttet innehåller ofta procenttal över 100 %. Nämnaren är hela dimensionens genomsnittliga siddjup och täljaren är dimensionsobjektets genomsnittliga siddjup. Om medelvärdet för hela dimensionens siddjup är lägre än medelvärdet för en given dimensionsposts siddjup visas procentvärden över 100 %. Sortering av rankade rapporter efter det här måttet visar ett onormalt medelvärde för siddjup, vilket vanligtvis inte är värdefullt. Adobe rekommenderar sortering efter andra mätvärden, som [Besök](visits.md), i rankade rapporter.