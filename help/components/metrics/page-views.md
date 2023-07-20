---
title: Sidvisningar
description: Antalet gånger som ett dimensionsobjekt har angetts eller befunnits i Adobe Analytics.
feature: Metrics
exl-id: 6b4fb7af-03e2-49e8-a431-f7746c89a626
source-git-commit: 60a630c9934d613aa69523bdb87b92165a135eb9
workflow-type: tm+mt
source-wordcount: '192'
ht-degree: 2%

---

# Sidvisningar

The **[!UICONTROL Page views]** mått visar hur många gånger en given dimensionsuppgift (dimensionsvärde) har definierats eller befunnits (dvs. när den förfaller) på en sida. Det är en av de vanligaste och mest grundläggande mätvärdena i rapporter.

Till exempel [!UICONTROL Days of Week] Dimensionen består av följande dimensionsobjekt: Söndag, måndag, tisdag, onsdag, torsdag, fredag och lördag.

## Hur det här måttet beräknas

Det här måttet räknar alla spårningsanrop för sidvyn ([`t()`](/help/implement/vars/functions/t-method.md)) i en rapportsvit. För dimensioner omfattar det träffar där en dimensionsobjekt definieras eller bevaras. Den innehåller inga anrop till länkspårning ([`tl()`](/help/implement/vars/functions/tl-method.md)) eller data från sammanfattning [Datakällor](/help/import/data-sources/overview.md).

## Jämför med liknande mätvärden

* **Sidvyer jämfört med [Besök](visits.md)**: Antal sidvyer det antal gånger en sida visas. Besök räknar antalet sessioner för besökare. Ett besök kan bestå av en eller flera sidvisningar.
* **Sidvyer jämfört med [Sidhändelser](page-events.md)**: Antal sidvyer antalet spårningsanrop för sidvy (`t()`) och utesluter anrop till länkspårning (`tl()`). Sidhändelser är motsatsen; de räknar antalet länkspårningsanrop och utesluter spårningsanrop för sidvy.
