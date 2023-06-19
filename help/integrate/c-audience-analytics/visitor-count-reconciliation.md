---
description: Det finns besökarstatistik i Adobe Analytics och Adobe Audience Manager som har liknande definitioner, men som av olika skäl inte är helt anpassade.
title: Skillnader i antal besökare
feature: Audience Analytics
exl-id: be5a935a-c3a2-4ab4-8cd7-ed54a37932c8
source-git-commit: 15f1cd260709c2ab82d56a545494c31ad86d0ab0
workflow-type: tm+mt
source-wordcount: '296'
ht-degree: 3%

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
   <td colname="col2"> <p><a href="https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/segments/segment-builder-data.html"  > Adobe Audience Manager: Total segmentpopulation</a> </p> </td> 
   <td colname="col3"> <p>Antal enheter (Experience Cloud-ID) som var medlemmar i ditt segment under uppslagsperioden. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p><a href="https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/segments/segment-builder-data.html"  > Adobe Audience Manager: Population av realtidssegment</a> </p> </td> 
   <td colname="col3"> <p>Antal enheter (Experience Cloud-ID) som var medlemmar i ditt segment och som nådde dina egenskaper under uppslagsperioden. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>Analyser: Unika besökare </p> </td> 
   <td colname="col3"> <p>Visar antalet unika besökare som nådde dina egenskaper under rapportfönstret. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>Analyser: Besökare med Experience Cloud-ID </p> </td> 
   <td colname="col3"> <p>Visar antalet unika besökare med ett Experience Cloud-ID som har nått dina egenskaper under rapporteringsfönstret. </p> </td> 
  </tr> 
 </tbody> 
</table>

Adobe Audience Manager segmentpopulation i realtid och Analytics-besökare med Experience Cloud-ID som används i Audience Analytics-rapporter kommer att vara de mest likartade. Under den närmaste tiden kommer det dock att finnas vissa skillnader mellan dem på grund av flera faktorer. Följande faktorer bidrar:

<table id="table_A391B37CC077456F8BB83BAA3C640EF6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Faktor </th> 
   <th colname="col2" class="entry"> Adobe Audience Manager: Segmentpopulering i realtid </th> 
   <th colname="col3" class="entry"> Analyser: Besökare med Experience Cloud-ID </th> 
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

Se [Förstå segment i Analytics och Audience Manager](/help/integrate/c-audience-analytics/aam-analytics-segments.md) för ytterligare förklaringar av nyanserna mellan Analytics och Audience Manager data och segmentering.
