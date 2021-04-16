---
description: Steg som beskriver hur klassificeringsdata kan undvikas i klassificeringsfilen.
subtopic: Classifications
title: Avbryta klassificeringsdata
feature: Administratörsverktyg
uuid: 724edcc5-4990-4f24-afbb-9aef301791a7
exl-id: 0d3a0e91-5537-43ee-bd28-9907ee6eb331
translation-type: tm+mt
source-git-commit: 78412c2588b07f47981ac0d953893db6b9e1d3c2
workflow-type: tm+mt
source-wordcount: '98'
ht-degree: 10%

---

# Avbryta klassificeringsdata

Steg som beskriver hur klassificeringsdata kan undvikas i klassificeringsfilen.

<!--Meike, please check this page against orginal. It might be missing information. -->

1. Kontrollera att klassificeringsfilformatet är v2.1.

   Om v2.1 är aktiverat visas en rad som liknar:

   >[!NOTE]
   >
   >Om du vill ange formatet v2.1 aktiverar du **[!UICONTROL Quoted Output]** när du exporterar filen på [!UICONTROL Classification Importer]-sidan ( [!UICONTROL Browser Export] eller [!UICONTROL FTP Export]).

1. Omge fältet som innehåller specialtecken med citattecken (`"`).

Ett dubbelt citattecken kan visas i en escape-cell genom att det ersätts med två citattecken (`" "`). Exempel:

```
My String "of data"
```

Escaped skulle vara:

```
"My String ""of data"""
```
