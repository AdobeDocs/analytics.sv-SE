---
description: Ni kan visa och analysera dataavvikelser i sitt sammanhang, inom Analysis Workspace.
title: Översikt över avvikelseidentifiering
feature: Anomaly Detection
role: User, Admin
exl-id: b1625206-c774-40ef-9d92-25ee8ff1478d
source-git-commit: d7a6867796f97f8a14cd8a3cfad115923b329c7c
workflow-type: tm+mt
source-wordcount: '1276'
ht-degree: 1%

---

# Översikt över avvikelseidentifiering

Ni kan visa och analysera dataavvikelser i sitt sammanhang inom Analysis Workspace. Bidragsanalys fungerar tillsammans med avvikelseidentifiering för att hjälpa till att identifiera vad som bidragit till avvikelsen.


>[!BEGINSHADEBOX]

Se ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Analysidentifiering](https://video.tv.adobe.com/v/25444?quality=12&learn=on){target="_blank"} för en demonstrationsvideo.

>[!ENDSHADEBOX]

>[!IMPORTANT]
>
>Adobe Analytics Select- och Adobe Analytics Foundation-kunder har endast tillgång till &quot;daglig granularitet&quot; för avvikelseidentifiering i Workspace. Mer information finns i [Berättiganden för avvikelseidentifiering och bidragsanalys](#anomaly-detection-and-contribution-analysis-entitlements).

## Avvikelseidentifiering

Analysidentifiering är en statistisk metod för att fastställa hur ett givet mätresultat har ändrats i förhållande till tidigare data.

Anomaly Detection gör det möjligt att skilja &quot;sanna signaler&quot; från &quot;brus&quot; och sedan identifiera potentiella faktorer som bidragit till dessa signaler eller avvikelser. Med andra ord kan du identifiera vilka statistiska fluktuationer som är viktiga och vilka som inte gör det. Sedan kan du identifiera roten till en sann avvikelse. Dessutom kan du få tillförlitliga KPI-prognoser.

Exempel på avvikelser du kan undersöka är:

* Drastiska droppar i genomsnittligt ordervärde
* Inträffar i order med låg intäkt
* Taggar eller droppar i testregistreringar
* Droppar i landningssidvyer
* Inslag i videobufferthändelser
* Taggar i låga videobithastigheter

Både avvikelseidentifiering och [bidragsanalys](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/virtual-analyst/anomaly-detection/anomaly-detection.html?lang=sv-SE) är centrala arbetsflöden i Analysis Workspace. Du kan köra Contribute Analysis mot eventuella avvikelser per dag och bädda in resultatet i ditt Analysis Workspace-projekt.

Analysis Workspace avvikelseavkänningsalgoritm innehåller

* Stöd för kornighet varje timme, vecka och månad, utöver den befintliga kornigheten.
* Kännedom om säsongsvaraktighet (t.ex. &quot;Black Friday&quot;) och semester.

## Bidragsanalys

Contribute Analysis avslöjar dolda mönster i era data för att förklara statistiska avvikelser och identifiera korrelationer bakom oväntade kundaktiviteter, obundna värden och plötsliga toppar eller dalar för valda mätvärden över konvergerande målgruppssegment.


>[!BEGINSHADEBOX]

En demonstrationsvideo finns i ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Contribute analysis](https://video.tv.adobe.com/v/25443?quality=12&learn=on){target="_blank"} .

>[!ENDSHADEBOX]


Något hände. Varför? Din rapport om avvikelseidentifiering visar en ovanlig topp i beställningarna och du vill veta varför. Vad hände med det vanliga? Vem svarar på vilken kampanj eller hänskjutning? Var det något som blev viralt? Vilka faktorer har bidragit till avvikelsen? Och kanske viktigast av allt: Hur kan jag samla in viktig information om min kund och upprepa det här resultatet? (Om en nedgång i ett mätvärde eller uppgång i ett negativt mätvärde inträffar, hur kan jag undvika det i framtiden?)

Med bidragsanalys kan ni omedelbart utvärdera era data för att få svar på varför en avvikelse inträffade. Den bryter ned bidragen till en avvikelse på några sekunder i vad som tidigare tog veckor, ger mönster för målgruppssegment och hjälper er att utveckla en berättelse för kundinteraktioner. Ni kan använda Contribute Analysis strategiskt för att identifiera och samla in meningsfulla associationer för att utveckla nya målgruppssegment, eller använda den taktiskt för att identifiera obunden eller bedräglig aktivitet som utlöser en varning.

[Anomaly Detection](#anomaly-detection) identifierar datatoppar och extrema statistiska dips baserat på valda mätvärden och valda målgruppssegment. Den sätter en historisk standard baserat på en utbildningsperiod och kartlägger sedan extrema förskjutningar som korrelerar med specifika händelser. Den kan rapportera en kraftig ökning av ett positivt ordermått eller en ökning av ett negativt Bounces-mått, eller en ökning av båda, och samla in statistiskt relevanta datapunkter som ska utvärderas med hjälp av bidragsanalys. När en statistisk avvikelse har identifierats kan ni med hjälp av bidragsanalys gå igenom och utvärdera relevanta marknadsförings- och kampanjvariabler för alla avvikande datapunkter. Den kör avancerade algoritmer och maskininlärningsprocesser för att utvärdera associationer som bidragit till en betydande topp eller dip. Beräkningarna visas sedan i interaktiva visualiseringar som utformats för att ge dig varierande perspektiv för att hjälpa dig att svara på varför något hände och vad du ska göra åt det.

Med bidragsanalys kan ni ta fram en berättelse som beskriver varför en avvikelse inträffade och hur ni ska reagera på den, samla in relevanta mätvärden och identifiera dolda punkter som ger er en övergripande anledning till målgruppsinteraktioner och trender kring kundernas intressen. Ibland är en avvikelse lätt att se och korrigera, som en felaktig order på 2 000 kajaker. Ibland är det komplicerat, till exempel att identifiera en ny trend under en tidsperiod i en region som bara reagerar på en viss riktad kampanj. Genom att samla artiklar för olika mått och deras associationer får ni en övergripande uppfattning om hur er målgrupp interagerar och bidrar till att skapa kontext för avvikande datapunkter.

Här är några exempel:

* Identifiera potentialen för återmarknadsföring genom att övervaka förändringar i produktefterfrågan.
* Förbättra kundupplevelsen genom att reagera på specifika målgruppsintressen.
* Identifiera bedrägliga order tidigt som en rapport utanför ramarna.
* Protect är du inte intresserad av företagsinformation genom att identifiera högt antal användare och nedladdningar.
* Övervaka åtgärder som att rapportera saknade javascript-taggar.

Efter en omfattande analys av en avvikelse genereras en bidragssammanfattning för de vanligaste artiklarna ordnade efter totalförekomster och postens procentandel av bidragande värden. Med ett normaliserat bidragsresultat kan du enkelt jämföra, kontrastera och associera med andra viktiga dimensionsobjekt.

## Tokens för bidragsanalys - översikt {#section_3EF8D2BBCE6E4C309D753BCF04A453D0}

Alla kunder med ett Contribute Analysis-berättigande kan köra en fullständig Contribute Analysis ett begränsat antal gånger i månaden i Analysis Workspace. **exkluderar** SiteCatalyst 15-kunder, Analytics Foundation-kunder och Analytics Select-kunder, som inte får någon bidragsanalys alls.

Antalet körningar per företag begränsas av månatliga tokens som beviljas baserat på den Adobe Analytics-produkt som ditt företag har köpt. Detta inkluderar möjligheten att begränsa åtkomst till bidragsanalys för att undvika tokenmissbruk.

## Frågor och svar {#section_11D0431AD2014B96AB9561CA66A367CE}

| Fråga | Svar |
| --- | --- |
| Varför har Adobe introducerat tokens? | Contribute Analysis har varit en av de viktigaste funktionerna i Adobe Analytics. Om du får ett litet antal&quot;fullständiga&quot; körningar per månad (i stället för bara tre dimensioner för vissa Analytics-produkter) kan du bättre se vad en obegränsad, fullständig bidragsanalys kan göra för dig. |
| Hur fungerar tokenering i bidragsanalys? Kostar det en token att läsa in ett projekt med en befintlig bidragsanalys, eller bara när ett helt nytt projekt körs? | Varje inloggningsföretag (inte varje användare) får ett visst antal tokens per månad, vilket gör att du kan köra en&quot;fullständig&quot; bidragsanalys i Analysis Workspace.  Varje gång du genererar en ny bidragsanalys betalar du en token. Att läsa in projekt med bidragsanalyser som körs i förväg kostar ingen token. |
| Vad kan vi göra om mitt företag har slut på tokens och vill köra ytterligare bidragsanalyser? | Du kan uppgradera till en annan Adobe Analytics-produkt, till exempel från Standard (2 tokens/månad) till Ultimate (20 tokens/månad). Du kan inte köpa fler tokens - du måste uppgradera inom det befintliga paketeringsramverket. |
| Hur begränsar jag åtkomsten till bidragsanalys? | Som standard har bara administratörer tillgång till att köra Contribute Analyses. Administratörer kan dock ge andra användare åtkomst genom att skapa en behörighetsgrupp i [Adobe Admin Console](https://experienceleague.adobe.com/docs/analytics/admin/admin-console/home.html?lang=sv-SE) . Du bör endast ge tillstånd att använda Contribute Analysis till användare som har en legitim anledning att använda den och som är betrodda att inte missbruka sin åtkomst. Behörigheten anropas [!UICONTROL Contribution Analysis] under [!UICONTROL Report Suite Tools]. [Läs mer](https://experienceleague.adobe.com/docs/analytics/admin/admin-console/permissions/report-suite-tools.html?lang=sv-SE) |
| Hur vet jag hur många tokens mitt företag har rätt till per månad och hur många vi har använt under den aktuella månaden? | Gå till [!UICONTROL Admin] > [!UICONTROL All admin] >[!UICONTROL Company settings Home] >[!UICONTROL View Feature Access Levels]. Titta under<ul><li>Bidragsanalys: Antal månatliga användningstoken</li><li>Bidragsanalys: Antal användningstoken som använts den här månaden</li></ul> |

## Anomaldetekterings- och bidragsanalysrättigheter {#section_9278D58F21A840AA9B1ED1BD07A1EF0A}

Nedan finns en lista med detaljerade berättiganden för avvikelseidentifiering och bidragsanalys i Analysis Workspace.

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
   <td colname="col1"> <p><a href="https://www.adobe.com/data-analytics-cloud/analytics/select.html?promoid=B4XQ3X7G&amp;mv=other"  > Välj </a> </p> </td> 
   <td colname="col2"> <p>Endast daglig granularitet </p> </td> 
   <td colname="col3"> <p>Inga variabler </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><a href="https://www.adobe.com/data-analytics-cloud/analytics/prime.html?promoid=91BF51TR&amp;mv=other"  > Prime </a> </p> </td> 
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
     <li id="li_AB3593200F33439BAEE8FEB13CAE57F4">ADOBE ANALYTICS OD </li> 
     <li id="li_2B7D625519BC4A4CB598C95F15D3029B">ADOBE ANALYTICS MA </li> 
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
