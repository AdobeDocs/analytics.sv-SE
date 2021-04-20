---
description: Alla segment som skapas i segmentbyggaren är inte kompatibla med Data warehouse. I den här tabellen visas de funktioner som stöds.
title: Segmentkompatibilitet för Data Warehouse
feature: Segmentation
uuid: 370258c5-8614-4434-871c-41753ed77f5c
exl-id: 66b86226-ef4c-4a1a-abe1-3c3accf419e5
translation-type: tm+mt
source-git-commit: f9b5380cfb2cdfe1827b8ee70f60c65ff5004b48
workflow-type: tm+mt
source-wordcount: '343'
ht-degree: 6%

---

# Segmentkompatibilitet för Data Warehouse

Alla segment som skapas i segmentbyggaren är inte kompatibla med [!DNL Data Warehouse]. I den här tabellen visas de funktioner som stöds.

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
   <td>Dra och släpp en dimension i segmentbyggarens <span class="uicontrol"> Definitions</span>-fält för att ta reda på om den är kompatibel med produkten. De här måtten stöds till exempel bara i Analysis Workspace, Rapporter och analyser: 
    <ul> 
     <li>Startserver </li> 
     <li>Postkategori </li> 
     <li>Anmälningsdatum </li> 
     <li>Alla söksidrankning </li> 
    </ul> </td> 
   <td> Dra och släpp en dimension i segmentbyggarens <span class="uicontrol"> Definitions</span>-fält för att ta reda på om den är kompatibel med produkten. De här måtten stöds till exempel bara i Data warehouse: 
    <ul> 
     <li>IP-adress </li> 
     <li>Sidans URL </li> 
     <li>Besökar-ID </li> 
     <li>Experience Cloud Visitor-ID </li> 
    </ul> <p>Följande dimensioner <b>kan inte </b>användas i Data warehouse-segment: </p> 
    <ul> 
     <li>Alla söksidrankning </li> 
     <li>AM/PM </li> 
     <li>Dag i månaden </li> 
     <li>Veckodag </li> 
     <li>Dag på året </li> 
     <li>Enhet för startaffärsenhet </li> 
     <li>Post (alla Dimensioner som börjar med Entry, förutom Entry Page) </li> 
     <li>Avsluta (alla Dimensioner som börjar med Avsluta, förutom Avsluta länk och Avsluta sida) </li> 
     <li>Hierarki (alla Dimensioner som börjar med hierarki) </li> 
     <li>Träff-djup </li> 
     <li>Träfftyp </li> 
     <li>Timdag </li> 
     <li>Månad på året </li> 
     <li>Sidorna hittades inte </li> 
     <li>Betalsökning </li> 
     <li>Kvartal på året </li> 
     <li>Återbesöksfrekvens </li> 
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
   <td> Stöds </td> 
  </tr>
  <tr>
    <td><b>'Är lika med någon av'- och 'Är inte lika med någon av'-operatorer</b></td>
    <td>Stöds</td>
    <td>Stöds inte</td>
  </tr>
 </tbody> 
</table>

*Obs! data warehouse stöder inte alla fall där en  `exclusion` eller  `without` en behållare används när  `AND/OR`. När du använder en sådan kombination stöds endast de segment som kan skrivas om som `A AND NOT B` (eller **ta med den här egenskapen**och **exkludera den här egenskapen**) i Data warehouse.*
