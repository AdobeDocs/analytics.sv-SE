---
title: Instanser
description: Antalet träffar som en variabel har angetts (och inte befunnits).
feature: Metrics
exl-id: 9d1a66b5-46f9-4834-87a1-5f63e386e61d
source-git-commit: 7d5383e1ee3bee189d3dd48bc6b899f4108f7ba8
workflow-type: tm+mt
source-wordcount: '129'
ht-degree: 1%

---

# Instanser

Måttet Instances visar hur många gånger en dimension uttryckligen definierades i en bildbegäran. Vissa dimensioner, till exempel [eVars](../dimensions/evar.md), bibehåll dimensionsobjekt efter den träff de ställs in på. Det här måttet är användbart när du vill se hur många gånger en dimensionspost har angetts utan de träffar där värdet kvarstod.

## Hur det här måttet beräknas

Av alla träffar i en rapportserie ska du bara inkludera träffar som uttryckligen anger ett dimensionsobjekt i bildbegäran. Vissa dimensioner, till exempel [eVars](../dimensions/evar.md), kvarstår utanför den träff de är inställda på. Mätvärden som [Sidvyer](page-views.md) och [Förekomster](occurrences.md) antal både initiala och beständiga värden. Det här måttet räknar inte beständiga värden.
