---
title: Avanmälan från samtyckeshantering
description: Se vilka sekretessinställningar en besökare valde ut.
exl-id: 2bf4d22c-5b24-47fb-b489-49388fcca5b1
feature: Dimensions
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '247'
ht-degree: 2%

---

# Avanmälan från samtyckeshantering

Medgivandehanteringsavanmälan [dimension](overview.md) visar vilka sekretessinställningar en besökare uttryckligen har avanmält sig från. Du kan använda den här dimensionen för att filtrera data baserat på sekretessinställningar eller se de vanligaste anledningarna till avanmälan av sekretess.

## Fyll den här dimensionen med data

Den här dimensionen samlar in data från följande [kontextdatavariabler](/help/implement/vars/page-vars/contextdata.md):

* `contextData.['cm.ssf']` när värdet är `1`. Om `cm.ssf` är lika med `0` eller är tom händer ingenting.
* `contextData.['opt.dmp']` när värdet är `N`. Om `opt.dmp` är lika med `Y` fylls dimensionen [Medgivandehantering ](cm-opt-in.md) i istället.
* `contextData.['opt.sell']` när värdet är `N`. Om `opt.sell` är lika med `Y` fylls dimensionen [Medgivandehantering ](cm-opt-in.md) i istället.

Organisationen bestämmer logiken för att implementera dessa kontextdatavariabler. De finns inte kvar efter den träff som de är inställda på, så du måste ange varje kontextdatavariabel på varje sida.

## Dimension-objekt

Följande tre värden ingår i Dimension:

* **`SSF`**: Besökaren avanmälde sig från [Vidarebefordran på serversidan](/help/admin/tools/manage-rs/edit-settings/general/c-server-side-forwarding/ssf.md). Dimensionsobjektet finns när kontextdatavariabeln `cm.ssf` är lika med `1`. Mer information finns i [Översikt över datasekretess](https://experienceleague.adobe.com/docs/audience-manager/user-guide/overview/data-privacy/data-privacy.html) i användarhandboken för Audience Manager. Träffen vidarebefordras inte till Adobe Audience Manager.
* **`DMP`**: Besökaren valde bort från delning till datahanteringsplattformar. Dimensionsobjektet finns när kontextdatavariabeln `opt.dmp` är lika med `N`. På samma sätt som `SSF` vidarebefordras träffen inte till Adobe Audience Manager.
* **`SELL`**: Besökaren valde att inte dela eller sälja data till tredje part. Den här dimensionen finns när kontextdatavariabeln `opt.sell` är lika med `N`.
