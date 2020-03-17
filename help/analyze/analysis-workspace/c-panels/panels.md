---
description: 'null'
title: Paneler - översikt
uuid: 480700e6-332e-44f2-a486-e3d1852cddbc
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Paneler - översikt

En panel är en samling tabeller och visualiseringar. Du kommer åt panelerna från den övre vänstra ikonen i arbetsytan. Paneler är användbara när du vill ordna dina projekt efter tidsperioder, affärsenheter, geografi, osv. Följande fyra typer av paneler är tillgängliga i Analysis Workspace: Tom panel, Attribution, Frihandspanel och Segmentjämförelse.

Panelen Tom och Frihand är platser där du kan börja analysera, medan attribuerings-IQ och Segmentjämförelse är mer avancerade analyser. Vi har också lagt till en plusknapp (+) så att du när som helst kan lägga till tomma paneler.

Standardstartpanelen är panelen Frihand, men du kan också göra den [tomma panelen](/help/analyze/analysis-workspace/c-panels/blank-panel.md) till standard.

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

