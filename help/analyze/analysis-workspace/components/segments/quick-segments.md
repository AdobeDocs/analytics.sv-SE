---
description: Använd snabbsegment i Analysis Workspace.
title: Snabbsegment
feature: Segmentation
role: User, Admin
exl-id: 680e7772-10d3-4448-b5bf-def3bc3429d2
source-git-commit: d64f6687dd6e6f688d332926e6d90fa699cac968
workflow-type: tm+mt
source-wordcount: '1127'
ht-degree: 0%

---

# Snabbsegment

Med snabbsegment kan du enkelt utforska data i ett visst projekt, utan att behöva skapa ett mer komplext komponentlistsegment i [segmentbyggare](/help/components/segmentation/segmentation-workflow/seg-build.md).

Tänk på följande när du skapar snabbsegment:

* Snabbsegment gäller bara för det projekt där de skapades. De är inte tillgängliga i andra projekt och kan inte delas med andra användare.
* Högst tre regler tillåts.
* Kapslade behållare eller sekventiella regler stöds inte.

I följande video visas hur du använder snabbsegment:

>[!VIDEO](https://video.tv.adobe.com/v/341466/?quality=12&learn=on)

## Skapa ett snabbsegment

Alla användare på arbetsytan Analys kan skapa ett snabbsegment.

Så här skapar du ett snabbsegment:

1. Välj en av följande metoder för att börja skapa snabbsegmentet:

   * **Ad hoc (dra och släpp):** Dra en komponent från den vänstra listen till släppzonen intill **Segment** -ikonen i panelhuvudet och välj sedan **Redigera** om du vill justera segmentet.

     ![Redigera ad hoc-segment](assets/filter-adhoc-edit.png)

     >[!NOTE]
     >
     > Tänk på följande när du skapar ett snabbsegment med ad hoc-funktioner (dra och släpp):
     > * Följande komponenttyper stöds inte: beräknade värden och dimensioner samt mätvärden som du inte kan bygga segment från.
     > * För alla dimensioner och händelser skapar Analysis Workspace&quot;finns&quot;-träffsegment. Exempel: `Hit where eVar1 exists` eller `Hit where event1 exists`.
     > * Om &quot;unspecified&quot; eller &quot;none&quot; släpps i segmentets släppzon konverteras det automatiskt till segmentet &quot;does not exist&quot; så att det behandlas korrekt i segment.


   * **Använda segmentikonen:** I en Freeform-tabell väljer du **Segment** -ikonen i panelhuvudet.

     ![Segmentfilter](assets/quick-seg1.png)

1. Justera någon av följande inställningar:

   | Inställning | Beskrivning |
   | --- | --- |
   | [!UICONTROL Name] | Standardnamnet för ett segment är en kombination av regelnamnen i segmentet. Du kan byta namn på segmentet till ett mer eget namn. |
   | [!UICONTROL Include/exclude] | Du kan antingen inkludera eller exkludera komponenter i segmentdefinitionen, men inte båda. |
   | [!UICONTROL Hit/Visit/Visitor] container | Snabbsegment innehåller ett [segmentbehållare](https://experienceleague.adobe.com/docs/analytics/components/segmentation/seg-overview.html#section_AF2A28BE92474DB386AE85743C71B2D6) bara så att du kan inkludera ett mått/mått/datumintervall i (eller exkludera det från) segmentet. [!UICONTROL Visitor] innehåller översiktsdata som är specifika för besökaren vid besök och sidvisningar. A [!UICONTROL Visit] kan du ange regler för att dela upp besökarens data baserat på besök och en [!UICONTROL Hit] kan du dela upp besökarinformation baserat på enskilda sidvyer. Standardbehållaren är [!UICONTROL Hit]. |
   | [!UICONTROL Components] (Dimension/mått/datumintervall) | Definiera upp till tre regler genom att lägga till komponenter (dimensioner, mått, datumintervall eller dimensionsvärden). Det finns tre sätt att hitta rätt komponent:<ul><li>Börja skriva så hittar snabbsegmentsverktyget automatiskt rätt komponent.</li><li>Använd listrutan för att hitta komponenten.</li><li>Dra och släpp komponenter från den vänstra listen.</li></ul> |
   | [!UICONTROL Operator] | Använd listrutan för att hitta standardoperatorer och [!UICONTROL Distinct Count] operatorer. Se [Segmentoperatorer](/help/components/segmentation/seg-reference/seg-operators.md). |
   | Plustecken (+) | Lägg till en annan regel |
   | OCH/ELLER-kvalificerare | Du kan lägga till&quot;AND&quot;- eller&quot;OR&quot;-kvalificerare i reglerna, men du kan inte blanda&quot;AND&quot; och&quot;OR&quot; i en enskild segmentdefinition. |
   | [!UICONTROL Apply] | Använd det här segmentet på panelen. Om segmentet inte innehåller några data tillfrågas du om du vill fortsätta. |
   | [!UICONTROL Open builder] | Öppnar segmentbyggaren. När du har sparat eller använt segmentet i segmentbyggaren betraktas det inte längre som ett&quot;snabbsegment&quot;. Den blir en del av segmentbiblioteket för komponentlistor. <p>Markera alternativet om du vill att komponenten ska vara tillgänglig i alla dina projekt och i den vänstra listen [!UICONTROL **Gör det här segmentet tillgängligt för alla projekt och lägg till det i komponentlistan**].</p><p>Mer information finns i avsnittet [Spara ett snabbsegment som ett komponentlistsegment](#save-a-quick-segment-as-a-component-list-segment) i den här artikeln.</p><p>**Obs!** Endast användare med behörigheten Skapa segment i [Adobe Admin Console](/help/admin/admin-console/permissions/analytics-tools.md) kan öppna segmentbyggaren.</p> |
   | [!UICONTROL Cancel] | Avbryt det här snabbsegmentet (använd det inte). |
   | [!UICONTROL Date range] | Valideraren använder panelens datumintervall för sin datasökning. Alla datumintervall som används i ett snabbsegment åsidosätter panelens datumintervall högst upp på panelen. |
   | Förhandsgranska (överst till höger) | Här kan du se om du har ett giltigt segment och hur brett segmentet är. Representerar den uppdelning av datauppsättningen som du kan förvänta dig att se när du använder det här segmentet. Du kan få ett meddelande som anger att det här segmentet saknar data. I så fall kan du fortsätta eller ändra segmentdefinitionen. |

1. Välj [!UICONTROL **Använd**] för att spara ändringarna.

## Redigera snabbsegment

1. Hovra över snabbsegmentet och välj **Redigera** -ikon.

   ![Redigera ad hoc-filter](assets/filter-adhoc-edit.png)

1. Redigera segmentdefinitionen och/eller segmentnamnet.

1. Välj [!UICONTROL **Använd**].

## Spara ett snabbsegment som ett komponentlistsegment

>[!IMPORTANT]
>
> Tänk på följande när du sparar ett snabbsegment:
> 
> * Om du vill spara ett snabbsegment måste du ha behörigheten Skapa segment i [Adobe Admin Console](/help/admin/admin-console/permissions/analytics-tools.md).
> 
> * När du har sparat eller använt segmentet kan det inte längre redigeras i snabbsegmentsverktyget. I stället måste du använda den vanliga segmentbyggaren.

Du kan välja att spara snabbsegment som komponentlistsegment. Fördelar med segment i komponentlistor är bland annat:

* Tillgänglighet i alla dina arbetsyteprojekt
* Stödja mer komplexa segment såväl som sekventiella segment

Du kan spara segment antingen från snabbsegmentsverktyget eller från [!UICONTROL Filter Builder].

### Spara i snabbsegmentsverktyget {#save2}

1. När du har tillämpat snabbsegmentet håller du pekaren över det och väljer ikonen för info (&quot;i&quot;).
1. Välj **[!UICONTROL Make available to all projects and add to your component list]**.
1. (Valfritt) Byt namn på segmentet.
1. Välj **[!UICONTROL Save]**.

   Segmentet visas nu i komponentlistan i den vänstra listen. Observera också att segmentets sidlist ändras från ljusblå till mörkblå, vilket anger att den inte längre kan redigeras eller öppnas i snabbsegmentsverktyget.

### Spara i segmentbyggaren {#save3}

1. När du har tillämpat snabbsegmentet håller du pekaren över det och väljer ikonen för info (&quot;i&quot;).
1. Välj **[!UICONTROL Save segment]**
1. (Valfritt) Byt namn på segmentet och välj sedan [!UICONTROL **Använd**].

   Gå tillbaka till arbetsytan och lägg märke till att segmentets sidlist ändras från ljusblå till mörkblå, vilket anger att den inte längre kan redigeras eller öppnas i snabbsegmentsverktyget. Och genom att spara det blir det en del av komponentlistan.

När du har tillämpat segmentet kan du välja att lägga till det i segmentkomponentlistan och göra det tillgängligt för alla projekt.

1. Håll pekaren över det sparade segmentet och välj pennikonen.

1. Välj [!UICONTROL **Open Builder**].

1. Lägg märke till [!UICONTROL **Segment endast för projekt**] dialog:

   ![segmentdialogruta endast för projekt](assets/project-only-segment-dialog.png)

1. Markera kryssrutan intill **[!UICONTROL Make available to all your projects and add to your component list.]**

1. Välj **[!UICONTROL Save]**.

   Segmentet visas nu i segmentkomponentlistan för alla dina projekt.
Du kan också [dela segmentet](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/curate.html#concept_4A9726927E7C44AFA260E2BB2721AFC6) med andra i organisationen.

## Exempel på snabbsegment

I följande exempel kombineras mått och mätvärden:

![](assets/quick-seg2.png)

## Känt fel

1. Skapa ett snabbsegment med 2 poster och **[!UICONTROL Save]** det som Test1.
1. Klicka **[!UICONTROL Save as]** och spara detta snabbsegment som Test2.
1. Redigera snabbsegmentet Test2 och spara det igen som Test2.
Observera att snabbsegmentet Test1 ändras av Test2.
