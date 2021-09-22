---
description: Använd snabbsegment i Analysis Workspace.
title: Snabbsegment
feature: Workspace Basics
role: User, Admin
source-git-commit: 31507092e659fa08a50e00f91bd36411e354cb21
workflow-type: tm+mt
source-wordcount: '449'
ht-degree: 0%

---


# Snabbsegment

Du kan skapa snabbsegment i ett projekt för att kringgå komplexiteten i den fullständiga [segmentbyggaren](/help/components/segmentation/segmentation-workflow/seg-build.md). En jämförelse av vad snabbsegment kan göra jämfört med helformaterade segment på komponentnivå finns [här](/help/analyze/analysis-workspace/components/segments/t-freeform-project-segment.md).

>[!IMPORTANT]
> Snabbsegment är för närvarande i begränsad testning och är inte allmänt tillgängliga än.

## Skapa snabbsegment

1. I en friformstabell klickar du på ikonen filter+ i panelhuvudet:

   ![](assets/quick-seg1.png)

   Observera att:

   - Det finns bara en segmentbehållare som gör att du kan inkludera ett mått-/mätvärde-/datumintervall i (eller exkludera det från) segmentet.
   - Du kan ange att behållaren ska vara på träffnivå, besöksnivå eller besökarnivå. Standardvärdet är Träff.

1. Lägg till ett mått-/mätvärde-/datumintervall på något av tre sätt:

   - Börja skriva så hittar [!UICONTROL Quick Segment builder] automatiskt rätt komponent.
   - Använd listrutan för att hitta komponenten.
   - Dra och släpp komponenter från den vänstra listen.

1. Ange den första regeln, till exempel `Page equals workspace`. Du kan ha upp till tre regler i en segmentdefinition. Klicka bara på plustecknet (+) för att lägga till en ny regel. Du kan lägga till&quot;AND&quot;- eller&quot;OR&quot;-kvalificerare i reglerna, men du kan inte blanda&quot;AND&quot; och&quot;OR&quot; i en enskild segmentdefinition.

   Här är ett exempel på ett segment som kombinerar mått och mätvärden:

   ![](assets/quick-seg2.png)

1. Klicka på **[!UICONTROL Apply]** om du vill använda det här segmentet på panelen.
Segmentet visas överst. Lägg märke till dess grå sidospalt, till skillnad från den blå sidolisten för segment på komponentnivå i segmentbiblioteket till vänster.

   ![](assets/quick-seg3.png)

## Redigera snabbsegment

1. Håll pekaren över snabbsegmentet och välj pennikonen.
1. Redigera segmentdefinitionen eller segmentnamnet.

## Spara snabbsegment

Du kan välja att spara snabbsegment genom att följa dessa steg.

>[!IMPORTANT]
>När du har sparat segmentet kan du inte längre redigera det i snabbsegmentbyggaren, utan bara i den vanliga segmentbyggaren.

1. Håll pekaren över snabbsegmentet och välj ikonen för info (&quot;i&quot;).
1. Välj **[!UICONTROL Save segment]**

   ![](assets/save-quick-seg.png)

1. Låt namnet vara som det är eller byt namn på segmentet.

1. Gå tillbaka till Workspace och se hur segmentet nu har en blå sidospalt som signalerar att det är en del av komponentbiblioteket.

   ![](assets/quick-seg4.png)

## Gör segment tillgängliga för alla projekt

När du har sparat segmentet kan du välja att lägga till det i segmentkomponentlistan och göra det tillgängligt för alla projekt.

1. Håll pekaren över det sparade segmentet och välj pennikonen.

1. Lägg märke till den här dialogrutan längst upp i Segment Builder:

   ![](assets/project-only.png)

1. Markera kryssrutan bredvid **[!UICONTROL Make this segment available to all your projects and add it to your component list.]**
1. Klicka på **[!UICONTROL Save]**.
1. Segmentet visas nu i segmentkomponentlistan för alla dina projekt.
1. Du kan även [dela segmentet](/help/components/segmentation/segmentation-workflow/t-seg-share.md).

## Förvandla ett snabbt segment till ett ad hoc-segment

1. Håll pekaren över det sparade segmentet och välj pennikonen.

1. Klicka **[!UICONTROL Apply]** högst upp i segmentbyggaren.

Mer information om ad hoc-segment finns [här](/help/analyze/analysis-workspace/components/segments/ad-hoc-segments.md)
