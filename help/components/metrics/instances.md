---
title: Instanser
description: Antalet träffar som en variabel har angetts (och inte befunnits).
translation-type: tm+mt
source-git-commit: 554ced510600a4d5866e89806b058b5d2d9a3edf
workflow-type: tm+mt
source-wordcount: '129'
ht-degree: 1%

---


# Instanser

Måttet Instances visar hur många gånger en dimension uttryckligen definierades i en bildbegäran. Vissa dimensioner, till exempel [eVars](../dimensions/evar.md), behåller dimensionsvärden efter träffen som de är inställda på. Det här måttet är användbart när du vill se hur många gånger ett dimensionsvärde har ställts in utan att träffarna där värdet kvarstod var.

## Hur det här måttet beräknas

Av alla träffar i en rapportserie ska du bara inkludera träffar som uttryckligen anger ett dimensionsvärde i bildbegäran. Vissa dimensioner, till exempel [eVars](../dimensions/evar.md), finns kvar utanför den träff de är inställda på. Mätvärden som [sidvyer](page-views.md) och [förekomster](occurrences.md) räknar både inledande och beständiga värden. Det här måttet räknar inte beständiga värden.