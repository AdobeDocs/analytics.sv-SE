---
description: Visar exempel på filtrerade och viktade mätvärden.
title: Filtrerade och viktade mätvärden
feature: Calculated Metrics
exl-id: bea46e03-7d05-44c8-b654-c61b1e32becc
source-git-commit: bf58da2a39e8b9fd298356f23a9bf8f6c394d3de
workflow-type: tm+mt
source-wordcount: '156'
ht-degree: 0%

---

# Filtrerade och viktade mätvärden

I den här artikeln visas exempel på filtrerade och viktade mätvärden.

## Filtrerad studs-hastighet

Det här enkla filtrerade måttet visar endast avhoppsfrekvensen för de sidor som har fler än 100 besök:

![Filtrerad studsfrekvens](assets/filtered-bounce-rate.png){zoomable="yes"}

Tänk på att den här formeln är beroende av ett konsekvent tidsintervall. Om du kör en rapport för en dag är alla sidor med fler än 20 besök värda att titta på. Om du kör det i en månad kanske du vill att filtret ska innehålla fler besök.

## Filtrerad studs-hastighet med procentig

Det här filtret visar studs-frekvensen för de 30 högsta procenten av sidorna, sorterade efter besök.

![Filtrerad studsfrekvens med percentil](assets/filtered-bounce-rate-with-percentile.png){zoomable="yes"}

## Viktat mått

Anta att du vill sortera efter studsfrekvens i allmänhet, men sidor med högre besök bör vara högre i listan. Du kan skapa en viktad studsfrekvens som ser ut så här:

![](assets/weighted-bounce-rate.png)
