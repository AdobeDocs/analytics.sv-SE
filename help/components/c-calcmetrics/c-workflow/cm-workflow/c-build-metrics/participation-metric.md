---
description: Med verktyget Beräknade mätvärden kan vem som helst skapa ett deltagandemått.
title: Deltagandemått
feature: Calculated Metrics
exl-id: bef185d6-72c0-4068-80f8-57261369573f
source-git-commit: 4bf8397ee979614539baf21b36363eb03357567a
workflow-type: tm+mt
source-wordcount: '142'
ht-degree: 0%

---

# Bygg ett delgivningsmått

Följande information förklarar hur du skapar ett mätvärde som visar vilka sidor som bidragit till (eller deltagit i) besök som innehöll en order.

Den här typen av information kan vara användbar för alla innehållsägare.

>[!NOTE]
>
>Du kan aktivera deltagandemått i Admin Tools, men bara för anpassade händelser 1-100.

1. Börja skapa ett beräknat mått enligt beskrivningen i [Bygg mätvärden](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/cm-build-metrics.md).

1. Ange måttet&quot;Deltagande&quot; i verktyget Beräknade mätvärden.

1. Dra success-händelsen &quot;Orders&quot; till arbetsytan Definition.

1. Ändra [attribueringsmodell](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/m-metric-type-alloc.md) för händelsen till **[!UICONTROL Participation]** under **[!UICONTROL Settings]** utrustning. Välj **[!UICONTROL Visit]** uppslag. Definitionen bör se ut ungefär så här:

   ![](assets/participation.png)

1. Välj [!UICONTROL **Spara**] för att spara måtten.

1. Använd det beräknade måttet i en **[!UICONTROL Pages]** rapport.

   ![](assets/participation-pages.png)

1. (Valfritt) Dela mätvärdena med andra användare i organisationen enligt beskrivningen i [Dela beräknade värden](/help/components/c-calcmetrics/c-workflow/cm-workflow/cm-sharing.md).
