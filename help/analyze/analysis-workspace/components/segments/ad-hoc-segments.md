---
description: Använd ad hoc-segment i Analysis Workspace.
title: Ad hoc-segment
feature: Segmentation
role: User, Admin
exl-id: 1c189abc-ab9f-413c-9be6-0d2fc457230e
source-git-commit: f50e3d9a1d3c1705c55a14af0e42a0da3ac00955
workflow-type: tm+mt
source-wordcount: '311'
ht-degree: 1%

---

# Ad hoc-projektsegment

Med ad hoc-projektsegment kan du dra och släppa alla komponenter direkt i panelens släppzon för att skapa ett segment. Segmentet blir ett [projektnivåsegment](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/components/segments/quick-segments.html?#what-are-project-only-segments%3F) lokalt till det aktuella projektet.

Här är en video om hur du skapar ad hoc-projektsegment:

>[!VIDEO](https://video.tv.adobe.com/v/23978/?quality=12)

1. Släpp en komponenttyp (dimension, dimensionsobjekt, händelse, mått, segment, segmentmall, datumintervall) i segmentsläppzonen längst upp på panelen. Komponenttyper konverteras automatiskt till ad hoc-segment eller [Snabbsegment](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/components/segments/quick-segments.html) om det är kompatibelt.
Här följer ett exempel på hur du skapar ett segment för den hänvisande domänen för Twitter:

   ![](assets/ad-hoc1.png)

   Panelen tillämpar automatiskt det här segmentet och du ser resultatet direkt.

1. Du kan lägga till ett obegränsat antal segment på en panel.
1. Om du bestämmer dig för att du vill spara det här segmentet, se avsnittet nedan.

Tänk på följande:

* Du **inte** släpp följande komponenttyper i segmentzonen: beräknade mått och mått/mätvärden som du inte kan bygga segment utifrån.
* För alla dimensioner och händelser skapar Analysis Workspace&quot;finns&quot;-träffsegment. Exempel: `Hit where eVar1 exists` eller `Hit where event1 exists`.
* Om &quot;unspecified&quot; eller &quot;none&quot; släpps i segmentets släppzon konverteras det automatiskt till segmentet &quot;does not exist&quot; så att det behandlas korrekt i segmentering.

Om du vill jämföra de olika segment du kan skapa och använda i ett projekt går du till [här](/help/analyze/analysis-workspace/components/segments/t-freeform-project-segment.md).

## Spara ad hoc-segment {#ad-hoc-save}

Ad hoc-segment kan göras tillgängliga för andra projekt genom att spara dem.

1. Håll pekaren över segmentet i släppzonen och klicka på ikonen i.
1. Klicka på redigeringspennan för att gå till segmentbyggaren.
1. Kontrollera **[!UICONTROL Make available to all projects and add to your component list]**.
1. Klicka på **[!UICONTROL SAVE]**.

När segmentet har sparats är det tillgängligt i den vänstra listan över komponenter för spår och kan delas med andra användare från segmenthanteraren.
