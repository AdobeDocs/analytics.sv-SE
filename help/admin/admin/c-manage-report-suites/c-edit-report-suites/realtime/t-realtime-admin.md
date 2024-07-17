---
description: Administrativa steg för att skapa realtidsrapporter.
title: Konfiguration av rapporter i realtid
feature: Real-time
exl-id: e039ed67-3694-40fc-a4d9-3cb576e0535c
source-git-commit: f1dde3a475fe1276fd9abbe1bdafd6723701f2cb
workflow-type: tm+mt
source-wordcount: '207'
ht-degree: 1%

---

# Konfiguration av rapporter i realtid

Administrativa steg för att skapa realtidsrapporter.

Du skapar realtidsrapporter i Adobe Analytics genom att välja rapportsviten och konfigurera upp till tre rapporter för den. Som standard har alla användare åtkomst till realtidsrapporter.

1. Välj den rapportsvit som du vill aktivera realtidsrapporter för.

   Navigera till **[!UICONTROL Analytics]** > **[!UICONTROL Admin > Report Suites]**.

1. Klicka på **[!UICONTROL Edit Settings]** > **[!UICONTROL Real-Time]**.

1. Ställ in datainsamling i realtid för upp till tre rapporter, med ett mått och tre dimensioner eller klassificeringar per rapport.

   ![](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/realtime/assets/real_time_admin.png)

   Mer information om vilka realtidsmått och -mått som stöds finns i [Metrisk och Dimensioner som stöds](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/realtime/realtime-metrics.md).

   Om du har skapat klassificeringar visas de med indrag under den dimension som de definierats för:

   ![](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/realtime/assets/classifications.png)

   >[!NOTE]
   >
   >För en enda realtidsrapport stöder vi för närvarande inte aktivering av dubblettdimensioner, även om en annan klassificering väljs för varje dimension.

   Mer information om klassificeringar finns i [Om klassificeringar](/help/components/classifications/c-classifications.md).

   >[!NOTE]
   >
   >Vissa dimensioner, som &quot;Sök nyckelord&quot; eller &quot;Produkt&quot;, finns inte kvar i realtid på samma sätt som i andra delar av Adobe Analytics. När du väljer ett icke-beständigt mått visas följande varning:

   ![](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/realtime/assets/warning_dimensions.png)

1. Klicka på **[!UICONTROL Save]**.

   Efter den här initiala rapportkonfigurationen kan det ta upp till 20 minuter innan data börjar strömmas. Från och med då blir data omedelbart tillgängliga.

1. Om du vill visa realtidsrapporten går du till:

   **[!UICONTROL Workspace]** > **[!UICONTROL Reports]** > **[!UICONTROL Engagement]** > **[!UICONTROL Real-Time]**.

