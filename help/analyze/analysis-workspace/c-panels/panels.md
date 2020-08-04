---
description: 'null'
title: Översikt över paneler
translation-type: tm+mt
source-git-commit: 68ff30395daf5cfb26d3e597ec4e6098a856fb51
workflow-type: tm+mt
source-wordcount: '477'
ht-degree: 2%

---


# Översikt över paneler

En panel är en samling tabeller och visualiseringar. Du kommer åt panelerna från den övre vänstra ikonen i arbetsytan. Paneler är användbara när du vill ordna dina projekt efter tidsperioder, affärsenheter, geografi, osv. Följande sex typer av paneler finns i Analysis Workspace:

* [Tom panel](blank-panel.md)
* [Panelen Snabbinsikter](quickinsight.md)
* [Analyser för målpanelen](a4t-panel.md)
* [Panelen Attribution](attribution.md)
* [Frihandspanel](freeform-panel.md)
* [Segmentjämförelsepanel](c-segment-comparison/segment-comparison.md)

Panelerna Quick Insights, Blank och Frihand är bra platser att börja med, medan Analytics for Target, Attribution IQ och Segment Comparison passar in på mer avancerade analyser. En `"+"` knapp är tillgänglig i projekt, så du kan när som helst lägga till tomma paneler.

Standardstartpanelen är friformspanelen, men du kan även göra den [tomma panelen](/help/analyze/analysis-workspace/c-panels/blank-panel.md) till standard.

## Nedrullningsbara filter i paneler {#section_D2828EEDD52944528E87F470EAB581CF}

Panelens listzon har funktioner för nedrullningsbar filtrering. Med dessa filter kan du interagera med projektdata på ett kontrollerat sätt så att du kan göra djupgående analyser, förenkla projekt och/eller dela insikter med andra.

Här är ett exempel på ett förenklat projekt: Anta att du har flera versioner av ett projekt/en panel för landsspecifik rapportering. Du kan nu komprimera dessa projekt/paneler till en enda panel och lägga till i en nedrullningsbar listruta i stället för att filtrera mellan olika datauppsättningar.

![](assets/dropdowns.png)

Tänk på detta:

* Du kan släppa flera komponenter (eller dimensionsobjekt) och sedan växla mellan dem i en listruta för att filtrera panelinnehållet.
* Du kan också skapa flera nedrullningsbara listor på samma panel.
* Du kan anpassa titeln på den nedrullningsbara listan genom att klicka på titeln och ändra den, eller ta bort titeln helt genom att klicka på x:et bredvid den.
* Du kan skapa nedrullningsbara filter med valfri komponenttyp: dimensioner, datumintervall, segment och mätvärden. Observera att datumintervall i listrutan alltid åsidosätter panelens datumintervall.
* Vi behåller komponentfärgerna från vänster skena: gult för dimensionsobjektlistrutor, grönt för mätvärden, blått för segment och lila för datumintervall.
* Dropzone kommer fortfarande att skapa träffnivåsegment för objekt som dras som segment. Du kan ändra dessa som vanligt genom att klicka på informationsikonen (i) bredvid segmentet, sedan den pennformade redigeringsikonen och redigera den i segmentbyggaren.

**Så här skapar och använder du nedrullningsbara filter:**

1. Markera ett objekt i den vänstra listen och släpp det **i panelens släppzon samtidigt som du håller ned tangenten**.

   ![](assets/create_dropdown.png)

   Detta gör att komponenterna förvandlas till en nedrullningsbar lista i stället för till ett segment. (Du kan även lägga till segment genom att inte hålla ned tangenten.)

   ![](assets/dropdown.png)

1. Välj ett av alternativen i listrutan om du vill ändra data i panelen nedan. (Du kan också välja att inte filtrera paneldata genom att markera **[!UICONTROL No filter]**.)
1. Om du till exempel även vill segmentera data efter marknadsföringskanal kan du lägga till en annan listruta som kallas&quot;marknadsföringskanal&quot;:

   ![](assets/mc_dropdown.png)

