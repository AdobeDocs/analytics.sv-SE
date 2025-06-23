---
title: Exkludera specifika datum i analysen
description: Tips för att exkludera datum eller datumintervall om du inte vill inkludera det i rapporter.
exl-id: 744666c0-17f3-443b-9760-9c8568bec600
feature: Curate and Share, Segmentation
source-git-commit: 29ab0cc535bd8f74b50428c11756bf8b446a23ab
workflow-type: tm+mt
source-wordcount: '565'
ht-degree: 0%

---

# Exkludera specifika datum i analysen

Om du har data som [påverkas av en händelse](overview.md) kan du använda ett segment för att exkludera datumintervall som du inte vill inkludera i dina rapporter. Genom att segmentera händelsestyrda datum kan ni förhindra att organisationen fattar beslut om delar av data.

## Isolera påverkade dagar {#isolate}

Skapa ett segment som isolerar den dag eller det datumintervall som påverkas. Det här segmentet är användbart om du bara vill fokusera på problemdagarna för att få mer information om hur det påverkar.

1. Öppna segmentverktyget genom att gå till **[!UICONTROL Components]** > **[!UICONTROL Segments]** och sedan klicka på **[!UICONTROL Add]**.
2. Dra dimensionen &#39;Dag&#39; till definitionsytan och ställ in den som motsvarar den dag du vill isolera.
3. Upprepa ovanstående steg för varje dag som du vill isolera i din rapport.

![Dagssegment som påverkas](assets/affected_days.jpg)

>[!TIP]
>
>Om du vill ändra programsatsen OR till en AND-programsats klickar du på nedpilen bredvid ELLER och väljer AND.

Adobe rekommenderar att du använder de orange dimensionskomponenterna och inte de lila datumintervallkomponenterna. Om du använder lila datumintervallkomponenter åsidosätter de projektets kalenderintervall:

![Uteslut segmentdagstyp](assets/exclude_segment_day_type.jpg)

## Uteslut påverkade dagar {#exclude}

Skapa ett segment som utesluter den dag eller det datumintervall som påverkas. Det här segmentet är användbart om du vill exkludera de dagar som fick problem för att minimera påverkan på den övergripande rapporteringen.

1. Öppna segmentverktyget genom att gå till **[!UICONTROL Components]** > **[!UICONTROL Segments]** och sedan klicka på **[!UICONTROL Add]**.
2. Klicka på **[!UICONTROL Options]** > **[!UICONTROL Exclude]** i det övre högra hörnet av segmentdefinitionsytan.
3. Dra dimensionen &#39;Dag&#39; till definitionsytan och ställ in den som motsvarar den dag du vill ta bort.
4. Upprepa ovanstående steg för varje dag som du vill ta bort i rapporten.

![Uteslut påverkade dagar](assets/exclude_affected_days.jpg)

## Använd dessa segment i rapporter

När du har skapat det uteslutna segmentet kan du använda det precis som du skulle ha gjort med andra segment.

### Jämföra segment i en trendrapport {#compare}

Du kan använda både segmentet&quot;Påverkade dagar&quot; och&quot;Uteslut påverkade dagar&quot; i en rapport för att jämföra dem sida vid sida. Jämför båda segmenten genom att dra dem över eller under ett mätvärde:

![Båda segmenten](assets/affected_and_exclude.png)

Om du inte vill visa nollor i tabellen eller visualiseringar (som orsakar dips) aktiverar du **[!UICONTROL Interpret zero as no value]** under kolumninställningar.

![Tolka noll](assets/interpret_zero.png)

Om du inte vill visa nollor i tabellen eller visualiseringar (som orsakar dips) aktiverar du **[!UICONTROL Interpret zero as no value]** under kolumninställningar.

![Tolka noll](assets/interpret_zero.png)

### Använd exkluderingssegmentet på ett projekt {#apply}

Du kan använda segmentet Uteslut påverkade dagar i ett Workspace-projekt. Dra det uteslutna segmentet till Workspace Canvas-avsnittet *Släpp ett segment här*.

>[!TIP]
>
>Inkludera en anteckning om uteslutna data i panelens beskrivning som kan hjälpa dem som tittar på rapporten. Högerklicka på en paneltitel och klicka sedan på **[!UICONTROL Edit description]**.

![Segment använt på en panel](assets/exclude_segment_panel.jpg)

### Använd exkluderingssegmentet i en virtuell rapportserie {#use-vrs}

Du kan använda segmentet i en [virtuell rapportsserie](/help/components/vrs/vrs-about.md) för att enklare exkludera data. Det här alternativet är idealiskt eftersom du inte behöver komma ihåg att använda segmentet för varje rapport som innehåller det datumintervall som påverkas. Om du redan använder virtuella rapportsviter som primär datakälla kan du lägga till segmentet i en befintlig virtuell rapportserie.

1. Navigera till **[!UICONTROL Components]** > **[!UICONTROL Virtual report suites]**.
2. Klicka på **[!UICONTROL Add]**.
3. Ange önskat namn och beskrivning för den virtuella rapportsviten.
4. Dra det uteslutna segmentet till området **[!UICONTROL Add segment]**.
5. Klicka på **[!UICONTROL Continue]** i det övre högra hörnet och sedan på **[!UICONTROL Save]**.

![Segmentet används i den virtuella rapportsviten](assets/exclude_segment_vrs.png)
