---
description: Administrativa steg för att skapa realtidsrapporter.
title: Konfiguration av rapporter i realtid
feature: Real-time
exl-id: e039ed67-3694-40fc-a4d9-3cb576e0535c
source-git-commit: a17297af84e1f5e7fe61f886eb3906c462229087
workflow-type: tm+mt
source-wordcount: '272'
ht-degree: 2%

---

# Konfiguration av rapporter i realtid

Administrativa steg för att skapa realtidsrapporter.

Att konfigurera realtidsrapporter i rapporter och analyser består av att välja rapportsviten och konfigurera upp till tre rapporter för den.

1. Välj den rapportsvit som du vill aktivera realtidsrapporter för.

   Navigera till **[!UICONTROL Analytics]** > **[!UICONTROL Reports]** > **[!UICONTROL View All Reports > Site Metrics]** > **[!UICONTROL Real-Time]** och väljer rapportsviten i listrutan högst upp:

   ![](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/realtime/assets/report_suite_selector.png)

   Om du försöker visa realtidsrapporter för en rapportserie som inte har konfigurerats för realtidsrapportering visas ett meddelande som gör att du kan konfigurera rapportsviten.

   ![](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/realtime/assets/rep_suite_not_set_up.png)

1. Klicka **[!UICONTROL Configure]** (kugghjulsikon) för att köra [!UICONTROL Report Suite Manager].

   (Även tillgängligt under **[!UICONTROL Analytics]** > **[!UICONTROL Admin > Report Suites]** > **[!UICONTROL Edit Settings]** > **[!UICONTROL Real-Time]**.)

1. Aktivera **[!UICONTROL Enable Real-Time]** inställning.
1. Ställ in datainsamling i realtid för upp till tre rapporter, med ett mått och tre dimensioner eller klassificeringar per rapport.

   ![](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/realtime/assets/real_time_admin.png)

   Information om vilka realtidsvärden och -dimensioner som stöds finns i [Mätvärden och Dimensioner som stöds](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/realtime/realtime-metrics.md).

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

1. Klicka **[!UICONTROL Save]** eller **[!UICONTROL Save and View Report]**.

   Efter den här initiala rapportkonfigurationen kan det ta upp till 20 minuter innan data börjar strömmas. Från och med då blir data omedelbart tillgängliga. Information om hur du visar realtidsrapporter finns i [Köra en realtidsrapport](https://experienceleague.adobe.com/docs/analytics/analyze/reports-analytics/t-running-report-types.html).

1. Som standard har alla användare åtkomst till realtidsrapporter.
