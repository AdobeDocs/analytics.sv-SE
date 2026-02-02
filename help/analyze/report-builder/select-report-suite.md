---
title: Välj en rapportsvit i Report Builder
description: Lär dig hur du väljer en rapportserie i Report Builder.
role: User
feature: Report Builder
type: Documentation
solution: Analytics
exl-id: 96e24d5d-78fb-4e5c-8513-c5fe221d0aeb
source-git-commit: 6f7de360ac24261eabb46c6cfce99449261706de
workflow-type: tm+mt
source-wordcount: '340'
ht-degree: 0%

---

# Välj en rapportsvit

Du kan välja en rapportsserie i listrutan eller välja en rapportsvit från en cell och automatiskt uppdatera ditt datablock med en ny rapportsvit.

## Välj rapportsvit från en cell

Om du väljer en rapportsserie från en cell är det enkelt att uppdatera datablock med hjälp av olika rapportsviter. I stället för att skapa helt nya rapporter med separata datablock kan du uppdatera datablocken med ett rapportpaket som är valt från en cell.

Att välja en rapportsvit från en cell är praktiskt när du har:

* Flera rapportsviter som liknar eller är identiska med varandra i strukturen.
* Komplicerade datablockformat som innehåller anpassade komponenter och layouter.

Om du vill välja en rapportserie från en cell skapar du först ett datablock och tilldelar flera rapportsviter till en cell utanför datablocket. Använd sedan panelen **[!UICONTROL Report suite from cell]** för att uppdatera dina datablock från olika rapportsviter.

1. Skapa ett datablock. Mer information om hur du skapar ett datablock finns i [Skapa ett datablock](/help/analyze/report-builder/create-a-data-block.md).

1. Välj ![DataViewSelector](/help/assets/icons/DataViewSelector.svg) i **[!UICONTROL Report suites]**.

1. Markera en cell utanför datablocket med ![DataBlockSelector](/help/assets/icons/DataBlockSelector.svg) .

1. Lägg till en eller flera rapportsviter från **[!UICONTROL Select report suites to add to report suite from cell]** genom att dra och släppa. Du kan också dubbelvälja en rapportserie och lägga till rapportsviten i listan **[!UICONTROL Report suites included]**.

   * Du kan använda ![Sök](/help/assets/icons/Search.svg) **[!UICONTROL _Välj rapportsviter_]** för att söka efter rapportsviter.
   * Använd ![MoreSmall](/help/assets/icons/MoreSmall.svg) för att öppna en snabbmeny så att du kan flytta rapportsviter uppåt eller nedåt i listan **[!UICONTROL Report suites included]**.
   * Använd ![CrossSize75](/help/assets/icons/CrossSize75.svg) om du vill ta bort en rapportsvit från listan **[!UICONTROL Report suites included]**.

   ![Välj en rapportserie från en cell](assets/dataviews-from-a-cell.png){zoomable="yes"}

1. Välj **[!UICONTROL Apply]** om du vill använda de markerade rapportsviterna i den markerade cellen.


## Ändra rapportsviten från en cell

1. Markera rapportsvitens cellplats i bladet.
1. I Report Builder-navet väljer du länken **[!UICONTROL Report suites from cell]** i **[!UICONTROL Quick edit]**.
1. Välj en rapportsvit i listrutan **[!UICONTROL Report suite]**.

   ![Ändra rapportserie från en cell](assets/change-data-view-from-cell.png){zoomable="yes"}
1. Valfritt, välj **[!UICONTROL Refresh data block(s) upon change]**.

1. Välj **[!UICONTROL Apply]**. Report Builder uppdaterar datablocket baserat på det valda rapportpaketet.
