---
description: Använd ad hoc-segment i Analysis Workspace.
title: Ad hoc-segment
feature: Workspace Basics
role: User, Admin
source-git-commit: f3185f1ee341348fb7bdbaab8b68d421e7c79076
workflow-type: tm+mt
source-wordcount: '368'
ht-degree: 0%

---


# Ad hoc-projektsegment

Här är en video om hur du skapar ad hoc-projektsegment:

>[!VIDEO](https://video.tv.adobe.com/v/23978/?quality=12)

Du kan skapa ad hoc-projektsegment om du snabbt vill utforska hur ett segment kan påverka projektet, utan att gå till segmentbyggaren. Tänk på dessa segment som tillfälliga segment på projektnivå. De är vanligtvis inte en del av ditt segment som&quot;bibliotek&quot;, som komponentsegment i den vänstra listen. Du kan dock spara dem enligt nedan.

En jämförelse av vad ad hoc-projektsegment kan göra jämfört med helformaterade segment på komponentnivå finns [här](/help/analyze/analysis-workspace/components/segments/t-freeform-project-segment.md).

1. Släpp en komponenttyp (dimension, dimensionsobjekt, händelse, mått, segment, segmentmall, datumintervall) i segmentsläppzonen längst upp på panelen. Komponenttyper konverteras automatiskt till segment.
Här följer ett exempel på hur du skapar ett segment för den hänvisande domänen för Twitter:

   ![](assets/ad-hoc1.png)

   Panelen tillämpar automatiskt det här segmentet och du ser resultatet direkt.

1. Du kan lägga till ett obegränsat antal komponenter på en panel.
1. Om du bestämmer dig för att du vill spara det här segmentet, se avsnittet nedan.

Tänk på följande:

* Du **kan inte** släppa följande komponenttyper i segmentzonen: beräknade mått och mått/mätvärden som du inte kan bygga segment utifrån.
* För alla dimensioner och händelser skapar Analysis Workspace&quot;finns&quot;-träffsegment. Exempel: `Hit where eVar1 exists` eller `Hit where event1 exists`.
* Om &quot;unspecified&quot; eller &quot;none&quot; släpps i segmentets släppzon konverteras det automatiskt till segmentet &quot;does not exist&quot; så att det behandlas korrekt i segmentering.

>[!NOTE]
>
>Segment som skapas på det här sättet är interna för projektet.

## Spara tillfälliga projektsegment {#ad-hoc-save}

Du kan välja att spara dessa segment genom att följa dessa steg:

1. Håll pekaren över segmentet i släppzonen och klicka på ikonen i.
1. Klicka på **[!UICONTROL Save]** på informationspanelen som visas.

   ![](assets/segment-info.png)

## Vad är segment med endast projekt?

Endast projektsegment är antingen snabbsegment eller tillfälliga projektsegment för arbetsytan. När du redigerar/öppnar dem i segmentbyggaren visas rutan för endast projekt. Om de använder ett snabbsegment i byggaren men inte markerar kryssrutan Gör tillgänglig är det fortfarande ett segment som bara är till för projektet, men det kan inte längre öppnas i QS-byggaren. Om de markerar kryssrutan och SPARA är den nu ett komponentlistsegment.