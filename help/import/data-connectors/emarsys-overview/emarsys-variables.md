---
description: Integreringen av Data Connectors för emarsys använder Analytics-variabler för att spåra olika mässiffror.
title: Analytics-variabler
uuid: 4d5e087c-f495-4aab-9ad1-9b901d34a254
exl-id: a59216f2-047b-429b-8714-a2bdaa271911
source-git-commit: f669af03a502d8a24cea3047b96ec7cba7c59e6f
workflow-type: tm+mt
source-wordcount: '248'
ht-degree: 6%

---

# Analytics-variabler{#analytics-variables}

Integreringen av Data Connectors för emarsys använder Analytics-variabler för att spåra olika mässiffror.

När du har identifierat händelsen och eVars som ska användas med minnesintegreringen aktiverar du dem i [Admin Console](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/c-admin-tools.html).

**Obligatoriska variabler**

<table id="table_5B8F3A1EB55D4BB48F669FB84C857256"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Variabeltyp </th> 
   <th colname="col2" class="entry"> Namn </th> 
   <th colname="col3" class="entry"> Populationsmetod </th> 
   <th colname="col4" class="entry"> Beskrivning </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> händelse (numerisk) </td> 
   <td colname="col2"> Summa studsar </td> 
   <td colname="col3"> <p>Automatiskt importerad från minnesmärken </p> </td> 
   <td colname="col4"> <p>Med händelsen Total Bounces kan du se antalet e-postmeddelanden som inte har levererats till mottagarna på grund av ett leveransproblem. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> händelse (numerisk) </td> 
   <td colname="col2"> Klickat </td> 
   <td colname="col3"> <p>Automatiskt importerad från minnesmärken </p> </td> 
   <td colname="col4"> <p>Med händelsen Klickat kan du se antalet besökare som klickade på e-postmeddelandet. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> händelse (numerisk) </td> 
   <td colname="col2"> Öppnad </td> 
   <td colname="col3"> <p>Automatiskt importerad från minnesmärken </p> </td> 
   <td colname="col4"> <p>Med händelsen Öppnad kan du se antalet besökare som öppnade e-postmeddelandet. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> händelse (numerisk) </td> 
   <td colname="col2"> Skickat </td> 
   <td colname="col3"> <p>Automatiskt importerad från minnesmärken </p> </td> 
   <td colname="col4"> <p>Med händelsen Skicka kan du se hur många e-postmeddelanden som har skickats. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> händelse (numerisk) </td> 
   <td colname="col2"> Avbeställ </td> 
   <td colname="col3"> <p>Automatiskt importerad från minnesmärken </p> </td> 
   <td colname="col4"> <p>Med händelsen Avbeställ kan du se hur många besökare som har öppnat e-postmeddelandet men sedan klickat på länken Avbeställ för att avanmäla dig från framtida e-postmeddelanden från din organisation. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> eVar </td> 
   <td colname="col2"> Mottagar-ID </td> 
   <td colname="col3"> <p>Samlas in från frågeparametrar i e-postlänkar via den automatiserade samlingsmetoden eller ett JavaScript-plugin-program. </p> </td> 
   <td colname="col4"> Mottagar-ID </td> 
  </tr> 
  <tr> 
   <td colname="col1"> eVar eller s.campaign </td> 
   <td colname="col2"> Meddelande-ID </td> 
   <td colname="col3"> <p>Samlas in från frågeparametrar i e-postlänkar via den automatiserade samlingsmetoden eller ett JavaScript-plugin-program. </p> </td> 
   <td colname="col4"> Det här värdet lagras ofta i kampanjvariabeln. </td> 
  </tr> 
 </tbody> 
</table>
