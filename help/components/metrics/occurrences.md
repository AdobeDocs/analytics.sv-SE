---
title: Förekomster
description: Antalet träffar som en variabel har angetts eller befunnits vara.
feature: Metrics
exl-id: 8428e813-0fb4-4620-884e-1aa92fe33209
source-git-commit: 7d5383e1ee3bee189d3dd48bc6b899f4108f7ba8
workflow-type: tm+mt
source-wordcount: '153'
ht-degree: 1%

---

# Förekomster

Måttet &#39;Förekomster&#39; visar antalet träffar där en given dimension har angetts eller sparats. När du drar en dimension i arbetsytan till en tom arbetsyta, använder Adobe automatiskt detta mått på projektet.

## Hur det här måttet beräknas

Av alla träffar i en rapportsserie ska du ta med träffar där ett dimensionsobjekt definieras eller bevaras. Vissa dimensioner, till exempel [eVars](../dimensions/evar.md), kvarstår utanför den träff de är inställda på. Det här måttet räknar både initiala och beständiga värden.

## Jämför med liknande mätvärden

* **Förekomster kontra [Instanser](instances.md)**: Antal förekomster där ett dimensionsobjekt har angetts eller befunnits. Instanser omfattar inte träffar där en dimensionspost finns kvar.
* **Förekomster kontra [Sidvyer](page-views.md)**: Förekomsterna innehåller alla träfftyper, inklusive spårningsanrop för sidvy ([`t()`](/help/implement/vars/functions/t-method.md)) och länkspårningsanrop ([`tl()`](/help/implement/vars/functions/tl-method.md)). Mätvärdet för sidvisningar inkluderar endast spårningsanrop för sidvy och utesluter anrop för länkspårning.
