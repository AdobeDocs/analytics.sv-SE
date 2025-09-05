---
description: Förstå vilka ID:n som registreras i era analysdata och bestäm vilka ni ska använda för förfrågningar om dataintegritet.
title: Bästa praxis för etikettering
feature: Data Governance
role: Admin
exl-id: 00da58b0-d613-4caa-b9c1-421b1b541f47
source-git-commit: 325a42c080290509309e90c9127138800d5ac496
workflow-type: tm+mt
source-wordcount: '2286'
ht-degree: 75%

---

# Bästa praxis för etikettering

Märkningen måste granskas varje gång en ny rapportserie skapas eller när en ny variabel aktiveras i en befintlig rapportserie. Du kan också behöva granska etiketteringen när nya lösningar är aktiverade, eftersom de kan visa nya variabler som kan kräva etiketter. En återimplementering av dina mobilappar eller webbplatser kan ändra hur befintliga variabler används, vilket också kan göra det nödvändigt att uppdatera etiketter.

Etiketterna I1, I2, S1 och S2 har samma betydelse som motsvarande DULE-etiketter i Adobe Experience Platform. De används dock för mycket olika syften. I Adobe Analytics används dessa etiketter för att identifiera fält som ska anonymiseras som ett resultat av en Privacy Service-förfrågan. Inom Adobe Experience Platform används de för åtkomstkontroll, samtyckeshantering och för att införa marknadsföringsbegränsningar för märkta fält. Adobe Experience Platform stöder många extra etiketter som inte används av Adobe Analytics. Om du använder Analytics Data Connector för att importera dina Adobe Analytics-data till Adobe Experience Platform, bör du se till att alla I1-, I2-, S1- och S2-etiketter som du har använt i Adobe Analytics också tillämpas på de scheman i Adobe Experience Platform som används av de importerade rapportsviterna.

## Direkt eller indirekt identifierbara ID:n {#direct-vs-indirect}

Innan du kan ta reda på vilka etiketter som ska användas på vilka variabler/fält måste du först förstå vilka ID:n som du hämtar i dina Analytics-data, och du måste bestämma vilka som ska användas för begäranden om datasekretess. Datasekretess utökar omfattningen av vad som kan anses vara ett ID. ID:n kan delas in i två huvudklasser: direkt identifierbar (identitetsetikett: I1) och indirekt identifierbar (identitetsetikett: I2).

* **Ett direkt identifierbart ID (I1)**: Namnger personen eller tillhandahåller en direkt metod för att kontakta honom/henne. Exempel kan vara någons namn (t.o.m. ett vanligt namn som Anders Svensson som kan delas av hundratals personer), deras e-postadresser eller telefonnummer, o.s.v. En postadress utan ett namn kan anses vara direkt identifierbart, även om den endast identifierar ett hushåll eller ett företag i stället för en viss person inom det hushållet eller företaget.
* **Ett indirekt identifierbart ID (I2)**: Tillåter inte identifiering av en enskild person, utan kan kombineras med annan information (som du kanske har tillgång till) för att identifiera någon. Exempel på ett indirekt identifierbart ID är ett kundlojalitetsnummer eller ett ID som används av ett företags CRM-system som är unikt för varje kund. Enligt datasekretess kan anonyma ID:n som lagras i de spårningscookies som används av Analytics anses vara indirekt identifierande, även om de bara kan identifiera en enhet snarare än en individ. På en delad enhet kan dessa cookies inte skilja mellan olika användare i systemet. Även om cookiefilen inte kan användas för att hitta en dator som innehåller cookien, och om någon har åtkomst till datorn och hittar cookien, kan de sedan koppla Analytics-cookiedata tillbaka till datorn.

En IP-adress anses också vara indirekt identifierbar, eftersom den vid en given tidpunkt bara kan tilldelas en enskild enhet. Internet-leverantörer kan däremot ändra IP-adresserna för de flesta användare regelbundet, så med tiden kan en IP-adress ha använts av någon av deras användare. Det är inte heller ovanligt att många kunder hos en Internet-leverantör eller flera anställda inom ett företag på samma intranät delar samma externa IP-adress. På grund av detta stöder inte Adobe att en IP-adress används som ID för en datasekretessbegäran. När ett ID som vi godkänner används som en del av en borttagningsbegäran, rensas även IP-adresserna som inträffade med det ID:t. Du måste bestämma om det finns andra insamlade ID:n som kan ingå i denna kategori, i1 eller I2, men som inte är lämpliga att använda som särskiljande ID för förfrågningar om dataintegritet.

Även om ditt företag samlar in många olika ID:n i era analysdata, kan du välja att endast använda en delmängd av dessa ID:n för begäranden om datasekretess. Detta kan bero på följande:

* I dina egna system kan du mappa ett av ID:n (till exempel e-postadress) till ett annat ID (till exempel CRM-ID). För konsekvensens skull väljer du att endast använda CRM-ID:t för begäranden om datasekretess i datasekretessbehandlingen.
* Du har ingen metod för att validera att någon faktiskt är den person som är kopplad till ID:t. Det kan till exempel vara svårt att validera att en IP-adress bara används av en person och att personen som skickar begäran faktiskt är den personen.
* Vissa ID:n kan motsvara flera personer och du vill inte riskera att returnera information om en person till någon annan med samma ID. Även om du till exempel kan verifiera att någon har namnet Anders Svensson kanske du inte vill returnera alla data om alla Anders Svensson i ditt system.
* Ett annat exempel är ett enhets-ID, till exempel cookie-ID för analys. Om ID:t finns i en mobilapp kan du bestämma att alla interaktioner som använder det ID:t ska vara tillgängliga för mobiltelefonens ägare. Om det däremot inträffar på en delad enhet, till exempel en dator i hemmet eller en dator i ett bibliotek eller ett Internetkafé, kan du bestämma att du inte kan skilja mellan användare av den enheten och risken för att returnera data för en annan användare är för stor för att den här typen av ID ska kunna användas.

## Bästa praxis för ID:n som stöds av Analytics {#best-practices-an}

Använd den här tabellen för att fastställa vilka typer av ID som du kommer att använda när du skickar begäranden om datasekretess till Analytics. När du känner till den här informationen är det enklare att avgöra vilka andra etiketter du ska använda för variablerna.

<table id="table_E25612E32A03449A8E5DA00B88FCEB9E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> ID-typ </th> 
   <th colname="col2" class="entry"> Rekommendationer </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Cookie-ID:er </p> 
    <ul id="ul_CB43CEA3054E490585CBF3AB46F95B5B"> 
     <li id="li_9174CB3910AF4EF8BA7165DB537765A5"> <a href="https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-privacy.html?lang=sv-SE"> (Äldre) Analytics-cookie </a> </li> 
     <li id="li_7B6A9A788BBD47428315B3893FC07BC3"> <a href="https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=sv-SE"> Identitetstjänstens cookie </a> (ECID), som tidigare kallades för Marketing Cloud ID (MCID) </li> 
    </ul> </td> 
   <td colname="col2"> <p>Dessa cookies identifierar en enhet eller, mer specifikt, en webbläsare för en användare av en enhet. För en delad enhet där en gemensam inloggning används kan detta ID gälla för alla användare av enheten. Adobe har skapat ett <a href="https://developer.adobe.com/experience-platform-apis/references/privacy-service/"> enhetligt JavaScript </a> som du kan placera på din webbplats för att samla in dessa cookies om du vill tillåta att de används för begäranden om datasekretess. </p> <p>Användare av Adobe Analytics Mobile SDK har också ett Experience Cloud ID (ECID). Det finns API-anrop i SDK som används för att läsa detta ID, så du kan förbättra din app och samla in den för att få en begäran om datasekretess. </p> <p>Många företag anser att webbläsarcookie-ID:n är delade enhets-ID:n. Därför kan de i samråd med sina juridiska team välja att inte ge stöd för att använda dem som godkända ID:n för förfrågningar om dataintegritet. Alternativt kan de välja att endast returnera en mycket begränsad mängd data när dessa ID:n används eller bara godkänna dem för borttagningsbegäranden. </p> <p>Dessa cookies har en ID-DEVICE-etikett som inte kan ändras (samt etiketterna I2 och DEL-DEVICE). Adobe Analytics-standardkonfigurationen returnerar bara allmän information om enheten, till exempel enhetstyp, operativsystem, webbläsare. samt den tid/de datum som webbplatsen besöktes när dessa ID:n användes. Om du väljer att stöda dessa ID:n för begäranden om datasekretess, vilket beskrivs nedan, kan du lägga till eller ta bort ACC-ALL-etiketter för att konfigurera den exakta uppsättning fält som du vill ska returneras för en begäran om datasekretess. </p> <p>Om rapportsviten motsvarar en mobilapp som kräver inloggning kan du bestämma att enhetens Experience Cloud-ID motsvarar en viss användare. I så fall kanske du vill märka fler fält med etiketten ACC-ALL, inklusive namnen på besökta sidor, visade produkter osv. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID:n i anpassade variabler </p> </td> 
   <td colname="col2"> <p>Vissa kunder placerar ID:er i <a href="/help/implement/vars/page-vars/evar.md"> anpassade trafikvariabler (props) eller anpassade konverteringsvariabler (eVars) </a>. Det vanligaste är ett CRM-ID, medan andra är e-postadresser, användarinloggningsnamn, kundlojalitetsnummer eller haschar av dessa värden. </p> 
    <ul id="ul_0B9492CF786046BB97E31CCF83A85FEA"> 
     <li id="li_D35B61CC6A8B485A8E09358A46D3F598">Om du vill använda något av dessa ID:n för begäranden om datasekretess ska du förse fältet som innehåller det med en ID-PERSON-etikett. </li> 
     <li id="li_94541340B054436297C5565F074413DC">(Mycket mindre vanligt) Om ett ID i en av dessa anpassade variabler bara identifierar en enhet som kan delas av flera personer, kan du i stället använda en ID-DEVICE-etikett. </li> 
     <li id="li_8115B999E8DA46CAB359BCF1F4A4DCAE">Dessa fält kräver också I1- eller I2-etiketter och ska innehålla etiketterna DEL-PERSON eller DEL-DEVICE. Alternativet PERSON/DEVICE för etiketten DEL matchar vanligtvis alternativet PERSON/DEVICE för ID-etiketten. </li> 
    </ul> <p> Det är ovanligt att en rapportserie har fler än en eller två anpassade variabler som innehåller ID:n som du vill använda för att identifiera registrerade personer för datasekretessförfrågningar. Du kan ha flera variabler som tilldelas I1- eller I2-etiketter, men vanligtvis har bara en eller två av dessa ID-PERSON- eller ID-DEVICE-etiketter. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Anpassat besökar-ID </p> </td> 
   <td colname="col2"> <p>Även om detta inte används i någon större utsträckning stöder Analytics även implementering där ett anpassat besökar-ID kan anges, som då används i stället för den gamla Analytics-spårningscookien. Det här fältet har etiketterna I2, ID-PERSON och DEL-PERSON. </p> <p>Många implementeringar härleder detta ID från ett CRM-ID så att det bara finns när någon är inloggad på sin plats. Detta gör att samma anpassade besökar-ID kan användas på olika enheter. En teknisk nackdel är att spårning som sker innan användaren loggar in inte kan knytas till spårning som samlas in efter att användaren har loggat in. Om du i stället använder det anpassade besökar-ID:t för att identifiera en enhet, ska du ändra etiketterna ID-PERSON och DEL-PERSON till ID-DEVICE respektive DEL-DEVICE. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Metodtips för att ange borttagningsetiketter {#best-practices-delete}

>[!NOTE]
>
>Säljare är alltid skiftlägeskänsliga. eVars är som standard inte skiftlägeskänsliga, men kan konfigureras via Adobes kundtjänst för att vara skiftlägeskänsliga. Om du har en skiftlägeskänslig eVar som innehåller ett ID är det ditt ansvar att använda rätt skiftläge när du skickar en begäran om datasekretess så att det skiftläge som används i begäran matchar det skiftläge som används i träffar som innehåller dessa ID:n.

Borttagningsetiketterna DEL-DEVICE och DEL-PERSON ska användas sparsamt. När det tillämpas på en variabel som inte innehåller ett ID som användes som en del av begäran om datasekretess ändras antalet (metrik) i historiska Analytics-rapporter nästan alltid.

* Vi rekommenderar att en av dessa etiketter används på alla variabler som är märkta I1, I2 eller S1. De kan inte tillämpas på variabler som inte har etiketten I1, I2 eller S1.
* DEL-etiketterna resulterar i att dessa variabler [anonymiseras](/help/admin/tools/privacy-labeling/labels.md#data-governance-labels) (ID:t ersätts med en slumpmässig sträng med prefixet ”Datasekretess-”). Samma anonymiserade värde ersätter alla instanser av det ursprungliga värdet i alla träffar som har identifierats av ett ID som används i begäran. Om det ursprungliga värdet i det här fältet var ett av dessa ID:n, ändras inte rapportens metrik.
* Om ett fält har etiketten ID-DEVICE ska du i allmänhet även tilldela etiketten DEL-DEVICE.
* Om ett fält har etiketten ID-PERSON ska du också tilldela etiketten DEL-PERSON.
* Om ett fält inte har någon ID-etikett, men innehåller identifieringsinformation som du vill anonymisera, beror den lämpliga etiketten (DEVICE eller PERSON) på implementeringen. Om du bara använder cookie-ID:n för begäranden om datasekretess ska du använda DEL-DEVICE.
* Om du använder anpassade ID:n i ett annat fält med en ID-PERSON-etikett, och du bara vill att detta ska rensas på rader där ID:t finns, använder du DEL-PERSON.
* Observera att om en DEL-DEVICE- eller DEL-PERSON-etikett anges för en variabel som inte också används som ett ID för den begäran (inklusive ett utökat ID), kommer unika värden i den variabeln endast att anonymiseras vid träffar där ett angivet (eller utökat) ID inträffar. Om andra träffar innehåller samma värde kommer det inte att uppdateras på de andra platserna. Detta kan leda till att antalet (metrik) ändras.

  Om du till exempel har tre träffar som innehåller värdet ”foo” i eVar7, men bara ett av dem innehåller ett ID i en annan variabel som matchas för en borttagning, ändras ”foo” i den träffen till ett värde som ”Datasekretess-123456789”, medan det förblir oförändrat i de andra två träffarna. En rapport som visar antalet unika värden för eVar7 visar nu ett mer unikt värde än det gjorde tidigare. En rapport som visar de högsta värdena för eVars kan innehålla ”foo” med endast två instanser (i stället för 3 tidigare), och det nya värdet visas också med en enda instans.

## Metodtips för att ange åtkomstetiketter {#best-practices-access}

Även om väldigt få fält kommer att ha någon av de andra etiketterna, så är det vanligt att ett stort antal fält har ACC-etiketter. Vilka åtkomstetiketter som är lämpliga beror på vilka ID:n du använder för begäranden om datasekretess.

<table id="table_A5B834CC08C641D99E2691A2361997E4"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Om du använder ... </th> 
   <th colname="col2" class="entry"> ... använd dessa rekommendationer </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Endast enhets-ID </p> </td> 
   <td colname="col2"> <p>Om de enda ID:n du använder är cookie ID:n eller de med ID-DEVICE-etikett, ska du bara använda ACC-ALL-etiketten. </p> <p>Du får ett par filer för varje åtkomstbegäran: en fil som innehåller en rad för varje matchande träff med alla angivna ACC-ALL-fält och en sammanfattningsfil som innehåller en sammanfattning av dessa data. </p> </td> 
  </tr> 
 </tbody> 
</table>
