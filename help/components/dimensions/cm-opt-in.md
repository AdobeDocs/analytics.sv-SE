---
title: Anmälan till samtyckeshantering
description: Se vilka sekretessinställningar en besökare valde.
source-git-commit: 49b2c144fea5786564ccb6dc70adead3bc669596
workflow-type: tm+mt
source-wordcount: '182'
ht-degree: 3%

---

# Anmälan till samtyckeshantering

Dimensionen för hantering av medgivande visar vilka sekretessinställningar en besökare har angett. Du kan använda den här dimensionen för att filtrera data baserat på sekretessinställningar eller se de vanligaste anledningarna till sekretessavanmälan.

## Fyll den här dimensionen med data

Den här dimensionen samlar in data från följande [Sammanhangsdatavariabler](/help/implement/vars/page-vars/contextdata.md):

* `contextData.['opt.dmp']` när inställt på `Y`. If `opt.dmp` är lika med `N`, [Medgivandehantering avanmäl dig](cm-opt-out.md) dimensionen fylls i i stället.
* `contextData.['opt.sell']` när inställt på `Y`. If `opt.sell` är lika med `N`, [Medgivandehantering avanmäl dig](cm-opt-out.md) dimensionen fylls i i stället.

Organisationen bestämmer logiken för att implementera dessa kontextdatavariabler. De finns inte kvar efter den träff som de är inställda på, så du måste ange varje kontextdatavariabel på varje sida.

## Dimensioner

Dimensionen innehåller följande två värden:

* **`DMP`**: Besökaren valde att dela till datahanteringsplattformar. Dimensionsobjektet finns när kontextdatavariabeln `opt.dmp` är lika med `Y`.
* **`SELL`**: Besökaren valde att dela eller sälja data till tredje part. Den här dimensionen visas när kontextdatavariabeln `opt.sell` är lika med `Y`.
