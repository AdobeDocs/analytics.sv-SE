---
description: Använd bidragsanalys för att identifiera statistiska avvikelser och korrelationer i data.
title: Översikt över bidragsanalys
uuid: 2bd295b0-c5ce-4443-86af-024efd20c021
feature: AI Tools
role: Business Practitioner, Administrator
translation-type: tm+mt
source-git-commit: 894ee7a8f761f7aa2590e06708be82e7ecfa3f6d
workflow-type: tm+mt
source-wordcount: '1161'
ht-degree: 6%

---


# Översikt över bidragsanalys

Contribute Analysis avslöjar dolda mönster i era data för att förklara statistiska avvikelser och identifiera korrelationer bakom oväntade kundaktiviteter, obundna värden och plötsliga toppar eller dalar för valda mätvärden över konvergerande målgruppssegment.

Något hände. Varför? Din rapport om avvikelseidentifiering visar en ovanlig topp i beställningarna och du vill veta varför. Vad hände med det vanliga? Vem svarar på vilken kampanj eller hänskjutning? Var det något som blev viralt? Vilka faktorer har bidragit till avvikelsen? Och kanske viktigast: Hur kan jag samla in viktig information om min kund och upprepa den här prestandan? (Om en nedgång i ett mätvärde eller ökning av ett negativt mätvärde inträffar, hur kan jag undvika det i framtiden?)

Med bidragsanalys kan ni omedelbart utvärdera era data för att få svar på varför en avvikelse inträffade. Den bryter ned bidragen till en avvikelse på några sekunder i vad som tidigare tog veckor, ger mönster för målgruppssegment och hjälper er att utveckla en berättelse för kundinteraktioner. Ni kan använda Contribute Analysis strategiskt för att identifiera och samla in meningsfulla associationer för att utveckla nya målgruppssegment, eller använda den taktiskt för att identifiera obunden eller bedräglig aktivitet som utlöser en varning.

[Analysidentifiering ](/help/analyze/analysis-workspace/virtual-analyst/c-anomaly-detection/anomaly-detection.md) identifierar datapisar och extrema statistiska dips baserat på valda mätvärden och valda målgruppssegment. Den sätter en historisk standard baserat på en utbildningsperiod och kartlägger sedan extrema förskjutningar som korrelerar med specifika händelser. Den kan rapportera en kraftig ökning av ett positivt ordermått eller en ökning av ett negativt Bounces-mått, eller en ökning av båda, och samla in statistiskt relevanta datapunkter som ska utvärderas med Contribute Analysis. När en statistisk avvikelse har identifierats kan ni med hjälp av bidragsanalys gå igenom och utvärdera relevanta marknadsförings- och kampanjvariabler för alla avvikande datapunkter. Den kör avancerade algoritmer och maskininlärningsprocesser för att utvärdera associationer som bidragit till en betydande topp eller dip. Beräkningarna visas sedan i interaktiva visualiseringar som utformats för att ge dig varierande perspektiv för att hjälpa dig att svara på varför något hände och vad du ska göra åt det.

Med bidragsanalys kan ni ta fram en berättelse som beskriver varför en avvikelse inträffade och hur ni ska reagera på den, samla in relevanta mätvärden och identifiera dolda punkter som ger er en övergripande anledning till målgruppsinteraktioner och trender kring kundernas intressen. Ibland är en avvikelse lätt att se och korrigera, som en felaktig order på 2 000 kajaker. Ibland är det komplicerat, till exempel att identifiera en ny trend under en tidsperiod i en region som bara reagerar på en viss riktad kampanj. Genom att samla artiklar för olika mått och deras associationer får ni en övergripande uppfattning om hur er målgrupp interagerar och bidrar till att skapa kontext för avvikande datapunkter.

Här är några exempel:

* Identifiera potentialen för återmarknadsföring genom att övervaka förändringar i produktefterfrågan.
* Förbättra kundupplevelsen genom att reagera på specifika målgruppsintressen.
* Identifiera bedrägliga order tidigt som en rapport utanför gränserna.
* Protect är du inte intresserad av företagsinformation genom att identifiera högt antal användare och nedladdningar.
* Övervaka åtgärder som att rapportera saknade javascript-taggar.

Efter en omfattande analys av en avvikelse genereras en bidragssammanfattning för de vanligaste artiklarna ordnade efter totalförekomster och postens procentandel av bidragande värden. Med ett normaliserat bidragsresultat kan du enkelt jämföra, kontrastera och associera med andra viktiga dimensionsobjekt.

## Tokens för bidragsanalys - översikt {#section_3EF8D2BBCE6E4C309D753BCF04A453D0}

>[!IMPORTANT]
>
>Contribute Analysis har tagits bort från funktionerna Rapporter och analyser och är nu bara tillgängligt via Analysis Workspace.

Alla kunder med ett Contribute Analysis-berättigande kan köra en fullständig Contribute Analysis ett begränsat antal gånger i månaden i Analysis Workspace. **Detta utesluter**-kunder (SiteCatalyst 15), Analytics Foundation-kunder och Analytics Select-kunder som inte får någon bidragsanalys alls.

Antalet körningar per företag begränsas av månatliga tokens som beviljas baserat på den Adobe Analytics-produkt som ditt företag har köpt. Detta inkluderar möjligheten att begränsa åtkomst till bidragsanalys för att undvika tokenmissbruk.

## Vanliga frågor {#section_11D0431AD2014B96AB9561CA66A367CE}

<table id="table_357775E5058644099E26B15A6790E8AF"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Fråga </th> 
   <th colname="col2" class="entry"> Svar </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>Varför har Adobe introducerat tokens?  </b> </p> </td> 
   <td colname="col2"> <p>Contribute Analysis har varit en av de mest intressanta funktionerna i Adobe Analytics. Om du får ett litet antal"fullständiga" körningar per månad (i stället för bara tre dimensioner för vissa Analytics-produkter) kan du bättre se vad en obegränsad, fullständig bidragsanalys kan göra för dig. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Hur fungerar tokenering i bidragsanalys? Kostar det en token att läsa in ett projekt med en befintlig bidragsanalys, eller bara när ett helt nytt projekt körs?</b> </p> </td> 
   <td colname="col2"> <p>Varje inloggningsföretag (inte varje användare) får ett visst antal tokens per månad, vilket gör att du kan köra en"fullständig" bidragsanalys i Analysis Workspace. </p> <p>Varje gång du genererar en ny bidragsanalys betalar du en token. Att läsa in projekt med bidragsanalyser som körs i förväg kostar ingen token. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Gäller tokens för bidragsanalys i rapporter och analyser?</b> </p> </td> 
   <td colname="col2"> <p>Nej. Bidragsanalys erbjuds inte längre i rapporter och analyser från och med versionen från april 2018. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Vad kan vi göra om mitt företag har slut på tokens och vill köra ytterligare bidragsanalyser?</b> </p> </td> 
   <td colname="col2"> <p>Du kan uppgradera till en annan Adobe Analytics-produkt, till exempel från Standard (2 tokens/månad) till Ultimate (20 tokens/månad). Du kan inte köpa fler tokens - du måste uppgradera inom det befintliga paketeringsramverket. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Hur begränsar jag åtkomsten till bidragsanalys?</b> </p> </td> 
   <td colname="col2"> <p>Som standard har bara administratörer tillgång till att köra Contribute Analyses, men administratörer kan bevilja åtkomst till andra användare genom att skapa en behörighetsgrupp i Admin Console <a href="https://docs.adobe.com/content/help/sv-SE/core-services/interface/manage-users-and-products/admin-getting-started.html"  > </a>. Du bör endast ge tillstånd att använda bidragsanalys till användare som har en legitim anledning att använda den och som är betrodda att inte missbruka sin åtkomst. </p> <p>Behörigheten kallas för"bidragsanalys" under <span class="ignoretag"><span class="uicontrol"> Analytics</span> &gt; <span class="uicontrol"> Admin</span> &gt; <span class="uicontrol"> Användarhantering</span> &gt; <span class="uicontrol"> Redigera grupper</span> &gt; <span class="uicontrol"> Redigera all rapportåtkomst</span> &gt; <span class="uicontrol"> Anpassa rapportverktyg</span> &gt; <span class="uicontrol"> Verktyg och rapporter</span></span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Hur vet jag hur många tokens mitt företag har rätt till per månad och hur många vi har använt under den aktuella månaden?</b> </p> </td> 
   <td colname="col2"> <p>Gå till <span class="ignoretag"><span class="uicontrol"> Admin</span> &gt; <span class="uicontrol"> Företagsinställningar</span> &gt; <span class="uicontrol"> Visa åtkomstnivåer för funktioner</span></span>. Det finns två nya objekt på den här sidan: </p> <p><img placement="break"  src="assets/ca_access_level.png" id="image_16012FE1162C485EA768D175F43D7563" width="500px" /> </p> </td> 
  </tr> 
 </tbody> 
</table>


## Anomaldetekterings- och bidragsanalysberättiganden {#section_9278D58F21A840AA9B1ED1BD07A1EF0A}

Nedan finns en lista med detaljerade berättiganden för avvikelseidentifiering och bidragsanalys i Analysis Workspace.

>[!IMPORTANT]
>
>Avvikelseidentifiering och bidragsanalys har tagits bort från funktionerna för rapporter och analyser och är nu bara tillgängliga via Analysis Workspace. Tänk på att kunder som använder Adobe Analytics Select och Adobe Analytics Foundation bara har tillgång till avvikelseidentifiering på dagsnivå i Workspace.

<table id="table_5C9B7E4AE82640B5A913519E576889B5"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Adobe Analytics Entitlement </th> 
   <th colname="col2" class="entry"> Avvikelseidentifiering </th> 
   <th colname="col3" class="entry"> Bidragsanalys </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Foundation </p> </td> 
   <td colname="col2"> <p>Endast daglig granularitet </p> </td> 
   <td colname="col3" colsep="1"> <p>Inga variabler </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><a href="https://www.adobe.com/data-analytics-cloud/analytics/select.html?promoid=B4XQ3X7G&amp;mv=other"  > Välj  </a> </p> </td> 
   <td colname="col2"> <p>Endast daglig granularitet </p> </td> 
   <td colname="col3"> <p>Inga variabler </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><a href="https://www.adobe.com/data-analytics-cloud/analytics/prime.html?promoid=91BF51TR&amp;mv=other"  > Prime  </a> </p> </td> 
   <td colname="col2"> <p>Ja </p> </td> 
   <td colname="col3"> <p>10 tokens per månad </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><a href="https://www.adobe.com/data-analytics-cloud/analytics/ultimate.html?promoid=8N4B5F1V&amp;mv=other"  > Ultimate</a> </p> </td> 
   <td colname="col2"> <p>Ja </p> </td> 
   <td colname="col3"> <p>20 tokens per månad </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>+Predictive Workbench </p> </td> 
   <td colname="col2"> <p>Ja </p> </td> 
   <td colname="col3"> <p>Obegränsat antal token </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Standard </p> 
    <ul id="ul_73D52020793B44868C9CE0F90893075D"> 
     <li id="li_21EE0871C87E43C8B781219B2BA0FA74">Adobe Analytics Core </li> 
     <li id="li_AB3593200F33439BAEE8FEB13CAE57F4">Adobe Analytics OD </li> 
     <li id="li_2B7D625519BC4A4CB598C95F15D3029B">Adobe Analytics MA </li> 
    </ul> </td> 
   <td colname="col2"> <p>Ja </p> </td> 
   <td colname="col3"> <p>2 variabler per månad </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Premium (360, Attribution) </p> </td> 
   <td colname="col2"> <p>Ja </p> </td> 
   <td colname="col3"> <p>2 variabler per månad </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Premium (fullständig, <a href="https://www.adobe.com/data-analytics-cloud/analytics/predictive-intelligence.html"  > Predictive Intelligence</a>) </p> </td> 
   <td colname="col2"> <p>Ja </p> </td> 
   <td colname="col3"> <p>Obegränsat antal token </p> </td> 
  </tr> 
 </tbody> 
</table>
