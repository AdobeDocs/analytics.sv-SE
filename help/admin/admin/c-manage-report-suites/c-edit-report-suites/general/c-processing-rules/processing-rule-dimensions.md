---
description: De dimensioner som du kan läsa och skriva (om inget annat anges) med bearbetningsregler.
subtopic: Processing rules
title: Dimensioner som är tillgängliga för bearbetningsregler
feature: Processing Rules
role: Admin
exl-id: ffd7a1d6-2c9d-41e7-9c75-9e47b6f9c283
source-git-commit: 429aaa43fdae669350bdb5a5a54a7d4b9b1c65f2
workflow-type: tm+mt
source-wordcount: '729'
ht-degree: 1%

---

# Dimensioner som är tillgängliga för bearbetningsregler

De dimensioner som du kan läsa och skriva (om inget annat anges) med bearbetningsregler.

## Anpassade värden och kontextdata {#section_7A5E1810CAC34B0BBC69F8F5F7C75AA5}

<table id="table_5011C501D5DC489E87A42FFC51DEB40D"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Värde </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Eget värde </p> </td> 
   <td colname="col2"> <p>Anpassad text eller anpassade värden som skrivs direkt i en bearbetningsregel. Dessa värden är tillgängliga i efterföljande villkor och regler. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Sammansatt värde </p> </td> 
   <td colname="col2"> <p>Värden som skapas genom att två värden kombineras. Till exempel kan kategori- och sidnamn kombineras för att skapa en underkategori. Dessa värden är tillgängliga i efterföljande villkor och regler. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ändrade värden </p> </td> 
   <td colname="col2"> <p>Om ett variabelvärde ändras med bearbetningsregler används det ändrade värdet i efterföljande villkor och regler. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Kontextdatavariabler </p> </td> 
   <td colname="col2"> <p>Namngivna variabler som skickas med en träff. </p> <p>Obs! Alla data i en kontextdatavariabel måste kopieras till en rapportvariabel för att kunna visas i en rapport. Kontextdatavariabler kan inte visas i något rapporteringsgränssnitt, inklusive ClickStream-dataflöden. </p> <p> <a href="/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/processing-rules-examples/processing-rules-copy-context-data.md"> Kopiera en kontextdatavariabel till en eVar </a> </p> <p> <a href="/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/processing-rules-examples/processing-rules-copy-context-data-event.md"> Ange en händelse med en kontextdatavariabel </a> </p> <p> <a href="/help/implement/vars/page-vars/contextdata.md"> kontextdatavariabler </a> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Trafikvariabler {#section_225156106F8B41F8BC1E68D58DDC2652}

<table id="table_575F618C59DC4933BC77F935518EAE39"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Variabel </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>prop 1-75 </p> </td> 
   <td colname="col2"> <p> <code> prop1 - prop75</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Hierarki 1-5 </p> </td> 
   <td colname="col2"> <p> <code> hier1 - hier5</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Platsavsnitt </p> </td> 
   <td colname="col2"> <p> <code> s.channel </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Server </p> </td> 
   <td colname="col2"> <p> <code> s.server </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Träffattribut {#section_07E69A86A47741A083FD84F112EB80D0}

<table id="table_9011B1FA462B4DBBAA58FC2D6D638DA1"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Attribut </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Report Suite-ID (skrivskyddat) </p> </td> 
   <td colname="col2"> <p>Rapportsviten som bearbetningsregeln körs på, vilket kanske inte är den ursprungliga rapportsviten som anges i AppMeasurementet. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Sidnamn </p> </td> 
   <td colname="col2"> <p> <code> s.pageName</code> </p> <p>Obs! Länkspårningsanrop tar bort variabeln <code>pageName</code> innan de når bearbetningsregler. Om du infogar ett sidnamnsvärde igen med bearbetningsregler betraktas träffen som en sidvy i stället för som ett länkspårningsanrop. Adobe rekommenderar att du kontrollerar att sidnamnet redan har angetts innan du ändrar det. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Sidans URL </p> </td> 
   <td colname="col2"> <code> s.pageURL</code> eller den aktuella sidans URL om <code> s.pageURL</code> inte anges. <p>Obs! Länkspårningsanrop tar bort variabeln <code>pageURL</code> innan de når bearbetningsregler. Om du infogar ett URL-värde för en sida på nytt med bearbetningsregler, betraktas träffen som en sidvy i stället för som ett länkspårningsanrop. Adobe rekommenderar att du kontrollerar att sidans URL är inställd innan du ändrar den. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Frågesträngsparameter </p> </td> 
   <td colname="col2"> <p>Värdet för en angiven frågesträngsparameter i den aktuella URL:en, eller null om det inte finns någon parameter. För URL:en <b>https://www.example.com/a.html?cid=ad1&amp;node=4</b> är värdet för frågesträngsparameter <span class="syntax codeph"> cid</span> <b>ad1</b> och värdet för frågesträngsparameter <span class="syntax codeph"> node</span> är <b>4</b>. </p> <p>Om du kör JavaScript AppMeasurement H.25.2 eller tidigare kan sidans URL-adress trunkeras efter 255 tecken. JavaScript AppMeasurement H.25.3 (släppt i januari 2013) och senare innehåller den fullständiga URL:en till bearbetningsregler. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Sidsökväg </p> </td> 
   <td colname="col2"> <p>Sökvägen till sidans URL. URL:en <b>https://www.example.com/news/a.html?cid=ad1</b> är <span class="syntax codeph"> news/a.html</span> . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Siddomän </p> </td> 
   <td colname="col2"> <p>Det fullständiga värdnamnet som anges i URL:en. https://<span class="syntax codeph"> en.main.example.co.uk</span>/index.jsp?q=value </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Rotdomän för sida </p> </td> 
   <td colname="col2"> <p>De två sista avsnitten i värdnamnet för sidan. https://en.main.example.<span class="syntax codeph"> co.uk</span>/index.jsp?q=value </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Sidfrågesträng </p> </td> 
   <td colname="col2"> <p>URL:ens fullständiga frågesträng. https://en.main.example.co.uk/index.jsp?<span class="syntax codeph"> q=värde</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Referent* (skrivskyddad) </p> </td> 
   <td colname="col2"> <p>HTTP-referent. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Refererar frågesträngsparameter (skrivskyddad) </p> </td> 
   <td colname="col2"> <p>Värdet för en angiven frågesträngsparameter i den refererande URL:en, eller null om det inte finns någon parameter. För URL:en <b>https://www.example.com/a.html?cid=ad1&amp;node=4</b> är värdet för frågesträngsparameter <span class="syntax codeph"> cid</span> <b>ad1</b> och värdet för frågesträngsparameter <span class="syntax codeph"> node</span> är <b>4</b>. </p> <p>Om du kör JavaScript AppMeasurement H.25.2 eller tidigare kan sidans URL-adress trunkeras efter 255 tecken. JavaScript AppMeasurement H.25.3 (släppt i januari 2013) och senare innehåller den fullständiga URL:en till bearbetningsregler. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Refererande domän (skrivskyddad) </p> </td> 
   <td colname="col2"> <p>Skådarens fullständiga värdnamn. https://<span class="syntax codeph"> en.main.example.co.uk</span>/index.jsp?q=value </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Refererande rotdomän (skrivskyddad) </p> </td> 
   <td colname="col2"> <p>De två sista avsnitten i referentens värdnamn. https://en.main.example.<span class="syntax codeph"> co.uk</span>/index.jsp?q=value </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Referensfrågesträng (skrivskyddad) </p> </td> 
   <td colname="col2"> <p>Frågesträngsparametrar som finns i den refererande URL:en. https://en.main.example.co.uk/index.jsp?<span class="syntax codeph"> q=värde</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>IP-adress (skrivskyddad) </p> </td> 
   <td colname="col2"> <p>IP-adress som rapporterats av webbläsaren. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Användaragent (skrivskyddad) </p> </td> 
   <td colname="col2"> <p>Användaragent som rapporterats av webbläsaren. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>AppMeasurementen kodversion (skrivskyddad) </p> </td> 
   <td colname="col2"> <p>Den version av AppMeasurement-biblioteket som användes för att göra begäran. När du använder bildfyrar kan du fylla i detta med ett anpassat värde som läses med bearbetningsregler. Det här värdet visas på följande plats i URL:en: </p> <p>https://server.net/b/ss/report-suite-ID/1/<span class="syntax codeph"> CODEVERSION</span>/.. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Konverteringsvariabler {#section_311856B21B3B49DBAA0539CFA06C409F}

<table id="table_E28729026EDA485989178A3B887B5983"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Variabel </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>eVar 1-N </p> </td> 
   <td colname="col2"> <p> <code> evar1</code> - <code> evarN</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Kampanjspårningskod </p> </td> 
   <td colname="col2"> <p> <code> s.campaign</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Valutakod </p> </td> 
   <td colname="col2"> <p> <code> s.currencyCode</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Listvariabler1-3 </p> </td> 
   <td colname="col2"> <p> <code> s.list1</code> - <code> s.list3</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Inköps-ID </p> </td> 
   <td colname="col2"> <p> <code> s.purchaseID</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Transaktions-ID </p> </td> 
   <td colname="col2"> <p> <code> s.transactionID </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Besökarläge </p> </td> 
   <td colname="col2"> <p> <code> s.state</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Besökarens postnummer </p> </td> 
   <td colname="col2"> <p> <code> s.zip</code> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Success Events {#section_C1946FEB64FC4F579671EC5E0D06AE8A}

Bearbetningsregler kan ange händelser men kan inte läsa dem som villkor.

<table id="table_926ED12B58CA4FB685D799DC6EE567C0"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Händelse </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Händelse 1-1000 </p> <p>(För SiteCatalyst 15-kunder, Event 1-100.) </p> </td> 
   <td colname="col2"> <p> <code> event1</code> - <code> event1000</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>purchase, scView, scAdd, and other cart events </p> </td> 
   <td colname="col2"> <p>Fördefinierade händelser. </p> </td> 
  </tr> 
 </tbody> 
</table>
