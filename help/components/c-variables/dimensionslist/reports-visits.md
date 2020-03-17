---
description: Visar antalet besök som gjorts på hela webbplatsen under en angiven tidsperiod.
title: Besök
topic: Reports
uuid: ff65bddf-fb65-4cf0-8aae-4ab59c2bb0a7
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Besök

Visar antalet besök som gjorts på hela webbplatsen under en angiven tidsperiod.

**Rapportegenskaper**

* Ett besök definieras som en sekvens av på varandra följande sidvisningar utan 30 minuters uppehåll, eller kontinuerlig aktivitet under 12 timmar.
* När ett besök har upphört att gälla påbörjas ett nytt besök vid varje efterföljande bildbegäran.
* En besökare har vanligtvis minst ett (men förmodligen fler än ett) besök.
* Början av ett besök är den första bildförfrågan som kommer från en ny besökare eller efter att en befintlig användares besök har gått ut. Detta kan identifieras som anmälningssida.
* Slutet på ett besök är den sista bildförfrågan innan ett besök upphör. Detta kan identifieras som Avsluta sida.

   Se [Inmatningar och utträdesrapporter](/help/components/c-variables/dimensionslist/reports-entries-exits.md).
* Timuppdelningar baseras på rapportsvitens tidszon.
* Den här rapporten innehåller inga radartiklar. Du kan bara visa den i det format som är avsett.
* Kornighet mellan timme, dag, vecka, månad, kvartal och år kan tillämpas. De här detaljnivåinställningarna är tillgängliga beroende på rapportens datumintervall.

Mer information om hur det här måttet behandlas i Experience Cloud finns i [Metric](/help/components/c-variables/c-metrics/metrics-visit.md) .

**Produktspecifik rapportinformation**

<table id="table_3138CA443CAC4F55838216E8B8786EE2"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Produkt </th> 
   <th colname="col2" class="entry"> Navigering </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> Rapporter och analyser </p> </td> 
   <td colname="col2"> <p> <span class="uicontrol"> Site Metrics</span> &gt; <span class="uicontrol"> Visits</span> </p> <p>Du kan köra en <span class="wintitle"> besöksrapport</span> på en vald sida. Besök som sträcker sig över midnatt räknas både den dag då besöket påbörjades och avslutades. Summan för det angivna datumintervallet tas dock bort. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Ad hoc-analys </p> </td> 
   <td colname="col2"> <p> <span class="uicontrol"> Rapporter</span> &gt; <span class="uicontrol"> Webbplatsstatistik</span> &gt; <span class="uicontrol"> Besök</span> </p> 
    <ul id="ul_73FEE02C129041D6A63F2DB07676960F"> 
     <li id="li_CC3BB22DE97941EB8032BE4421FFC173"> Du kan dela upp varje objekt i den här rapporten med nästan alla andra rapporter och variabler, så att du kan se uppdelningar efter alla detaljer. </li> 
     <li id="li_D53D480D73264D47945C9E1202B7BD4F">Besök som sträcker sig över midnatt räknas både den dag då besöket påbörjades och avslutades. Summan för det angivna datumintervallet är dock deduplicerad. </li> 
     <li id="li_B8BCC584F95B407DB87F5EA57CC88F62">Ni kan använda alla konverterings- och trafikvärden i den här rapporten, samt använda olika allokeringar för alla konverteringsvärden. </li> 
     <li id="li_0F342D3DCFF44ABAB79BD0F9E7F43E1E">Den här rapporten kan använda flera mycket avancerade segment. </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

