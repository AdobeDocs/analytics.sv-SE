---
description: En panel som visar nästa eller föregående dimensionsobjekt för en viss dimension.
title: Panelen Nästa eller föregående objekt
feature: Panels
role: User, Admin
exl-id: 9f2f8134-2a38-42bb-b195-5e5601d33c4e
source-git-commit: d173a6c6c9751a86f4218ec842da17da14f8485b
workflow-type: tm+mt
source-wordcount: '409'
ht-degree: 0%

---

# Panelen Nästa eller föregående objekt

Panelen innehåller ett antal tabeller och visualiseringar för att enkelt identifiera nästa eller föregående dimensionsobjekt för en viss dimension. Du kanske till exempel vill utforska vilka sidor kunderna besöker oftast efter att de besökt hemsidan.

## Öppna panelen

Du kommer åt panelen inifrån [!UICONTROL Reports] eller inom [!UICONTROL Workspace].

| Åtkomstpunkt | Beskrivning |
| --- | --- |
| [!UICONTROL Reports] | <ul><li>Panelen har redan släppts i ett projekt.</li><li>Den vänstra listen är komprimerad.</li><li>Om du valde [!UICONTROL Next page]har standardinställningar redan tillämpats, till exempel [!UICONTROL Page] for [!UICONTROL Dimension]och den översta sidan som [!UICONTROL Dimension Item], [!UICONTROL Next] for [!UICONTROL Direction] och [!UICONTROL Visit] for [!UICONTROL Container]. Du kan ändra alla dessa inställningar.</li></ul>![Panelen Nästa/Föregående](assets/next-previous.png) |
| Arbetsyta | Skapa ett nytt projekt och välj panelikonen i den vänstra listen. Dra sedan [!UICONTROL Next or previous item] ovanför friformstabellen. Observera att [!UICONTROL Dimension] och [!UICONTROL Dimension Item] fält lämnas tomma. Välj en dimension i listrutan. [!UICONTROL Dimension items] fylls i baserat på [!UICONTROL dimension] du valde. Den översta dimensionsobjektet läggs till, men du kan välja en annan artikel. Standardvärdena är Nästa och Besökare. Även här kan du ändra dem.<p>![Panelen Nästa/Föregående](assets/next-previous2.png) |

{style="table-layout:auto"}

## Panelindata {#Input}

Du kan konfigurera [!UICONTROL Next or previous item] Panelen med dessa indatainställningar:

| Inställning | Beskrivning |
| --- | --- |
| Släppzon för segment (eller annan komponent) | Du kan dra och släppa segment eller andra komponenter för att ytterligare filtrera panelresultaten. |
| Dimension | Dimensionen som du vill utforska nästa eller föregående objekt för. |
| Dimension | Det specifika objektet i mitten av nästa/föregående fråga. |
| Riktning | Ange om du letar efter [!UICONTROL Next] eller [!UICONTROL Previous] dimensionsobjekt. |
| Behållare | [!UICONTROL Visit] eller [!UICONTROL Visitor] (standard) avgör omfattningen av din förfrågan. |

{style="table-layout:auto"}

Klicka **[!UICONTROL Build]** för att skapa panelen.

## Panelutdata {#output}

The [!UICONTROL Next or previous item] panelen returnerar en mängd data och visualiseringar som hjälper dig att förstå vad som händer efter eller före specifika dimensionsobjekt.

![Nästa/Föregående panelutdata](assets/next-previous-output.png)

![Nästa/Föregående panelutdata](assets/next-previous-output2.png)

| Visualisering | Beskrivning |
| --- | --- |
| Vågrätt fält | Visar nästa (eller föregående) objekt baserat på den dimensionspost du valde. Om du placerar pekaren över ett enskilt fält markeras motsvarande objekt i tabellen Frihand. |
| Sammanfattningsnummer | Sammanfattningsnummer på hög nivå för alla förekomster av nästa eller föregående dimensionsobjekt för den aktuella månaden (hittills). |
| Frihandsregister | Visar nästa (eller föregående) objekt baserat på den dimensionspost som du har valt i ett tabellformat. Det var till exempel de mest populära sidorna (av händelser) som folk gick till efter (eller före) hemsidan eller arbetsytesidan. |

{style="table-layout:auto"}
