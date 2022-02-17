---
description: Rättigheter för beräknade värden skiljer sig mellan användare på administratörsnivå och icke-administratörer.
title: Rollbaserade rättigheter för beräknade mätvärden
feature: Calculated Metrics
exl-id: 018d9ef5-5a6f-4ebc-a241-c1291ba6b561
source-git-commit: 35413ac43eed5ab7218794f26e4753acf08f18ee
workflow-type: tm+mt
source-wordcount: '251'
ht-degree: 2%

---

# Beräknade mätvärden: rollbaserade behörigheter

Rättigheter för beräknade värden skiljer sig mellan användare på administratörsnivå och icke-administratörer.

<table id="table_13F72FD90C964B86BD4B51E6F51ED292"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> </th> 
   <th colname="col02" class="entry"> Skapa </th> 
   <th colname="col2" class="entry"> Dela </th> 
   <th colname="col3" class="entry"> Visa/hantera </th> 
   <th colname="col4" class="entry"> Godkänn </th> 
   <th colname="col5" class="entry"> Använd </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>Användare på administratörsnivå</b> </td> 
   <td colname="col02"> Administratörer kan skapa beräknade mätvärden samt skapa produktprofiler i Admin Console för att begränsa användarnas behörighet att skapa beräknade mätvärden. </td> 
   <td colname="col2"> Kan delas med hela företaget, med användargrupper och med enskilda användare. </td> 
   <td colname="col3"> <span class="keyword"> Rapporter och analyser</span>: Kan visa/redigera/ta bort/etc. egna och andra användares beräknade värden. <p> <span class="keyword"> Report Builder </span>: Kan visa/redigera/ta bort/etc. sina egna beräknade värden och de som delas med dem. </p> </td> 
   <td colname="col4"> Kan godkänna beräknade värden som kanoniska. </td> 
   <td colname="col5"> Kan använda alla beräknade värden i hela organisationen. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Användare på annan nivå än administratörsnivå</b> </td> 
   <td colname="col02"> Som standard kan användare skapa beräknade värden. Dessa rättigheter kan dock begränsas av administratörer. </td> 
   <td colname="col2"> Kan endast dela med enskilda användare </td> 
   <td colname="col3"> Kan visa/redigera/ta bort/etc. bara deras egna beräknade värden. <p>Icke-adminanvändare måste ha tillgång till alla komponenthändelser för att kunna se delade mått (behörigheterna i Admin Console används fortfarande). </p> <p>Om en instrumentpanel eller schemalagd rapport delas med en icke-admin-användare och de inte har mätvärdena delade med sig, kommer rapporten att köras med det mätvärde som används (förutsatt att de har behörighet att visa händelserna). De kan dock inte se definitionen eller redigera måttet. </p> </td> 
   <td colname="col4"> Kan endast förbruka godkända beräknade värden, kan inte markeras som godkänt. </td> 
   <td colname="col5"> Kan använda egna beräknade värden och segment som har delats med dem. </td> 
  </tr> 
 </tbody> 
</table>
