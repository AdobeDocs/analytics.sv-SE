---
description: Lär dig hur du skapar en begäran om avvikelseidentifiering i Report Builder.
title: Konfigurera en begäran om avvikelseidentifiering
uuid: 1e504ff9-df88-4fa7-95ea-1ca05a6f9c0d
feature: Report Builder
role: User, Admin
exl-id: 0a8b1971-8d32-424a-9d41-d7ab2af54d1e
source-git-commit: 2eff7656741bdba3d5d7d1f33e9261b59f8e6083
workflow-type: tm+mt
source-wordcount: '173'
ht-degree: 0%

---

# Konfigurera en begäran om avvikelseidentifiering

Så här skapar du en begäran om avvikelseidentifiering i Report Builder:

1. Välj en trendrapport, till exempel en **[!UICONTROL Site Metrics]** > **[!UICONTROL Traffic]**-rapport.
1. Välj **[!UICONTROL Day]** på menyn [!UICONTROL Apply Granularity].

   >[!NOTE]
   >
   >Menyn [!UICONTROL Anomaly Detection] är bara tillgänglig när du väljer Daggranularitet. De föregående 30 dagarnas data används som utbildningsperiod för statistiska data, oavsett vilket datumintervall du väljer.

1. När du har konfigurerat datumintervall klickar du på **[!UICONTROL Next]**.

   I begärandeguiden: Steg 2 av 2 lägger du till ett mått, till exempel **[!UICONTROL Visits]**.

   Klicka på länken **[!UICONTROL None]** för det nya måttet.

   ![Skärmbild som visar avvikelseidentifiering infogar och infogar sedan alternativ för nedre och övre gräns och förväntas.](assets/anomaly_select.png)

1. Välj **[!UICONTROL Anomaly Detection]** > **[!UICONTROL `<selection>`]**.

   ![Skärmbild som visar Request Wizard Step 2 - Trafikrapport.](assets/anomaly_visit.png)

   När du väljer något av dessa alternativ skapas kopior av det ursprungliga måttet för avvikelseidentifiering. För Besök-måttet läggs till exempel ett värde för Lägre gräns för besök till i gruppen [!UICONTROL Metric].
1. Klicka på **[!UICONTROL Finish]** och markera cellen för utdata till Excel.

   Definitioner finns i [Analysidentifiering](/help/analyze/analysis-workspace/c-anomaly-detection/anomaly-detection.md).
