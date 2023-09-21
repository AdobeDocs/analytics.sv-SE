---
title: Anmälan till samtyckeshantering
description: Se vilka sekretessinställningar en besökare valde.
exl-id: b2768180-b763-41fb-8cba-665fac047e29
feature: Dimensions
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '182'
ht-degree: 3%

---

# Anmälan till samtyckeshantering

Medgivandehanteringsanmälan [dimension](overview.md) visar vilka sekretessinställningar som en besökare har valt. Du kan använda den här dimensionen för att filtrera data baserat på sekretessinställningar eller se de vanligaste anledningarna till sekretessavanmälan.

## Fyll den här dimensionen med data

Den här dimensionen samlar in data från följande [Sammanhangsdatavariabler](/help/implement/vars/page-vars/contextdata.md):

* `contextData.['opt.dmp']` när inställt på `Y`. If `opt.dmp` är lika med `N`, [Medgivandehantering avanmäl dig](cm-opt-out.md) dimensionen fylls i i stället.
* `contextData.['opt.sell']` när inställt på `Y`. If `opt.sell` är lika med `N`, [Medgivandehantering avanmäl dig](cm-opt-out.md) dimensionen fylls i i stället.

Organisationen bestämmer logiken för att implementera dessa kontextdatavariabler. De finns inte kvar efter den träff som de är inställda på, så du måste ange varje kontextdatavariabel på varje sida.

## Dimensioner

Dimensionen innehåller följande två värden:

* **`DMP`**: Besökaren valde att dela till datahanteringsplattformar. Dimensionsobjektet finns när kontextdatavariabeln `opt.dmp` är lika med `Y`.
* **`SELL`**: Besökaren valde att dela eller sälja data till tredje part. Den här dimensionen visas när kontextdatavariabeln `opt.sell` är lika med `Y`.
