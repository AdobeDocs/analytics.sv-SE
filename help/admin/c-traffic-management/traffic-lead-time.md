---
description: Adobe kräver förhandsmeddelande om nya kontoinställningar, trafiktoppar och trafikökningar. Maskinvara måste tilldelas i förväg för att minimera latens och eventuella negativa konsekvenser för det övergripande systemet.
title: Ledtid som krävs för trafikökningar
feature: Traffic Management
exl-id: fb428f8d-9dff-43a6-a1e8-1a892cbed7ac
source-git-commit: 72bd67179e003b70233d863d34153fec77548256
workflow-type: tm+mt
source-wordcount: '332'
ht-degree: 4%

---

# Ledtid som krävs för trafikökningar

Adobe kräver förhandsmeddelande om nya kontoinställningar, trafiktoppar och trafikökningar. Maskinvara måste tilldelas i förväg för att minimera latens och eventuella negativa konsekvenser för det övergripande systemet.

Allokering av maskinvara styrs av varningar som skickas via användargränssnittet för rapporter och analyser.

>[!IMPORTANT]
>
>Adobe kan inte hantera platshållartrafikändringsbegäranden. Om inget annat anges, följ den föreslagna ledtiden så nära som möjligt, inklusive att inte skicka en varning för tidigt. Se [Schemalägg en trafiktoppning](/help/admin/c-traffic-management/t-traffic-schedule-spike.md) eller [Ange permanent trafikökning](/help/admin/c-traffic-management/t-traffic-permanent.md).

Använd följande riktlinjer för att avgöra hur långt i förväg du måste skicka in en trafikvarning:

## Leadtider för maskinvaruallokering

<table id="table_A67CC3B164F740088797BD8913244E47">
 <thead>
  <tr>
   <th colname="col1" class="entry"> Uppskattningar av trafiken per dag (träffar) </th>
   <th colname="col2" class="entry"> <p>Leadtid krävs (januari-oktober) </p> </th>
   <th colname="col3" class="entry"> <p>Leadtid krävs (november-december) </p> </th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td colname="col1"> Upp till 1 000 000 </td>
   <td colname="col2"> Ingen produktionstid behövs </td>
   <td colname="col3"> Ingen produktionstid behövs </td>
  </tr>
  <tr>
   <td colname="col1"> 1 000 000 - 5 000 000 </td>
   <td colname="col2"> Två affärsdagar </td>
   <td colname="col3" morerows="3"> Alla trafikökningar som ska genomföras november-december ska vara inlämnade senast den 1 september. Detta för att ge tid för inköp av kapacitet om det behövs för att ta hand om semestertrafiken. </td>
  </tr>
  <tr>
   <td colname="col1"> 5 000 000 - 10 000 000 </td>
   <td colname="col2"> En kalendervecka </td>
  </tr>
  <tr>
   <td colname="col1"> 10 000 000 - 25 000 000 </td>
   <td colname="col2"> Två kalenderveckor </td>
  </tr>
  <tr>
   <td colname="col1"> <p>Över 25 000 000 </p> </td>
   <td colname="col2"> En eller flera månader </td>
  </tr>
 </tbody>
</table>

Andra saker att tänka på:

* Om du har flera rapportsviter som startar eller ökar, och som sammanlagt ökar de siffror som anges ovan, används ledtiden som en summa av den trafik som förväntas för var och en av dem.
* Ha följande information tillgänglig för att skicka in en trafikändring:

   * Rapportsvit-ID
   * Beräknade träffar per dag
   * Publiceringsdatum

* Klientaviseringar behövs också när trafiken minskar eller när en rapportsserie är inaktuell.

## Maskinvaruavallokering på grund av orealiserad trafik

Maskinvara för nya konton, trafiktoppar och trafikökningar kommer att tas bort om den planerade trafiken i kundvarningen inte kommer inom fyra veckor efter&quot;live-datumet&quot;. Om trafiken fortfarande förväntas måste en ny kundvarning genereras i samband med en trafikökning.
