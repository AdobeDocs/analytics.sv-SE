---
description: Steg som beskriver hur du skapar en begäran om avvikelseidentifiering i Report Builder.
title: Konfigurera en begäran om avvikelseidentifiering
topic: Report builder
uuid: 1e504ff9-df88-4fa7-95ea-1ca05a6f9c0d
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Konfigurera en begäran om avvikelseidentifiering

Steg som beskriver hur du skapar en begäran om avvikelseidentifiering i Report Builder.

1. Välj en trendrapport, t.ex. en **[!UICONTROL Site Metrics]** > **[!UICONTROL Traffic]** rapport.
1. Välj på [!UICONTROL Apply Granularity] menyn **[!UICONTROL Day]**.

   >[!NOTE]
   >
   >Menyn är bara tillgänglig när du väljer daggranularitet. [!UICONTROL Anomaly Detection] De föregående 30 dagarnas data används som utbildningsperiod för statistiska data, oavsett vilket datumintervall du väljer.

1. När du har konfigurerat datumintervall klickar du på **[!UICONTROL Next]**.

   Stegresultat 1. I Request Wizard: Steg 2 av 2, lägg till ett mätvärde, till exempel **[!UICONTROL Visits]**.

   Stegresultat 1. Klicka på **[!UICONTROL None]** länken om du vill se det nya måttet.

   ![Stegresultat](assets/anomaly_select.png)

1. Välj **[!UICONTROL Anomaly Detection]** > **[!UICONTROL `<selection>`]**.

   ![Steginformation](assets/anomaly_visit.png)

   När du väljer något av dessa alternativ skapas kopior av det ursprungliga måttet för avvikelseidentifiering. För Besök-måttet läggs till exempel ett värde för Lägre bindningsbesök till i [!UICONTROL Metric] gruppen.
1. Klicka på **[!UICONTROL Finish]** och markera cellen för utdata till Excel.

   Definitioner finns i [avvikelseidentifiering](/help/analyze/analysis-workspace/virtual-analyst/c-anomaly-detection/anomaly-detection.md) .
