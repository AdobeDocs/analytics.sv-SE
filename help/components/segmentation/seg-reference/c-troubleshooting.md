---
description: Felsök och åtgärda problem som rör segment.
title: Felsökning av segmentering
feature: Segmentation
exl-id: ca51110e-1ba7-4182-b5b2-baf9b0c017af
source-git-commit: d85e6990998e3c153ef969d8dc7f3a4835f683bf
workflow-type: tm+mt
source-wordcount: '164'
ht-degree: 0%

---

# Felsökning av segmentering

<!-- Looks like this is not part anymore of the current UI.

## Error: "Incompatible elements in this segment" {#incompatible}

This error occurs when you try to save a segment in the Data Warehouse folder where the segment contains elements not compatible with Data Warehouse. To resolve this error, do one of two things:

* Save the segment in a different folder 
* Remove or change the incompatible portions of the segment.

-->

## Varför returnerar mitt segment inga data alls? {#no-data}

Möjliga orsaker:

* Invertera kapsling - t.ex. kapsling av en ![användare](/help/assets/icons/User.svg) **[!UICONTROL Visitor]** -behållare under en ![Besök](/help/assets/icons/Visit.svg) **[!UICONTROL Visit]** -behållare.
* Rapporten stöder inte segmentering.
* Det finns inga data som matchar segmenteringskriterierna.

## Varför kan jag inte se segmentet jag skapade i segmenthanteraren? {#invisible}

Möjliga orsaker:

* Vissa dimensioner är bara tillgängliga i Data Warehouse och inte i segmenthanteraren.
* Segmentet kontrolleras bara för en viss rapportserie.
* Ett delat segment kan ha tagits bort av en annan användare.
* Det gick inte att läsa in segment på grund av ett datacenter- eller webbläsarcacheproblem.
* Segmentet har inte sparats.
* IP-adressen kan blockeras vid användarens slut.

## Varför verkar de data som visas när du har använt ett segment felaktigt? {#page-data}

Möjliga orsaker:

* Regler eller operatorer är felaktiga för det obligatoriska resultatet.
* Felaktig användning av behållare i segmentet.
* Trafikvariablerna som används för segmentering är inte korrekt inställda eller har gått ut.
