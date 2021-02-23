---
title: 'Förklaring av sidvisningsmått | Adobe Analytics '
description: Lär dig hur måtten för sidvisningar fungerar i Adobe Analytics och förstå skillnaden mellan sidvisningar och besök.
translation-type: tm+mt
source-git-commit: c588087b949093152435967f62e43758e9e86208
workflow-type: tm+mt
source-wordcount: '176'
ht-degree: 0%

---


# Läs om sidvisningar med Adobe Analytics

Måttet för sidvisningar visar hur många gånger ett visst dimensionsobjekt har angetts eller sparats på en sida. Det är en av de vanligaste och mest grundläggande mätvärdena i rapporter.

## Hur det här måttet beräknas

Det här måttet räknar alla spårningsanrop för sidvy ([`t()`](/help/implement/vars/functions/t-method.md)) i en rapportserie. För dimensioner inkluderar det träffar där en dimensionsobjekt definieras eller bevaras. Den innehåller inte anrop till länkspårning ([`tl()`](/help/implement/vars/functions/tl-method.md)).

## Jämför med liknande mätvärden

* **Sidvyer jämfört med  [besök](visits.md)**: Sidvyer är antalet gånger som en sida visas. Besök anger antalet sessioner för besökarna. Ett besök består av en eller flera sidor.
* **Sidvyer jämfört med  [sidhändelser](page-events.md)**: Sidvyer räknar antalet anrop till spårning av sidvy (`t()`) och utesluter anrop till spårning av länkar (`tl()`). Sidhändelser är motsatsen; antalet anrop för länkspårning, och inte sidvisningar.