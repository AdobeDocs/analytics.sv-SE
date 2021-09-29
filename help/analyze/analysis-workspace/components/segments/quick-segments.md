---
description: Använd snabbsegment i Analysis Workspace.
title: Snabbsegment
feature: Workspace Basics
role: User, Admin
source-git-commit: 7e95e1a51dac7771e32ab378209935d2806d752e
workflow-type: tm+mt
source-wordcount: '885'
ht-degree: 1%

---


# Snabbsegment

Du kan skapa snabbsegment i ett projekt för att kringgå komplexiteten i den fullständiga [segmentbyggaren](/help/components/segmentation/segmentation-workflow/seg-build.md). Snabbsegment

* Gäller endast projekt i vilka de har skapats (du kan ändra detta).
* Tillåt upp till tre regler.
* Innesluta inte kapslade behållare eller sekventiella regler.
* Arbeta i projekt med flera rapportsviter.

Om du vill jämföra vad snabbsegment kan göra med fullständiga komponentlistesegment går du [hit](/help/analyze/analysis-workspace/components/segments/t-freeform-project-segment.md).

>[!IMPORTANT]
> Snabbsegment är för närvarande i begränsad testning och är inte allmänt tillgängliga än.

## Förutsättningar

Användarna behöver behörigheten [!UICONTROL Segment Creation] i [Adobe Admin Console](https://experienceleague.adobe.com/docs/analytics/admin/admin-console/permissions/summary-tables.html?lang=en#analytics-tools) för att kunna skapa snabbsegment.

## Skapa snabbsegment

I en friformstabell klickar du på ikonen filter+ i panelhuvudet:

![](assets/quick-seg1.png)

| Inställning | Beskrivning |
| --- | --- |
| Namn | Standardnamnet för ett segment är en kombination av regelnamnen i segmentet. Du kan byta namn på segmentet. |
| Inkludera/exkludera | Du kan antingen inkludera eller exkludera komponenter i segmentdefinitionen, men inte båda. |
| Behållare för träff/besök/besök | Snabbsegment innehåller bara en [segmentbehållare](https://experienceleague.adobe.com/docs/analytics/components/segmentation/seg-overview.html?lang=en#section_AF2A28BE92474DB386AE85743C71B2D6) som gör att du kan inkludera ett mått-/mätvärde-/datumintervall i (eller exkludera det från) segmentet. [!UICONTROL Visitor] innehåller översiktsdata som är specifika för besökaren vid besök och sidvisningar. Med en [!UICONTROL Visit]-behållare kan du ange regler för att dela upp besökarens data baserat på besök, och med en [!UICONTROL Hit]-behållare kan du dela upp besökarinformation baserat på enskilda sidvyer. Standardbehållaren är [!UICONTROL Hit]. |
| Komponenter (Dimension/mått/datumintervall) | Definiera upp till tre regler genom att lägga till komponentdimensioner och/eller mätvärden och/eller datumintervall och deras värden. Det finns tre sätt att hitta rätt komponent:<ul><li>Börja skriva så hittar verktyget [!UICONTROL Quick Segment] automatiskt rätt komponent.</li><li>Använd listrutan för att hitta komponenten.</li><li>Dra och släpp komponenter från den vänstra listen.</li></ul> |
| Operator | Använd listrutan för att hitta standardoperatorer och [!UICONTROL Distinct Count]-operatorer. [Läs mer](https://experienceleague.adobe.com/docs/analytics/components/segmentation/segment-reference/seg-operators.html?lang=en) |
| Plustecken (+) | Lägg till en annan regel |
| OCH/ELLER-kvalificerare | Du kan lägga till&quot;AND&quot;- eller&quot;OR&quot;-kvalificerare i reglerna, men du kan inte blanda&quot;AND&quot; och&quot;OR&quot; i en enskild segmentdefinition. |
| Använd | Använd det här segmentet på panelen. Om segmentet inte innehåller några data tillfrågas du om du vill fortsätta. |
| Open Builder | Öppnar segmentbyggaren. När du har sparat segmentet i segmentbyggaren betraktas det inte längre som ett&quot;snabbsegment&quot;. Den blir en del av segmentbiblioteket för komponentlistor. |
| Avbryt | Avbryt det här snabbsegmentet - använd det inte. |
| Datumintervall | Valideraren använder panelens datumintervall för sin datasökning. Alla datumintervall som används i ett snabbsegment åsidosätter panelens datumintervall högst upp på panelen. |
| Förhandsgranska (överst till höger) | Här kan du se om du har ett giltigt segment och hur brett segmentet är. Representerar den uppdelning av datauppsättningen som du kan förvänta dig att se när du använder det här segmentet. kan du få ett meddelande som anger att det här segmentet saknar data. Du kan fortsätta eller ändra segmentdefinitionen. |

Här är ett exempel på ett segment som kombinerar mått och mätvärden:

![](assets/quick-seg2.png)

Segmentet visas överst. Lägg märke till dess blå, randiga sidospalt, till skillnad från den blå sidolisten för segment på komponentnivå i segmentbiblioteket till vänster.

![](assets/quick-seg3.png)

## Redigera snabbsegment

1. Håll pekaren över snabbsegmentet och välj pennikonen.
1. Redigera segmentdefinitionen eller segmentnamnet.

## Spara snabbsegment

Du kan välja att spara snabbsegment antingen i [!UICONTROL Quick Segment Builder] eller i [!UICONTROL Segment Builder].

>[!IMPORTANT]
>När du har sparat eller använt segmentet kan du inte längre redigera det i snabbsegmentsverktyget, utan bara i den vanliga segmentbyggaren.

### Spara i snabbsegmentsverktyget

1. När du har använt snabbsegmentet håller du pekaren över det och väljer ikonen för info (&quot;i&quot;).
1. Klicka på **[!UICONTROL Make available to all projects and add to your component list]**.
1. (Valfritt) Byt namn på segmentet.
1. Klicka på **[!UICONTROL Save]**.

Lägg märke till hur segmentets sidlist ändras från randig blå till blå. Den visas nu i komponentlistan i den vänstra listen.

### Spara i Segment Builder

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

Endast projektsegment är antingen snabbsegment eller tillfälliga projektsegment för arbetsytan. När du redigerar/öppnar dem i [!UICONTROL Segment Builder] visas rutan för endast projekt. Om du använder ett snabbsegment i byggaren men inte markerar kryssrutan Gör tillgänglig är det fortfarande ett segment som bara är till för projektet, men det kan inte längre öppnas i [!UICONTROL Quick Segment Builder]. Om du markerar rutan och klickar på **[!UICONTROL SAVE]** är det nu ett komponentlistsegment.