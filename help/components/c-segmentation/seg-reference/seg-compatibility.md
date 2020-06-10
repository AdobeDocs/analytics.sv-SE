---
description: Alla segment som skapas i segmentbyggaren är inte kompatibla med datalagret. I den här tabellen visas de funktioner som stöds.
title: Datalagersegmentkompatibilitet
topic: Segments
uuid: 370258c5-8614-4434-871c-41753ed77f5c
translation-type: tm+mt
source-git-commit: a28a05047e95d12343fd94f7b11e5cabf7fac070
workflow-type: tm+mt
source-wordcount: '350'
ht-degree: 1%

---


# Datalagersegmentkompatibilitet

Alla segment som skapas i segmentbyggaren är inte kompatibla med [!DNL Data Warehouse]. I den här tabellen visas de funktioner som stöds.

<table> 
 <thead> 
  <tr> 
   <th> </th> 
   <th> Analysis Workspace, Reports &amp; Analytics, Ad hoc Analysis </th> 
   <th> Data Warehouse </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td > <b>Exkludera behållare</b> </td> 
   <td> Stöds på alla nivåer </td> 
   <td> Stöds endast i specialfall på den översta nivån </td> 
  </tr> 
  <tr> 
   <td> <b>Sekventiella segment</b> </td> 
   <td> Stöds </td> 
   <td> Stöds inte </td> 
  </tr> 
  <tr> 
   <td> <b>AND och OR kan kombineras utan gränser</b> </td> 
   <td> Stöds </td> 
   <td> Vissa begränsningar. Se *anm.* nedan. </td> 
  </tr> 
  <tr> 
   <td> <b>Kapslade behållare</b> </td> 
   <td> Stöds </td> 
   <td> Vissa begränsningar (de måste minska i omfång, besökare kan till exempel innehålla träffar, men inte tvärtom) </td> 
  </tr> 
  <tr> 
   <td> <b>Dimensioner</b> </td> 
   <td>Dra och släpp en dimension i segmentbyggarens <span class="uicontrol"> definitionsfält</span> för att ta reda på om den är kompatibel med produkten. De här dimensionerna stöds till exempel bara i Analysis Workspace, Reports &amp; Analytics och Ad Hoc Analysis: 
    <ul> 
     <li>Startserver </li> 
     <li>Postkategori </li> 
     <li>Anmälningsdatum </li> 
     <li>Alla söksidrankning </li> 
    </ul> </td> 
   <td> Dra och släpp en dimension i segmentbyggarens <span class="uicontrol"> definitionsfält</span> för att ta reda på om den är kompatibel med produkten. De här dimensionerna stöds till exempel bara i datalagret: 
    <ul> 
     <li>IP-adress </li> 
     <li>Sidans URL </li> 
     <li>Besökar-ID </li> 
     <li>Experience Cloud-besökar-ID </li> 
    </ul> <p>Följande dimensioner <b>kan inte </b>användas i datalagersegment: </p> 
    <ul> 
     <li>Alla söksidrankning </li> 
     <li>AM/PM </li> 
     <li>Dag i månaden </li> 
     <li>Veckodag </li> 
     <li>Dag på året </li> 
     <li>Enhet för startaffärsenhet </li> 
     <li>Post (alla dimensioner som börjar med Inmatning, förutom Inmatningssida) </li> 
     <li>Avsluta (alla dimensioner med början vid Avsluta, förutom Avsluta länk och Avsluta sida) </li> 
     <li>Hierarki (alla dimensioner med början från hierarki) </li> 
     <li>Träff-djup </li> 
     <li>Träfftyp </li> 
     <li>Timdag </li> 
     <li>Månad på året </li> 
     <li>Sidorna hittades inte </li> 
     <li>Betalsökning </li> 
     <li>Kvartal på året </li> 
     <li>Returfrekvens </li> 
     <li>Besök på en sida </li> 
     <li>Tid före händelse </li> 
     <li>Tid som använts på sidan - paketerad </li> 
     <li>Tid per besök - paketerad </li> 
     <li>Orsak till avanmälan av spårning </li> 
     <li>USA </li> 
     <li>Veckodag/Veckoslut </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td> <b>Segmentstapling</b> </td> 
   <td> Stöds </td> 
   <td> Stöds inte </td> 
  </tr>
  <tr>
    <td><b>'Är lika med någon av'- och 'Är inte lika med någon av'-operatorer</b></td>
    <td>Stöds</td>
    <td>Stöds inte</td>
  </tr>
 </tbody> 
</table>

*Obs! Datalagret stöder inte alla fall där en`exclusion`eller`without`en behållare används vid användning`AND/OR`. När du använder en sådan kombination stöds endast de segment som kan skrivas om som`A AND NOT B`(eller **inkludera den här egenskapen**och ****exkludera den) i datalagret.*
