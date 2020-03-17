---
description: Med verktyget Beräknade mätvärden kan vem som helst skapa ett deltagandemått.
title: Deltagandemått
uuid: 7cb191be-bc4e-46ef-8a20-ccba5355e253
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Deltagandemått

Här följer ett enkelt exempel: Du är innehållsägare och vill se vilka sidor som har bidragit till (dvs. deltagit i) besök som innehöll en order. Så här:

> [!NOTE] Tidigare var du tvungen att göra detta via Admin Tools. Du kan fortfarande aktivera deltagandemått i Admin Tools, men bara för anpassade händelser 1-100.

Här följer några enkla exempel: Du är innehållsägare och vill se vilka sidor som har bidragit till (deltagit i) besök som innehöll en e-postregistrering. Så här:

1. Skapa ett nytt mått i verktyget Beräknade mätvärden.
1. Dra success-händelsen &quot;Orders&quot; till arbetsytan Definition.
1. Ändra [attribueringsmodellen](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/m-metric-type-alloc.md) för den händelsen till **[!UICONTROL Participation]** under **[!UICONTROL Settings]** kugghjulet. Välj **[!UICONTROL Visit]** uppslag. Definitionen bör se ut ungefär så här:

   ![](assets/participation.png)

1. Spara måtten.
1. Använd det beräknade måttet i en **[!UICONTROL Pages]** rapport.

   ![](assets/participation-pages.png)

1. (Valfritt) Dela mätvärdena med andra användare i organisationen.

