---
description: Du kan ange ett datumintervall genom att markera celler i ett kalkylblad som innehåller en begäran. Report builder använder den specifika informationen om datumintervall i dessa begäranden. Om du väljer dagens datum visas deldata baserat på tidpunkten på dagen då begäran körs.
title: Datum från en cell
uuid: 0d9bf08d-d39d-4f37-94f1-232da0813245
feature: Report Builder
role: User, Admin
exl-id: e10573cc-984e-4202-a797-c2c9bec2af96
source-git-commit: e54b63bdfc32cf628ea1c6456df421b2d3d23b2c
workflow-type: tm+mt
source-wordcount: '170'
ht-degree: 0%

---

# Datum från en cell

Du kan ange ett datumintervall genom att markera celler i ett kalkylblad som innehåller en begäran. Report builder använder den specifika informationen om datumintervall i dessa begäranden. Om du väljer dagens datum visas deldata baserat på tidpunkten på dagen då begäran körs.

**Konfigurera datum från en cell**

1. På [!UICONTROL Request Wizard: Step 1], markera **[!UICONTROL Dates From Cell]**.
1. Ange cellreferenser i dialogrutan **[!UICONTROL From]** och **[!UICONTROL To]** eller klicka på väljaren och markera cellerna som innehåller förfrågningarna med start- och slutdatum.

   Skapa till exempel en Report Builder-begäran med datumintervallet inställt på&quot;igår&quot; och skriv ut begärandedatumet i samma cell som&quot;today()-1&quot;.

Här är en lista över datumformat som stöds:

![Skärmbild med datumformat som stöds.](assets/date-formats.png)

