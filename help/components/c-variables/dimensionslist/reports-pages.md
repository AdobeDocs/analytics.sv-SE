---
description: Ordnar sidorna på webbplatsen baserat på de sidor som får flest trafik. Om din affärsfråga handlar om kvantitativa data för sidor kan du använda den här rapporten för att besvara den frågan genom att lägga till rätt statistik.
title: Sidor
topic: Reports
uuid: 6435e262-e734-4c15-af5b-173799d5cc43
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Sidor

Ordnar sidorna på webbplatsen baserat på de sidor som får flest trafik. Om din affärsfråga handlar om kvantitativa data för sidor kan du använda den här rapporten för att besvara den frågan genom att lägga till rätt statistik.

## Allokering, Förfallotid och Specialvärden {#section_4D8CE5E111DD48FBBDCF9B5A1F16E92E}

Observera att i Rapporter och analyser används linjär allokering för måtten på sidrapporten. Intäkterna delas till exempel mellan alla sidor som visas före en köphändelse. Detta kan skapa förvirring för vissa mätvärden som du kanske bara kan förvänta dig på en sida, till exempel en kundvagnsaddition.

<table id="table_EC7423532C7E44DE97B7FC0321585A2B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> </th> 
   <th colname="col2" class="entry">Rapporter &amp; <p>Analyser </p> </th> 
   <th colname="col3" class="entry"> Ad hoc-analys </th> 
   <th colname="col4" class="entry"> Datalager </th> 
   <th colname="col5" class="entry"> Analysis Workspace </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Måttallokering </td> 
   <td colname="col2"> Linjär </td> 
   <td colname="col3"> Allokering är specifikt för varje dimension. Standardvärdet är Senaste beröringstilldelning, men sidnamnsdimensionen är ett undantag. Om du använder en anpassad händelse för pagename blir det Exact Hit-allokering. </td> 
   <td colname="col4"> <p>Värden som angetts i samma sidvy </p> </td> 
   <td colname="col5"> <p>Värden som angetts i samma sidvy </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Värdena förfaller efter </td> 
   <td colname="col2"> Sidvy </td> 
   <td colname="col3"> Sidvy </td> 
   <td colname="col4"> Sidvy </td> 
   <td colname="col5"> Sidvy </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Värdegränser </td> 
   <td colname="col2"> <p>De första 500 kB unika per månad + nya värden med trafik </p> </td> 
   <td colname="col3"> <p>De första 500 kB unika per månad + nya värden med trafik </p> </td> 
   <td colname="col4"> Ingen </td> 
   <td colname="col5"> <p>De första 500 kB unika per månad + nya värden med trafik </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Specialvärden </td> 
   <td colname="col2"> <p>(lågtrafik) representerar värden över de första 500 kB som inte har fått tillräckligt mycket trafik för att rapporteras. </p> </td> 
   <td colname="col3"> <p>(lågtrafik) representerar värden över de första 500 kB som inte har fått tillräckligt mycket trafik för att rapporteras. </p> </td> 
   <td colname="col4"> ingen </td> 
   <td colname="col5"> <p>(lågtrafik) representerar värden över de första 500 kB som inte har fått tillräckligt mycket trafik för att rapporteras. </p> </td> 
  </tr> 
 </tbody> 
</table>

I Rapporter och analyser gäller linjär allokering om du använder en anpassad händelse som mått i en sidrapport.

Detta innebär att även om händelsen skickades med ett s.tl()-anrop, kommer den att få den linjära allokeringen för alla tidigare s.t()-anrop. Exempel:

| Sidnamn | Page_event | Händelser |
|---|---|---|
| Page1 | **s.t()** |  |
| Page1 | s.tl() | Event1 |
| Page1 | s.tl() | Event1 |
| Page1 | s.tl() | Event1 |
| Page2 | **s.t()** |  |
| Page2 | **s.t()** |  |
| Page2 | s.tl() | Event1 |

I det här scenariot får vi följande allokering i rapporten Sidor:

| Sidor | Sidor | Händelse 1 |
|---|---|---|
| Sida 1 | 1 | 1+1+1+1/3 = 3.33 |
| Sidan 2 | 2 | 2/3 = 0.67 |

Även om händelsen skickas för ett s.tl-anrop får sidan som visas före händelsen som skickades (s.t()-anropet) delvis kredit.

## Anteckningar {#section_47B0F4746D4847AC9E8697127063F4D0}

* Om det inte finns något sidnamn används URL-adressen.
* Om du har en träff utan sidnamn, sid-URL eller händelselista (ingen e-handelshändelse), utesluts träffen.
* Uppdelningar på sidor visar alla sidor som har ett bestående värde.

