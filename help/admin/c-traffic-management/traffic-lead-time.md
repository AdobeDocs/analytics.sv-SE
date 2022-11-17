---
description: Adobe kräver förhandsmeddelande om nya kontoinställningar, trafiktoppar och trafikökningar. Maskinvara måste tilldelas i förväg för att minimera latens och eventuella negativa konsekvenser för det övergripande systemet.
title: Ledtid som krävs för trafikökningar
feature: Traffic Management
exl-id: fb428f8d-9dff-43a6-a1e8-1a892cbed7ac
source-git-commit: f9462d1b8b2795bec9dab9b479d4885fcaa92b5d
workflow-type: tm+mt
source-wordcount: '341'
ht-degree: 3%

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
   <th colname="col1" class="entry"> Trafikändringstyp </th>
   <th colname="col2" class="entry"> Lead-tid krävs </th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td colname="col1"> Ny kontoinställning </td>
   <td colname="col2"> <ul><li>3 arbetsdagar</li></ul></td>
  </tr>
  <tr>
   <td colname="col1"> Trafikkramp eller plötslig permanent trafikökning med upp till 25 procent i genomsnittlig daglig volym jämfört med de senaste 30 dagarna</td>
   <td colname="col2"> <ul><li>Rapportsviter med &lt; 100M träffar/dag: Ingen avisering krävs</li><li>Rapportera programsviter med &gt; 100 MB träffar/dag: 5 arbetsdagar</li></ul></td>
  </tr>
  <tr>
   <td colname="col1"> Trafikantoppen eller plötslig permanent trafikökning med mer än 25 procent i genomsnittlig daglig volym jämfört med de senaste 30 dagarna</td>
   <td colname="col2"> <ul><li>5 arbetsdagar</li></ul></td>
  </tr>
  <tr>
   <td colname="col1"> Helgsevenemang oktober-december </td>
   <td colname="col2"> <ul><li>En kalendermånad</li></ul> </td>
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
