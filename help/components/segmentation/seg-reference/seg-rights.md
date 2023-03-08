---
description: Segmentfunktionaliteten skiljer sig nu oftast mellan användare på administrationsnivå och icke-administratörer.
title: Segmentbehörigheter efter roll
feature: Segmentation
exl-id: 54e35663-8a8d-4064-a44c-2385e24e6e10
source-git-commit: b8640d1387a475e2a9dd082759f0514bd18c1b6e
workflow-type: tm+mt
source-wordcount: '133'
ht-degree: 6%

---

# Segmentbehörigheter efter roll

Segmentfunktionaliteten skiljer sig nu oftast mellan användare på administrationsnivå och icke-administratörer.

<table id="table_13F72FD90C964B86BD4B51E6F51ED292"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"></th> 
   <th colname="col2" class="entry"> Dela segment </th> 
   <th colname="col3" class="entry"> Visa/hantera segment </th> 
   <th colname="col4" class="entry"> Godkänna segment </th> 
   <th colname="col5" class="entry"> Tillämpar segment </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>Användare på administratörsnivå</b> </td> 
   <td colname="col2"> Kan delas med hela företaget, med användargrupper och med enskilda användare. </td> 
   <td colname="col3"> <span class="keyword"> Analysis Workspace, rapporter och analyser </span>: Kan visa/redigera/ta bort/etc. sina egna och andra användarsegment. <p> <span class="keyword"> Report Builder </span>: Kan visa/redigera/ta bort/etc. sina egna segment och de som delas med dem. </p> </td> 
   <td colname="col4"> Kan godkänna segment som kanoniska. </td> 
   <td colname="col5"> Kan användas i alla segment i hela organisationen. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Användare på annan nivå än administratörsnivå</b> </td> 
   <td colname="col2"> Kan endast dela med enskilda användare </td> 
   <td colname="col3"> Kan visa/redigera/ta bort/etc. bara sina egna segment. </td> 
   <td colname="col4"> Kan endast förbruka godkända segment, kan inte markeras som godkänt. </td> 
   <td colname="col5"> Kan tillämpa egna segment och segment som har delats med dem. </td> 
  </tr> 
 </tbody> 
</table>
