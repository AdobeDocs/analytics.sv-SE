---
description: Använd snabbsegment i Analysis Workspace.
title: Snabbsegment
feature: Workspace Basics
role: User, Admin
source-git-commit: 9622131ebd4a856cb7756e6844d7d7979029e70e
workflow-type: tm+mt
source-wordcount: '322'
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

   - Börja skriva så hittar snabbsegmentsverktyget automatiskt rätt komponent.
   - Använd listrutan för att hitta komponenten.
   - Dra och släpp komponenter från den vänstra listen.

1. Ange den första regeln, till exempel `Page equals workspace`. Du kan ha upp till tre regler i segmentdefinitionerna. Klicka bara på plustecknet (+) för att lägga till en ny regel. Du kan lägga till&quot;AND&quot;- eller&quot;OR&quot;-kvalificerare i reglerna, men du kan inte blanda&quot;AND&quot; och&quot;OR&quot; i en enskild segmentdefinition.

   Här är ett exempel på ett segment som kombinerar mått och mätvärden:

   ![](assets/quick-seg2.png)

1. Klicka på **[!UICONTROL Apply]** om du vill använda det här segmentet på panelen.
Segmentet visas överst. Lägg märke till dess grå sidospalt, till skillnad från det blå fältet för segment på komponentnivå till vänster.

   ![](assets/quick-seg3.png)

## Göra snabba segment offentliga

Du kan välja att göra dessa segment offentliga (globala) genom att följa dessa steg:

1. Håll pekaren över snabbsegmentet och klicka på ikonen&quot;i&quot;.
1. Klicka på **[!UICONTROL Open builder]**.
Då öppnas segmentet i segmentbyggaren.
   >[!NOTE]
   >När du har tillämpat eller sparat segmentet i segmentbyggaren kan du inte längre redigera det i snabbsegmentbyggaren.
1. Klicka på **[!UICONTROL OK]**.
1. Klicka på **[!UICONTROL Apply]** i Segment Builder.
1. Gå tillbaka till Workspace och se hur segmentet nu har en blå sidospalt som signalerar att det är en del av komponentbiblioteket.

   ![](assets/quick-seg4.png)

