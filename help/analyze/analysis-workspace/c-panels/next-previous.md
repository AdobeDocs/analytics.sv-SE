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

Du kan komma åt panelen inifrån [!UICONTROL Reports] eller i [!UICONTROL Workspace].

| Åtkomstpunkt | Beskrivning |
| --- | --- |
| [!UICONTROL Reports] | <ul><li>Panelen har redan släppts i ett projekt.</li><li>Den vänstra listen är komprimerad.</li><li>Om du valde [!UICONTROL Next page] har standardinställningar redan tillämpats, till exempel [!UICONTROL Page] för [!UICONTROL Dimension] och den översta sidan som [!UICONTROL Dimension Item], [!UICONTROL Next] för [!UICONTROL Direction] och [!UICONTROL Visit] för [!UICONTROL Container]. Du kan ändra alla dessa inställningar.</li></ul>![Nästa/Föregående panel](assets/next-previous.png) |
| Workspace | Skapa ett nytt projekt och välj panelikonen i den vänstra listen. Dra sedan panelen [!UICONTROL Next or previous item] ovanför frihandstabellen. Observera att fälten [!UICONTROL Dimension] och [!UICONTROL Dimension Item] är tomma. Välj en dimension i listrutan. [!UICONTROL Dimension items] fylls i baserat på den [!UICONTROL dimension] du valde. Den översta dimensionsobjektet läggs till, men du kan välja en annan artikel. Standardvärdena är Nästa och Besökare. Även här kan du ändra dem.<p>![Nästa/Föregående panel](assets/next-previous2.png) |

{style="table-layout:auto"}

## Panelindata {#Input}

Du kan konfigurera panelen [!UICONTROL Next or previous item] med följande indatainställningar:

| Inställning | Beskrivning |
| --- | --- |
| Släppzon för segment (eller annan komponent) | Du kan dra och släppa segment eller andra komponenter för att ytterligare filtrera panelresultaten. |
| Dimension | Dimensionen som du vill utforska nästa eller föregående objekt för. |
| Dimension | Det specifika objektet i mitten av nästa/föregående fråga. |
| Riktning | Ange om du letar efter dimensionsobjektet [!UICONTROL Next] eller [!UICONTROL Previous]. |
| Behållare | [!UICONTROL Visit] eller [!UICONTROL Visitor] (standard) avgör omfattningen av din fråga. |

{style="table-layout:auto"}

Klicka på **[!UICONTROL Build]** för att skapa panelen.

## Panelutdata {#output}

Panelen [!UICONTROL Next or previous item] returnerar en mängd data och visualiseringar som hjälper dig att förstå vilka förekomster som följer eller föregår specifika dimensionsobjekt.

![Nästa/Föregående panelutdata](assets/next-previous-output.png)

![Nästa/Föregående panelutdata](assets/next-previous-output2.png)

| Visualisering | Beskrivning |
| --- | --- |
| Vågrätt fält | Visar nästa (eller föregående) objekt baserat på den dimensionspost du valde. Om du placerar pekaren över ett enskilt fält markeras motsvarande objekt i tabellen Frihand. |
| Sammanfattningsnummer | Sammanfattningsnummer på hög nivå för alla förekomster av nästa eller föregående dimensionsobjekt för den aktuella månaden (hittills). |
| Frihandsregister | Visar nästa (eller föregående) objekt baserat på den dimensionspost som du har valt i ett tabellformat. Det var till exempel de mest populära sidorna (av händelser) som folk gick till efter (eller före) hemsidan eller arbetsytesidan. |

{style="table-layout:auto"}
