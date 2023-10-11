---
description: En rapportsvit definierar den fullständiga, oberoende rapporteringen på en vald webbplats, en uppsättning webbplatser eller en delmängd av webbsidor.
title: Hanterare för rapportsvit
feature: Report Suite Settings
exl-id: c36e5378-c8a7-4f18-b143-8ce862638c76
source-git-commit: 266cf18050d60f08f7e170c56453d1e1d805cb7b
workflow-type: tm+mt
source-wordcount: '405'
ht-degree: 3%

---

# Hanterare för rapportsvit

En rapportsvit definierar den fullständiga, oberoende rapporteringen för följande datalager:

* En enda webbplats (oftast)

* En del eller delmängd av en webbplats

* Ett globalt segment som består av flera webbplatsers tal för att få summor

Analyslösningar sammanställer och rapporterar om dessa datalager. Med Admin Report Suite Manager kan du definiera regler som styr hur data behandlas i en rapportserie.

När du loggar in på en Adobe Analytics-lösning väljer du en rapportsvit att använda (förutom när du använder sammanslagningar som kombinerar rapportsviter).

Så här kommer du åt en rapportserie:

**[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL All admin]** > **[!UICONTROL Report suites]**

>[!NOTE]
>
>Virtuella rapporteringsprogram hanteras via **[!UICONTROL Analytics]** > **[!UICONTROL Components]** > **[!UICONTROL Virtual report suites]**. Läs mer i [Virtuell rapportsvitdokumentation](/help/components/vrs/vrs-about.md).

## Beskrivning av Report Suite Manager {#section_0C94DC9EACDA4F5891F5CD63EE80B125}

I följande tabell beskrivs elementen i [!UICONTROL Report Suite Manager] sida.

<table id="table_F739FBD8DB8D409E916F12F61C5953D0"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Element </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Välj Report Suite</span> </td> 
   <td colname="col2"> <p>The <span class="wintitle"> Report Suite Manager</span> markerar en vald rapportserie. Du kan välja flera rapportsviter med <span class="uicontrol"> Ctrl+klicka</span> eller <span class="uicontrol"> Skift+klicka</span>. </p> <p>En vald rapportsvit förblir markerad tills du väljer en annan rapportsvit. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Hämta</span> </td> 
   <td colname="col2"> Skapar ett Excel-kalkylblad med alla inställningar för de markerade rapportsviterna. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Sök</span> </td> 
   <td colname="col2"> Här kan du hitta en viss rapportserie i Report Suite-listan. Sökverktyget innehåller både grundläggande namnbaserad sökning och en avancerad söksida för djupgående sökningar. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Grupper</span> </td> 
   <td colname="col2"> <p>Här kan du ordna dina rapportsviter i anpassade grupper. Du kan snabbt komma åt flera rapportsviter som delar liknande inställningar eller som du vanligtvis redigerar tillsammans. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Sparade sökningar</span> </td> 
   <td colname="col2"> <p>En dynamisk grupp som använder <span class="wintitle"> Avancerad sökning</span> -funktion för att definiera en uppsättning villkor som bestämmer dess medlemmar. När du lägger till eller ändrar rapportsviter i <span class="wintitle"> Report Suite Manager</span>, <span class="wintitle"> Sparad sökning</span> lägger automatiskt till de rapportsviter som matchar kriterierna. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Samlingar</span> </td> 
   <td colname="col2"> <p>En sammanslagning är en enda rapportserie som kombinerar spårningsdata från flera andra rapportsviter. </p> <p>Se <a href="/help/admin/admin/c-manage-report-suites/rollup-report-suite.md"> Sammanslagningsrapportsviter</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Redigera inställningar</span> </td> 
   <td colname="col2"> När du redigerar en rapportserie används ändringarna på alla valda rapportsviter. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Skapa nytt</span> </td> 
   <td colname="col2">Se <a href="/help/admin/admin/c-manage-report-suites/c-new-report-suite/new-report-suite.md"> Ny rapportsvit</a>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Anpassa kolumner</span> </td> 
   <td colname="col2">Här kan du välja vilka kolumner som ska läggas till i <span class="wintitle"> Report Suite Manager</span>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Rapportsvit-ID</span> </td> 
   <td colname="col2">Se <a href="/help/admin/admin/c-manage-report-suites/c-new-report-suite/new-report-suite.md"> Ny rapportsvit</a>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Platsrubrik</span> </td> 
   <td colname="col2"> <p>Identifierar rapportsviter i Admin Tools och i listrutan för rapportsviter i rubriken för marknadsföringsrapport. </p> <p>Se <a href="/help/admin/admin/c-manage-report-suites/c-new-report-suite/new-report-suite.md"> Ny rapportsvit</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Bas-URL</span> </td> 
   <td colname="col2"> <p>Definierar basdomänen för rapportsviten. </p> <p>Se <a href="/help/admin/admin/c-manage-report-suites/c-new-report-suite/new-report-suite.md"> Ny rapportsvit</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>
