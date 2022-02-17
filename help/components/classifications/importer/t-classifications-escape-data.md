---
description: Steg som beskriver hur klassificeringsdata kan undvikas i klassificeringsfilen.
title: Avbryta klassificeringsdata
feature: Classifications
exl-id: 0d3a0e91-5537-43ee-bd28-9907ee6eb331
source-git-commit: 35413ac43eed5ab7218794f26e4753acf08f18ee
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
   >Om du vill ange ett format för v2.1 aktiverar du **[!UICONTROL Quoted Output]** vid export av filen på [!UICONTROL Classification Importer] sida ( [!UICONTROL Browser Export] eller [!UICONTROL FTP Export]).

1. Omge fältet som innehåller specialtecken med citattecken (`"`).

Ett dubbelt citattecken kan visas i en escape-cell genom att det ersätts med två dubbla citattecken (`" "`). Exempel:

```
My String "of data"
```

Escaped skulle vara:

```
"My String ""of data"""
```
