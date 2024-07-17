---
title: Läs in igen
description: Antalet gånger som sidan lästes in på nytt.
feature: Metrics
exl-id: 9539a733-9e9f-48b3-b8ab-8d969de27f87
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '63'
ht-degree: 0%

---

# Läs in igen

[Måttet ](overview.md) för att läsa in igen visar hur många gånger ett dimensionsobjekt fanns under en omläsning. En besökare som uppdaterar sin webbläsare är det vanligaste sättet att utlösa en omladdning.

## Hur det här måttet beräknas

Det här måttet räknar antalet träffar där dimensionen [`Page`](../dimensions/page.md) innehåller samma värde som föregående träff.
