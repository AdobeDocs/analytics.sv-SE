---
description: Visar hur du skapar ett enkelt mått för"Sidvyer per besök".
title: Bygg ett enkelt mått för"sidvyer per besök"
feature: Calculated Metrics
exl-id: 2d1c4677-b07c-4eca-97b7-e5e4594daee1
source-git-commit: bf58da2a39e8b9fd298356f23a9bf8f6c394d3de
workflow-type: tm+mt
source-wordcount: '210'
ht-degree: 0%

---

# Bygg ett enkelt beräknat mått

I följande information förklaras hur du skapar en enkel *sidvy per besök*-mätare.

1. Börja med att skapa ett mätvärde enligt beskrivningen i [Bygg mått](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/cm-build-metrics.md).
1. Namnge måttet `Page Views per Visits` eller något liknande.
1. Ge måttet ett användarvänligt **[!UICONTROL Description]** för att visa vad måttet används för.
1. Välj höger **[!UICONTROL Format]**. Välj **[!UICONTROL Decimal]** för det här exemplet.
1. Bestäm hur många decimaler du vill att rapporten ska visa.
1. Välj ▲ **[!UICONTROL Good (Green)]** i listrutan **[!UICONTROL Show updward trend as]**.
1. Lägg till en **[!UICONTROL Tag]** för att ordna dina mått.
1. För det här beräknade måttet drar du först **[!UICONTROL Page Views]** från **[!UICONTROL Dimensions]**-komponenterna till **[!UICONTROL Definition]**-delen av arbetsytan.
1. Dra sedan **[!UICONTROL Visits]** från **[!UICONTROL Metrics]**-komponenterna och släpp måttet under **[!UICONTROL Page Views]** (vänta tills den blå linjen visas innan du släpper måttet).
1. Välj divisionsoperatorn ![Dividera](/help/assets/icons/Divide.svg). (Divide är standardoperator.)
1. Du kan se en **[!UICONTROL Preview]** av måtten medan du skapar måttet.
1. [Produktkompatibilitet](../../../cm-compatibility.md) visar om måttet är kompatibelt med aktuella data eller endast med fullständigt bearbetade data.

   ![Enkelt beräknat mått](assets/simple-calculated-metric.png)
1. Välj **[!UICONTROL Save]**.

   Observera att formeln **[!UICONTROL Summary]** uppdateras varje gång du ändrar måttdefinitionen.

1. (Valfritt) Om du vill dela, godkänna, (om-)tagga, byta namn på eller ta bort ett mätresultat går du till [hanteraren för beräknade värden](/help/components/c-calcmetrics/c-workflow/cm-workflow/cm-manager.md).

