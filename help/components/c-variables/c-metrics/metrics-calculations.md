---
description: Mätvärdena beräknas med hjälp av standardmetoder, deltagarmetoder, senaste metoder och linjär allokeringsmetod. Varje metod beräknar värden på olika sätt baserat på formler.
title: Måttberäkningar
topic: Metrics
uuid: 2af58f1e-12c5-4828-ae39-c9aeaef6b705
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Måttberäkningar

Mätvärdena beräknas med hjälp av standardmetoder, deltagarmetoder, senaste metoder och linjär allokeringsmetod. Varje metod beräknar värden på olika sätt baserat på formler.

<table id="table_6F81A12174D84124B7FD81FBBEDF18A2"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Måttberäkning </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Original </td> 
   <td colname="col2"> <p>Det första variabelvärdet som är associerat med händelsen success krediteras. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Senaste </td> 
   <td colname="col2"> <p>Det sista variabelvärdet som är associerat med händelsen success krediteras. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Linjär </td> 
   <td colname="col2"> <p>När linjär allokering har valts delas lyckade händelser jämnt in i alla variabelvärden som visas vid besöket. För numeriska händelser och valutakurshändelser som <span class="term"> Intäkter</span>delas det monetära beloppet. För räknehändelser som <span class="term"> beställningar</span>tilldelas en bråkdel av evenemanget till varje variabelvärde i besöket. Dessa bråktal i rapporteringen summeras och avrundas sedan till närmaste heltal i rapporteringen. </p> <p>Exempel: vid ett besök där fyra sidor besöktes före en lyckad händelse skulle varje sida få en belöning för 25 % av evenemanget. Om <span class="varname"> kampanjen</span> hade två värden vid samma besök skulle varje kampanjvärde få 50 % av tillgodoräknandet av evenemanget. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> deltagande </td> 
   <td colname="col2"> <p>Tilldelar fullständig kredit till varje variabelvärde som bidrog till en lyckad händelse inom ett besök. Denna beräkning kan även gälla för alla besökarsessioner om ni använder statistik för deltagande mellan besök. </p> <p>Mer information finns i <a href="/help/components/c-variables/c-metrics/metrics-participation.md"  > Deltagande</a> . </p> </td> 
  </tr> 
 </tbody> 
</table>

## Exempel - Måttberäkning {#section_4CE01DA35108418D9909823A7ECC4B45}

Anta att din webbplats har en intern sökning som spåras med en konverteringsvariabel (eVar). Besökaren utför flera interna sökningar innan han/hon gör ett köp på 100 USD:

*`Pet`* > *`Feline`* > *`Cat`* > *`Kitten`* > $100 inköp

Vid rapportering är kreditallokeringen följande:

<table id="table_91A7244E77854838A8392B49366FB445"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> eVar-värde </th> 
   <th colname="col2" class="entry"> Första </th> 
   <th colname="col3" class="entry"> Sista </th> 
   <th colname="col4" class="entry"> Linjär </th> 
   <th colname="col5" class="entry"> deltagande </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Djurt </p> </td> 
   <td colname="col2"> <p>$100 </p> </td> 
   <td colname="col3"> <p>$0 </p> </td> 
   <td colname="col4"> <p>$25 </p> </td> 
   <td colname="col5"> <p>$100 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Filine </p> </td> 
   <td colname="col2"> <p>$0 </p> </td> 
   <td colname="col3"> <p>$0 </p> </td> 
   <td colname="col4"> <p>$25 </p> </td> 
   <td colname="col5"> <p>$100 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Katt </p> </td> 
   <td colname="col2"> <p>$0 </p> </td> 
   <td colname="col3"> <p>$0 </p> </td> 
   <td colname="col4"> <p>$25 </p> </td> 
   <td colname="col5"> <p>$100 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Kattunge </p> </td> 
   <td colname="col2"> <p>$0 </p> </td> 
   <td colname="col3"> <p>$100 </p> </td> 
   <td colname="col4"> <p>$25 </p> </td> 
   <td colname="col5"> <p>$100 </p> </td> 
  </tr> 
 </tbody> 
</table>

