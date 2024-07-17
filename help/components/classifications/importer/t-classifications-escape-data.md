---
description: Steg som beskriver hur klassificeringsdata kan undvikas i klassificeringsfilen.
title: Escape-klassificeringsdata
feature: Classifications
exl-id: 0d3a0e91-5537-43ee-bd28-9907ee6eb331
source-git-commit: ce7f953b8f7f1f7d0616074454e4401937fcc0c7
workflow-type: tm+mt
source-wordcount: '92'
ht-degree: 2%

---

# Escape-klassificeringsdata

Så här undviker du klassificeringsdata i klassificeringsfilen:

<!--Meike, please check this page against orginal. It might be missing information. -->

1. Kontrollera att klassificeringsfilformatet är v2.1.

   Om v2.1 är aktiverat visas en rad som liknar:

   >[!NOTE]
   >
   >Om du vill ange formatet v2.1 aktiverar du **[!UICONTROL Quoted Output]** när du exporterar filen på [!UICONTROL Classification Importer]-sidan ( [!UICONTROL Browser Export] eller [!UICONTROL FTP Export]).

1. Omge fältet som innehåller specialtecken med dubbla citattecken (`"`).

Ett dubbelt citattecken kan förekomma i en escape-cell genom att ersätta det med två dubbla citattecken (`" "`). Exempel:

```
My String "of data"
```

Escaped skulle vara:

```
"My String ""of data"""
```
