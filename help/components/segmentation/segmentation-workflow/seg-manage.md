---
description: Segmenthanteraren erbjuder många sätt att strukturera segment, som att dela, filtrera, tagga, godkänna, kopiera, ta bort och markera som favoriter.
title: Hantera segment (segmenthanteraren)
feature: Segmentation
exl-id: be182a55-23cb-415f-a7d0-3c1efeead1a1
source-git-commit: df9c6d59ef5f5c43d0e1ef822bd23bc0e09ff20e
workflow-type: tm+mt
source-wordcount: '744'
ht-degree: 0%

---

# Segmenthanterare

Segmenthanteraren erbjuder många sätt att strukturera segment, som att dela, filtrera, tagga, godkänna, kopiera, ta bort och markera som favoriter.

Segmenthanteraren i Analytics visar alla segment som du äger och som har delats med dig. Administratörsnivåanvändare kan se alla segment i organisationen. I den här översikten presenteras användargränssnittet och funktionerna i segmenthanteraren.

![Segmenthanteraren](assets/segments-manager.png)

## Öppna segmenthanteraren

1. I Adobe Analytics väljer du fliken **[!UICONTROL Components]** och sedan **[!UICONTROL Segments]**.

   eller

   I en befintlig rapport väljer du segmentikonen ![](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Segmentation_18_N.svg) i den vänstra navigeringen och sedan **[!UICONTROL Manage]**.

## Tillgängliga åtgärder i segmenthanteraren

I segmenthanteraren kan du:

* [Filtrera segment](/help/components/segmentation/segmentation-workflow/t-seg-filter.md)

* [Markera segment som favoriter](/help/components/segmentation/segmentation-workflow/t-seg-favorite.md)

* [Godkänn segment](/help/components/segmentation/segmentation-workflow/seg-approve.md)

* [Tagga segment](/help/components/segmentation/segmentation-workflow/seg-tag.md)

* [Dela segment](/help/components/segmentation/segmentation-workflow/t-seg-share.md)

* Exportera ett segment till en CSV-fil.

* [Kopiera segment](/help/components/segmentation/segmentation-workflow/seg-copy.md)

* [Ta bort segment](/help/components/segmentation/segmentation-workflow/seg-delete.md)

## Konfigurera kolumner

Du kan konfigurera den information som visas för varje segment i segmenthanteraren genom att konfigurera de kolumner som visas.

Så här konfigurerar du synliga kolumner i segmenthanteraren:

1. I Adobe Analytics väljer du fliken **[!UICONTROL Components]** och sedan **[!UICONTROL Segments]**.

1. I segmenthanteraren väljer du ikonen **Anpassa kolumner** ![Anpassa kolumner](assets/customize-columns-icon.png) och markerar sedan de kolumner som du vill ska visas i segmenthanteraren.

   Följande kolumner är tillgängliga:

   | Kolumnrubrik | Beskrivning |
   |---|---|
   | Titel och beskrivning | Dessa värden anges i segmentbyggaren. Om du vill redigera titeln och beskrivningen markerar du titellänken för att öppna segmentbyggaren. |
   | Favoriter | Visar stjärnikoner bredvid varje segment, så att du kan markera segment som favoriter. Mer information finns i [Markera segment som favoriter](/help/components/segmentation/segmentation-workflow/t-seg-favorite.md). |
   | Rapportsviter | Den här kolumnen anger i vilken rapportsserie segmentet senast sparades. |
   | Ägare | Anger vem som äger segmentet. Som icke-administratör kan du bara se segment som du äger eller de som delats med dig. |
   | Taggar (inte incheckad i kolumnväljare, därför visas inte kolumnen) | Taggar som har tillämpats på segmentet, antingen av dig eller av personer som delat segmentet med dig. |
   | Delas med | Visar enskilda personer eller grupper (endast Admin) eller Alla (endast Admin) som du har delat segmentet med. <p>När ett segment delas av dig eller med dig visas en delningsikon bredvid segmentnamnet.</p> |
   | Ändrat den | Visar datumet då segmentet senast ändrades. |
   | Används i | Visar hur många komponenter segmentet används i. <p>Om segmentet till exempel används i 40 projekt och 2 varningar visas värdet för den här kolumnen som [!UICONTROL **42 komponenter**].</p> <p>Markera värdet i den här kolumnen för att se hur segmentet delas upp (till exempel [!UICONTROL **Projekt (40)**], [!UICONTROL **Varningar (2)**]).</p><p>Segment kan användas i följande komponenttyper:</p> <ul><li>Larm</li><li>Projekt</li><li>Schemalagda projekt</li><li>Beräknade mått</li></ul><p>Den här informationen kan hjälpa dig att avgöra om en komponent är värdefull för användare i organisationen, var den används och om den behöver tas bort eller ändras.</p><p>Tänk på följande när du visar den här kolumnen:</p><ul><li>Den här informationen inkluderar inte användning från API, Report Builder eller Data Warehouse.</li><li>Kolumnen [!UICONTROL **Används i**] visas inte som standard. [Konfigurera kolumner](#configure-columns) så att de visas.</li><li>Om det inte finns några data i den här kolumnen för en viss komponent, men den har datumet [!UICONTROL **Senast använd**], kan komponenten ha använts i en analys utan att sparas.</li><li>Den här informationen är endast tillgänglig för systemadministratörer.</li></ul><p>Du kan använda [Data Dictionary](/help/analyze/analysis-workspace/components/data-dictionary/data-dictionary-overview.md) tillsammans med den här informationen för att hjälpa dig att hålla reda på och bättre förstå hur komponenter används i din organisation.</p> |
   | Senast använd | Visar datumet då segmentet senast användes i någon av följande komponenttyper: <ul><li>Larm</li><li>Beräknade mått</li><li>Projekt</li><li>Schemalagda projekt</li><li>Segment</li></ul> <p>Den här informationen kan hjälpa dig att avgöra om en komponent är värdefull för användare i organisationen, var den används och om den behöver tas bort eller ändras.</p><p>Tänk på följande när du visar den här kolumnen:</p><ul><li>Den här informationen inkluderar inte användning från API, Report Builder eller Data Warehouse.</li><li>För vissa komponenter kanske den här kolumnen inte innehåller data om komponenten senast användes före september 2023.</li><li>Den här informationen är endast tillgänglig för systemadministratörer.</li></ul><p>Du kan använda [Data Dictionary](/help/analyze/analysis-workspace/components/data-dictionary/data-dictionary-overview.md) tillsammans med den här informationen för att hjälpa dig att hålla reda på och bättre förstå hur komponenter används i din organisation. |

   {style="table-layout:auto"}

## Videoinstruktion {#section_B3C5DA22DC5248DBA17C56E03DA2D4F2}

Den här [Adobe Analytics-videon](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/components/segmentation/segment-management-and-sharing.html) ger en kort översikt över hur du använder segmenthanteraren.


