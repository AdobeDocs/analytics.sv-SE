---
title: Genomsnittligt siddjup
description: Hur många sidor i genomsnitt dimensionen finns på.
feature: Metrics
exl-id: 6625405a-bda5-4723-8d22-4bc5b7e44d4e
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '365'
ht-degree: 0%

---

# Genomsnittligt siddjup

Det genomsnittliga siddjupet [måttet](overview.md) visar i genomsnitt hur långt ett dimensionsobjekt sträcker sig till ett visst besök. På din hemsida (som är en dimensionspost för siddimensionen) visas vanligtvis ett mindre medeldjup än din inköpsbekräftelse, vilket troligen sträcker sig längre in i ett besök. Du kan använda den här informationen för att optimera vissa sidor mot nya besökare om sidan i genomsnitt har ett lågt djup.

>[!TIP]
>
>Använd det här måttet tillsammans med andra mätvärden, som [Besök](visits.md), för att få bättre insikter. Om du bara använder det här måttet kan du få dimensionsobjekt som innehåller avvikande siddjup, vilket vanligtvis inte är någon värdefull insikt.

## Hur det här måttet beräknas

Den första sidan i ett besök har siddjupet `0`. Nästa sida har siddjupet 1 och ökar sidvisningen till slutet av besöket. Det här måttet ökar bara med sidvyanrop ([`t()`](/help/implement/vars/functions/t-method.md)) och inte med länkspårningsanrop ([`tl()`](/help/implement/vars/functions/tl-method.md)).

För en given dimensionsuppgift lägger du till alla siddjup för den dimensionsobjektet och dividerar den med besök. Resultatet är det genomsnittliga siddjupet, avrundat till närmaste heltal. Dimensioner med ett genomsnittligt siddjup på `0` innebär att de ofta fanns på besökets första sida.

Här följer ett exempel:

```text
Page1 > Page2 > Page2 > Page3 > Page4 > Page2
```

Om vi ville ha ett genomsnittligt siddjup för dimensionsobjektet `Page2` skulle det beräknas så här:

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

Det här måttet innehåller ofta procenttal över 100 %. Nämnaren är hela dimensionens genomsnittliga siddjup och täljaren är dimensionsobjektets genomsnittliga siddjup.

Om medelvärdet för hela dimensionens siddjup är lägre än medelvärdet för ett angivet dimensionsobjekts siddjup visas procentvärden över 100 %. Om du sorterar rankade rapporter efter det här måttet visas ett genomsnittligt siddjup som vanligen inte är värdefullt. Adobe rekommenderar sortering efter ett annat mått, som [Besök](visits.md), i rankade rapporter.
