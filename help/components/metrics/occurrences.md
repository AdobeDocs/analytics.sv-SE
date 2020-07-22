---
title: Förekomster
description: Antalet träffar som en variabel har angetts eller befunnits vara.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '164'
ht-degree: 1%

---


# Förekomster

Måttet &#39;Förekomster&#39; visar antalet träffar där en given dimension har angetts eller sparats. När du drar en dimension i arbetsytan till en tom arbetsyta, tillämpar Adobe automatiskt detta mått på projektet.

## Hur det här måttet beräknas

Av alla träffar i en rapportsserie ska du ta med träffar där ett dimensionsobjekt definieras eller bevaras. Vissa dimensioner, till exempel [eVars](../dimensions/evar.md), finns kvar utanför den träff de är inställda på. Mätvärden som [sidvyer](page-views.md) och [förekomster](occurrences.md) räknar både inledande och beständiga värden. Det här måttet räknar inte beständiga värden.

## Jämför med liknande mätvärden

* **Förekomster kontra[förekomster](instances.md)**: Antal förekomster där ett dimensionsobjekt har angetts eller befunnits. Instanser omfattar inte träffar där en dimensionspost finns kvar.
* **Förekomster kontra[sidvyer](page-views.md)**: Förekomster omfattar alla träfftyper, inklusive spårningsanrop för sidvy ([`t()`](/help/implement/vars/functions/t-method.md)) och anrop för länkspårning ([`tl()`](/help/implement/vars/functions/tl-method.md)). Mätvärdet för sidvisningar inkluderar endast spårningsanrop för sidvy och utesluter anrop för länkspårning.