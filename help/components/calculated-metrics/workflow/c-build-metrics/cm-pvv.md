---
description: Lär dig hur du bygger ett enkelt beräknat mätresultat.
title: Bygg ett enkelt beräknat mått
feature: Calculated Metrics
exl-id: 2d1c4677-b07c-4eca-97b7-e5e4594daee1
source-git-commit: 0fbd80070051286f999af8eec9100f617cc498d5
workflow-type: tm+mt
source-wordcount: '204'
ht-degree: 0%

---

# Bygg ett enkelt beräknat mått

I följande information förklaras hur du skapar en enkel *sidvy per besök*-mätare.

1. Börja med att skapa ett mätvärde enligt beskrivningen i [Bygg mått](/help/components/calculated-metrics/workflow/c-build-metrics/cm-build-metrics.md).
1. Namnge måttet `Page Views per Visit` eller något liknande.
1. Ge måttet ett användarvänligt **[!UICONTROL Description]** för att visa vad måttet används för.
1. Välj höger **[!UICONTROL Format]**. Välj **[!UICONTROL Decimal]** för det här exemplet.
1. Bestäm hur många decimaler du vill att rapporten ska visa.
1. Välj **[!UICONTROL Show updward trend as]** ▲ i listrutan **[!UICONTROL Good (Green)]**.
1. Lägg till en **[!UICONTROL Tag]** för att ordna dina mått.
1. För det här beräknade måttet drar du först **[!UICONTROL Page Views]** från **[!UICONTROL Metrics]**-komponenterna till **[!UICONTROL Definition]**-delen av arbetsytan.
1. Dra sedan **[!UICONTROL Visits]** från **[!UICONTROL Metrics]**-komponenterna och släpp måttet under **[!UICONTROL Page Views]** (vänta tills den blå linjen visas innan du släpper måttet).
1. Välj divisionsoperatorn ![Dividera](/help/assets/icons/Divide.svg). (Divide är standardoperator.)
1. Du kan se en **[!UICONTROL Preview]** av måtten medan du skapar måttet.
1. [Produktkompatibilitet](/help/components/calculated-metrics/cm-compatibility.md) visar om måttet är kompatibelt med aktuella data eller endast med fullständigt bearbetade data.

   ![Enkelt beräknat mått](assets/simple-calculated-metric.png)
1. Välj **[!UICONTROL Save]**.

   Observera att formeln **[!UICONTROL Summary]** uppdateras varje gång du ändrar måttdefinitionen.

1. (Valfritt) Om du vill dela, godkänna, (om-)tagga, byta namn på eller ta bort ett mätresultat går du till [hanteraren för beräknade värden](/help/components/calculated-metrics/workflow/cm-manager.md).

