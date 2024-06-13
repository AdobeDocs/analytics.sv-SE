---
description: Skapa, redigera eller ta bort aviseringar.
title: Varningshanteraren (Analysis Workspace)
feature: Alerts
role: User, Admin
exl-id: c33a9a30-f53f-443c-96b7-6a87d03573c7
source-git-commit: 58e1d3025b455de7fa07037b3b0659330c8324c7
workflow-type: tm+mt
source-wordcount: '323'
ht-degree: 0%

---


# Hantera aviseringar

Du kan hantera befintliga aviseringar i Varningshanteraren. Du kan utföra olika hanteringsåtgärder för varningar, som taggning, namnbyte, borttagning med mera.

Varningshanteraren är mycket strukturerad som [Segmenthanteraren](https://experienceleague.adobe.com/docs/analytics/components/segmentation/segmentation-workflow/seg-manage.html) och [Beräknad måtthanterare](https://experienceleague.adobe.com/docs/analytics/components/calculated-metrics/calcmetric-workflow/cm-manager.html).

## Skapa aviseringar

Så här skapar du aviseringar från Alerts Manager:

1. Välj **[!UICONTROL Components]** > **[!UICONTROL Alerts]** för att få tillgång till Alerts Manager i Adobe Analytics.

   ![](assets/alert-manager.png)

1. Välj [!UICONTROL **Lägg till**] (eller [!UICONTROL **Skapa ny avisering**] om du inte har några befintliga aviseringar).

1. Välj den varningstyp som motsvarar den varning som du vill skapa:

   * [!UICONTROL **Varning om analysdata**]: En varning som meddelar dig när onormala händelser inträffar i dina data.

     Om du väljer det här alternativet fortsätter du med [Skapa aviseringar](/help/analyze/analysis-workspace/c-intelligent-alerts/alert-builder.md) om du vill ha mer information om hur du skapar varningar.

   * [!UICONTROL **Användningsvarning för serversamtal**]: En varning som meddelar dig om risken eller förekomsten av en överbelastning i serveranropets förbrukning och åtagandedata.

     Om du väljer det här alternativet fortsätter du med [Användningsvarningar för serversamtal](/help/admin/admin/c-server-call-usage/scu-alerts.md).

     >[!NOTE]
     >
     >Du måste vara Analytics-administratör eller en användare med användarbehörighet för serversamtal för att få åtkomst till serversamtalsanvändning.




## Hantera befintliga aviseringar

Så här hanterar du befintliga aviseringar i Varningshanteraren:

1. Välj **[!UICONTROL Components]** > **[!UICONTROL Alerts]** för att få tillgång till Alerts Manager i Adobe Analytics.

   ![](assets/alert-manager.png)

1. Välj en eller flera aviseringar som du vill hantera.

   ![](assets/alert-manager-tasks.png)

1. Välj något av följande alternativ i åtgärdsfältet:

   | Åtgärd | Funktion |
   |---------|----------|
   | [!UICONTROL **Tagg**] | Använd en tagg på en varning. Det gör det enklare att ordna varningar. |
   | [!UICONTROL **Ta bort**] | Tar bort varningen. |
   | [!UICONTROL **Byt namn**] | Byter namn på aviseringen. |
   | [!UICONTROL **Godkänn**] | Markera aviseringen som Godkänd. |
   | [!UICONTROL **Kopiera**] | Skapar en kopia (dubblett) av varningen. |
   | [!UICONTROL **Inaktivera**] | Inaktiverar en avisering som är aktiverad. |
   | [!UICONTROL **Aktivera**] | Aktiverar en varning som är inaktiverad. |
   | [!UICONTROL **Förnya**] | Förnyar aviseringens förfallodatum. Detta utökar förfallodatumet till 1 år från den dag du valde det här alternativet, oavsett det ursprungliga förfallodatumet. |
   | [!UICONTROL **Exportera till CSV**] | Exporterar varningen till en CSV-fil. |
