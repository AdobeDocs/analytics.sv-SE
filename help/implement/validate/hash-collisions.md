---
title: Hash-kollisioner
description: Beskriver vad en hash-kollision är och hur den kan visa sig.
feature: Validation
exl-id: 693d5c03-4afa-4890-be4f-7dc58a1df553
source-git-commit: b3c74782ef6183fa63674b98e4c0fc39fc09441b
workflow-type: tm+mt
source-wordcount: '443'
ht-degree: 2%

---

# Hash-kollisioner

Adobe behandlar prop- och eVar-värden som strängar, även om värdet är ett tal. Ibland är strängarna hundratals tecken långa, andra gånger korta. Strängarna används inte direkt i bearbetningen för att spara utrymme, förbättra prestanda och göra allting jämnt. I stället beräknas en 32- eller 64-bitars hash för varje värde. Alla rapporter körs på dessa hashvärden, där varje hash ersätts med den ursprungliga texten. Hash-kodning ökar prestandan för Analytics-rapporter drastiskt.

För de flesta fält konverteras strängen först till enbart små bokstäver (vilket minskar antalet unika värden). Värden hashas månadsvis (första gången de visas varje månad). Från månad till månad finns det en liten möjlighet att två unika variabelvärden hash-kodas till samma värde. Detta koncept kallas *hash-kollision*.

Hash-kollisioner kan visa sig i rapporter på följande sätt:

* Om du trendar ett värde och ser en toppning under en månad, är det troligt att ytterligare värden för den variabeln hash-kodas till samma värde som det du tittar på.
* Samma sak händer för segment med ett visst värde.

## Exempel på hash-kollision

Sannolikheten för hash-kollisioner ökar med antalet unika värden i en dimension. Ett av värdena som kommer in sent i månaden kan till exempel få samma hash-värde som ett värde tidigare i månaden. Följande exempel kan förklara hur detta kan få segmentresultaten att ändras. Anta att eVar62 får värdet 100 den 18 februari. Analyserna kommer att ha en tabell som kan se ut så här:

<table id="table_6A49D1D5932E485DB2083154897E5074"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> eVar62-strängvärde </th> 
   <th colname="col2" class="entry"> Hash </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> Värde 99 </p> </td> 
   <td colname="col2"> <p> 111 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b> Värde 100</b> </p> </td> 
   <td colname="col2"> <p> <b> 123</b> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Värde 101 </p> </td> 
   <td colname="col2"> <p> 222 </p> </td> 
  </tr> 
 </tbody> 
</table>

Om du skapar ett segment som letar efter besök där eVar62=&quot;value 500&quot; används avgör Analytics om &quot;value 500&quot; innehåller en hash. Eftersom värdet 500 inte finns returnerar Analytics noll besök. Den 23 februari får eVar62&quot;value 500&quot; och hash for det är också 123. Tabellen ser ut så här:

<table id="table_5FCF0BCDA5E740CCA266A822D9084C49"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> eVar62-strängvärde </th> 
   <th colname="col2" class="entry"> Hash </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> Värde 99 </p> </td> 
   <td colname="col2"> <p> 111 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b> Värde 100</b> </p> </td> 
   <td colname="col2"> <p> <b> 123</b> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Värde 101 </p> </td> 
   <td colname="col2"> <p> 222 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b> Värde 500</b> </p> </td> 
   <td colname="col2"> <p> <b> 123</b> </p> </td> 
  </tr> 
 </tbody> 
</table>

När samma segment körs igen letar programmet efter hash-värdet 500, hittar 123 och rapporten returnerar alla besök som innehåller hash 123. Nu kommer besök som gjordes den 18 februari att ingå i resultaten.

Den här situationen kan skapa problem när Analytics används. Adobe fortsätter att undersöka sätt att minska sannolikheten för dessa hash-kollisioner i framtiden. Förslag för att undvika detta är att hitta sätt att sprida unika värden mellan variabler, ta bort onödiga värden med bearbetningsregler eller på annat sätt minska antalet värden per variabel.
