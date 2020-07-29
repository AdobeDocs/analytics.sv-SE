---
description: Administrativa steg för att skapa realtidsrapporter.
title: Konfiguration av rapporter i realtid
topic: Admin tools
uuid: f48692a0-77c0-4ee4-b3ec-eaa842d06ac8
translation-type: tm+mt
source-git-commit: 6778dd290424651dc959224daa0eef8ebd8196e5
workflow-type: tm+mt
source-wordcount: '274'
ht-degree: 2%

---


# Konfiguration av rapporter i realtid

Administrativa steg för att skapa realtidsrapporter.

Du skapar realtidsrapporter i Rapporter och Analytics genom att välja rapportsviten och konfigurera upp till tre rapporter för den.

1. Välj den rapportsvit som du vill aktivera realtidsrapporter för.

   Navigera till **[!UICONTROL Analytics]** > **[!UICONTROL Reports]** > **[!UICONTROL View All Reports > Site Metrics]** > **[!UICONTROL Real-Time]** och välj rapportsviten i listrutan högst upp:

   ![](assets/report_suite_selector.png)

   Om du försöker visa realtidsrapporter för en rapportserie som inte har konfigurerats för realtidsrapportering visas ett meddelande som gör att du kan konfigurera rapportsviten.

   ![](assets/rep_suite_not_set_up.png)

1. Klicka **[!UICONTROL Configure]** (kugghjulsikon) för att köra [!UICONTROL Report Suite Manager].

   (Även tillgängligt under **[!UICONTROL Analytics]** > **[!UICONTROL Admin > Report Suites]** > **[!UICONTROL Edit Settings]** > **[!UICONTROL Real-Time]**.)

1. Aktivera **[!UICONTROL Enable Real-Time]** inställningen.
1. Ställ in datainsamling i realtid för upp till tre rapporter, med ett mått och tre dimensioner eller klassificeringar per rapport.

   ![](assets/real_time_admin.png)

   Mer information om vilka realtidsmått och -mått som stöds finns i [Metrisk och Dimensioner](/help/admin/admin/realtime/realtime-metrics.md)som stöds.

   Om du har skapat klassificeringar visas de med indrag under den dimension som de definierats för:

   ![](assets/classifications.png)

   >[!NOTE]
   >
   >För en enda realtidsrapport stöder vi för närvarande inte aktivering av dubblettdimensioner, även om en annan klassificering väljs för varje dimension.

   Mer information om klassificeringar finns i [Om klassificeringar](/help/components/classifications/c-classifications.md).

   >[!NOTE]
   >
   >Vissa dimensioner, som &quot;Sök nyckelord&quot; eller &quot;Produkt&quot;, finns inte kvar i realtid på samma sätt som i andra delar av Adobe Analytics. När du väljer ett icke-beständigt mått visas följande varning:

   ![](assets/warning_dimensions.png)

1. Klicka på **[!UICONTROL Save]** eller **[!UICONTROL Save and View Report]**.

   Efter den här initiala rapportkonfigurationen kan det ta upp till 20 minuter innan data börjar strömmas. Från och med då blir data omedelbart tillgängliga. Mer information om hur du visar realtidsrapporter finns i [Köra en realtidsrapport](https://docs.adobe.com/content/help/en/analytics/analyze/reports-analytics/t-running-report-types.html).

1. Som standard har alla användare åtkomst till realtidsrapporter.
