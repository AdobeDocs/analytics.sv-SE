---
title: Genomsnittlig tid på plats
description: Genomsnittlig tid mellan träffar för en given dimensionsartikel.
feature: Metrics
exl-id: bf9056e2-4f6d-4c4f-b641-d3146ce269ff
source-git-commit: 9e140a6be5ab151d7a4e88e317c59eafea4d6e1d
workflow-type: tm+mt
source-wordcount: '558'
ht-degree: 0%

---

# Genomsnittlig tid på plats

[Måttet](overview.md) för genomsnittlig tid på platsen visar hur lång tid det tar mellan träffarna för en given dimensionspost. Det här måttet är användbart när du vill se den genomsnittliga tiden för specifika dimensionsobjekt. Du kan också trender för detta mätresultat över tiden för att se hur den totala tiden som används ändras. Det här måttet visas i formatet `HH:MM:SS`.

Det här måttet är relaterat till [tiden per besök](../dimensions/time-spent-per-visit.md)-dimensionen.

## Hur det här måttet beräknas

För en given dimensionsuppgift tar du tidsstämpeln för varje träff där dimensionsobjektet finns. Jämför det med tidsstämpeln för nästa träff i besöket. Om träffen inte har någon efterföljande träff ska du inte ta med den i det här måttet. Av all tid som har ägnats åt dimensionsobjektet dividerar du alla med antalet&quot;sekvenser&quot; för dimensionsobjektet. En sekvens är där en dimensionspost är densamma för en eller flera efterföljande träffar. Resultattalet är det mätvärde som visas i rapporter.

Här följer ett exempel:

| `Timestamp` | `Page` |
| --- | --- |
| `12:03:00` | `Home page` |
| `12:04:20` | `Product page A` |
| `12:05:30` | `Product page A` |
| `12:07:00` | `Product page B` |
| `12:07:40` | `Product page A` |
| `12:08:10` | `Checkout` |
| `12:10:00` | `Purchase` |
| `12:25:00` | `Home page` |
| `12:25:40` | `Product page A` |


Om du vill ha genomsnittlig tid på platsen för dimensionsobjektet `Product page A` måste du först ta den tid som förflutit mellan träffar för den dimensionen:

* **12:04:20 - 12:05:30** - 1 minut 10 sekunder
* **12:05:30 - 12:07:00** - 1 minut 30 sekunder
* **12:07:40 - 12:08:10** - 30 sekunder
* **12:25:40 - ?** - ingår inte

Den totala tidsåtgången för `Product page A` är `00:03:10`. Det fanns två sekvenser i besöket; den första sekvensen för de två på varandra följande värdena och den andra före utcheckningen. Den sista träffen vid besöket är inte en sekvens eftersom det inte finns någon sluttidsstämpel.

Den genomsnittliga tiden på platsen för `Product page A` är `00:01:35`.

>[!NOTE]
>
>Det här måttet visar värdet `"Invalid"` om dimensionsobjektet bara innehåller träffar som var senaste i ett besök. Det här måttet kräver en efterföljande träff för att spåra hur mycket tid som använts.

## Genomsnittlig tid på plats (sekunder)

Mätvärdet för genomsnittlig tid på plats (sekunder) visar samma data som ett heltal i stället för i formatet `HH:MM:SS`. Det här måttet är mest värdefullt som en komponent i beräknade värden.

## Uppdelningssummor matchar inte den överordnade radobjektet

Mätvärdet för genomsnittlig tid på plats använder obrutna sekvenser av en given dimension. Indelningsdimensionen är inte beroende av den överordnade dimensionen vid beräkning av dessa sekvenser. Här följer ett exempel:

| `Timestamp` | `Page name` | `Site section` |
| --- | --- | --- |
| `12:00:00` | `Home` | `Foxes` |
| `12:00:30` | `Product` | `Foxes` |
| `12:02:10` | `Home` | `Foxes` |
| `12:02:20` | `(None; exit link click)` | `(None; exit link click)` |

Följande beräkning används för att beräkna den genomsnittliga tiden på platsen för dimensionsobjektet `Home`:

```text
(30 + 10) / 2 = 20 seconds average time on site
```

Om du tillämpade en uppdelning med dimensionen [Platsavsnitt](../dimensions/site-section.md) skulle följande beräkning användas:

```text
(30 + 100 + 10) / 1 = 140 seconds (2 minutes 20 seconds) average time on site
```

Eftersom det fanns en enda sekvens i uppdelningsdimensionen används en annan nämnare än dess överordnade dimension. Dessa mätvärden ger vanligtvis liknande resultat på besöksnivå, men kan vara annorlunda på en träffnivå.

## Procent över 100 %

Det här måttet innehåller ofta procenttal över 100 %. Nämnaren är hela dimensionens genomsnittliga tid på platsen, och täljaren är dimensionsobjektets genomsnittliga tid på platsen. Om hela dimensionens genomsnittliga tid på platsen är lägre än en given dimensionsobjekts genomsnittliga tid på platsen, visas procentsatser över 100 %. Sortering av rankade rapporter efter det här måttet visar en onormal genomsnittlig tid på webbplatsvärden, vilket vanligtvis inte är värdefullt. Adobe rekommenderar sortering efter ett annat mått, som [Besök](visits.md), i rankade rapporter.

Mer allmän information om hur lång tid du tillbringar finns i [Tidsåtgång - översikt](time-spent.md).
