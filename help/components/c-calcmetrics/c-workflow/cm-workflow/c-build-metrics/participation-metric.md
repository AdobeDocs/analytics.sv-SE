---
description: Med verktyget Beräknade mätvärden kan vem som helst skapa ett deltagandemått.
title: Deltagandemått
feature: Calculated Metrics
exl-id: bef185d6-72c0-4068-80f8-57261369573f
source-git-commit: 183f6e39fb1d14b7b29817e76da0302ba23cd5d6
workflow-type: tm+mt
source-wordcount: '179'
ht-degree: 0%

---

# Deltagandestatistik


Deltagandestatistik används för att kvantifiera hur enskilda värden för en dimension (som sidvyer) bidrar till eller deltar i besök som innehåller ett visst mått (som beställningar).

Stegen nedan visar hur du kan skapa ett deltagandemått.

1. [Skapa ett beräknat mått](../cm-workflow.md) och i [verktyget för beräknade värden](cm-build-metrics.md) namnger du måttet `Orders (Visit Participation)` eller något liknande.
1. Dra ett mätvärde som innehåller en lyckad händelse, till exempel [!DNL Online Orders], till området [!UICONTROL **[!UICONTROL Definition]**].
1. Välj ![Kugga](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Settings_18_N.svg) för måttet.
1. I popup-fönstret som visas väljer du **[!UICONTROL Use a non-default attribution model]** för att definiera [-attribueringsmodellen](m-metric-type-alloc.md#attribution-models) för den händelsen till **[!UICONTROL Participation]** och väljer **[!UICONTROL Visits]** för [!UICONTROL Container]. Bekräfta genom att välja **[!UICONTROL Apply]**.


   ![Popup-meny för kolumnattribueringsmodell med deltagande valt som modell och besök valda för behållare.](assets/participation-setup.png)

   **(Partition|Besök|30 dagar)** har lagts till i måttkomponentens namn.



1. Välj [!UICONTROL **Spara**] om du vill spara måttet.
1. Använd det beräknade måttet i rapporten. Använd till exempel det beräknade [!DNL Orders (Session Participation)]-måttet i en rapport för att visa vilken kundnivå som bidragit till (eller deltagit i) sessioner som innehöll en order.

   ![Frihandsregister med kundnivå och beställningar.](assets/participation-pages-customer-tier.png)


<!--

The following information explains how to create a metric that shows which pages contributed to (or participated in) visits that contained an order.

This type of information could be useful for any content owner.

>[!NOTE]
>
>You can enable participation metrics in the Admin Tools, but only for custom events 1 - 100.

1. Begin creating a calculated metric, as described in [Build metrics](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/cm-build-metrics.md).

1. In the Calculated metrics builder, name the metric "Participation".

1. Drag the success event "Orders" into the Definition canvas.

1. Change the [attribution model](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/m-metric-type-alloc.md) of that event to **[!UICONTROL Participation]** under the **[!UICONTROL Settings]** gear. Select **[!UICONTROL Visit]** lookback. The definition should look similar to this:

   ![](assets/participation.png)

1. Select [!UICONTROL **Save**] to save the metric.

1. Use the calculated metric in a **[!UICONTROL Pages]** report.

    ![](assets/participation-pages.png)

1. (Optional) Share the metric with other users in your organization, as described in [Share calculated metrics](/help/components/c-calcmetrics/c-workflow/cm-workflow/cm-sharing.md).
-->