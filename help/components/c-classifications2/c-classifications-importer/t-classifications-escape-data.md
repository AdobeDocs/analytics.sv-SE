---
description: Steg som beskriver hur klassificeringsdata kan undvikas i klassificeringsfilen.
subtopic: Classifications
title: Escape-klassificeringsdata
topic: Admin tools
uuid: 724edcc5-4990-4f24-afbb-9aef301791a7
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Escape-klassificeringsdata

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
