---
title: Sidvisningar
description: Antalet gånger som ett dimensionsobjekt har angetts eller befunnits i Adobe Analytics.
feature: Metrics
exl-id: 6b4fb7af-03e2-49e8-a431-f7746c89a626
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '192'
ht-degree: 2%

---

# Sidvisningar

The **[!UICONTROL Page views]** [mått](overview.md) visar hur många gånger en given dimensionsuppgift (dimensionsvärde) har definierats eller befunnits (dvs. när den förfaller) på en sida. Det är en av de vanligaste och mest grundläggande mätvärdena i rapporter.

Till exempel [!UICONTROL Days of Week] Dimensionen består av följande dimensionsposter: söndag, måndag, tisdag, onsdag, torsdag, fredag och lördag.

## Hur det här måttet beräknas

Det här måttet räknar alla spårningsanrop för sidvyn ([`t()`](/help/implement/vars/functions/t-method.md)) i en rapportsvit. För dimensioner omfattar det träffar där en dimensionsobjekt definieras eller bevaras. Den innehåller inga anrop till länkspårning ([`tl()`](/help/implement/vars/functions/tl-method.md)) eller data från sammanfattning [Datakällor](/help/import/data-sources/overview.md).

## Jämför med liknande mätvärden

* **Sidvyer jämfört med [Besök](visits.md)**: Sidvyer räknar antalet gånger en sida visas. Besök räknar antalet sessioner för besökare. Ett besök kan bestå av en eller flera sidvisningar.
* **Sidvyer jämfört med [Sidhändelser](page-events.md)**: Sidvisningar räknar antalet anrop till spårning av sidvy (`t()`), och utelämnar anrop till länkspårning (`tl()`). Sidhändelser är motsatta. De räknar antalet anrop om länkspårning och utesluter anrop om spårning av sidvy.
