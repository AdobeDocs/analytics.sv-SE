---
title: Instanser
description: Antalet träffar som en variabel har angetts (och inte befunnits).
feature: Metrics
exl-id: 9d1a66b5-46f9-4834-87a1-5f63e386e61d
source-git-commit: 813d209980ad02c412970a698c282c1358921ed6
workflow-type: tm+mt
source-wordcount: '263'
ht-degree: 0%

---

# Instanser

Instanserna [metrisk](overview.md) visar hur många gånger en dimension har definierats explicit i en bildbegäran. Vissa dimensioner, till exempel [eVars](../dimensions/evar.md), kvarstår dimensionsobjekt efter träffen de är inställda på. Det här måttet är användbart när du vill se hur många gånger en dimensionspost har angetts utan de träffar där värdet kvarstod.

## Hur det här måttet beräknas

Av alla träffar i en rapportserie ska du bara inkludera träffar som uttryckligen anger ett dimensionsobjekt i bildbegäran. Vissa dimensioner, till exempel [eVars](../dimensions/evar.md), finns kvar efter den träff de har angetts för. Mätvärden som [Sidvyer](page-views.md) och [Förekomster](occurrences.md) räknar både initiala och beständiga värden. Det här måttet räknar inte beständiga värden.

En besökare kommer till exempel till din webbplats och använder intern sökning. Du kan spåra intern sökning i eVar1. Efter att ha använt intern sökning en gång besöker de ytterligare fem sidor innan de går.

Om du visar en rapport i Workspace ser du en eVar1-instans och sex förekomster. En instans räknas på sökresultatsidan, medan förekomstmåttet räknar det ursprungliga värdet och efterföljande beständiga värden.

## Jämför med liknande mätvärden

* **Förekomster kontra [Förekomster](occurrences.md)**: Förekomster innehåller inte träffar där ett dimensionsobjekt finns. Antal förekomster där ett dimensionsobjekt har angetts eller befunnits.
* **Instanser kontra [Sidvyer](page-views.md)**: Förekomster omfattar alla träfftyper, inklusive spårningsanrop för sidvy ([`t()`](/help/implement/vars/functions/t-method.md)), länkspårningsanrop ([`tl()`](/help/implement/vars/functions/tl-method.md)) och data från sammanfattning [Datakällor](/help/import/data-sources/overview.md). Mätvärdet för sidvisningar inkluderar endast spårningsanrop för sidvy, exklusive länkspårningsanrop och sammanfattningsdatakällor.
