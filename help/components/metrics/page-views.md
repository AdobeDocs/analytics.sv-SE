---
title: Sidvisningar
description: Antalet gånger som ett dimensionsobjekt har angetts eller befunnits i Adobe Analytics.
feature: Metrics
exl-id: 6b4fb7af-03e2-49e8-a431-f7746c89a626
source-git-commit: 66be48d0f41061d259cc53fb835ebd155294a710
workflow-type: tm+mt
source-wordcount: '167'
ht-degree: 2%

---

# Sidvisningar

**[!UICONTROL Page views]** [Mått](overview.md) visar hur många gånger ett angivet dimensionsobjekt har angetts eller befunnits på en sida. Det är en av de vanligaste och mest grundläggande mätvärdena i rapporter.

## Hur det här måttet beräknas

Det här måttet räknar alla spårningsanrop för sidvy ([`t()`](/help/implement/vars/functions/t-method.md)) i en rapportsvit. För dimensioner omfattar den träffar där en dimensionsobjekt är inställd eller beständig. Den innehåller inte länkspårningsanrop ([`tl()`](/help/implement/vars/functions/tl-method.md)) eller data från [datakällor](/help/import/data-sources/overview.md).

## Jämför med liknande mätvärden

* **Sidvyer jämfört med [Besök](visits.md)**: Sidvyer räknar antalet gånger som en sida visas. Besök räknar antalet sessioner för besökare. Ett besök består av en eller flera sidvisningar.
* **Sidvyer jämfört med [Sidhändelser](page-events.md)**: I sidvyer räknas antalet anrop för spårning av sidvy (`t()`) och länkspårningsanrop utesluts (`tl()`). Sidhändelser är motsatta. De räknar antalet anrop om länkspårning och utesluter anrop om spårning av sidvy.
