---
description: Visar en beskrivning av söknyckelord.
title: Sök nyckelord
topic: Reports
uuid: db9d477b-b711-4b93-9c25-3aebe5f2ace6
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Sök nyckelord

Visar en beskrivning av söknyckelord.

**Sök nyckelord - alla**: Visar en beskrivning av varje söknyckelord som har använts för att hitta platsen. Du kan sortera den här listan efter sidvyer eller söknyckelord genom att klicka på kolumnrubriken ovanför listan. Klicka på förstoringsglaset bredvid ett söknyckelord för att se sökresultaten för din webbplats.

**Nyckelord för sökning - betald**: Visar en beskrivning av varje betalt söknyckelord som används för att hitta platsen. Du kan sortera den här listan efter sidvyer eller söknyckelord genom att klicka på kolumnrubriken ovanför listan. Klicka på förstoringsglaset bredvid ett söknyckelord för att se sökresultaten för din webbplats.

**Sök efter nyckelord - naturligt**: Visar en beskrivning av varje naturligt söknyckelord som används för att hitta platsen. Du kan sortera den här listan efter sidvyer eller söknyckelord genom att klicka på kolumnrubriken ovanför listan. Klicka på förstoringsglaset bredvid ett söknyckelord för att se sökresultaten för din webbplats.

>[!IMPORTANT]
>
>För betald och naturlig sökning slutade sökmotorer att tillhandahålla (i de flesta fall) söknyckelorden som en del av referenten. Därför klassificerar Adobe alltid Google- (eller Bing- eller Yahoo-domänen) som sökning. Baserat på formatet och innehållet i referensprogrammet (även utan nyckelorden) kan Adobe avgöra ofta att det var resultatet av en sökning, så sökningen räknas med Nyckelord som inte är tillgängliga. [Mer ...](https://helpx.adobe.com/analytics/kb/keyword-unavailable.html)

## Allokering, Förfallotid och Specialvärden {#section_4D8CE5E111DD48FBBDCF9B5A1F16E92E}

<table id="table_EC7423532C7E44DE97B7FC0321585A2B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> </th> 
   <th colname="col2" class="entry"> <p>Analysis Workspace </p> <p>Rapporter och analyser </p> </th> 
   <th colname="col3" class="entry"> Ad hoc-analys </th> 
   <th colname="col4" class="entry"> Datalager </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Måttallokering </td> 
   <td colname="col2"> <p>Ursprungligt värde (standard) </p> <p> Kan ändras till linjär. </p> </td> 
   <td colname="col3"> Senaste (kan ändras till linjär med den linjära versionen av en metik) </td> 
   <td colname="col4"> <p>Ursprungligt värde (standard) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Värdena förfaller efter </td> 
   <td colname="col2"> Besök - kan förkortas men inte förlängas </td> 
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
   <td colname="col2"> <p>"Ingen": summor för hela webbplatsen som inte hade något nyckelord under besöket. </p> "Nyckelordet är inte tillgängligt" är sökningar där nyckelordet har tagits bort från sökningen och inte skickas till datainsamlingen. Detta inträffar vanligtvis när en kund är inloggad på ett Google-konto. Gäller betald och naturlig. </td> 
   <td colname="col3"> (lågtrafik) representerar värden över de första 500 kB som inte har fått tillräckligt mycket trafik för att rapporteras. </td> 
   <td colname="col4"> <p> Tom - motsvarar ingen, totalsummor för hela webbplatsen som inte hade något nyckelord under besöket. </p> <p>"Nyckelordet är inte tillgängligt" är sökningar där nyckelordet har tagits bort från sökningen och inte skickas till datainsamlingen. Detta inträffar vanligtvis när en kund är inloggad på ett Google-konto. Gäller betald och naturlig. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Rapporthistorik {#section_6C0FCEA9DAF04D97BA056E153B7E4628}

| Datum | Ändra |
|---|---|
| 1/16/2014 | Datalagret uppdaterades för att matcha logiken som används i marknadsföringsrapporter och analyser. Före detta datum fanns inga nyckelord kvar under besöket. |

