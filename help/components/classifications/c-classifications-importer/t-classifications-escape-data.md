---
description: Steg som beskriver hur klassificeringsdata kan undvikas i klassificeringsfilen.
subtopic: Classifications
title: Avbryta klassificeringsdata
topic: Admin tools
uuid: 724edcc5-4990-4f24-afbb-9aef301791a7
translation-type: tm+mt
source-git-commit: 6778dd290424651dc959224daa0eef8ebd8196e5
workflow-type: tm+mt
source-wordcount: '96'
ht-degree: 8%

---


# Avbryta klassificeringsdata

Steg som beskriver hur klassificeringsdata kan undvikas i klassificeringsfilen.

<!--Meike, please check this page against orginal. It might be missing information. -->

1. Kontrollera att klassificeringsfilformatet är v2.1.

   Om v2.1 är aktiverat visas en rad som liknar:

   >[!NOTE]
   >
   >Om du vill ange formatet v2.1 aktiverar du **[!UICONTROL Quoted Output]** när du exporterar filen på [!UICONTROL Classification Importer] sidan ( [!UICONTROL Browser Export] eller [!UICONTROL FTP Export]).

1. Omge fältet som innehåller specialtecken med citattecken (`"`).

Ett dubbelt citattecken kan visas i en escape-cell genom att det ersätts med två dubbla citattecken (`" "`). Exempel:

```
My String "of data"
```

Escaped skulle vara:

```
"My String ""of data"""
```
