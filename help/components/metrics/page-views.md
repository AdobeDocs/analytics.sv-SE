---
title: 'Förklaring av sidvisningsmått | Adobe Analytics '
description: Lär dig hur måtten för sidvisningar fungerar i Adobe Analytics och förstå skillnaden mellan sidvisningar och besök.
feature: Metrics
exl-id: 6b4fb7af-03e2-49e8-a431-f7746c89a626
source-git-commit: 7d5383e1ee3bee189d3dd48bc6b899f4108f7ba8
workflow-type: tm+mt
source-wordcount: '176'
ht-degree: 0%

---

# Läs om sidvisningar med Adobe Analytics

Måttet för sidvisningar visar hur många gånger ett visst dimensionsobjekt har angetts eller sparats på en sida. Det är en av de vanligaste och mest grundläggande mätvärdena i rapporter.

## Hur det här måttet beräknas

Det här måttet räknar alla spårningsanrop för sidvyn ([`t()`](/help/implement/vars/functions/t-method.md)) i en rapportsvit. För dimensioner inkluderar det träffar där en dimensionsobjekt definieras eller bevaras. Den innehåller inga anrop till länkspårning ([`tl()`](/help/implement/vars/functions/tl-method.md)).

## Jämför med liknande mätvärden

* **Sidvyer jämfört med [Besök](visits.md)**: Sidvyer är antalet gånger som en sida visas. Besök anger antalet sessioner för besökarna. Ett besök består av en eller flera sidor.
* **Sidvyer jämfört med [Sidhändelser](page-events.md)**: Sidvyer räknar antalet spårningsanrop för sidvy (`t()`) och utesluter anrop till länkspårning (`tl()`). Sidhändelser är motsatsen; antalet anrop för länkspårning, och inte sidvisningar.
