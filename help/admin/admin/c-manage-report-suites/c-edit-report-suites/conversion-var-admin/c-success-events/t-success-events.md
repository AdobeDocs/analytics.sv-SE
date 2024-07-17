---
description: Steg som beskriver hur du konfigurerar lyckade händelser.
title: Konfigurera lyckade händelser
feature: Event
role: Admin
exl-id: 0e9a6d8f-2ce7-4551-885d-bd77ff131da0
source-git-commit: d173a6c6c9751a86f4218ec842da17da14f8485b
workflow-type: tm+mt
source-wordcount: '221'
ht-degree: 7%

---

# Konfigurera lyckade händelser

Så här konfigurerar du lyckade händelser:

1. Klicka på **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]**.
1. Välj en rapportsvit.
1. Klicka på **[!UICONTROL Edit Settings]** > **[!UICONTROL Conversion]** > **[!UICONTROL Success Events]**.

   ![Stegresultat](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/c-success-events/assets/success_event_page.png)

1. Markera kryssrutan bredvid varje objekt i kolumnen **[!UICONTROL Name]** om du vill aktivera redigering och ange sedan önskat namn.
1. Markera kryssrutan bredvid varje objekt i kolumnen **[!UICONTROL Type]** för att aktivera listrutan och välj sedan önskad typ.

   >[!NOTE]
   >
   >Se [Ändra händelsetyp](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/c-success-events/event-type.md) innan du ändrar en händelsetyp.

   Gå till sidan [Slutförda händelser - beskrivningar](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/c-success-events/success-event.md) om du vill ha information om dessa element.

1. I kolumnen **[!UICONTROL Polarity]** anger du om en uppåtgående trend för det här måttet är bra eller dåligt.
1. I kolumnen **[!UICONTROL Visibility]** kan du dölja standardvärden (inbyggda), anpassade händelser och inbyggda händelser i Menu, Metric Selectors, Calculated Metrics Builder och Segment Builder.

   Den här inställningen påverkar inte datainsamlingen för det måttet eller händelsen. Den påverkar bara dess synlighet i användargränssnittet enligt följande:


   | Inställning | Synlig i | Inte synlig i |
   |---------|----------|---------|
   | [!UICONTROL **Visas överallt**] | <ul><li>Analysis Workspace</li><li>Segment Builder</li><li>Beräknad metrisk Builder</li></ul> | Ej tillämpligt |
   | [!UICONTROL **Builders**] | <ul><li>Segment Builder</li><li>Beräknad metrisk Builder</li><li>Analysis Workspace</li></ul> |
   | [!UICONTROL **Dold överallt**] | Ej tillämpligt | <ul><li>Analysis Workspace</li><li>Segment Builder</li><li>Beräknad metrisk Builder</li></ul> |

1. Ange en beskrivning.
1. Kontrollera om händelsen alltid ska spelas in.
1. Aktivera eller inaktivera deltagarstatistik.

   >[!NOTE]
   >
   >Du kan aktivera deltagande för upp till 100 anpassade händelser. Utöver detta kan du skapa deltagandemått i [Calculated Metrics](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/participation-metric.md)-byggaren.

1. Klicka på **[!UICONTROL Save]**.
