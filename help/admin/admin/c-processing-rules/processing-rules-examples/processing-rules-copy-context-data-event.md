---
description: Bearbetningsregler kan utlösa händelser baserade på kontextdatavariabler.
subtopic: Processing rules
title: Ange en händelse med hjälp av en kontextdatavariabel
feature: Administratörsverktyg
uuid: 4a6018eb-03e2-4ec8-874b-e48bf716e103
exl-id: f0af0e23-c08a-4f82-85b4-25064eeaa3c6
translation-type: tm+mt
source-git-commit: 78412c2588b07f47981ac0d953893db6b9e1d3c2
workflow-type: tm+mt
source-wordcount: '160'
ht-degree: 12%

---

# Ange en händelse med hjälp av en kontextdatavariabel

Bearbetningsregler kan utlösa händelser baserade på kontextdatavariabler.

Kontextdatavariabler anges i AppMeasurement i följande format:

```
 s.contextData['search_term']
```

Listan [!UICONTROL Context Variables] innehåller alla variabler som har skickats till rapportsviten under de senaste 30 dagarna. Om du känner till namnet på kontextdatavariabeln men inte har skickat den till den aktuella rapportsviten kan du lägga till ett värde genom att skriva variabelnamnet och klicka på **[!UICONTROL Add variable name context data]**:

![](assets/add-context-variable.png)

Följande regeldefinition utökas på [Kopiera en kontextdatavariabel till en eVar](/help/admin/admin/c-processing-rules/processing-rules-examples/processing-rules-copy-context-data.md)-regel för att även ange en händelse för varje träff som innehåller en specifik kontextdatavariabel:

| Regeluppsättning | Värde |
|---|---|
| Villkor | Om kontextdata för &#39;search_term&#39; har angetts |
| Åtgärd | Ange händelsen &#39;searches&#39; |

Exempel:

![](assets/processing_rule_set_event.png)

Se [Kontextdatavariabler](https://docs.adobe.com/content/help/en/analytics/implementation/vars/page-vars/contextdata.html) i implementeringshjälpen.
