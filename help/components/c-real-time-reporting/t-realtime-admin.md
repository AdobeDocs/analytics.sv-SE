---
description: Administrativa steg för att skapa realtidsrapporter.
title: Konfigurera realtidsrapporter
feature: Real-time
exl-id: 9e7fc67c-71d5-465a-9553-5bb7e02a9bfd
source-git-commit: ee55349a8c676023a5ce33b56592cad7642199b8
workflow-type: tm+mt
source-wordcount: '272'
ht-degree: 0%

---

# Konfigurera realtidsrapporter

Följande information innehåller administrativa steg för att konfigurera realtidsrapporter.

Det består av att välja rapportsviten och konfigurera upp till tre rapporter för den.

1. Välj den rapportsvit som du vill aktivera realtidsrapporter för.

   1. I Analysis Workspace väljer du fliken [!UICONTROL **Workspace**] och sedan [!UICONTROL **Rapporter**] > [!UICONTROL **engagemang**] > **[!UICONTROL Real-Time]**.

   1. Välj rapportsviten i listrutan högst upp:

      ![](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/realtime/assets/report_suite_selector.png)

      Om du försöker visa realtidsrapporter för en rapportserie som inte har konfigurerats för realtidsrapportering visas ett meddelande som gör att du kan konfigurera rapportsviten.

      ![](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/realtime/assets/rep_suite_not_set_up.png)

1. Välj **[!UICONTROL Configure]** om du vill köra [!UICONTROL Report Suite Manager].

   (Även tillgängligt under **[!UICONTROL Analytics]** > **[!UICONTROL Admin > Report Suites]** > **[!UICONTROL Edit Settings]** > **[!UICONTROL Real-Time]**.)

1. Aktivera inställningen **[!UICONTROL Enable Real-Time]**.
1. Ställ in datainsamling i realtid för upp till tre rapporter, med ett mått och tre dimensioner eller klassificeringar per rapport.

   ![](assets/real_time_admin.png)

   Mer information om vilka realtidsmått och -mått som stöds finns i [Metrisk och Dimensioner som stöds](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/realtime/realtime-metrics.md).

   Om du har skapat klassificeringar visas de med indrag under den dimension som de definierats för:

   ![](assets/classifications.png)

   >[!NOTE]
   >
   >För en enda realtidsrapport stöder vi för närvarande inte aktivering av dubblettdimensioner, även om en annan klassificering väljs för varje dimension.

   Mer information om klassificeringar finns i [Om klassificeringar](/help/components/classifications/c-classifications.md).

   >[!NOTE]
   >
   >Vissa dimensioner, som &quot;Sök nyckelord&quot; eller &quot;Produkt&quot;, finns inte kvar i realtid på samma sätt som i andra delar av Adobe Analytics. När du väljer ett icke-beständigt mått visas följande varning:

   ![](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/realtime/assets/warning_dimensions.png)

1. Välj **[!UICONTROL Save]** eller **[!UICONTROL Save and View Report]**.

   Efter den här initiala rapportkonfigurationen kan det ta upp till 20 minuter innan data börjar strömmas. Från och med då blir data omedelbart tillgängliga. Mer information om hur du visar realtidsrapporter finns i [Kör en realtidsrapport](https://experienceleague.adobe.com/docs/analytics/analyze/reports-analytics/t-running-report-types.html).

1. Som standard har alla användare åtkomst till realtidsrapporter.
