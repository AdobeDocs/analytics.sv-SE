---
description: Visar de domäner som refererade till de kunder som mest påverkade webbplatsens framgångsmått. Hänvisarna delas in i två huvudkategorier Domäner och URL:er. Domäner refererar till domännamnet och visas som basdomän utan frågesträngen eller underkatalogerna kopplade. URL:er innehåller basdomännamnet samt eventuella frågesträngar och underkataloger.
title: Refererande domäner
topic: Reports
uuid: ab310bb8-51b1-4428-a42e-2377d36ca986
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Refererande domäner

Visar de domäner som refererade till de kunder som mest påverkade webbplatsens framgångsmått. Referenser kan delas in i två huvudkategorier: Domäner och URL:er. Domäner refererar till domännamnet och visas som basdomän utan frågesträngen eller underkatalogerna kopplade. URL:er innehåller basdomännamnet samt eventuella frågesträngar och underkataloger.

## Allokering, Förfallotid och Specialvärden {#section_4D8CE5E111DD48FBBDCF9B5A1F16E92E}

<table id="table_EC7423532C7E44DE97B7FC0321585A2B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> </th> 
   <th colname="col2" class="entry"> Rapporter och analyser </th> 
   <th colname="col3" class="entry"> Ad hoc-analys </th> 
   <th colname="col4" class="entry"> Datalager </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Måttallokering </td> 
   <td colname="col2"> <p>Senaste </p> </td> 
   <td colname="col3"> <p>Senaste (kan ändras till linjär med den linjära versionen av en metik) </p> </td> 
   <td colname="col4"> <p>Senaste </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Värdena förfaller efter </td> 
   <td colname="col2"> Besök - kan förkortas men inte förlängas </td> 
   <td colname="col3"> Besök </td> 
   <td colname="col4"> Besök </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Värdegränser </td> 
   <td colname="col2"> Ingen </td> 
   <td colname="col3"> Ingen </td> 
   <td colname="col4"> Ingen </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Specialvärden </td> 
   <td colname="col2"> <p>" Typed/Bookmarked": besök utan hänvisande domän. </p> </td> 
   <td colname="col3"> <p>" Typed/Bookmarked": besök utan hänvisande domän. </p> </td> 
   <td colname="col4"> <p>" Typed/Bookmarked": besök utan hänvisande domän. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Anteckningar {#section_B83A3571D64E4E7792712FAF740D7955}

* Referenten, typen av referent och referensdomän anges vid den första träffen av besöket, eller under ett besök när referenten är extern (om en besökare lämnar din webbplats använder till exempel en sökmotor och sedan återgår till din webbplats innan det första besöket upphör). Dessa värden ställs in samtidigt och kvarstår under hela besöket.
* Det typbestämda/bokmärkta linjeobjektet innehåller inte andra referenstyper, t.ex. inget JavaScript eller på din plats. Därför kommer radobjekten inte att matcha summan på grund av dessa utelämnanden.
* Före juli 2012 fanns inte mobiltrafiken med i den här rapporten.

