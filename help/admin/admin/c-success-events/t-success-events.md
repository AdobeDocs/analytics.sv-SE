---
description: Steg som beskriver hur du konfigurerar lyckade händelser.
title: Konfigurera slutförda händelser
feature: Administratörsverktyg
uuid: ca3d3f46-5fad-4481-aef6-04cad6bc6e2d
exl-id: 0e9a6d8f-2ce7-4551-885d-bd77ff131da0
translation-type: tm+mt
source-git-commit: 78412c2588b07f47981ac0d953893db6b9e1d3c2
workflow-type: tm+mt
source-wordcount: '189'
ht-degree: 9%

---

# Konfigurera slutförda händelser

Steg som beskriver hur du konfigurerar lyckade händelser.

1. Klicka på **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]**.
1. Välja en rapportsvit.
1. Klicka på **[!UICONTROL Edit Settings]** > **[!UICONTROL Conversion]** > **[!UICONTROL Success Events]**.

   ![Stegresultat](assets/success_event_page.png)

1. Markera kryssrutan bredvid varje objekt i kolumnen **[!UICONTROL Name]** för att aktivera redigering och ange sedan önskat namn.
1. Markera kryssrutan bredvid varje objekt i kolumnen **[!UICONTROL Type]** för att aktivera listrutan och välj sedan önskad typ.

   >[!NOTE]
   >
   >Se [Ändra händelsetyp](/help/admin/admin/c-success-events/event-type.md) innan du ändrar en händelsetyp.

   På [sidan Slutförda händelser - beskrivningar](/help/admin/admin/c-success-events/success-event.md) finns information om dessa element.

1. I kolumnen **[!UICONTROL Polarity]** anger du om en uppåtgående trend för det här måttet är bra eller dåligt.
1. I kolumnen **[!UICONTROL Visibility]** kan du dölja standardvärden (inbyggda), anpassade händelser och inbyggda händelser i Menu, Metric Selectors, Calculated Metrics Builder och Segment Builder.

   Den här inställningen påverkar inte datainsamlingen för det mätvärdet eller händelsen. påverkar bara synligheten i användargränssnittet. [Mer...](/help/admin/admin/metric-visibility.md)
1. Ange en beskrivning.
1. Kontrollera om händelsen alltid ska spelas in.
1. Aktivera eller inaktivera deltagarstatistik.

   >[!NOTE]
   >
   >Du kan aktivera deltagande för upp till 100 anpassade händelser. Utöver detta kan du skapa deltagandemått i [Calculated Metrics](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/participation-metric.md)-byggaren.

1. Klicka på **[!UICONTROL Save]**.
