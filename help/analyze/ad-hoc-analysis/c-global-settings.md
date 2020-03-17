---
description: Konfigurera globala beteendeinställningar. Du kan till exempel konfigurera Spara automatiskt, diagram och tabellinställningar samt ange teckensnitt och språkområde.
title: Inställningar
uuid: 34444052-479b-4923-b379-a03ca614bf3e
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Inställningar

Konfigurera globala beteendeinställningar. Du kan till exempel konfigurera Spara automatiskt, diagram och tabellinställningar samt ange teckensnitt och språkområde.

## Inställningar {#concept_D21E3D6F13EA4F97913F60C243B72173}

Konfigurera globala beteendeinställningar. Du kan till exempel konfigurera Spara automatiskt, diagram och tabellinställningar samt ange teckensnitt och språkområde.

Klicka **[!UICONTROL Tools]** > **[!UICONTROL Settings]** för att komma åt [!UICONTROL Global Settings].

## Fliken Allmänna inställningar - Definitioner {#reference_EADAF83466994F89BCC6B0F49A9A53DB}

Konfigurera beteendeinställningar för datakällor, projektsparande, diagram och tabeller.

<!-- 

r_dsc_general_settings.xml

 -->

<table id="table_C18A0F1C9E214EB585A29801BA2400F8"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Fält </p> </th> 
   <th colname="col2" class="entry"> <p>Definition </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> Datainställningar </p> </td> 
   <td colname="col2"> <p> <span class="uicontrol"> Antal upprepningsinstanser</span>: Anger om instanser räknas i rapporter. Om du har flera sekventiella värden för samma variabel kan du alltså räkna dem som en eller flera instanser av variabeln. </p> <p>Du kan till exempel se upprepade sidladdningar, vilket är det antal gånger som sidorna på webbplatsen läses in eller uppdateras under ett enda besök. Med det här alternativet kan du ange om flera träffar på samma sida ska räknas som en eller flera sidvyer. </p> <p> <span class="uicontrol"> <span class="keyword"> Ad hoc</span> </span>: Anger <span class="keyword"> Ad Hoc</span> som enda datakälla för rapportering. Dessa data kommer från bildbegäranden som genereras av webbsidor. </p> <p> <span class="uicontrol"> <span class="keyword"> Datakällor</span> </span>: Anger om data som överförts från andra Adobe-källor eller anpassade datakällor ska användas. Dessa data blir tillgängliga för produkter i <span class="keyword"> Experience Cloud</span>. Mer information finns i <a href="https://marketing.adobe.com/resources/help/en_US/sc/datasources/index.html"  > Datakällor</a> . </p> <p> <span class="uicontrol"> Båda</span>: (Standard) Använder data från <span class="keyword"> ad hoc-analyser</span> och andra datakällor. </p> <p>Obs! Om du ändrar dessa alternativ kan det leda till skillnader i rapporteringen mellan <span class="keyword"> ad hoc-analysdata</span> och marknadsföringsrapporter <span class="keyword"> och analysdata.</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Spara automatiskt </p> </td> 
   <td colname="col2"> <p> <span class="uicontrol"> Spara automatiskt aktiverat</span>: Aktiverar autosparfunktioner. </p> <p> <span class="uicontrol"> Spara projektfrekvens</span>automatiskt: Gör att du kan justera tidsstegen för funktionen Spara automatiskt. En automatisk projektsparfunktion skapas endast vid en ad hoc-krasch. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Diagraminställningar </p> </td> 
   <td colname="col2"> <p><b>Komprimera diagram som standard</b>: Klicka på den här knappen om du vill visa rapporter utan diagram i det övre avsnittet. När en rapport visas med det här alternativet kan du utöka den manuellt. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Tabellinställningar </p> </td> 
   <td colname="col2"> <p> <span class="uicontrol"> Visa radnummer</span>: Aktiverar eller inaktiverar radnumrering i rapporttabellen. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Rankad flik - Definitioner {#reference_FB9BADD7E3DA42C1BB2A02A6E9D5C1CF}

Konfigurera hur data visas i kolumner och välj standardvärden för trafik- och konverteringsrapporter.

<!-- 

r_dsc_ranked_tab.xml

 -->

| Fält | Definition |
|--- |--- |
| Kolumninställningar | Konfigurera hur du vill visa celldata i tabeller och stolpdiagram. |
| Välj standardmått | Välj standardvärden för trafik- och konverteringsrapporter, utöver de värden som är tillgängliga för alla rapporter.    Inkludera rapportspecifik standard: Anger om standardmått ska inkluderas när vyn anpassas. |

## Fliken Webbplatsanalys - definitioner {#reference_9DD37C8EF718409E990E149596282FF8}

Konfigurera mått och andra grafiska inställningar för platsanalysrapporten.

<!-- 

r_dsc_site_analysis_tab.xml

 -->

| Fält | Definition |
|--- |--- |
| Mått | Välj mätvärden som representeras av cylinderbredd och cylinderhöjd. Bestäm vilka mätvärden som ska visas med färg och bestämma vilka färger som ska motsvara lågt värde och högt värde för det måttet. Du kan ange mätvärden för X- och Y-axeln och lägga till andra mätvärden som du vill ska visas i rapportens popup-text. Du kan också invertera alla valda mätvärden för visningen. |
| Allmänt och larm | Aktivera och inaktivera vissa grafiska element i rapporten. Du kan konfigurera varningsmeddelanden som visas i rapporten när mätvärden som är kopplade till sidorna som representeras av cylindrar skickar ett visst värde. |

## Fliken Teckensnitt och Språk - Definitioner {#reference_5F2129B67CC44E5BA9EA7E30A35BFB49}

Ange nationella inställningar för språk och standardteckensnitt. Du måste starta om för att ändringarna av teckensnitt och språk ska börja gälla.

<!-- 

r_dsc_font_locale.xml

 -->

| Fält | Definition |
|--- |--- |
| Välj en språkinställning | Här kan du ange vilket språk som ska visas i användargränssnittet. |
| Välj ett teckensnitt | Här kan du ange vilket teckensnitt som ska visas. |
