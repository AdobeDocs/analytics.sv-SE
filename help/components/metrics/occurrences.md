---
title: Förekomster
description: Antalet träffar som en variabel har angetts eller befunnits vara.
feature: Metrics
exl-id: 8428e813-0fb4-4620-884e-1aa92fe33209
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '161'
ht-degree: 1%

---

# Förekomster

&#39;Förekomster&#39; [mått](overview.md) visar antalet träffar där en given dimension angavs eller bestals. När du drar en dimension i arbetsytan till en tom arbetsyta, använder Adobe automatiskt det här måttet på projektet.

## Hur det här måttet beräknas

Av alla träffar i en rapportsserie ska du ta med träffar där ett dimensionsobjekt definieras eller bevaras. Vissa dimensioner, till exempel [eVars](../dimensions/evar.md), kvarstår utanför den träff de är inställda på. Det här måttet räknar både initiala och beständiga värden.

## Jämför med liknande mätvärden

* **Förekomster kontra [Instanser](instances.md)**: Antal förekomster träffar där ett dimensionsobjekt angavs eller beständig. Instanser omfattar inte träffar där en dimensionspost finns kvar.
* **Förekomster kontra [Sidvyer](page-views.md)**: Förekomsterna innehåller alla träfftyper, inklusive spårningsanrop för sidvy ([`t()`](/help/implement/vars/functions/t-method.md)), länkspårningsanrop ([`tl()`](/help/implement/vars/functions/tl-method.md)) och data från sammanfattningar [Datakällor](/help/import/data-sources/overview.md). Mätvärdet för sidvisningar inkluderar endast spårningsanrop för sidvy, exklusive länkspårningsanrop och sammanfattningsdatakällor.
