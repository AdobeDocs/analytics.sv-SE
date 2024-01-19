---
description: Adobe kräver förhandsmeddelande om nya kontoinställningar, trafiktoppar och trafikökningar. Maskinvara måste tilldelas i förväg för att minimera latens och eventuella negativa konsekvenser för det övergripande systemet.
title: Begärd ledtid för trafikökningar
feature: Traffic Management
exl-id: fb428f8d-9dff-43a6-a1e8-1a892cbed7ac
source-git-commit: 726e5ee71be60838e48bb682d7fd48bfc1f96ec3
workflow-type: tm+mt
source-wordcount: '325'
ht-degree: 0%

---

# Begärd ledtid för trafikökningar

Adobe kräver förhandsmeddelande om nya kontoinställningar, trafiktoppar och trafikökningar. Maskinvara måste tilldelas i förväg för att minimera latens och eventuella negativa konsekvenser för det övergripande systemet.

>[!IMPORTANT]
>
>Adobe kan inte hantera platshållartrafikändringsbegäranden. Om inget annat anges, följ den föreslagna ledtiden så nära som möjligt, inklusive att inte skicka en varning för tidigt.

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
   <td colname="col2"> <ul><li>Rapportsviter med &lt; 100M träffar/dag: Ingen avisering krävs</li><li>Rapportera sviter med &gt; 100 MB träffar/dag: 5 arbetsdagar</li></ul></td>
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

* Klientaviseringar behövs också när trafiken minskar eller när en rapportsserie är föråldrad.

## Maskinvaruavallokering på grund av orealiserad trafik

Maskinvara för nya konton, trafiktoppar och trafikökningar kommer att tas bort om den planerade trafiken i kundvarningen inte kommer inom fyra veckor efter&quot;live-datumet&quot;. Om trafiken fortfarande förväntas måste en ny kundvarning genereras i samband med en trafikökning.
