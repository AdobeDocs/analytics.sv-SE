---
description: Alla segment som skapas i segmentbyggaren är inte kompatibla med Data Warehouse. I den här tabellen visas de funktioner som stöds.
title: Data Warehouse segmentkompatibilitet
feature: Segmentation
exl-id: 66b86226-ef4c-4a1a-abe1-3c3accf419e5
source-git-commit: 80e4a3ba4a5985563fcf02acf06997b4592261e4
workflow-type: tm+mt
source-wordcount: '342'
ht-degree: 1%

---

# Data Warehouse segmentkompatibilitet

Alla segment som skapats i segmentverktyget är inte kompatibla med [!DNL Data Warehouse]. I den här tabellen visas de funktioner som stöds.

<table> 
 <thead> 
  <tr> 
   <th> </th> 
   <th> Analysis Workspace, rapporter och analyser </th> 
   <th> Data Warehouse </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td > <b>Uteslut behållare</b> </td> 
   <td> Stöds på alla nivåer </td> 
   <td> Stöds endast i specialfall på den översta nivån </td> 
  </tr> 
  <tr> 
   <td> <b>Sekventiella segment</b> </td> 
   <td> Stöds </td> 
   <td> Stöds inte </td> 
  </tr> 
  <tr> 
   <td> <b>AND och OR kan kombineras utan begränsningar</b> </td> 
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
   <td>Dra och släpp en dimension i segmentbyggarens fält <span class="uicontrol"> Definitioner </span> för att ta reda på om den är kompatibel med produkten. De här måtten stöds till exempel bara i Analysis Workspace, Rapporter och analyser: 
    <ul> 
     <li>Startserver </li> 
     <li>Postkategori </li> 
     <li>Anmälningsdatum </li> 
     <li>Alla söksidrankning </li> 
    </ul> </td> 
   <td> Dra och släpp en dimension i segmentbyggarens fält <span class="uicontrol"> Definitioner </span> för att ta reda på om den är kompatibel med produkten. De här måtten stöds till exempel bara i Data Warehouse: 
    <ul> 
     <li>IP-adress </li> 
     <li>Sidans URL </li> 
     <li>Besökar-ID </li> 
     <li>Experience Cloud Visitor-ID </li> 
    </ul> <p>Följande dimensioner <b>kan inte </b>användas i Data Warehouse-segment: </p> 
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
     <li>Veckodag/vecka </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td> <b>Segmentstapling</b> </td> 
   <td> Stöds </td> 
   <td> Stöds </td> 
  </tr>
  <tr>
    <td><b>'Är lika med någon av'- och 'Är inte lika med någon av'-operatorer</b></td>
    <td>Stöds</td>
    <td>Stöds inte</td>
  </tr>
 </tbody> 
</table>

*Obs! Data Warehouse stöder inte alla fall där en `exclusion` - eller `without` -behållare används när `AND/OR` används. När du använder en sådan kombination stöds endast de segment som kan skrivas om som `A AND NOT B` (eller **include this property**&#x200B;och **exclude this property**) i Data Warehouse.*
