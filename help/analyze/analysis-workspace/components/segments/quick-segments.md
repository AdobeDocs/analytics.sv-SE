---
description: Använd snabbsegment i Analysis Workspace.
title: Snabbsegment
feature: Workspace Basics
role: User, Admin
source-git-commit: ef232d1227430bb2430ca1da09756f5dd5106b1f
workflow-type: tm+mt
source-wordcount: '716'
ht-degree: 0%

---


# Snabbsegment

Du kan skapa snabbsegment i ett projekt för att kringgå komplexiteten i den fullständiga [segmentbyggaren](/help/components/segmentation/segmentation-workflow/seg-build.md). Om du vill jämföra vad snabbsegment kan göra med fullständiga komponentlistesegment går du [hit](/help/analyze/analysis-workspace/components/segments/t-freeform-project-segment.md). Snabbsegment tillåter upp till tre regler och hanterar inte kapslade behållare eller sekventiella segment.

>[!IMPORTANT]
> Snabbsegment är för närvarande i begränsad testning och är inte allmänt tillgängliga än.

## Skapa snabbsegment

I en friformstabell klickar du på ikonen filter+ i panelhuvudet:

![](assets/quick-seg1.png)

| Inställning | Beskrivning |
| --- | --- |
| Namn | Standardnamnet för ett segment är en kombination av reglerna i segmentet. Du kan byta namn på segmentet. |
| Inkludera/exkludera | Du kan inkludera eller exkludera komponenter i segmentdefinitionen, men inte båda. |
| Behållare för träff/besök/besök | Snabbsegment innehåller bara en [segmentbehållare](https://experienceleague.adobe.com/docs/analytics/components/segmentation/seg-overview.html?lang=en#section_AF2A28BE92474DB386AE85743C71B2D6) som gör att du kan inkludera ett mått-/mätvärde-/datumintervall i (eller exkludera det från) segmentet. [!UICONTROL Visitor] innehåller översiktsdata som är specifika för besökaren vid besök och sidvisningar. Med en [!UICONTROL Visit]-behållare kan du ange regler för att dela upp besökarens data baserat på besök, och med en [!UICONTROL Hit]-behållare kan du dela upp besökarinformation baserat på enskilda sidvyer. Standardbehållaren är [!UICONTROL Hit]. |
| Komponenter (Dimension/mått/datumintervall) | Definiera upp till tre regler genom att lägga till komponentdimensioner och/eller mätvärden och/eller datumintervall. Det finns tre sätt att hitta rätt komponent:<ul><li>Börja skriva så hittar verktyget [!UICONTROL Quick Segment] automatiskt rätt komponent.</li><li>Använd listrutan för att hitta komponenten.</li><li>Dra och släpp komponenter från den vänstra listen.</li></ul> |
| Operator | Använd listrutan för att hitta standardoperatorer som `contains` och [!UICONTROL Distinct Count] operatorer. |
| Plustecken (+) | Lägg till en annan regel |
| Och/eller kvalificerare | Du kan lägga till&quot;AND&quot;- eller&quot;OR&quot;-kvalificerare i reglerna, men du kan inte blanda&quot;AND&quot; och&quot;OR&quot; i en enskild segmentdefinition. |
| Använd | Använd det här segmentet på panelen. |
| Open Builder | Öppnar segmentbyggaren. |
| Avbryt | Avbryt det här snabbsegmentet - använd det inte. |
| Datumintervall | Valideraren använder panelens datumintervall för sin datasökning. Alla datumintervall som används i ett snabbsegment åsidosätter panelens datumintervall högst upp på panelen. |
| Förhandsgranska (överst till höger) | Här kan du se om du har ett giltigt segment och hur brett segmentet är. Representerar den uppdelning av datauppsättningen som du kan förvänta dig att se när du använder det här segmentet. |

Här är ett exempel på ett segment som kombinerar mått och mätvärden:

![](assets/quick-seg2.png)

Segmentet visas överst. Lägg märke till dess grå sidospalt, till skillnad från den blå sidolisten för segment på komponentnivå i segmentbiblioteket till vänster.

![](assets/quick-seg3.png)

## Redigera snabbsegment

1. Håll pekaren över snabbsegmentet och välj pennikonen.
1. Redigera segmentdefinitionen eller segmentnamnet.

## Spara snabbsegment

Du kan välja att spara snabbsegment antingen i snabbsegmentsverktyget eller genom att följa dessa steg.

>[!IMPORTANT]
>När du har sparat eller använt segmentet kan du inte längre redigera det i snabbsegmentsverktyget, utan bara i den vanliga segmentbyggaren.

1. Håll pekaren över snabbsegmentet och välj ikonen för info (&quot;i&quot;).
1. Välj **[!UICONTROL Save segment]**

   ![](assets/save-quick-seg.png)

1. Låt namnet vara som det är eller byt namn på segmentet.

   Gå tillbaka till arbetsytan och se hur segmentet nu har en blå sidospalt. Det innebär att den inte längre kan redigeras/öppnas i snabbsegmentsverktyget. Och genom att spara det blir det en del av komponentlistan.

   ![](assets/quick-seg4.png)

När du har tillämpat segmentet kan du välja att lägga till det i segmentkomponentlistan och göra det tillgängligt för alla projekt.

1. Håll pekaren över det sparade segmentet och välj pennikonen.

1. Lägg märke till den här dialogrutan längst upp i Segment Builder:

   ![](assets/project-only.png)

1. Markera kryssrutan bredvid **[!UICONTROL Make this segment available to all your projects and add it to your component list.]**
1. Klicka på **[!UICONTROL Save]**.
1. Segmentet visas nu i segmentkomponentlistan för alla dina projekt.
1. Du kan även [dela segmentet](/help/components/segmentation/segmentation-workflow/t-seg-share.md) med andra personer i organisationen.

## Vad är segment med endast projekt?

Endast projektsegment är antingen snabbsegment eller tillfälliga projektsegment för arbetsytan. När du redigerar/öppnar dem i segmentbyggaren visas rutan för endast projekt. Om de använder ett snabbsegment i byggaren men inte markerar kryssrutan Gör tillgänglig är det fortfarande ett segment som bara är till för projektet, men det kan inte längre öppnas i QS-byggaren. Om de markerar kryssrutan och SPARA är den nu ett komponentlistsegment.