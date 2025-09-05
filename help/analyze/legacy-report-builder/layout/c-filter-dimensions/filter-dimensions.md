---
description: Du kan filtrera efter dimensioner som du lägger till i rutnätet Radetiketter. Filter begränsar de data som returneras av begäranden och kan tillämpas från pivottabellen eller anpassade layouter. När du konfigurerar dimensionsfiltrering från pivotlayouten kan du dessutom ange antalet poster från cellen.
title: Översikt över filterdimensioner
uuid: c54d5add-f278-476d-8f14-73f1c2e37671
feature: Report Builder
role: User, Admin
exl-id: eded07d5-3c06-419b-92fd-1a48856ac293
source-git-commit: e09234ca27fbf923e026aa1f2ed0ebfed636bf7c
workflow-type: tm+mt
source-wordcount: '446'
ht-degree: 7%

---

# Översikt över filterdimensioner

{{legacy-arb}}

Du kan filtrera efter dimensioner som du lägger till i rutnätet Radetiketter. Filter begränsar de data som returneras av begäranden och kan tillämpas från pivottabellen eller anpassade layouter. När du konfigurerar dimensionsfiltrering från pivotlayouten kan du dessutom ange antalet poster från cellen.

Det valda filterformuläret fylls i baserat på det element och mått som valts i Report Builder-begäran.

## Definiera filter - värden och specialtecken {#section_15840216A4044C40974945FAA435AD93}

Information om filter i panelen **[!UICONTROL Most Popular Filter]** > **[!UICONTROL Define Filter]**.

![Skärmbild som visar dialogrutan Definiera filter med alternativ för att filtrera efter program, användare och projekt.](/help/admin/tools/assets/filter.png)

Följande tabeller innehåller exempel och information om filter:

<table id="table_8AC3A26FF02143DBA949B30F2A46CF11"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Filter </th> 
   <th colname="col02" class="entry"> Beskrivning </th> 
   <th colname="col2" class="entry"> Exempelfilter </th> 
   <th colname="col3" class="entry"> Matcha resultat </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Innehåller alla termer </p> </td> 
   <td colname="col02"> <p>Innehåller alla blankstegsavgränsade värden i valfri ordning. </p> </td> 
   <td colname="col2"> <p>a b c </p> </td> 
   <td colname="col3"> <p>Matchar <span class="term"> a b c</span> och <span class="term"> b a c</span> osv. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Innehåller valfri term </p> </td> 
   <td colname="col02"> <p>Innehåller minst ett av filtren (utrymmesavgränsat). </p> </td> 
   <td colname="col2"> <p>A B C </p> </td> 
   <td colname="col3"> <p>Matchar <span class="term"> A1</span>, <span class="term"> B2</span>, <span class="term"> C3</span>, men inte <span class="term"> D4</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Innehåller frasen </p> </td> 
   <td colname="col02"> <p>Innehåller sökfiltret och eventuellt andra termer. </p> </td> 
   <td colname="col2"> <p>abc </p> </td> 
   <td colname="col3"> <p>Matchar <span class="term"> abc</span> och <span class="term"> abc def</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Innehåller inga termer </p> </td> 
   <td colname="col02"> <p>Returnerar allt såvida det inte innehåller ett värde som du anger. </p> </td> 
   <td colname="col2"> <p>a b c </p> </td> 
   <td colname="col3"> <p>Matchar <span class="term"> d e f</span> men inte <span class="term"> c d e f</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Innehåller inte frasen </p> </td> 
   <td colname="col02"> <p>Returnerar allt som inte innehåller din fras. </p> </td> 
   <td colname="col2"> <p>abc </p> </td> 
   <td colname="col3"> <p>Utesluter <span class="term"> abc</span>, <span class="term"> abc def</span> och matchar <span class="term"> def</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Är lika med </p> </td> 
   <td colname="col02"> <p>Returnerar en exakt matchning. </p> </td> 
   <td colname="col2"> <p>abc </p> </td> 
   <td colname="col3"> <p> <span class="term"> abc</span> returneras, och inget annat. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Är inte lika med </p> </td> 
   <td colname="col02"> <p>Returnerar allt som inte matchar inmatningen exakt. </p> </td> 
   <td colname="col2"> <p>a </p> </td> 
   <td colname="col3"> <p>Matchar inte <span class="term"> a</span>. </p> <p>Matchar <span class="term"> a b c</span>. </p> <p>Matchar <span class="term"> abc</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Börjar med </p> </td> 
   <td colname="col02"> <p>Returnerar resultat som börjar med ett visst värde. </p> </td> 
   <td colname="col2"> <p>abc </p> </td> 
   <td colname="col3"> <p>Matchar <span class="term"> abcd</span> men inte <span class="term"> 1abc</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Slutar med </p> </td> 
   <td colname="col02"> <p>Returnerar resultat som slutar med det angivna värdet. </p> </td> 
   <td colname="col2"> <p>xyz </p> </td> 
   <td colname="col3"> <p>Matchar <span class="term"> wxyz</span> men inte <span class="term"> wxyz0</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Avancerat (specialtecken) </p> </td> 
   <td colname="col02"> <p>Här kan du skriva regextecken: </p> <p> <code> "", ^, -, *, $, | </code> </p> </td> 
   <td colname="col2"> <p>"^Home*Page$" | sport </p> </td> 
   <td colname="col3"> <p> Detta definierar ett filter som börjar med <span class="term"> Home</span> och sedan söker efter noll eller flera tecken och slutar sedan med <span class="term"> Page</span>. </p> <p>Alla sidor med <span class="term"> sport</span> i den. </p> <p>Några exempel matchar: </p> 
    <ul id="ul_72D76C5AFEAF405E8A0E4E3C604D10AE"> 
     <li id="li_4D490059B667450DA8A0103167C7B391">HomePage </li> 
     <li id="li_1351619156274092AEB2771D882AD357">Home and (other characters) Page </li> 
     <li id="li_940EAA99A8CF49308E8471065EB317B1">Hemsport </li> 
     <li id="li_50A895F14A454BE9BF06EE0F07F99B3B">sportsida </li> 
     <li id="li_F3CE0D07941D4C2485D2DE0B73E00677">sport </li> 
     <li id="li_E84C15C061824A5D922D9900392F2996">xyz sportabc </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

<table id="table_8BBB06C8860745DEA41B39673699DC0F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Specialtecken </th> 
   <th colname="col2" class="entry"> Syfte </th> 
   <th colname="col3" class="entry"> Anteckningar </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> " " </td> 
   <td colname="col2"> Är lika med </td> 
   <td colname="col3"> <p>Inte escape-konverterad om den inte paras med en annan citattecken. <span class="term"> 17" Display</span> är till exempel inte en fras. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> * </td> 
   <td colname="col2"> Jokertecken </td> 
   <td colname="col3"> <p>Samma som den asterisk som används i ett reguljärt uttryck. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ^ </td> 
   <td colname="col2"> Börjar med </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> $ </td> 
   <td colname="col2"> Slutar med </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> - </td> 
   <td colname="col2"> Inte </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> | </td> 
   <td colname="col2"> eller </td> 
   <td colname="col3"> <p>Stöds endast i filtret <span class="term"> Advanced (specialtecken)</span>. </p> </td> 
  </tr> 
 </tbody> 
</table>
