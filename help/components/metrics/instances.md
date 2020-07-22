---
title: Instanser
description: Antalet träffar som en variabel har angetts (och inte befunnits).
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '129'
ht-degree: 1%

---


# Instanser

Måttet Instances visar hur många gånger en dimension uttryckligen definierades i en bildbegäran. Vissa dimensioner, till exempel [eVars](../dimensions/evar.md), behåller dimensionsobjekt efter träffen som de är inställda på. Det här måttet är användbart när du vill se hur många gånger en dimensionspost har angetts utan de träffar där värdet kvarstod.

## Hur det här måttet beräknas

Av alla träffar i en rapportserie ska du bara inkludera träffar som uttryckligen anger ett dimensionsobjekt i bildbegäran. Vissa dimensioner, till exempel [eVars](../dimensions/evar.md), finns kvar utanför den träff de är inställda på. Mätvärden som [sidvyer](page-views.md) och [förekomster](occurrences.md) räknar både inledande och beständiga värden. Det här måttet räknar inte beständiga värden.