---
description: Visar hur du skapar ett enkelt mått för"Sidvyer per besök".
title: Skapa ett enkelt mätvärde för sidvisningar per besök
feature: Calculated Metrics
exl-id: 2d1c4677-b07c-4eca-97b7-e5e4594daee1
source-git-commit: 35413ac43eed5ab7218794f26e4753acf08f18ee
workflow-type: tm+mt
source-wordcount: '243'
ht-degree: 6%

---

# Skapa ett enkelt mätvärde för sidvisningar per besök

Visar hur du skapar ett enkelt mått för&quot;Sidvyer per besök&quot;.

En detaljerad beskrivning av UI-komponenterna finns i [Byggmått](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/cm-build-metrics.md).

Så här skapar du ett enkelt mått för&quot;Sidvyer per besök&quot;.

1. Navigera till verktyget för beräkning av mått.
1. Ange måttet&quot;Sidvyer per besök&quot; eller något liknande.
1. Ge den ett användarvänligt **[!UICONTROL Description]** för att visa vad det används för.
1. Välj höger **[!UICONTROL Format]**, i det här fallet Decimal.
1. Bestäm hur många decimaler du vill att rapporten ska visa.
1. Ange metrisk polaritet. För detta mätresultat skulle en uppåtgående trend vara bra (grön) grej.
1. Lägg till en **[!UICONTROL Tag]** för att ordna mätvärden.
1. För detta mått drar du först sidvyer till arbetsytan och drar sedan besök under (vänta tills den blå linjen visas för att släppa den).
1. Välj operatorn Dela. (Divide är standardoperator.)
1. Nu kan du se en **[!UICONTROL Preview]** av mätvärdena när du bygger upp dem, längst upp till höger.
1. Produktkompatibiliteten visar om mätvärdena är kompatibla med [Aktuella data](https://experienceleague.adobe.com/docs/analytics/analyze/reports-analytics/current-data.html) eller endast med fullständigt bearbetade data.
1. Klicka på **[!UICONTROL Save]**.
1. Observera att **[!UICONTROL Summary]** formeln uppdateras varje gång du ändrar måttdefinitionen.
1. Du dirigeras nu automatiskt till [Beräknad måtthanterare](/help/components/c-calcmetrics/c-workflow/cm-workflow/cm-manager.md), som liknar segmenthanteraren. Du kan dela, godkänna, (om-)tagga, byta namn på eller ta bort mätvärden.
