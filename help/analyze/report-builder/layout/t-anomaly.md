---
description: Steg som beskriver hur du skapar en begäran om avvikelseidentifiering i Report Builder.
title: Konfigurera en förfrågan om avvikelseidentifiering
uuid: 1e504ff9-df88-4fa7-95ea-1ca05a6f9c0d
feature: Report Builder
role: Affärsledare, administratör
translation-type: tm+mt
source-git-commit: 894ee7a8f761f7aa2590e06708be82e7ecfa3f6d
workflow-type: tm+mt
source-wordcount: '162'
ht-degree: 8%

---


# Konfigurera en förfrågan om avvikelseidentifiering

Steg som beskriver hur du skapar en begäran om avvikelseidentifiering i Report Builder.

1. Välj en trendrapport, till exempel en **[!UICONTROL Site Metrics]** > **[!UICONTROL Traffic]**-rapport.
1. Välj **[!UICONTROL Day]** på menyn [!UICONTROL Apply Granularity].

   >[!NOTE]
   >
   >Menyn [!UICONTROL Anomaly Detection] är bara tillgänglig när du väljer Daggranularitet. De föregående 30 dagarnas data används som utbildningsperiod för statistiska data, oavsett vilket datumintervall du väljer.

1. När du har konfigurerat datumintervall klickar du på **[!UICONTROL Next]**.

   Stegresultat 1. I Request Wizard: Steg 2 av 2, lägg till ett mått, till exempel **[!UICONTROL Visits]**.

   Stegresultat 1. Klicka på länken **[!UICONTROL None]** för att se det nya måttet.

   ![Stegresultat](assets/anomaly_select.png)

1. Välj **[!UICONTROL Anomaly Detection]** > **[!UICONTROL `<selection>`]**.

   ![Steginformation](assets/anomaly_visit.png)

   När du väljer något av dessa alternativ skapas kopior av det ursprungliga måttet för avvikelseidentifiering. För Besök-måttet läggs till exempel ett värde för Lägre bindningsbesök till i gruppen [!UICONTROL Metric].
1. Klicka på **[!UICONTROL Finish]** och markera cellen för utdata till Excel.

   Se [Analysidentifiering](/help/analyze/analysis-workspace/virtual-analyst/c-anomaly-detection/anomaly-detection.md) för definitioner.
