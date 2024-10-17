---
description: Lär dig hur du uppdaterar begäranden efter att du har redigerat eller tillämpat filter på dem, eller om du vill visa senare data.
title: Så här uppdaterar du en begäran
uuid: bb94fcc6-027b-4134-adc8-56a1ea7cc56b
feature: Report Builder
role: User, Admin
exl-id: 319dc040-92cf-4289-9373-bc165e58c2db
source-git-commit: fcecc8a493852f5682fd7fbd5b9bb484a850922c
workflow-type: tm+mt
source-wordcount: '185'
ht-degree: 0%

---

# Uppdatera en begäran

{{legacy-arb}}

Uppdatera förfrågningar när du har uppdaterat dem med redigeringar, filter eller när du behöver visa nyare data. Du kan markera flera begäranden i ett kalkylblad och uppdatera alla samtidigt.

Om du ökar datumintervallet för en begäran och sedan uppdaterar begäran, lägger Report Builder till celler för det tillagda antalet tidsperioder.

1. Skapa och kör en begäran.
1. När du har ändrat begäran högerklickar du på begäran och väljer sedan **[!UICONTROL Refresh Request]** på snabbmenyn. (Du kan också klicka i begäran och sedan klicka på **[!UICONTROL Refresh]** i verktygsfältet.)

   Systemet visar formuläret [!UICONTROL Refresh Requests]:

   **Nu datum:** Det datum som du vill basera uppdateringen på. Kallas även datumet [!UICONTROL As Of].

   **Ange till aktuellt datum för framtida uppdateringsåtgärder:** Om du aktiverar det här alternativet anges att Report Builder alltid ska använda det aktuella datumet som [!UICONTROL Now] (eller [!UICONTROL As Of])-datum. Du kan återställa den här inställningen genom att klicka på [!UICONTROL Options] i verktygsfältet.
1. Klicka på **[!UICONTROL OK]**.

   När en uppdatering har slutförts rapporteras detta med en grön ikon på [!UICONTROL Request Manager].
