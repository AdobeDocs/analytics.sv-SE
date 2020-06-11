---
title: Sidvyer
description: Antalet gånger som en sida visades.
translation-type: tm+mt
source-git-commit: 54aeaa35fea8f725c87030936fa24f415064e333
workflow-type: tm+mt
source-wordcount: '153'
ht-degree: 0%

---


# Sidvyer

Mätvärdet för sidvisningar visar hur många gånger ett givet dimensionsvärde har angetts eller sparats på en sida. Det är en av de vanligaste och mest grundläggande mätvärdena i rapporter.

## Hur det här måttet beräknas

Det här måttet räknar alla spårningsanrop ([`t()`](/help/implement/vars/functions/t-method.md)) för sidvyn i en rapportserie. För dimensioner inkluderar det träffar där ett dimensionsvärde definieras eller bevaras. Den innehåller inte anrop till länkspårning ([`tl()`](/help/implement/vars/functions/tl-method.md)).

## Jämför med liknande mätvärden

* **Sidvyer jämfört med[besök](visits.md)**: Sidvyer är antalet gånger som en sida visas. Besök anger antalet sessioner för besökarna. Ett besök består av en eller flera sidor.
* **Sidvyer jämfört med[sidhändelser](page-events.md)**: Sidvyer räknar antalet anrop till spårning av sidvy (`t()`) och utesluter anrop till spårning av länkar (`tl()`). Sidhändelser är motsatsen; antalet anrop för länkspårning, och inte sidvisningar.