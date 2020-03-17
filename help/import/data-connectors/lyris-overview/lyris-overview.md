---
description: Beskriver de marknadsföringseffektiviteter som uppnås genom integreringen.
title: Lyris Data Connector for Adobe Analytics
uuid: db213865-1296-4a93-a0a2-781c026b2be5
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Lyris Data Connector for Adobe Analytics{#lyris-data-connector-for-adobe-analytics}

Beskriver de marknadsföringseffektiviteter som uppnås genom integreringen.

E-postintegreringen med Adobe® Data Connectors™ kombinerar beteendeinformation från Adobe Analytics med e-postmarknadsföring i Lyris för att omdefiniera framgångsmått och inrikta er på målgrupper med mer relevanta meddelanden.

Leverans av relevanta e-postmeddelanden till dessa marknadssegment kan leda till helt nya intäktsmöjligheter och leda till ökad konvertering och ökade intäkter bland nya och befintliga e-postkampanjer. Att leverera relevanta e-postmeddelanden baserade på produkter som visats under ett besök eller produkter som lämnats i en övergiven kundvagn har till exempel visat sig ha en dramatisk inverkan på intäkterna, med minimal inverkan på kostnaden eftersom det bara är att dra nytta av besökare som sajten redan får.

Den ökade marknadsföringseffektiviteten är en av de största fördelarna med att integrera Adobe Analytics med Lyris. Dessutom synkroniserar den här integreringen automatiskt e-poststatistik med Adobe Analytics-data så ofta som en timme för rapporter med slutna slingor.

## Viktiga fördelar och funktioner{#key-benefits-and-features}

Beskriver de viktigaste fördelarna med att integrera Lyris och Adobe Marketing Reports och Analytics.

Integreringen av Lyris och Adobe Analytics ger följande viktiga fördelar:

* Samla marknadsförings- och analysdata via e-post i ett enda rapporteringsgränssnitt
* Optimera e-postkampanjer genom konvertering och bidrag till intäkter och webbplatsens framgång
* Återmarknadsföring till viktiga besökare och marknadssegment baserat på dynamiska marknadsföringssegment

### Dynamiska marknadsföringssegment

E-postintegreringen stöder dynamiska marknadsföringssegment som hjälper er att utveckla verksamheten. Den här integreringen innehåller följande marknadsföringssegment:

* **Profil** för kundvagnsöverlämning: Hjälp besökarna att konvertera till kunder med finjusterade kampanjer som är särskilt utformade för dem som tvekar att slutföra kundvagnen
* **Inköpsprofiler**: Öka antalet upprepade order och det genomsnittliga ordervärdet genom kampanjer riktade mot besökares inköpsmönster
* **Beteendeprofil** för produkt-/innehållsvy: Nå potentiella kunder genom marknadsföringssegment baserat på produktvisningar och profiler för innehållsåtkomst
* Kunderna kan också skapa och schemalägga **anpassade ommarknadsföringssegment** som är specifika för användarnas behov.

## Krav för integrering{#integration-prerequisites}

Beskriver förutsättningarna för en lyckad integrering.

Innan du aktiverar den här integreringen ska du granska följande objekt mot dina distributioner av Adobe Analytics och e-postprogrammet.

Detta garanterar att bästa praxis och förutsättningar finns på plats före aktiveringen, vilket ger en optimal och lyckad integrering.

### Krav för Adobe Analytics {#section-ddb9d4f3b283438ea33788f47f35e69a}

* **Report-Suite-specifik**: Observera att den här integreringen är specifik för rapportsviten. Kontrollera att du har valt önskat rapportpaket innan du aktiverar integreringen
* **Tillgängliga och konfigurerade analysvariabler**: Den här integreringen kräver anpassade händelser och anpassade eVars-variabler, samt eventuellt ytterligare händelser och ytterligare eVars-variabler.

* **Auktoriserat ombud**: Observera att aktiveringen av integreringen kan medföra att ditt företag debiteras i enlighet med ditt serviceavtal med Adobe, Inc. eller ditt serviceavtal med någon av Adobes betrodda partners, beroende på vad som är tillämpligt. Genom att aktivera integreringen intygar du härmed att du är en behörig representant för ditt företag; och som sådan går ditt företag med på att betala eventuella avgifter som anges i det serviceavtal som beskrivs ovan.
* **Adobe Analytics-datalager**: Den här integreringen kräver att datalagret i Adobe Analytics är aktiverat för att generera segment för återmarknadsföring. Om du inte har aktiverat datalager kontaktar du Adobe för mer information.
* **Mottagar-ID**: Integreringen kräver att vi hämtar och lagrar ett &quot;Visitor ID&quot; i en Analytics-variabel (eVar). Besökar-ID (kallas ofta för &quot;Mottagar-ID&quot;) är en kodad eller numerisk representation av en e-postadress från Lyris-systemet. Detta&quot;Mottagar-ID&quot; är kopplat till besökarbeteende längre fram i kedjan på webbplatsen (kundvagnsöverläggningar, inköp osv.) som återförs till Lyris-systemet och kan utnyttjas för återmarknadsföring. Som en del av konfigurationsprocessen måste du identifiera en eVar för detta när du uppmanas till det av guiden.
* **Extern spårning**: Om du för närvarande inte följer den bästa metoden att aktivera extern spårning för varje e-postkampanj som du skickar måste du göra det för att integreringen ska lyckas. Se avsnittet Lyris nedan för mer information
* **Integritetsefterlevnad**: Genom att aktivera spårning av mottagare eller besökar-ID kan den här funktionen spåra personligt identifierbar information om webbplatsens besökare. Detta påverkar integriteten och kräver att organisationen implementerar lämpliga procedurer, t.ex. meddelar besökarna på webbplatsen och ger dem sitt samtycke.

### Krav för Lyris EmailLabs {#section-84abae9401224a3699fed861f715ebde}

* **Giltigt Lyris-konto**: För att kunna använda den här integreringen av Data Connector måste du ha ett giltigt Lyris-konto.
* **Kontoinformation**: Du behöver följande information om ditt Lyris-konto under den här integrationsinställningen:

   * *Lyris API-nyckel*: Används för datapopulation
   * *Frågesträngsparametrar*: Dessa läggs till i landningssidans URL för meddelande-ID och mottagar-ID (besökar-ID).
   * *Lyris Server/URL*: Servervärdet som du använder i Lyris-systemet
   * *ID* för borisplats: Detta är också känt som&quot;Kund-ID&quot;, det unika värdet för din instans av Lyris HQ. Det här finns under Kundinformation i avsnittet Kontostartsida i EmailLabs.

## Konfigurera Adobe Analytics-variabler för Lyris{#configure-adobe-analytics-variables-for-lyris}

Beskriver de eVars och Events som ska reserveras för varje implementering av rapportsviten.

Den här integreringen kräver att minst 2 eVars reserveras för varje implementering av rapportsviten. Förutom dessa eVars kan ett antal händelser reserveras beroende på vilka Lyris-data du vill se i Analytics. Dessa eVars och händelser beskrivs i tabellen nedan:

<table id="table_43E32344E9E54FED8491F28047249329"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Variabeltyp </th> 
   <th colname="col2" class="entry"> Variabelnamn </th> 
   <th colname="col3" class="entry"> Så här används variabeln </th> 
   <th colname="col4" class="entry"> Inställningar </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> eVar </td> 
   <td colname="col2"> Meddelande-ID </td> 
   <td colname="col3"> Så här fångar du den enskilda e-postmeddelandekampanjen </td> 
   <td colname="col4"> <p>Status: Aktiverad </p> <p>Allokering: Senaste </p> <p>Förfaller efter: "Affärsbeslut" </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> eVar </td> 
   <td colname="col2"> E-postmottagar-ID </td> 
   <td colname="col3"> För att samla in den anonyma identifieringen för den kund som klickade på e-postkampanjen </td> 
   <td colname="col4"> <p>Status: Aktiverad </p> <p>Allokering: Senaste </p> <p>Förfaller efter: "Affärsbeslut" </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Händelse </td> 
   <td colname="col2"> Lyris - skickade e-postmeddelanden </td> 
   <td colname="col3"> Till butiksnr av mejl som skickats från Lyris </td> 
   <td colname="col4">Typ: Numeriskt <p>Deltagande: Aktiverad </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Händelse </td> 
   <td colname="col2"> Lyris - öppna e-postmeddelanden </td> 
   <td colname="col3"> Till butiksnr av e-postmeddelanden som öppnats </td> 
   <td colname="col4">Typ: Numeriskt <p>Deltagande: Aktiverad </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Händelse </td> 
   <td colname="col2"> Lyris - unika e-postmeddelanden öppnade </td> 
   <td colname="col3"> Till butiksnr av unika e-postmeddelanden som öppnats </td> 
   <td colname="col4">Typ: Numeriskt <p>Deltagande: Aktiverad </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Händelse </td> 
   <td colname="col2"> Lyris - skicka e-postklick </td> 
   <td colname="col3"> Till butiksnr antal gånger som någon klickar på ett e-postmeddelande </td> 
   <td colname="col4">Typ: Numeriskt <p>Deltagande: Aktiverad </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Händelse </td> 
   <td colname="col2"> Lyris - E-poststudsar </td> 
   <td colname="col3"> För lagring av nej. av e-postmeddelanden som studsade </td> 
   <td colname="col4">Typ: Numeriskt <p>Deltagande: Aktiverad </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Händelse </td> 
   <td colname="col2"> Lyris - Avbeställ e-post </td> 
   <td colname="col3"> För lagring av nej. av e-postprenumerationer som har inaktiverats </td> 
   <td colname="col4">Typ: Numeriskt <p>Deltagande: Aktiverad </p> </td> 
  </tr> 
 </tbody> 
</table>
