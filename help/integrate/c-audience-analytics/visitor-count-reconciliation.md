---
description: Det finns besökarstatistik i Adobe Analytics och Adobe Audience Manager som har liknande definitioner, men som av olika skäl inte är helt anpassade.
title: Skillnader i antal besökare
uuid: c3bbb887-bd02-4c1c-9a2b-64811c0ef56a
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Skillnader i antal besökare

Det finns besökarstatistik i Adobe Analytics och Adobe Audience Manager som har liknande definitioner, men som av olika skäl inte är helt anpassade.

Besökarstatistik är:

<table id="table_F9FE107A89934C3B854C55D7D76AC6E8"> 
 <thead> 
  <tr> 
   <th colname="col2" class="entry"> Mått </th> 
   <th colname="col3" class="entry"> Definition </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col2"> <p><a href="https://marketing.adobe.com/resources/help/en_US/aam/segment-builder-data.html"  > AAM: Total segmentpopulation</a> </p> </td> 
   <td colname="col3"> <p>Antal enheter (Experience Cloud ID:n) som var medlemmar i ditt segment under uppslagsperioden. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p><a href="https://marketing.adobe.com/resources/help/en_US/aam/segment-builder-data.html"  > AAM: Population av realtidssegment</a> </p> </td> 
   <td colname="col3"> <p>Antal enheter (Experience Cloud-ID:n) som var medlemmar i ditt segment och som nådde upp till dina egenskaper under sökningsperioden. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>Analyser: Unika besökare </p> </td> 
   <td colname="col3"> <p>Visar antalet unika besökare som nådde dina egenskaper under rapportfönstret. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>Analyser: Besökare med Experience Cloud ID </p> </td> 
   <td colname="col3"> <p>Visar antalet unika besökare med ett Experience Cloud-ID som har nått dina egenskaper under rapporteringsfönstret. </p> </td> 
  </tr> 
 </tbody> 
</table>

AAM Real-time Segment Population and Analytics Visitors med det Experience Cloud ID som används i Audience Analytics-rapporter kommer att vara det mest likartade. Under den närmaste tiden kommer det dock att finnas vissa skillnader mellan dem på grund av flera faktorer. Följande faktorer bidrar:

<table id="table_A391B37CC077456F8BB83BAA3C640EF6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Faktor </th> 
   <th colname="col2" class="entry"> AAM: Segmentpopulering i realtid </th> 
   <th colname="col3" class="entry"> Analyser: Besökare med Experience Cloud ID </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Tidszon </p> </td> 
   <td colname="col2"> <p>UTC (Coordinated Universal Time) </p> </td> 
   <td colname="col3"> <p>Angivet per rapportsvit </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Egna filter </p> </td> 
   <td colname="col2"> <p>Nej </p> </td> 
   <td colname="col3"> <p>Ja, t.ex. IP-filter, robotfilter </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Gräns för 150 segment </p> </td> 
   <td colname="col2"> <p>Nej </p> </td> 
   <td colname="col3"> <p>Ja - Analysantalet kan påverkas upp till 5 % av integreringsgränsen på 150 segment. "Målgruppsgräns nådd" visas i dimensionen Målgruppsnamn om trunkering har gjorts. </p> </td> 
  </tr> 
 </tbody> 
</table>

Se [Förstå segment i Analytics och Audience Manager](/help/integrate/c-audience-analytics/aam-analytics-segments.md) för ytterligare förklaringar av nyanserna mellan Analytics och Audience Manager-data och segmentering.
