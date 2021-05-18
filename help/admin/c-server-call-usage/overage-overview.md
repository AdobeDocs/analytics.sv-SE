---
description: Översikt över Adobe Analytics serversamtalsfunktion.
title: Översikt över användning av serversamtal
uuid: 6e014364-efc1-4769-a0b5-cf105c0ed9b1
exl-id: d3d64f1e-f01b-4b9e-9aee-c14e574fc40b
source-git-commit: d198e8ef0ec8415a4a555d3c385823baad6104fe
workflow-type: tm+mt
source-wordcount: '1029'
ht-degree: 1%

---

# Översikt över användning av serversamtal

## Varför övervaka och varna för användning av serversamtal? {#section_060C29BF1D00444B85892AD1FCF55290}

Adobe Analytics Server Call Usage behandlar dina förfrågningar om genomskinlighet både i webbläsare och i mobilserverns anropsdata. Du får tillgång till

* En kontrollpanel för användning av serversamtal som spårar dina förbrukningsdata för serversamtal och jämför dem med din avtalsgräns. (**[!UICONTROL Analytics > Admin > Server Call Usage]**)
* En varningstyp för användning av serveranrop i varningsbyggaren som gör att du kan konfigurera varningar för att förhindra överskjutande delar (**[!UICONTROL Analytics > Components >Alerts]**)

De viktigaste fördelarna med användning av serversamtal är:

* **Synlighet** för förbrukning och bindningsuppgifter för serversamtal, inklusive mobilförbrukning i förhållande till den avtalsenliga gränsen för hur många serversamtal som används.
* **Varningar** för att meddela dig om risken eller förekomsten av en övertäckning och förbereda för/påverka möjligheten att ådra sig överskjutande delar.

Tidigare kunde du få åtkomst till serversamtalsförbrukningsdata varje månad under **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Billing]**, men dessa data uppdaterades bara 6 dagar efter att faktureringen hade stängts för den månaden. Uppgifterna inkluderade inte heller mobilförbrukning. Den här funktionen ersätter även den aktuella **[!UICONTROL Billing Information]**-rapporten under **[!UICONTROL Analytics]** > **[!UICONTROL Reports]**.

## Förutsättningar {#section_49AE590FFC7C4E8A83C640C4AAA581AA}

* **Behörigheter:** För att få åtkomst till instrumentpanelen för användning av serversamtal och varningsbyggaren/hanteraren måste du vara en Adobe Analytics-administratör.
* **behörigheter:** Administratörer kan ge åtkomst till icke-administratörer: behörigheten anropas  **[!UICONTROL Server Call Usage]**. Se [Användarbehörighet för serversamtal](/help/admin/c-server-call-usage/overage-overview.md#section_FCC58EB635954A32990D4E67B52B4369).

## Viktig terminologi {#section_CBA348A039F34563B097CD8890AB358D}

Här är en kort introduktion till viktig terminologi för användning av serversamtal:

<table id="table_4E97F85F13344A2C962FA4FA5A51642E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Term </th> 
   <th colname="col2" class="entry"> Definition </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Serversamtal </p> </td> 
   <td colname="col2"> <p>Ett serveranrop, även kallat "träff" eller "bildbegäran", är en instans där data skickas till Adobe-servrar för bearbetning. Den vanligaste typen av serveranrop är en sidvy. En sidvy inträffar när en besökare visar en sida på webbplatsen och ett serveranrop genereras till Adobe, där informationen samlas in, bearbetas och sedan inkluderas i rapportens statistik. </p> <p>Det finns andra typer av serveranrop, bland annat avslutslänkar och filhämtningar, där data skickas till Adobe för att bearbeta, men de registreras inte som en ny sidvy. Även"utelämnade" sidvyer (som inte ingår i dina rapporter med till exempel ett IP-adressintervall som du konfigurerar) är serversamtal eftersom de tas emot och behandlas av Adobe, men aldrig visas i dina rapporter. </p> <p><b>Primärt serversamtal</b>: Begäranden som tas emot direkt från besökarwebbläsare eller API:t för datainfogning. Innehåller primära träffar (sidvyer), primära anpassade händelser, primära nedladdningshändelser och primära avslutningshändelser. </p> <p><b>Sekundärt serversamtal</b>: Kopior av primära serveranrop som har skapats av flera Suite-taggar eller kopierats/flyttats av en VISTA-regel. Om ett sekundärt serveranrop har flyttats (inte kopierats) till en annan rapportserie via en VISTA-regel, dras de ackumulerade sekundära anropen från de primära serversamtalen. </p> <p><b>Mobilt primärserversamtal  </b> </p> <p>Begäranden som tagits emot direkt från någon av de mobila SDK:erna. Inkludera trackAction, trackState, trackApp Crashes, trackActionFromBackground, trackLocation, trackBeacon, trackPushMessageClickThrough, trackTimedActionBacklog, trackLifetimeValueIncrease.</p> <p><b>Mobilsamtal till sekundär server</b> </p> <p>Kopior av primära serveranrop som har skapats av flera Suite-taggar eller kopierats/flyttats av en VISTA-regel. Om ett sekundärt serveranrop har flyttats (inte kopierats) till en annan rapportserie via en VISTA-regel, dras de ackumulerade sekundära anropen från de primära serversamtalen. </p> <p>Obs!  Om ditt företag enligt avtal endast är berättigat till Mobile Server-samtal (primära eller sekundära) räknas både din webb- och mobilspecifika användning av ditt mobila åtagande. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Faktureringsföretag (fakturerings-ID) </p> </td> 
   <td colname="col2"> <p>Den juridiska person som faktureras för serversamtal. Till exempel adobe.com. Varje faktureringsföretag har ett fakturerings-ID som används för att unikt identifiera faktureringskunden. Ett fakturerings-ID kan vara knutet till flera Experience Cloud-organisationer. det inte alltid finns en 1:1-relation mellan en organisation och ett fakturerings-ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Inloggningsföretag </p> </td> 
   <td colname="col2"> <p>Ett faktureringsföretag kan ha <a href="https://helpx.adobe.com/analytics/kb/multiple-login-companies.html"> flera inloggningsföretag </a>. Ett inloggningsföretag är en samling rapportsviter som används av din organisation. Vissa organisationer har flera inloggningsföretag som gäller för olika delar av organisationen. Detta är särskilt användbart för stora organisationer som arbetar med olika affärsenheter där många rapporteringsprogram inte är tillämpliga för andra i företaget. </p> <p>Detta är ofta ett företags regionala dotterbolag. I det här exemplet visas inloggningsföretag och deras tillhörande rapportsviter: </p> 
    <ul id="ul_8C756C7972D04F5E89D6E32BB06D26C3"> 
     <li id="li_EA6257FED7854B6FAA071926D0F8A07C">adobe.global: RS1, RS2, RS3, RS4 </li> 
     <li id="li_3EAFB556849E4CCC9D96D5A3492EC898">adobe.us: RS1, RS2 </li> 
     <li id="li_572FFB3F4BF545BDB13102D82CE5E50C">adobe.in: RS3 </li> 
     <li id="li_B6ACBA35E18A427AA83F76BD38E502D7">adobe.de: RS4 </li> 
    </ul> <p>Obs!  Data om användning av serveranrop för <u>alla</u> rapportsviter inom ett faktureringsföretag är synliga för alla användare med rätt <a href="/help/admin/c-server-call-usage/overage-overview.md#section_FCC58EB635954A32990D4E67B52B4369"> behörighet</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Experience Cloud organisation </p> </td> 
   <td colname="col2"> <p>En organisation är den enhet som gör det möjligt för en administratör att konfigurera grupper och användare samt att styra enkel inloggning i Experience Cloud. Organisationen fungerar som ett inloggningsföretag som omfattar alla produkter och lösningar från Experience Cloud. </p> <p>Oftast är en organisation ditt företagsnamn. Ett företag kan dock ha många organisationer. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Serversamtalsåtagande </p> </td> 
   <td colname="col2"> <p>När ditt företag tecknar ett kontrakt med Adobe identifierar säljteamet på Adobe tillsammans med dig, kunden, typerna (primär, sekundär, Mobile Primary, Mobile Secondary) och det ungefärliga antalet serversamtal som du förväntar dig under avtalsperioden. Detta är din totala bindningstid för serversamtal. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Användningsperiod </p> </td> 
   <td colname="col2"> <p>För övervakning av användning av serversamtal delas detta totala åtagande för serversamtal upp i mindre användningsperioder (t.ex. 3 månader) för att underlätta jämförelser mellan år och år. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Kontraktsperiod </p> </td> 
   <td colname="col2"> <p>Kontraktsperioderna kan vara längre än flera år. Anta att ert företag har ett abonnemang på 6 miljoner samtal för en 3-årig kontraktstid. För att övervaka användningen av serversamtal kan denna treårsperiod delas upp i mindre användningsperioder för att underlätta jämförelser mellan år och år. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Användarbehörighet för serveranrop {#section_FCC58EB635954A32990D4E67B52B4369}

Behörighet för användning av serversamtal beviljas automatiskt till Analytics-administratörer. Det gör att användarna kan visa kontrollpanelen och skapa serversamtalsaviseringar. Administratörer kan välja att ge icke-administratörer denna behörighet.

>[!NOTE]
>
>Ditt företag kan välja vilka inloggningsföretag som har åtkomst till serversamtalsanvändning.

<table id="table_86256AD8B4554F369439A8FDF2F545E1"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Behörighetsnamn </th> 
   <th colname="col3" class="entry"> Bevilja behörighet om du är inloggad på Adobe Analytics (äldre inloggning) </th> 
   <th colname="col4" class="entry"> Bevilja behörighet om du är inloggad på Adobe Experience Cloud </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Användning av serversamtal </p> </td> 
   <td colname="col3"> 
    <ol id="ol_13A984328D264488B7045DC7521A5F55"> 
     <li id="li_ACDA518C7D184084AC1DFA7B38C67314">Logga in på Analytics via sc.omniture.com. </li> 
     <li id="li_066D90AB071941C3869EDAFCE981707A">Navigera till <span class="ignoretag"> <span class="uicontrol"> Admin </span> &gt; <span class="uicontrol"> Alla administratörer </span> &gt; <span class="uicontrol"> Användarhantering </span> &gt; <span class="uicontrol"> Grupper </span> &gt; <span class="uicontrol"> Redigera all rapportåtkomst </span> &gt; <span class="uicontrol"> Analysverktyg </span> &gt; &lt;a 13/&gt; Anpassa </span> &gt; <span class="uicontrol"> Användning av serversamtal </span> </span><span class="uicontrol"> </span></li> 
    </ol> </td> 
   <td colname="col4"> 
    <ol id="ol_518673ED323A4C5993A3B9F4BA09E405"> 
     <li id="li_56FF685A3B454ECEA5F16BB591A60034">Logga in på login.experienceCloud.adobe.com.</li> 
     <li id="li_FA1AE0F19DEF4AB2AA77B22CCA2995F9">Klicka på <span class="uicontrol"> Analytics </span>. </li> 
     <li id="li_22A4CBB84B5A451780873BBE67E6E6EF">Navigera till <span class="ignoretag"> <span class="uicontrol"> Products </span> &gt; <span class="uicontrol"> Product Profile </span> &gt; <span class="uicontrol"> Permissions </span> &gt; <span class="uicontrol"> Analytics Tools </span> &gt; <span class="uicontrol"> Server Call Usage </span> </span> </li> 
    </ol> </td> 
  </tr> 
 </tbody> 
</table>
