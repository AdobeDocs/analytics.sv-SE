---
description: Visar i genomsnitt hur långt inom ett besök varje värde har utlösts. Detta mått är värdefullt för att avgöra hur långt inom ett besök målgruppen kommer till en viss sida eller ett visst prop-värde. Genomsnittligt siddjup är tillgängligt för alla variabler där målning är aktiverat.
title: Genomsnittligt siddjup
topic: Metrics
uuid: 4d8a3a3c-c698-4210-8dd8-a02a1638483c
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Genomsnittligt siddjup

Visar i genomsnitt hur långt inom ett besök varje värde har utlösts. Detta mått är värdefullt för att avgöra hur långt inom ett besök målgruppen kommer till en viss sida eller ett visst prop-värde. Genomsnittligt siddjup är tillgängligt för alla variabler där målning är aktiverat.

Om ett besök till exempel innehåller följande sökväg: Sidan A > Sida B > Sida C > Sida D > Sida E > Sida F. Djupet är ett index där sidan finns. &quot;Page A&quot; har till exempel djupet 0, medan &quot;Page F&quot;. har ett djup på fem. Genomsnittet baseras på en kombination av alla besök. Ett siddjup med ett värde som är mindre än ett (till exempel 0,9) är medelvärdet av alla sidor som besöktes före sidan i fråga.

[!UICONTROL Page Depth] hjälper dig att förstå var en viss sida vanligtvis finns i en användarsökväg, oavsett tidigare eller kommande sidor i den här sökvägen. Det hjälper dig att få insikt i hur sidan passar in i den övergripande bilden av användarens upplevelse på din webbplats. Denna insikt kan bäst ses i en [!UICONTROL Pages] rapport.

<table id="table_E92B185A487C40E28C70EA30EDF73A40"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Användningsområden </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Trafik </td> 
   <td colname="col2"> <p>Beräkningen av sidhändelser och sidor som visas delade av besök, som visar ett medeltal av en sidas klicknummer. Se samma besöksväg: </p> <p>A &gt; B &gt; B &gt; C &gt; D &gt; B </p> <p>Klicknumret beräknas för varje sida och sidhändelse, inklusive omladdningar när alternativet Antal upprepningsinstanser är aktiverat (detta är aktiverat som standard i ad hoc-analys och är alltid aktiverat i marknadsföringsrapporter och analyser). Vid det här besöket får sidan A klicknumret 0. För sida B är klicknumren 1, 2 och 5. Beräkningen för medelvärdet skulle vara [(1+2+5) / 3] för ett medelstort siddjup på 2,67 för sida B. </p> <p>När alternativet Antal upprepningsinstanser är inaktiverat får sidan B 1 och 4. Den andra räknas inte. Beräkningen skulle vara [(1+4) / 2 = 2.5]. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Konvertering </td> 
   <td colname="col2"> Ej tillämpligt </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [Siddjupsrapport](/help/components/c-variables/dimensionslist/reports-page-depth.md)

