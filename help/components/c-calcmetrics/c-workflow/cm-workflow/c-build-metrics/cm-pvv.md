---
description: Visar hur du skapar ett enkelt mått för"Sidvyer per besök".
title: Skapa ett enkelt mätvärde för sidvisningar per besök
feature: Calculated Metrics
exl-id: 2d1c4677-b07c-4eca-97b7-e5e4594daee1
source-git-commit: 7722a2f01ff77dfec8ce110fd04fe977f6c627c6
workflow-type: tm+mt
source-wordcount: '228'
ht-degree: 3%

---

# Bygg en sidvy per besök-mätare

I följande information förklaras hur du skapar ett enkelt mått för&quot;Sidvyer per besök&quot;.

Så här skapar du ett enkelt mått för&quot;Sidvyer per besök&quot;:

1. Börja skapa ett mätvärde enligt beskrivningen i [Bygg mätvärden](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/cm-build-metrics.md).
1. Ange måttet&quot;Sidvyer per besök&quot; eller något liknande.
1. Ge den ett användarvänligt **[!UICONTROL Description]** för att visa vad det används för.
1. Välj höger **[!UICONTROL Format]**. I det här exemplet väljer du [!UICONTROL **Decimal**].
1. Bestäm hur många decimaler du vill att rapporten ska visa.
1. I [!UICONTROL **Visa uppåtgående trend som**] nedrullningsbar meny, välja [!UICONTROL **Bra (grönt)**].
1. Lägg till en **[!UICONTROL Tag]** för att ordna mätvärden.
1. För det här måttet drar du först sidvyer till [!UICONTROL **Definition**] på arbetsytan och dra sedan besökarna under den (vänta tills den blå linjen visas innan du släpper den).
1. Välj operatorn Dela. (Divide är standardoperator.)
1. Nu kan du se en **[!UICONTROL Preview]** av mätvärdena när du bygger upp dem, längst upp till höger.
1. Produktkompatibiliteten visar om mätvärdena är kompatibla med [Aktuella data](https://experienceleague.adobe.com/docs/analytics/analyze/reports-analytics/current-data.html) eller endast med fullständigt bearbetade data.
1. Välj **[!UICONTROL Save]**.

   Observera att **[!UICONTROL Summary]** formeln uppdateras varje gång du ändrar måttdefinitionen.

1. (Valfritt) Du kan gå till [Sidan Beräknade mått](/help/components/c-calcmetrics/c-workflow/cm-workflow/cm-manager.md).
