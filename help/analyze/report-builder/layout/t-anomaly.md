---
description: Steg som beskriver hur du skapar en begäran om avvikelseidentifiering i Report Builder.
title: Konfigurera en förfrågan om avvikelseidentifiering
uuid: 1e504ff9-df88-4fa7-95ea-1ca05a6f9c0d
feature: Report Builder
role: User, Admin
exl-id: 0a8b1971-8d32-424a-9d41-d7ab2af54d1e
source-git-commit: ce7f953b8f7f1f7d0616074454e4401937fcc0c7
workflow-type: tm+mt
source-wordcount: '153'
ht-degree: 7%

---

# Konfigurera en förfrågan om avvikelseidentifiering

Så här skapar du en begäran om avvikelseidentifiering i Report Builder:

1. Välj en trendrapport, till exempel en **[!UICONTROL Site Metrics]** > **[!UICONTROL Traffic]** rapport.
1. I [!UICONTROL Apply Granularity] meny, välja **[!UICONTROL Day]**.

   >[!NOTE]
   >
   >The [!UICONTROL Anomaly Detection] -menyn är bara tillgänglig när du väljer Daggranularitet. De föregående 30 dagarnas data används som utbildningsperiod för statistiska data, oavsett vilket datumintervall du väljer.

1. När du har konfigurerat datumintervall klickar du på **[!UICONTROL Next]**.

   Stegresultat 1. I Request Wizard: Steg 2 av 2, lägg till ett mått, som **[!UICONTROL Visits]**.

   Stegresultat 1. Klicka på knappen **[!UICONTROL None]** länk.

   ![Stegresultat](assets/anomaly_select.png)

1. Välj **[!UICONTROL Anomaly Detection]** > **[!UICONTROL `<selection>`]**.

   ![Steginformation](assets/anomaly_visit.png)

   När du väljer något av dessa alternativ skapas kopior av det ursprungliga måttet för avvikelseidentifiering. För Besök-måttet läggs till exempel ett värde för Lägre bindningsbesök till i [!UICONTROL Metric] grupp.
1. Klicka **[!UICONTROL Finish]** och markera cellen för utdata till Excel.

   Se [Analysidentifiering](/help/analyze/analysis-workspace/virtual-analyst/c-anomaly-detection/anomaly-detection.md) för definitioner.
