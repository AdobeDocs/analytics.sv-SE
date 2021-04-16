---
description: Datakällkategorier identifierar olika typer av datakällor som erbjuder liknande funktionalitet.
subtopic: Data sources
title: Översikt över datatyper och kategorier
topic-fix: Developer and implementation
uuid: b5004cdc-b68a-4a82-a159-a7cd7b8bfe21
exl-id: d459fd06-a0fe-49e6-8624-b42f0c60ee6e
translation-type: tm+mt
source-git-commit: 78412c2588b07f47981ac0d953893db6b9e1d3c2
workflow-type: tm+mt
source-wordcount: '907'
ht-degree: 4%

---

# Översikt över datatyper och kategorier

Datakällkategorier identifierar olika typer av datakällor som erbjuder liknande funktionalitet.

Med kategorier kan du gruppera datakällor utifrån användarens perspektiv. När du skapar en datakälla via användargränssnittet för datakällor väljer du först en datakällkategori och sedan en viss datakälltyp. Varje kategori innehåller typer av datakällor som stöder liknande typer av data. Datakällor har följande kategorier för datakällor:

## Webbplatsanvändning {#section_4BA8D97B6BA848518F21760AE49F41D1}

<table id="table_2562E7A400214B8F9BB9177D210348F4"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Datakälla </p> </th> 
   <th colname="col2" class="entry"> <p>Bearbetningstyp </p> </th> 
   <th colname="col3" class="entry"> <p>Beskrivning </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Webbserverloggfiler </p> </td> 
   <td colname="col2"> <p> <a href="/help/import/c-data-sources/c-datasrc-types/datasrc-web-log.md"   > Webblogg  </a> </p> </td> 
   <td colname="col3"> <p>De flesta webbservrar genererar loggfiler som registrerar varje sida som hanteras. Med den här datakällan kan du bearbeta loggfilerna från de flesta webbserverdata och lägga till dessa data i dina rapporter. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Advertising Cloud Bulk Upload </p> </td> 
   <td colname="col2"> <p> <a href="/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md"   > Konvertering </a> </p> </td> 
   <td colname="col3"> <p>Ger manuella och automatiserade massöverföringar i Advertising Cloud. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Datakälla för trafik på webbplatsnivå </p> </td> 
   <td colname="col2"> <p> <a href="/help/import/c-data-sources/c-datasrc-types/datasrc-traffic.md"   > Trafik </a> </p> </td> 
   <td colname="col3"> <p>Importerar trafikdata för hela webbplatsen. Exempel: Sidvyer. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Datakälla för fördelningstrafik </p> </td> 
   <td colname="col2"> <p> <a href="/help/import/c-data-sources/c-datasrc-types/datasrc-traffic.md"   > Trafik </a> </p> </td> 
   <td colname="col3"> <p>Importerar trafikdata som har delats upp av en annan webbplatsvariabel. Exempel: Sidvyer efter produkt. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Annonskampanjer {#section_9AE27E347CFC48F29E7C1134B6E928A6}

<table id="table_2A297A86CC3E4B1E8B72389AA148549A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Datakälla </p> </th> 
   <th colname="col2" class="entry"> <p>Bearbetningstyp </p> </th> 
   <th colname="col3" class="entry"> <p>Beskrivning </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Allmän annonsserver </p> </td> 
   <td colname="col2"> <p> <a href="/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md"   > Konvertering </a> </p> </td> 
   <td colname="col3"> <p>Gör att ni kan integrera visningar och annan toppnivåstatistik om era annonsserveraktiviteter i marknadsföringsrapporter. Detta är den allmänna datakällan för annonsservern och bör användas om din specifika annonsserver inte stöds. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Allmän e-postkampanjserver </p> </td> 
   <td colname="col2"> <p> <a href="/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md"   > Konvertering </a> </p> </td> 
   <td colname="col3"> <p>Gör att ni kan integrera mätvärden från era e-postkampanjservrar i marknadsföringsrapporter. </p> <p>Vanliga inbyggda mätvärden är antalet skickade meddelanden, skickade meddelanden och lästa meddelanden. Detta är den allmänna datakällan för e-postkampanjen och bör användas om din specifika e-postkampanjserver inte stöds. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Allmän tjänst för betalning per klick </p> </td> 
   <td colname="col2"> <p> <a href="/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md"   > Konvertering </a> </p> </td> 
   <td colname="col3"> <p> Gör att du kan importera data om hur mycket du betalar per klick, inklusive visningar, klickningar och kostnader. </p> <p>Detta är den generiska datakällan för betalning per klick och bör användas om din specifika tjänst för betalning per klick inte stöds. </p> </td> 
  </tr> 
 </tbody> 
</table>

## CRM (Customer Relationship Management) {#section_013A1C5D3CAD4CCEAD22C2FDD26715A0}

<table id="table_5895659CAB2C415AB2AA59A2E6C75AD1"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Datakälla </p> </th> 
   <th colname="col2" class="entry"> <p>Bearbetningstyp </p> </th> 
   <th colname="col3" class="entry"> <p>Beskrivning </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Allmänt callcenter </p> </td> 
   <td colname="col2"> <p> <a href="/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md"   > Konvertering </a> </p> </td> 
   <td colname="col3"> <p>Gör att ni kan integrera information om ert callcenter i marknadsföringsrapporter. De vanligaste mätvärdena är antalet samtal, telefontid, agenten och den totala försäljningen. </p> <p>Den här datakällan är den generiska datakällan för call center och bör användas om din specifika call center-programvara inte stöds. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> </p> <p>Allmän kundsupport </p> <p>Program </p> </td> 
   <td colname="col2"> <p> <a href="/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md"   > Konvertering </a> </p> </td> 
   <td colname="col3"> <p>Här kan ni integrera information från era kundsupportprogram i marknadsföringsrapporter. Det innehåller mätvärden som antalet nya incidenter, antalet åtgärdade incidenter och hur lång tid som har ägnats åt att lösa incidenter. </p> <p>Detta är den allmänna datakällan för kundsupport och bör användas om ditt specifika kundtjänstprogram inte stöds. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Kundnöjdhet {#section_1058CA3860044630B0B06EEDA261DBA2}

<table id="table_3811CA1E2B7C45D7A0CBEC5CE44C11A8"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Datakälla </p> </th> 
   <th colname="col2" class="entry"> <p>Bearbetningstyp </p> </th> 
   <th colname="col3" class="entry"> <p>Beskrivning </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Allmänna undersökningsdata </p> </td> 
   <td colname="col2"> <p> <a href="/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md"   > Konvertering </a> </p> </td> 
   <td colname="col3"> <p>Gör att ni kan integrera undersökningsresultat från ett tredjepartsverktyg i marknadsföringsrapporter och visa hur nöjda kunderna är genom deras interaktioner med er webbplats. </p> <p>Detta är den allmänna datakällan för undersökningen och bör användas om din specifika datatjänst för undersökningen inte stöds. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Webbplatsprestanda {#section_3A7BECB0B4B247FB991DC59237ECFE1F}

<table id="table_7B623D08275E4FDEADDD85EA89A2B7C7"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Datakälla </p> </th> 
   <th colname="col2" class="entry"> <p>Bearbetningstyp </p> </th> 
   <th colname="col3" class="entry"> <p>Beskrivning </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Allmän nedladdningshastighet </p> </td> 
   <td colname="col2"> <p> <a href="/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md"   > Konvertering </a> </p> </td> 
   <td colname="col3"> <p>Gör att du kan integrera data från ett program eller en tjänst som spårar hastigheten på dina hämtningar med dina data. </p> <p>Detta är den allmänna datakällan för nedladdningshastighet och bör användas om din specifika programvara eller tjänst för nedladdningshastighet inte stöds. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Allmän {#section_9B9A2A9871894B6491032AE1E961629A}

<table id="table_D63A6A00C93A4CD48FEBE7BC24E5DA9F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Datakälla </p> </th> 
   <th colname="col2" class="entry"> <p>Bearbetningstyp </p> </th> 
   <th colname="col3" class="entry"> <p>Beskrivning </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> </p> <p>Allmän datakälla (endast sammanfattningsdata) </p> </td> 
   <td colname="col2"> <p> <a href="/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md"   > Konvertering </a> </p> </td> 
   <td colname="col3"> <p>Använd den här datakällan när det inte finns någon bättre matchning mot den typ av data som du vill importera till marketing reports and analytics. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Allmän datakälla (fullständig bearbetning) </p> </td> 
   <td colname="col2"> <p> <a href="/help/import/c-data-sources/c-datasrc-types/datasrc-full-processing.md"   > Fullständig bearbetning  </a> </p> </td> 
   <td colname="col3"> <p>Gör att du kan importera loggfilsdata. Dessa data bearbetas som om de togs emot av datainsamlingsservrar vid den angivna tidpunkten (varje träff får en tidsstämpel). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> </p> <p>Allmän datakälla (transaktions-ID) </p> </td> 
   <td colname="col2"> <p> <a href="/help/import/c-data-sources/c-datasrc-types/datasrc-transactionid.md"   > Transaktions-ID </a> </p> <p> <a href="/help/import/c-data-sources/c-datasrc-types/datasrc-visitorid.md"   > Besökar-ID </a> </p> </td> 
   <td colname="col3"> <p>Gör att du kan koppla en offlinehändelse till en onlinehändelse. Transaktions-ID:t fungerar som en nyckel mellan offline- och onlinehändelserna. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Onlineköp {#section_2B2D4DBB045548C3A5DC7DEF81BA56D1}

<table id="table_EE450D955D4C4264A40142AF6D74F1AA"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Datakälla </p> </th> 
   <th colname="col2" class="entry"> <p>Bearbetningstyp </p> </th> 
   <th colname="col3" class="entry"> <p>Beskrivning </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Produktreturer </p> </td> 
   <td colname="col2"> <p> <a href="/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md"   > Konvertering </a> </p> </td> 
   <td colname="col3"> <p>Gör att du kan importera produktreturdata som ska kopplas till ett köp-ID så att du kan identifiera sökmotorer, nyckelord, kampanjer och andra attribut som är mer benägna att generera returer. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Produktkostnad </p> </td> 
   <td colname="col2"> <p> <a href="/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md"   > Konvertering </a> </p> </td> 
   <td colname="col3"> <p>Här kan du ange den faktiska kostnaden för produkter som köpts och levererats från din webbplats genom att associera kostnad eller vinst med enskilda produkter så att du kan rapportera korrekt om de mest lönsamma kampanjerna, nyckelorden och interna kampanjerna för din webbplats. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Orderstatus </p> </td> 
   <td colname="col2"> <p> <a href="/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md"   > Konvertering </a> </p> </td> 
   <td colname="col3"> <p>Här kan du använda mätvärden för att identifiera status för varje beställning som gjorts, inklusive beställningar som annullerats, skickats, slutförts eller bedömts vara bedrägliga. </p> <p>Orderstatusrapportering kan identifiera vilka förvärvsmetoder som genererar den högsta orderslutförandefrekvensen. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Leads och citattecken {#section_0B3EAA59BEC94244BE3EB3825D719DF6}

<table id="table_85B095414F6C4644A191A94AC0CAD13D"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Datakälla </p> </th> 
   <th colname="col2" class="entry"> <p>Bearbetningstyp </p> </th> 
   <th colname="col3" class="entry"> <p>Beskrivning </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Generering av leads </p> </td> 
   <td colname="col2"> <p> <a href="/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md"   > Konvertering </a> </p> </td> 
   <td colname="col3"> <p>Här kan du överföra information om resultatet av leads för varje lead som genereras på din webbplats, inklusive faktiska intäkter som genereras. </p> <p>När intäkterna har tilldelats till lead-ID:n kan ni identifiera era mest lönsamma kampanjer och kampanjer. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Online-offert </p> </td> 
   <td colname="col2"> <p> <a href="/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md"   > Konvertering </a> </p> </td> 
   <td colname="col3"> <p>Här kan du överföra information om resultatet av leads för varje lead som genereras på din webbplats, inklusive faktiska intäkter som genereras. </p> <p>När intäkterna har tilldelats till lead-ID:n kan ni identifiera era mest lönsamma kampanjer och kampanjer. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Data för callcenter </p> </td> 
   <td colname="col2"> <p> <a href="/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md"   > Konvertering </a> </p> </td> 
   <td colname="col3"> <p>Gör att du kan överföra kundtjänsttransaktioner så att du kan identifiera taktiker (kampanjer, kampanjer och så vidare). som får kunderna att ringa. </p> </td> 
  </tr> 
 </tbody> 
</table>
