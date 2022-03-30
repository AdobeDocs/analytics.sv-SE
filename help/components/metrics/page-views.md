---
title: Sidvisningar
description: Antalet gånger som ett dimensionsobjekt har angetts eller befunnits i Adobe Analytics.
feature: Metrics
exl-id: 6b4fb7af-03e2-49e8-a431-f7746c89a626
source-git-commit: 65f87bf4b5b3897c9ef68d091858332c08cbf699
workflow-type: tm+mt
source-wordcount: '162'
ht-degree: 2%

---

# Sidvisningar

Måttet för sidvisningar visar hur många gånger ett visst dimensionsobjekt har angetts eller sparats på en sida. Det är en av de vanligaste och mest grundläggande mätvärdena i rapporter.

## Hur det här måttet beräknas

Det här måttet räknar alla spårningsanrop för sidvyn ([`t()`](/help/implement/vars/functions/t-method.md)) i en rapportsvit. För dimensioner omfattar det träffar där en dimensionsobjekt definieras eller bevaras. Den innehåller inga anrop till länkspårning ([`tl()`](/help/implement/vars/functions/tl-method.md)).

## Jämför med liknande mätvärden

* **Sidvyer jämfört med [Besök](visits.md)**: Antal sidvyer det antal gånger en sida visas. Besök räknar antalet sessioner för besökare. Ett besök består av en eller flera sidvisningar.
* **Sidvyer jämfört med [Sidhändelser](page-events.md)**: Antal sidvyer antalet spårningsanrop för sidvy (`t()`) och utesluter anrop till länkspårning (`tl()`). Sidhändelser är motsatsen; de räknar antalet länkspårningsanrop och utesluter spårningsanrop för sidvy.
