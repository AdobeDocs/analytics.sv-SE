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

Medgivandehanteringsavanmälan [dimension](overview.md) visar vilka sekretessinställningar en besökare har angett. Du kan använda den här dimensionen för att filtrera data baserat på sekretessinställningar eller se de vanligaste anledningarna till sekretessavanmälan.

## Fyll den här dimensionen med data

Den här dimensionen samlar in data från följande [kontextdatavariabler](/help/implement/vars/page-vars/contextdata.md):

* `contextData.['opt.dmp']` när värdet är `Y`. Om `opt.dmp` är lika med `N` fylls dimensionen [Medgivandehantering som avanmälan](cm-opt-out.md) i istället.
* `contextData.['opt.sell']` när värdet är `Y`. Om `opt.sell` är lika med `N` fylls dimensionen [Medgivandehantering som avanmälan](cm-opt-out.md) i istället.

Organisationen bestämmer logiken för att implementera dessa kontextdatavariabler. De finns inte kvar efter den träff som de är inställda på, så du måste ange varje kontextdatavariabel på varje sida.

## Dimensioner

Dimensionen innehåller följande två värden:

* **`DMP`**: Besökaren valde att dela till datahanteringsplattformar. Dimensionsobjektet finns när kontextdatavariabeln `opt.dmp` är lika med `Y`.
* **`SELL`**: Besökaren valde att dela eller sälja data till tredje part. Den här dimensionen finns när kontextdatavariabeln `opt.sell` är lika med `Y`.
