---
description: En rapportsvit definierar den fullständiga, oberoende rapporteringen på en vald webbplats, en uppsättning webbplatser eller en delmängd av webbsidor. Vanligtvis är en rapportserie en webbplats, men den kan vara ett globalt segment där du har kombinerat flera webbplatsers nummer för att få summor. När du loggar in på en Adobe Analytics-lösning väljer du en rapportsvit att använda (förutom när du använder sammanslagningar som kombinerar rapportsviter). En rapportsvit kan dessutom vara mindre än en webbplats om du vill köra rapporter för en del av webbplatsen. Analytics lösningar sammanställer och rapporterar om dessa datalager. Med Admin Report Suite Manager kan du definiera regler som styr hur data behandlas i en rapportserie.
title: Hanterare för rapportsvit
topic: Admin tools
uuid: 018c4f63-4d87-4a2e-8c71-1ba7f5dd9446
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '527'
ht-degree: 2%

---


# Hanterare för rapportsvit

En rapportsvit definierar den fullständiga, oberoende rapporteringen på en vald webbplats, en uppsättning webbplatser eller en delmängd av webbsidor. Vanligtvis är en rapportserie en webbplats, men den kan vara ett globalt segment där du har kombinerat flera webbplatsers nummer för att få summor. När du loggar in på en Adobe Analytics-lösning väljer du en rapportsvit att använda (förutom när du använder sammanslagningar som kombinerar rapportsviter). En rapportsvit kan dessutom vara mindre än en webbplats om du vill köra rapporter för en del av webbplatsen. Analytics lösningar sammanställer och rapporterar om dessa datalager. Med Admin Report Suite Manager kan du definiera regler som styr hur data behandlas i en rapportserie.

**[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]**

>[!NOTE]
>
>Virtuella rapportsviter hanteras via **[!UICONTROL Analytics]** > **[!UICONTROL Components]** > **[!UICONTROL Virtual Report Suites]**. Se dokumentationen för [Virtual Report Suite](/help/components/vrs/vrs-about.md).

## Beskrivning av Report Suite Manager {#section_0C94DC9EACDA4F5891F5CD63EE80B125}

I följande tabell beskrivs element på [!UICONTROL Report Suite Manager] sidan.

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
   <td colname="col2"> <p>Report Suite Manager <span class="wintitle"></span> markerar ett valt rapportpaket. Du kan välja flera rapportsviter genom att <span class="uicontrol"> Ctrl-klicka</span> eller <span class="uicontrol"> Skift-klicka</span>. </p> <p>En vald rapportsvit förblir markerad tills du väljer en annan rapportsvit. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Hämta</span> </td> 
   <td colname="col2"> Skapar ett Excel-kalkylblad med alla inställningar för de markerade rapportsviterna. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Sök</span> </td> 
   <td colname="col2"> Här kan du hitta en specifik rapportsserie i Report Suite-listan. Sökverktyget innehåller både grundläggande namnbaserad sökning och en avancerad söksida för djupgående sökningar. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Grupper</span> </td> 
   <td colname="col2"> <p>Här kan du ordna dina rapportsviter i anpassade grupper. Du kan snabbt komma åt flera rapportsviter som delar liknande inställningar eller som du vanligtvis redigerar tillsammans. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Sparade sökningar</span> </td> 
   <td colname="col2"> <p>En dynamisk grupp som använder funktionen <span class="wintitle"> Avancerad sökning</span> för att definiera en uppsättning villkor som bestämmer dess medlemmar. När du lägger till eller ändrar rapportsviter i <span class="wintitle"> Report Suite Manager</span>lägger den <span class="wintitle"> sparade sökningen</span> automatiskt till de rapportsviter som matchar kriterierna. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Samlingar</span> </td> 
   <td colname="col2"> <p>En sammanslagning är en enda rapportserie som kombinerar spårningsdata från flera andra rapportsviter. </p> <p>Se <a href="/help/admin/c-manage-report-suites/rollup-report-suite.md"> Samlingsrapportsviter</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Redigera inställningar</span> </td> 
   <td colname="col2"> När du redigerar en rapportserie används ändringarna på alla valda rapportsviter. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Skapa nytt</span> </td> 
   <td colname="col2">Se <a href="/help/admin/c-manage-report-suites/c-new-report-suite/new-report-suite.md"> New Report Suite</a>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Anpassa kolumner</span> </td> 
   <td colname="col2">Här kan du välja kolumner att lägga till i <span class="wintitle"> Report Suite Manager</span>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Rapportsvit-ID</span> </td> 
   <td colname="col2">Se <a href="/help/admin/c-manage-report-suites/c-new-report-suite/new-report-suite.md"> New Report Suite</a>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Platsrubrik</span> </td> 
   <td colname="col2"> <p>Identifierar rapportsviter i Admin Tools och i listrutan för rapportsviter i rubriken för marknadsföringsrapport. </p> <p>Se <a href="/help/admin/c-manage-report-suites/c-new-report-suite/new-report-suite.md"> New Report Suite</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Bas-URL</span> </td> 
   <td colname="col2"> <p>Definierar basdomänen för rapportsviten. </p> <p>Se <a href="/help/admin/c-manage-report-suites/c-new-report-suite/new-report-suite.md"> New Report Suite</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

