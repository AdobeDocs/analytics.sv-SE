---
description: Översikt över Adobe Analytics serversamtalsfunktion.
title: Översikt över användning av serversamtal
feature: Server Call Usage
exl-id: d3d64f1e-f01b-4b9e-9aee-c14e574fc40b
role: Admin
source-git-commit: 58e1d3025b455de7fa07037b3b0659330c8324c7
workflow-type: tm+mt
source-wordcount: '993'
ht-degree: 1%

---

# Serversamtalsanvändning

Adobe Analytics serveranrop åtgärdar dina krav på genomskinlighet, både vad gäller webbläsare och mobilserveranrop. Du får tillgång till

* En kontrollpanel för användning av serveranrop som spårar dina förbrukningsdata för serveranrop och jämför dem med din avtalsgräns. (I Adobe Analytics väljer du > [!UICONTROL **Admin**] > [!UICONTROL **Serversamtalsanvändning**])
* En varningstyp för användning av serveranrop i varningsverktyget som gör att du kan konfigurera varningar för att förhindra överage (I Adobe Analytics väljer du [!UICONTROL **Komponenter**] > [!UICONTROL **Varningar**])

De viktigaste fördelarna med användning av serversamtal är:

* **Synlighet** i förbruknings- och åtagandedata för serversamtal, inklusive mobilförbrukning i förhållande till den avtalsenliga gränsen för användning av serversamtal.
* **Varningar** om du vill meddela dig om risken eller förekomsten av en övertäckning och förbereda dig för/agera om risken för överskjutande delar kan uppstå.

## Förutsättningar {#section_49AE590FFC7C4E8A83C640C4AAA581AA}

* **Behörigheter:** Du måste vara en Adobe Analytics-administratör för att få åtkomst till kontrollpanelen för användning av serveranrop och varningsverktyget eller aviseringshanteraren.
* **Behörigheter:** Administratörer kan ge åtkomst till icke-administratörer: behörigheten kallas **[!UICONTROL Server call usage]**. Se [Användarbehörighet för serversamtal](#server-call-usage-permission).

## Viktig terminologi {#terminology}

Följande termer är viktiga när det gäller att förstå användningen av serversamtal:

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
   <td colname="col2"> <p>Ett serveranrop, även kallat "träff" eller "bildbegäran", är en instans där data skickas till Adobe-servrar för bearbetning. Den vanligaste typen av serveranrop är en sidvy. En sidvy inträffar när en besökare visar en sida på webbplatsen och ett serveranrop genereras till Adobe, där informationen samlas in, bearbetas och sedan inkluderas i rapportens statistik. </p> <p>Det finns andra typer av serveranrop, bland annat avslutslänkar och filhämtningar, där data skickas till Adobe för att bearbeta, men de registreras inte som en ny sidvy. Även"utelämnade" sidvyer (som inte ingår i dina rapporter med till exempel ett IP-adressintervall som du konfigurerar) är serversamtal eftersom de tas emot och behandlas av Adobe, men aldrig visas i dina rapporter. </p> <p><b>Primärt serveranrop</b>: Begäranden har tagits emot direkt från webbläsare för webbplatsbesökare eller API:t för datainmatning. Innehåller primära träffar (sidvyer), primära anpassade händelser, primära nedladdningshändelser och primära avslutningshändelser. </p> <p><b>Sekundärt serveranrop</b>: Kopior av primära serveranrop som har skapats av flera Suite-taggar eller kopierats/flyttats av en VISTA-regel. Om ett sekundärt serveranrop har flyttats (inte kopierats) till en annan rapportserie via en VISTA-regel, dras de ackumulerade sekundära anropen från de primära serversamtalen. </p> <p><b>Mobilt primärt serversamtal </b> </p> <p>Begäranden som tagits emot direkt från någon av de mobila SDK:erna. Inkludera trackAction, trackState, trackApp Crashes, trackActionFromBackground, trackLocation, trackBeacon, trackPushMessageClickThrough, trackTimedActionBacklog, trackLifetimeValueIncrease.</p> <p><b>Mobilt sekundärt serversamtal</b> </p> <p>Kopior av primära serveranrop som har skapats av flera Suite-taggar eller kopierats/flyttats av en VISTA-regel. Om ett sekundärt serveranrop har flyttats (inte kopierats) till en annan rapportserie via en VISTA-regel, dras de ackumulerade sekundära anropen från de primära serversamtalen. </p> <p>Obs! Om ditt företag enligt avtal endast är berättigat till Mobile Server-samtal (primär eller sekundär) räknas både din webb- och mobilspecifika användning av ditt mobila åtagande. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Faktureringsföretag (fakturerings-ID) </p> </td> 
   <td colname="col2"> <p>Den juridiska person som faktureras för serversamtal. Exempel: adobe.com. Varje faktureringsföretag har ett fakturerings-ID som används för att unikt identifiera faktureringskunden. Ett fakturerings-ID kan vara knutet till flera Experience Cloud Orgs. Det finns inte alltid en 1:1-relation mellan en organisation och ett fakturerings-ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Inloggningsföretag </p> </td> 
   <td colname="col2"> <p>Ett faktureringsföretag kan ha <a href="https://helpx.adobe.com/analytics/kb/multiple-login-companies.html"> flera inloggningsföretag </a>. Ett inloggningsföretag är en samling rapportsviter som används av din organisation. Vissa organisationer har flera inloggningsföretag som gäller för olika delar av organisationen. Detta är särskilt användbart för stora organisationer som arbetar med olika affärsenheter där många rapporteringsprogram inte är tillämpliga för andra i företaget. </p> <p>Detta är ofta ett företags regionala dotterbolag. I det här exemplet visas inloggningsföretag och deras tillhörande rapportsviter: </p> 
    <ul id="ul_8C756C7972D04F5E89D6E32BB06D26C3"> 
     <li id="li_EA6257FED7854B6FAA071926D0F8A07C">adobe.global: RS1, RS2, RS3, RS4 </li> 
     <li id="li_3EAFB556849E4CCC9D96D5A3492EC898">adobe.us: RS1, RS2 </li> 
     <li id="li_572FFB3F4BF545BDB13102D82CE5E50C">adobe.in: RS3 </li> 
     <li id="li_B6ACBA35E18A427AA83F76BD38E502D7">adobe.de: RS4 </li> 
    </ul> <p>Obs! Data om användning av serveranrop för <u>alla</u>-rapportsviter inom ett faktureringsföretag visas för alla användare med rätt <a href="/help/admin/admin/c-server-call-usage/overage-overview.md#section_FCC58EB635954A32990D4E67B52B4369"> behörighet </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Experience Cloud organisation </p> </td> 
   <td colname="col2"> <p>En organisation är den enhet som gör det möjligt för en administratör att konfigurera grupper och användare samt att styra enkel inloggning i Experience Cloud. Organisationen fungerar som ett inloggningsföretag som omfattar alla produkter och lösningar från Experience Cloud. </p> <p>Oftast är en organisation ditt företagsnamn. Ett företag kan dock ha många organisationer. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Utfästelse vid serveranrop </p> </td> 
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

## Användarbehörighet för serversamtal {#permission}

Användarbehörighet för serveranrop beviljas automatiskt till Analytics-administratörer. Det gör att användarna kan visa kontrollpanelen och skapa serversamtalsaviseringar. Administratörer kan välja att ge icke-administratörer denna behörighet.

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
   <td colname="col1"> <p>Serversamtalsanvändning </p> </td> 
   <td colname="col3"> 
    <ol id="ol_13A984328D264488B7045DC7521A5F55"> 
     <li id="li_ACDA518C7D184084AC1DFA7B38C67314">Logga in på Analytics via sc.omniture.com. </li> 
     <li id="li_066D90AB071941C3869EDAFCE981707A">Navigera till <span class="ignoretag"> <span class="uicontrol"> Admin </span> &gt; <span class="uicontrol"> Alla administratörer </span> &gt; <span class="uicontrol"> Användarhantering </span> &gt; <span class="uicontrol"> Grupper </span> &gt; <span class="uicontrol"> Redigera åtkomst till alla rapporter </span> &gt; <span class="uicontrol"> Analysverktyg </span> &gt; <span class="uicontrol"> Anpassa </span> &gt; <span class="uicontrol"> användning av serveranrop </span> </span>&rbrace; </li> 
    </ol> </td> 
   <td colname="col4"> 
    <ol id="ol_518673ED323A4C5993A3B9F4BA09E405"> 
     <li id="li_56FF685A3B454ECEA5F16BB591A60034">Logga in på login.experiencecloud.adobe.com.</li> 
     <li id="li_FA1AE0F19DEF4AB2AA77B22CCA2995F9">Klicka på <span class="uicontrol"> Analytics </span>. </li> 
     <li id="li_22A4CBB84B5A451780873BBE67E6E6EF">Navigera till <span class="ignoretag"> <span class="uicontrol"> Produkter </span> &gt; <span class="uicontrol"> Produktprofil </span> &gt; <span class="uicontrol"> Behörigheter </span> &gt; <span class="uicontrol"> Analysverktyg </span> &gt; <span class="uicontrol"> användning av serveranrop </span> </span> </li> 
    </ol> </td> 
  </tr> 
 </tbody> 
</table>
