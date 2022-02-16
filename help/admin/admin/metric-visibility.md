---
description: Du kan dölja standardvärden (inbyggda), anpassade händelser och inbyggda händelser i Menu, Metric Selectors, Calculated Metric Builder och Segment Builder.
title: Måttsynlighet
feature: Admin Tools
exl-id: 8ff06677-a9fc-4a12-bf8d-8a7ce05db922
source-git-commit: 2c0aef13bdb88b0a7aa9f100c72c21f66a14c8dd
workflow-type: tm+mt
source-wordcount: '147'
ht-degree: 9%

---

# Måttsynlighet

Du kan dölja standardvärden (inbyggda), anpassade händelser och inbyggda händelser i Menu, Metric Selectors, Calculated Metric Builder och Segment Builder.

1. Navigera till **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]** > **[!UICONTROL Edit Settings]** > **[!UICONTROL Conversion]** > **[!UICONTROL Success Events]**. [Mer...](/help/admin/admin/c-success-events/t-success-events.md)
1. Ställ in synlighetskolumnen på antingen **[!UICONTROL Visible Everywhere]**, **[!UICONTROL Builders]**, eller **[!UICONTROL Hidden Everywhere]**.

Denna inställning påverkar inte datainsamlingen för detta mätresultat. påverkar bara synligheten i användargränssnittet. Så här påverkar inställningarna synligheten för måtten i användargränssnittet:

<table id="table_26814F83F39C47D08361365E2658D249"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Inställning </th> 
   <th colname="col2" class="entry"> Synlig i </th> 
   <th colname="col3" class="entry"> Inte synlig i </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>Synlig överallt</b> </td> 
   <td colname="col2"> 
    <ul id="ul_2CCF931F462D48E3B06AE246A1A3AD91"> 
     <li id="li_C2889DBECE6D488C94B118FA33CD3988">Rapporter och analyser (meny- och mätväljare) </li> 
     <li id="li_EB7D70B1BAC840A6A32B56A1DD8F8D55">Analysis Workspace </li> 
     <li id="li_0C550B8F99C94620999331BBA1F3659C">Segment Builder </li> 
     <li id="li_E2663CFA5F8541C39CE9A18173A074AC">Beräknad metrisk Builder </li> 
    </ul> </td> 
   <td colname="col3"> Ej tillämpligt </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Builders</b> </td> 
   <td colname="col2"> 
    <ul id="ul_33E40D88D3B44CCDBA8DE6EA53794C6D"> 
     <li id="li_D72D1EB1A6164657A68AC5BDE4749BA2">Segment Builder </li> 
     <li id="li_9644DE132891444E8C98C8ADD5B17FBA">Beräknad metrisk Builder </li> 
    </ul> </td> 
   <td colname="col3"> 
    <ul id="ul_C21BB852A6E94BF288DA237772538F96"> 
     <li id="li_499402E46BD243588B0E437928734222">Rapporter och analyser (meny- och mätväljare) </li> 
     <li id="li_844967A5C7204ABE964E6DD5789E582E">Analysis Workspace </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Dold överallt</b> </td> 
   <td colname="col2"> Ej tillämpligt </td> 
   <td colname="col3"> 
    <ul id="ul_CB9780D567BD4DBA90C092DDA892BF41"> 
     <li id="li_CF90047F78FD4BB28E90E95B9B367445">Rapporter och analyser (meny- och mätväljare) </li> 
     <li id="li_9B41995CA7F3437485BAFF08A422FBFE">Analysis Workspace </li> 
     <li id="li_B4C8C6A35AB44E83B140F2C8073EEE17">Segment Builder </li> 
     <li id="li_35F3A8DD8F8C4770AEFBD68575DFAE62">Beräknad metrisk Builder </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>
