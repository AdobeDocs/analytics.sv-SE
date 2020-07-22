---
title: Sidvyer
description: Antalet gånger som en sida visades.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '153'
ht-degree: 0%

---


# Sidvyer

Måttet för sidvisningar visar hur många gånger ett visst dimensionsobjekt har angetts eller sparats på en sida. Det är en av de vanligaste och mest grundläggande mätvärdena i rapporter.

## Hur det här måttet beräknas

Det här måttet räknar alla spårningsanrop ([`t()`](/help/implement/vars/functions/t-method.md)) för sidvyn i en rapportserie. För dimensioner inkluderar det träffar där en dimensionsobjekt definieras eller bevaras. Den innehåller inte anrop till länkspårning ([`tl()`](/help/implement/vars/functions/tl-method.md)).

## Jämför med liknande mätvärden

* **Sidvyer jämfört med[besök](visits.md)**: Sidvyer är antalet gånger som en sida visas. Besök anger antalet sessioner för besökarna. Ett besök består av en eller flera sidor.
* **Sidvyer jämfört med[sidhändelser](page-events.md)**: Sidvyer räknar antalet anrop till spårning av sidvy (`t()`) och utesluter anrop till spårning av länkar (`tl()`). Sidhändelser är motsatsen; antalet anrop för länkspårning, och inte sidvisningar.