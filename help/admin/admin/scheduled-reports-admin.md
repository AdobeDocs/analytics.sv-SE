---
description: Tillåter användare på administratörsnivå att se och hantera schemalagda rapporter i hela organisationen.
title: Schemalagd rapportkö
topic: Reports
uuid: 3fcf92d3-a472-465f-ad7a-c48cd9a8238b
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Schemalagd rapportkö

Tillåter användare på administratörsnivå att se och hantera schemalagda rapporter i hela organisationen.

**[!UICONTROL Analytics]** > **[!UICONTROL Components]** > **[!UICONTROL Scheduled Reports]**

Funktioner på administratörsnivå i hanteraren för schemalagda rapporter är bland annat:

* Alternativet att [visa alla schemalagda rapporter](/help/admin/admin/scheduled-reports-admin.md#section_3F167CAAEEC24140B476CF95B7402690) i organisationen.
* [Avancerade filtreringsfunktioner](/help/admin/admin/scheduled-reports-admin.md#section_206A52A85DE84947AAB3AD082FBF6275) i hela organisationen.
* Den nya fliken [Rapportkö](/help/admin/admin/scheduled-reports-admin.md#section_03C866115D354BB182E90BF4D52F1E0B) som visar alla rapporter som är köade för körning på rapportservrar.
* Visar [Schedule-ID](/help/admin/admin/scheduled-reports-admin.md#section_568B70F4228C4229977CB85D2DCD53A1) i rapportkögränssnittet.

## Visa alla schemalagda rapporter {#section_3F167CAAEEC24140B476CF95B7402690}

På **[!UICONTROL Report List]** fliken kan du **[!UICONTROL Show All Scheduled Reports]** i din organisation, förutom de som du har schemalagt personligen.

> [!NOTE] I **[!UICONTROL Report Name]** kolumnen visas namnet på den rapport som schemaläggs och i **[!UICONTROL File Name]** kolumnen visas eventuella egna filnamn som du har angett i Avancerade leveransalternativ. Om du schemalägger flera rapporter av samma rapporttyp och anger anpassade namn för var och en av dem, kommer schemalagda rapporthanterare att visa flera poster med samma rapportnamn, men med olika filnamn. Detta beror på att serverdelsrapporten som schemaläggs är densamma, så kolumnen Rapportnamn skulle ha samma rapportnamn för alla förutom anpassade filnamn (som angetts).

![](assets/show_all_scheduled_reports.png)

## Avancerade filtreringsfunktioner {#section_206A52A85DE84947AAB3AD082FBF6275}

Om du till exempel vill filtrera alla rapporter som är schemalagda till en timme, anger du **[!UICONTROL Frequency equals Hourly]** i **[!UICONTROL Advanced]** -filtret och klickar på **[!UICONTROL Apply]**:

![](assets/advanced_filtering_schedl_reports.png)

## Rapportkö {#section_03C866115D354BB182E90BF4D52F1E0B}

Med den här kön kan du hantera och eventuellt ta bort alla schemalagda rapporter som är &quot;insvepta&quot; i kön. (Rapporterar vanligtvis timeout efter 4 timmar.)

![](assets/scheduled_reports_2.png)

I rapportkön kan du även&quot;Hoppa över en schemalagd rapport en gång&quot;. Klicka bara på den blå ikonen i **[!UICONTROL Manage]** kolumnen.

## Schema-ID {#section_568B70F4228C4229977CB85D2DCD53A1}

Om du har **[!UICONTROL Schedule ID]** exponerats i gränssnittet för rapportkön blir det lättare att kontakta Adobe Client Care för att få hjälp med att lösa ett problem med schemalagda rapporter.

![](assets/schedule_id.png)
