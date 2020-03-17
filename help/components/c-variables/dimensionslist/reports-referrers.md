---
description: Visar den domän eller URL-adress dit dina besökare kom från innan de kom till din webbplats, de metoder besökarna använder för att hitta din webbplats och antalet besök på din webbplats som kommer från dessa hänvisande platser.
title: Referenter
topic: Reports
uuid: e63b47b4-49f3-43af-8409-3272bec0484e
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Referenter

Visar den domän eller URL-adress dit dina besökare kom från innan de kom till din webbplats, de metoder besökarna använder för att hitta din webbplats och antalet besök på din webbplats som kommer från dessa hänvisande platser.

Om en besökare till exempel klickar på en länk från plats A och kommer till din plats, är plats A referenten om den inte är definierad som en del av din domän. Under implementeringen kan din implementeringskonsult hjälpa dig att definiera de domäner och URL:er som är en del av din webbplats. (Den här ändringen kan göras efter implementeringen.)

Domäner eller URL-adresser som inte ingår i de definierade domänerna och URL-adresserna betraktas som referenter. Webbsida A och webbsida B läggs till i det interna URL-filtret, men webbsida C läggs inte till. I det här fallet betraktas webbsida C som en referent.

## Allokering, Förfallotid och Specialvärden {#section_4D8CE5E111DD48FBBDCF9B5A1F16E92E}

<table id="table_EC7423532C7E44DE97B7FC0321585A2B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> </th> 
   <th colname="col2" class="entry"> Marknadsföringsrapporter och -analyser (SiteCatalyst) </th> 
   <th colname="col3" class="entry"> Ad hoc-analys </th> 
   <th colname="col4" class="entry"> Datalager </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Måttallokering </td> 
   <td colname="col2"> Senaste </td> 
   <td colname="col3"> Senaste </td> 
   <td colname="col4"> Senaste </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Värdena förfaller efter </td> 
   <td colname="col2"> Besök </td> 
   <td colname="col3"> Besök </td> 
   <td colname="col4"> Besök </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Värdegränser </td> 
   <td colname="col2"> Inga begränsningar (kan ändras i en framtida version) </td> 
   <td colname="col3"> Inga begränsningar (kan ändras i en framtida version) </td> 
   <td colname="col4"> ingen </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Specialvärden </td> 
   <td colname="col2"> <p>"Ingen": totalsummor som inte hade någon hänvisare under besöket. </p> </td> 
   <td colname="col3"> <p>"Ingen": totalsummor som inte hade någon hänvisare under besöket. </p> </td> 
   <td colname="col4"> <p> Tom - motsvarar ingen, totalsummor för hela webbplatsen som inte hade någon hänvisare under besöket. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Anteckningar {#section_B83A3571D64E4E7792712FAF740D7955}

* Referenten, typen av referent och referensdomän anges vid den första träffen av besöket, eller under ett besök när referenten är extern (om en besökare lämnar din webbplats använder till exempel en sökmotor och sedan återgår till din webbplats innan det första besöket upphör). Dessa värden ställs in samtidigt och kvarstår under hela besöket.
* Interna URL:er filtreras. Endast referenter som inte matchar de interna URL-filtren finns i den här rapporten.
* Motsvarande mått kallas Referer Instance i ad hoc-analyser.
* Typade/bokmärkta värden tas inte med i referensrapporten. Det innebär att webbplatsomfattande besök inte matchar besöken i den här rapporten.

## Rapporthistorik {#section_6C0FCEA9DAF04D97BA056E153B7E4628}

<table id="table_9DFA79EC6A5A48648F2FB5418E1752DB"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Datum </th> 
   <th colname="col2" class="entry"> Ändra </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 1/16/2014 </td> 
   <td colname="col2"> Datalagret uppdaterades för att matcha logiken som används i marknadsföringsrapporter och analyser. Före detta datum fanns inga nyckelord kvar under besöket. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 6/19/2012 </td> 
   <td colname="col2"> <p> Före juli 2012 innehåller"Ingen" all mobiltrafik, typbestämd/bokmärkt samt besök utan JavaScript. Efter juli 2012 innehåller"Ingen" endast träffar utan JavaScript på första besökssidan. </p> </td> 
  </tr> 
 </tbody> 
</table>

