---
description: Alla segment som skapas i segmentbyggaren är inte kompatibla med datalagret. I den här tabellen visas de funktioner som stöds.
title: Datalagersegmentkompatibilitet
topic: Segments
uuid: 370258c5-8614-4434-871c-41753ed77f5c
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Datalagersegmentkompatibilitet

Alla segment som skapas i segmentbyggaren är inte kompatibla med [!DNL Data Warehouse]. I den här tabellen visas de funktioner som stöds.

<table id="table_BBB1DAFDF85041598FA4AF869172CF7F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> </th> 
   <th colname="col2" class="entry"> Analysis Workspace, Reports &amp; Analytics, Ad hoc Analysis </th> 
   <th colname="col3" class="entry"> Datalager </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>Exkluderar</b> </td> 
   <td colname="col2"> Stöds på alla nivåer </td> 
   <td colname="col3"> Stöds endast i specialfall på den översta nivån </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Sekventiella segment</b> </td> 
   <td colname="col2"> Stöds </td> 
   <td colname="col3"> Stöds inte </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>AND och OR kan kombineras utan gränser</b> </td> 
   <td colname="col2"> Stöds </td> 
   <td colname="col3"> Vissa begränsningar. Se *anm.* nedan. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Kapslade behållare</b> </td> 
   <td colname="col2"> Stöds </td> 
   <td colname="col3"> Vissa begränsningar (de måste minska i omfång, besökare kan till exempel innehålla träffar, men inte tvärtom) </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Dimensioner</b> </td> 
   <td colname="col2">Dra och släpp en dimension i segmentbyggarens <span class="uicontrol"> definitionsfält</span> för att ta reda på om den är kompatibel med produkten. De här dimensionerna stöds till exempel bara i Analysis Workspace, Reports &amp; Analytics och Ad Hoc Analysis: 
    <ul id="ul_BD708CC3A16743F49F998D1046EC70A3"> 
     <li id="li_240DA619D50B4336ACD9117BF59AF10A">Startserver </li> 
     <li id="li_222D4D4116674EF8A52945CCB9C78719">Postkategori </li> 
     <li id="li_5A43C846E2EA4EFCB892DE9E0607C68C">Anmälningsdatum </li> 
     <li id="li_8E9CABBE04FC4A7A9A5D2BDD34AD3C87">Alla söksidrankning </li> 
    </ul> </td> 
   <td colname="col3"> Dra och släpp en dimension i segmentbyggarens <span class="uicontrol"> definitionsfält</span> för att ta reda på om den är kompatibel med produkten. De här dimensionerna stöds till exempel bara i datalagret: 
    <ul id="ul_61A5B314CCCF497DB0385324E3309E22"> 
     <li id="li_1254089BDFAE4E0F8E51CB1511BBBF53">IP-adress </li> 
     <li id="li_D8E040F77A8C46A084547F4FE685CB10">Sidans URL </li> 
     <li id="li_4C79AE900CF6458780C124143DC6FA5B">Besökar-ID </li> 
     <li id="li_4EC10645DE9740609D8DDFD4F668FE67">Experience Cloud-besökar-ID </li> 
    </ul> <p>Följande dimensioner <b>kan inte </b>användas i datalagersegment: </p> 
    <ul id="ul_FE143F6D1ABF45DAA444E1B5691C7D4F"> 
     <li id="li_E77F3CC45BA04674B857FE5AB19D56F1">Alla söksidrankning </li> 
     <li id="li_95E1549C13F14BA0B32686401EE78E31">AM/PM </li> 
     <li id="li_6F1C8FC2E7674A0CA14B70B65784D896">Dag i månaden </li> 
     <li id="li_79D1A91D741D4CCC937D07906D71F964">Veckodag </li> 
     <li id="li_4008565353084611BD782B98D50C0611">Dag på året </li> 
     <li id="li_F87D78F125874087BFF74FAAE2BA46F5">Enhet för startaffärsenhet </li> 
     <li id="li_53DA4E64C6714CFF90D164245D01C16A">Post (alla dimensioner som börjar med Inmatning, förutom Inmatningssida) </li> 
     <li id="li_7F26B0E54A4A48319F31D8FC499D1CF2">Avsluta (alla dimensioner med början vid Avsluta, förutom Avsluta länk och Avsluta sida) </li> 
     <li id="li_1877D2D8A95B43F29CAA426BF2FE4996">Hierarki (alla dimensioner med början från hierarki) </li> 
     <li id="li_DF0BCC63ED274ABEA1C5A28274936310">Träff-djup </li> 
     <li id="li_98BE56213E1A4FD28D4858D53C46D23E">Träfftyp </li> 
     <li id="li_52ECB31657DF4180BDB9C8D21CC74313">Timdag </li> 
     <li id="li_93716207F2614822ACB84100B35D27BC">Månad på året </li> 
     <li id="li_FFC8E1F7092C4876A7E9F2365CC234B9">Sidorna hittades inte </li> 
     <li id="li_7A070C8E0F664F5AB554555B17D0E4E6">Betalsökning </li> 
     <li id="li_12228C18BF90463C8D8394FB810843D3">Kvartal på året </li> 
     <li id="li_1833B6E2011C4757A60CAA2C98B35AFA">Returfrekvens </li> 
     <li id="li_39154CD74A534D9AA09C701FE1E2C521">Besök på en sida </li> 
     <li id="li_84BDE34DD577488881E8842D2DE72D3C">Tid före händelse </li> 
     <li id="li_552BE3414CC949B3B24BE99298945874">Tid som använts på sidan - paketerad </li> 
     <li id="li_33D815E04CB3493C82BE33E958C2D7B9">Tid per besök - paketerad </li> 
     <li id="li_76F2BB88B8CD456DB50D04F36BB7854B">Orsak till avanmälan av spårning </li> 
     <li id="li_07345E08D0584CEC99128A0542587019">USA </li> 
     <li id="li_3D6BD9E927334B9BBC29E602D1103F7A">Veckodag/Veckoslut </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Segmentstapling</b> </td> 
   <td colname="col2"> Stöds </td> 
   <td colname="col3"> Stöds inte </td> 
  </tr> 
 </tbody> 
</table>

*Obs! Datalagret stöder inte alla fall där en`exclusion`eller`without`en behållare används vid användning`AND/OR`. När du använder en sådan kombination stöds endast de segment som kan skrivas om som`A AND NOT B`(eller **inkludera den här egenskapen**och ****exkludera den) i datalagret.*
