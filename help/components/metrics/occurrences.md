---
title: Förekomster
description: Antalet träffar som en variabel har angetts eller befunnits vara.
feature: Metrics
exl-id: 8428e813-0fb4-4620-884e-1aa92fe33209
source-git-commit: 0c5062363e10d9b545a3209ebaefcc6fa5d02c8b
workflow-type: tm+mt
source-wordcount: '280'
ht-degree: 0%

---

# Förekomster

&#39;Förekomsterna&#39; [metrisk](overview.md) visar antalet träffar där en given dimension har angetts eller sparats. När du drar en dimension i Workspace till en tom arbetsyta, använder Adobe automatiskt detta mått på projektet.

## Hur det här måttet beräknas

Av alla träffar i en rapportsserie ska du ta med träffar där ett dimensionsobjekt definieras eller bevaras. Vissa dimensioner, till exempel [eVars](../dimensions/evar.md), finns kvar efter den träff de har angetts för. Det här måttet räknar både initiala och beständiga värden.

## Jämför med liknande mätvärden

* **Förekomster kontra [Förekomster](instances.md)**: Antal förekomster där ett dimensionsobjekt har angetts eller befunnits. Instanser omfattar inte träffar där en dimensionspost finns kvar.
* **Förekomster kontra [Sidvyer](page-views.md)**: Förekomsterna innehåller alla träfftyper, inklusive spårningsanrop för sidvy ([`t()`](/help/implement/vars/functions/t-method.md)), länkspårningsanrop ([`tl()`](/help/implement/vars/functions/tl-method.md)) och data från sammanfattningen [Datakällor](/help/import/data-sources/overview.md). Mätvärdet för sidvisningar inkluderar endast spårningsanrop för sidvy, exklusive länkspårningsanrop och sammanfattningsdatakällor.

## Persistence

Persistence är möjligheten för ett givet dimensionsvärde att relatera till ett mätvärde efter händelsen det är inställt på. Den använder en kombination av allokering och förfallodatum. Allokering låter dig avgöra vilket värde som behålls när mer än en dimensionspost kan finnas i taget i en enda kolumn. Med Förfallotid kan du bestämma hur länge en dimensionspost ska vara kvar efter den händelse den är inställd på.

Persistence är bara tillgängligt för dimensioner och är retroaktivt för de data det tillämpas på. Det är en omedelbar dataomvandling som sker innan filtrering eller andra analysåtgärder tillämpas. Om persistence inte är aktiverat, relaterar dimensionen endast till mått som finns i samma händelse.