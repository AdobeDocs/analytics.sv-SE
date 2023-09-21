---
title: Avanmälan från samtyckeshantering
description: Se vilka sekretessinställningar en besökare valde ut.
exl-id: 2bf4d22c-5b24-47fb-b489-49388fcca5b1
feature: Dimensions
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '254'
ht-degree: 2%

---

# Avanmälan från samtyckeshantering

Medgivandehanteringsavanmälan [dimension](overview.md) visar vilka sekretessinställningar en besökare uttryckligen har avanmält sig från. Du kan använda den här dimensionen för att filtrera data baserat på sekretessinställningar eller se de vanligaste anledningarna till avanmälan av sekretess.

## Fyll den här dimensionen med data

Den här dimensionen samlar in data från följande [Sammanhangsdatavariabler](/help/implement/vars/page-vars/contextdata.md):

* `contextData.['cm.ssf']` när inställt på `1`. If `cm.ssf` är lika med `0` eller är tom gör den här variabeln ingenting.
* `contextData.['opt.dmp']` när inställt på `N`. If `opt.dmp` är lika med `Y`, [Medgivandehantering - anmälan](cm-opt-in.md) dimensionen fylls i i stället.
* `contextData.['opt.sell']` när inställt på `N`. If `opt.sell` är lika med `Y`, [Medgivandehantering - anmälan](cm-opt-in.md) dimensionen fylls i i stället.

Organisationen bestämmer logiken för att implementera dessa kontextdatavariabler. De finns inte kvar efter den träff som de är inställda på, så du måste ange varje kontextdatavariabel på varje sida.

## Dimensioner

Dimensionen innehåller följande tre värden:

* **`SSF`**: Besökaren valde bort från [Vidarebefordran på serversidan](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/c-server-side-forwarding/ssf.md). Dimensionsobjektet finns när kontextdatavariabeln `cm.ssf` är lika med `1`. Se [Översikt över dataintegritet](https://experienceleague.adobe.com/docs/audience-manager/user-guide/overview/data-privacy/data-privacy.html) i användarhandboken för Audience Manager om du vill ha mer information. Träffen vidarebefordras inte till Adobe Audience Manager.
* **`DMP`**: Besökaren valde bort från delning till datahanteringsplattformar. Dimensionsobjektet finns när kontextdatavariabeln `opt.dmp` är lika med `N`. Liknar `SSF`, skickas träffen inte vidare till Adobe Audience Manager.
* **`SELL`**: Besökaren valde att inte dela eller sälja uppgifterna till tredje part. Den här dimensionen visas när kontextdatavariabeln `opt.sell` är lika med `N`.
