---
description: Efter distributionen bör du verifiera att integreringen kan överföra data genom följande kontroller.
title: Verifiera integreringen
uuid: 5f0f9f69-e932-4472-8578-dd3af1315c0c
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Verifiera integreringen{#verifying-the-integration}

Efter distributionen bör du verifiera att integreringen kan överföra data genom följande kontroller.

1. Visa integreringsaktivitetsloggen.
   1. Navigera till **[!UICONTROL Support]** > **[!UICONTROL Integration Activity Log]** i Adobe Experience Cloud.

      ![](assets/integration_activity_log.png)

   1. Sök efter poster som **[!UICONTROL Classification Data imported successfully]**, **[!UICONTROL Metrics Data imported successfully]** och **[!UICONTROL Metric Data exported successfully]**. Dessa poster ska visas inom 1 dag efter slutförd distribution.
1. Visa dina rapportdata i Adobe Analytics.

   1. Navigera till **[!UICONTROL Custom Conversion]** > **[!UICONTROL Custom Conversion 1-10]** > **[!UICONTROL Message ID Reports]**.

      ![](assets/reporting.png)

   1. Leta efter svarsrapportering. Dessa data ska visas inom 24-48 timmar efter att distributionen lyckades.
