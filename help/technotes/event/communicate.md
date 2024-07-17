---
title: förmedla genomslag till användarna
description: Lär dig effektiva sätt att förmedla effekten av en händelse i organisationen.
exl-id: 9ba83f3f-2eea-44c2-80b2-a0a9111d51cf
feature: Event
source-git-commit: 93099d36a65ca2bf16fbd6342f01bfecdc8c798e
workflow-type: tm+mt
source-wordcount: '339'
ht-degree: 0%

---

# Informera användarna om händelseeffekter

Om du har data som [påverkas av en händelse](overview.md) är det viktigt att kommunicera den händelsen till användarna i din organisation.

* Utveckla en gemensam ansvarsfriskrivning som du kan använda i kommunikationen för att uppnå enhetlighet
* Kommunicera kontinuerligt till Analytics-användare och viktiga intressenter under och efter evenemanget
* Placera en påminnelse i kalendern för efterföljande milstolpar, t.ex. följande månad eller år. Den här informationen kan i framtiden hjälpa till att påminna användare som tittar på rapporter om effekten i månads- eller årsrapporter.

I Adobe Analytics visas olika sätt att kommunicera med användare i organisationen i följande avsnitt. Du kan även använda andra metoder utanför Adobe Analytics, till exempel e-post, för att kommunicera med användare.

## Kommunicera via paneler eller visualiseringsbeskrivningar

Om du har ett Workspace-projekt som delas mellan användare i organisationen kan du förmedla effekten av en händelse via paneler eller visualiseringsbeskrivningar. Högerklicka på en panel eller ett visualiseringshuvud och välj sedan **[!UICONTROL Edit description]**.

![Panelbeskrivning](assets/panel_description.png)

## Kommunicera med textvisualiseringar

Du kan också förmedla påverkan av en händelse genom dedikerade textvisualiseringar. Se [Textvisualiseringar](/help/analyze/analysis-workspace/visualizations/text.md) i användarhandboken för Analysera.

![Textvisualisering](assets/text_visualization.png)

## Lägga till anpassade kalenderhändelser i trender i Workspace

För all visualisering i Workspace kan du lägga till i en serie som representerar det datumintervall som påverkas.

1. Skapa ett beräknat mått med segmentet Påverkade dagar genom att följa [Uteslut specifika datum i analysen](segments.md).
1. Lägg till det önskade måttet på den beräknade mätarbetsytan.

   ![Mått](assets/calcmetric_event.png)

1. Lägg till en titel och en beskrivning som informerar användarna om effekten. Du kan också tagga det här måttet som en kalenderanteckning om du vill.

   ![Titel och beskrivning](assets/calcmetric_title_description.png)

1. I ett frihandsbord lägger du till dimensionen &#39;Dag&#39;. Lägg till &#39;Besök&#39; och ditt beräknade mått som kolumner sida vid sida.

   ![Frihandstabell](assets/calcmetric_freeform.png)

1. Klicka på kugghjulsikonen för kolumninställningar för det beräknade måttet och aktivera **[!UICONTROL Interpret zero as no value]**.

   ![Beräknade måttinställningar](assets/calcmetric_zero_no_value.png)

1. Lägg till en linjevisualisering. Dagar som påverkas representeras med en annan färg. Användarna kan också klicka på ikonen Info i det beräknade måttet för mer information.

   ![Informationsikon](assets/calcmetric_infoicon.png)

