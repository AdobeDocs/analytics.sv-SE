---
description: 'null'
title: Bästa praxis för märkning
uuid: d1e9bfff-9b04-4e3e-9b4e-a6e527b1b2e3
translation-type: tm+mt
source-git-commit: 12a7452337307ca019c005dc20e3b551d96e1289

---


# Bästa praxis för märkning

> [!NOTE] Kom ihåg att etiketter måste granskas varje gång en ny rapportserie skapas eller när en ny variabel aktiveras i en befintlig rapportserie. Du kan också behöva granska etiketten när nya lösningar är aktiverade, eftersom de kan visa nya variabler som kan kräva etiketter. En omimplementering av dina mobilappar eller webbplatser kan ändra det sätt på vilket befintliga variabler används, vilket också kan göra det nödvändigt att uppdatera etiketterna.

## Direkt kontra indirekt identifierbara ID:n {#section_030799AA1397433FBA61A2BC60A7A750}

Innan du kan ta reda på vilka etiketter som ska användas på vilka variabler/fält är det först nödvändigt att förstå vilka ID:n som du hämtar i dina Analytics-data och att bestämma vilka som ska användas för förfrågningar om dataintegritet. Dataintegritet utökar omfattningen av vad som kan anses vara ett ID. ID:n kan delas in i två huvudklasser: direkt identifierbar (identitetsetikett: I1) och indirekt identifierbar (identitetsetikett: I2).

* **Ett direkt identifierbart ID (I1)**: Namnger personen eller tillhandahåller en direkt metod för att kontakta honom/henne. Exempel är någons namn (t.o.m. ett gemensamt namn som John Smith som kan delas av hundratals personer), deras e-postadresser eller telefonnummer etc. En postadress utan namn kan anses vara direkt identifierbar, även om den endast kan identifiera ett hushåll eller ett företag i stället för en viss person inom det hushållet eller företaget.
* **Ett indirekt identifierbart ID (I2)**: Tillåter inte identifiering av en enskild person, utan kan kombineras med annan information (som du kanske har tillgång till) för att identifiera någon. Exempel är ett kundlojalitetsnummer eller ett ID som används av ett företags CRM-system och som är unikt för varje kund. Enligt datasekretess kan anonyma ID:n som lagras i de spårningskakor som används av Analytics anses vara indirekt identifierande, även om de bara kan identifiera en enhet snarare än en individ. på en delad enhet kan dessa cookies inte skilja mellan olika användare i systemet. Även om cookie-filen inte kan användas för att hitta en dator som innehåller cookien, och om någon har åtkomst till datorn och hittar cookien, kan de sedan koppla Analytics-cookie-data tillbaka till datorn.

   En IP-adress anses också vara indirekt identifierbar, eftersom den vid en given tidpunkt bara kan tilldelas en enskild enhet. Internet-leverantörer kan dock ändra IP-adresserna för de flesta användare regelbundet, så över tiden kan en IP-adress ha använts av någon av deras användare. Det är inte heller ovanligt för många kunder hos en Internet-leverantör eller flera anställda inom ett företag på samma intranät att dela samma externa IP-adress. På grund av detta kommer Adobe inte att ha stöd för att använda en IP-adress som ID för en begäran om [dataskydd.](/help/admin/c-data-governance/gdpr-submit-access-delete.md#submit-requests) När ett ID som vi godkänner används som en del av en borttagningsbegäran, rensas även IP-adresserna som inträffade med det ID:t. Du måste bestämma om det finns andra ID:n som du samlar in som kan ingå i denna kategori, i1 eller I2, men som inte är lämpliga att använda som särskiljande ID för förfrågningar om dataintegritet.

Även om ditt företag samlar in många olika ID:n i era analysdata, kan du välja att endast använda en delmängd av dessa ID:n för förfrågningar om dataintegritet. Detta kan bero på följande:

* I dina egna system kan du mappa ett av ID:n (till exempel e-postadress) till ett annat ID (till exempel CRM-ID). För konsekvensens skull väljer du att endast använda CRM-ID:t för datasekretessförfrågningar i datasekretessbehandlingen.
* Du har ingen metod för att validera att någon faktiskt är den person som är kopplad till ID:t. Det kan till exempel vara svårt att validera att en IP-adress bara användes av en person och att personen som skickar begäran faktiskt är den personen.
* Vissa ID:n kan motsvara flera personer och du vill inte riskera att returnera information om en person till någon annan med samma ID. Även om du till exempel kan verifiera att någon har namnet Sven Smith kanske du inte vill returnera alla data om alla Sven Svensson i ditt system.
* Ett annat exempel är ett enhets-ID, till exempel cookie-ID för analys. Om ID:t finns i en mobilapp kan du bestämma att alla interaktioner som använder det ID:t ska vara tillgängliga för mobiltelefonens ägare. Om det däremot inträffar på en delad enhet, till exempel en hemdator eller en dator i ett bibliotek eller en Internetkafé, kan du bestämma att du inte kan skilja mellan användare av den enheten och risken för att returnera data för en annan användare är för stor för att den här typen av ID ska kunna användas.

## Bästa praxis för ID:n som stöds av Analytics {#section_B6481505FF1949498D4B4B35B780D050}

Använd den här tabellen för att fastställa vilka typer av ID som du kommer att använda när du skickar förfrågningar om dataintegritet till Analytics. När du känner till den här informationen är det enklare att avgöra vilka andra etiketter du ska använda för variablerna.

<table id="table_E25612E32A03449A8E5DA00B88FCEB9E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> ID-typ </th> 
   <th colname="col2" class="entry"> Rekommendationer </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Cookie-ID </p> 
    <ul id="ul_CB43CEA3054E490585CBF3AB46F95B5B"> 
     <li id="li_9174CB3910AF4EF8BA7165DB537765A5"> <a href="https://marketing.adobe.com/resources/help/en_US/whitepapers/cookies/cookies_analytics.html"> (Äldre) Analytics Cookie </a> </li> 
     <li id="li_7B6A9A788BBD47428315B3893FC07BC3"> <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/"> Identitetstjänstens cookie </a> (ECID), som tidigare kallades för Marketing Cloud ID (MCID) </li> 
    </ul> </td> 
   <td colname="col2"> <p>Dessa cookies identifierar en enhet eller, mer specifikt, en webbläsare för en användare av en enhet. För en delad enhet där en gemensam inloggning används kan detta ID gälla för alla användare av enheten. Adobe har skapat ett <a href="https://www.adobe.io/apis/cloudplatform/gdpr/services/allservices.htm"> enhetligt JavaScript </a> som du kan placera på din webbplats för att samla in dessa cookies om du vill tillåta att de används för förfrågningar om dataintegritet. </p> <p>Användare av Adobe Analytics Mobile SDK har också ett Experience Cloud ID (ECID). Det finns API-anrop i SDK för att läsa detta ID, så du kan förbättra din app och samla in den för att få en begäran om dataintegritet. </p> <p>Många företag anser att webbläsar-cookie-ID:n är delade enhets-ID:n. Detta innebär att de i samråd med sina juridiska team kan välja att inte ge stöd för att använda dem som godtagbara ID:n för förfrågningar om dataintegritet, eller välja att endast returnera en mycket begränsad mängd data när dessa ID:n används eller att de endast kan godkänna dem för borttagningsförfrågningar. </p> <p>Dessa cookies har en ID-DEVICE-etikett som inte kan ändras (samt etiketterna I2 och DEL-DEVICE). Adobe Analytics-standardkonfigurationen returnerar bara allmän information om enheten, till exempel enhetstyp, operativsystem, webbläsare. samt den tid/de datum som webbplatsen besöktes när dessa ID:n användes. Om du väljer att ge stöd för dessa ID:n för förfrågningar om dataskydd, vilket beskrivs nedan, kan du lägga till eller ta bort ACC-ALL-etiketter för att konfigurera den exakta uppsättning fält som du vill ska returneras för en begäran om dataintegritet. </p> <p>Speciellt om rapportsviten motsvarar en mobilapp, och din mobilapp kräver inloggning, kan du bestämma att Experience Cloud-ID:t för enheten motsvarar en viss användare och därför vill du märka fler fält med ACC-ALL-etiketten, inklusive namnen på besökta sidor, visade produkter osv. </p> <p>Obs!  Om du anger alternativet "expandIds" i din datasekretessbegäran kommer dina förfrågningar alltid att innehålla cookie-ID:n, förutom eventuella andra ID:n du anger. Mer information finns <a href="/help/admin/c-data-governance/gdpr-id-expansion.md"> i </a> ID-expansion. I dessa fall returnerar träffar som bara har ett cookie-ID, men inte ett annat ID, endast data som är märkta ACC-ALL som en del av åtkomstbegäran. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID:n i anpassade variabler </p> </td> 
   <td colname="col2"> <p>Vissa kunder placerar ID:n i <a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/props_eVars.html"> anpassade trafikvariabler (props) eller anpassade konverteringsvariabler (eVars) </a>. Det vanligaste är ett CRM-ID, medan andra är e-postadresser, användarinloggningsnamn, kundlojalitetsnummer eller hascher av dessa värden. </p> 
    <ul id="ul_0B9492CF786046BB97E31CCF83A85FEA"> 
     <li id="li_D35B61CC6A8B485A8E09358A46D3F598">Om du vill använda något av dessa ID:n för datasekretessförfrågningar ska du ge fältet som innehåller det en ID-PERSON-etikett. </li> 
     <li id="li_94541340B054436297C5565F074413DC">(Mycket mindre vanligt) Om ett ID i en av dessa anpassade variabler bara identifierar en enhet som kan delas av flera personer, kan du i stället använda en ID-DEVICE-etikett. </li> 
     <li id="li_8115B999E8DA46CAB359BCF1F4A4DCAE">Dessa fält kräver också I1- eller I2-etiketter och ska innehålla etiketterna DEL-PERSON eller DEL-DEVICE. Alternativet PERSON/DEVICE för etiketten DEL matchar vanligtvis alternativet PERSON/DEVICE för ID-etiketten. </li> 
    </ul> <p> Det är sällsynt att en rapportserie har mer än en eller två anpassade variabler som innehåller ID:n som du vill använda för att identifiera de registrerade för förfrågningar om dataintegritet. Du kan ha flera variabler som tilldelas I1- eller I2-etiketter, men vanligtvis har bara en eller två av dessa ID-PERSON- eller ID-DEVICE-etiketter. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Anpassat besökar-ID </p> </td> 
   <td colname="col2"> <p>Även om detta inte används i någon större utsträckning stöder Analytics även en implementering där ett anpassat besökar-ID kan anges, som om det finns används i stället för den gamla cookien för analysspårning. Det här fältet har etiketterna I2, ID-PERSON och DEL-PERSON. </p> <p>Många implementeringar härleder detta ID från ett CRM-ID så det finns bara när någon är inloggad på sin plats. Detta gör att samma anpassade besökar-ID kan användas på olika enheter. En teknisk nackdel är att spårning som sker innan användaren loggar in inte kan knytas till spårning som samlas in efter att användaren har loggat in. Om du i stället använder det anpassade besökar-ID:t för att identifiera en enhet bör du ändra etiketterna ID-PERSON och DEL-PERSON till ID-DEVICE respektive DEL-DEVICE. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Bästa tillvägagångssätt för att ange borttagningsetiketter {#section_08166C99B48E49218392FAC18922C10E}

> [!NOTE] Säljare är alltid skiftlägeskänsliga. Varor är som standard inte skiftlägeskänsliga, men kan konfigureras via Adobes kundtjänst för att vara skiftlägeskänsliga. Om du har en skiftlägeskänslig eVar som innehåller ett ID är det ditt ansvar att använda rätt fall när du skickar en begäran om dataintegritet så att det fall som används i begäran matchar det fall som används i träffar som innehåller dessa ID:n.

Ta bort etiketterna DEL-DEVICE och DEL-PERSON bör användas sparsamt. När det tillämpas på en variabel som inte innehåller ett ID som användes som en del av dataintegritetsbegäran ändras antalet (mått) i historiska analysrapporter nästan alltid.

* Vi rekommenderar att en av dessa etiketter används på alla variabler som är märkta I1, I2 eller S1. De kan inte tillämpas på någon variabel som inte har etiketten I1, I2 eller S1.
* DELL-etiketterna resulterar i att dessa variabler [anonymiseras](/help/admin/c-data-governance/gdpr-labels.md#data-governance-labels) (ID:t ersätts med en slumpmässig sträng med prefixet&quot;Data Privacy-&quot;). Samma anonyma värde ersätter alla instanser av det ursprungliga värdet i alla träffar som har identifierats av ett ID som används i begäran. Om det ursprungliga värdet i det här fältet var ett av dessa ID:n ändras inte rapportens mått.
* Om ett fält har etiketten ID-DEVICE bör du i allmänhet även tilldela etiketten DEL-DEVICE.
* Om ett fält har etiketten ID-PERSON bör du också tilldela etiketten DEL-PERSON.
* Om ett fält inte har någon ID-etikett, men innehåller identifieringsinformation som du vill anonymisera, beror den lämpliga etiketten (DEVICE eller PERSON) på implementeringen. Om du bara använder cookie-ID:n för datasekretessförfrågningar bör du använda DEL-DEVICE.
* Om du använder anpassade ID:n i ett annat fält med en ID-PERSON-etikett, och du bara vill att detta ska rensas på rader där ID:t finns, använder du DEL-PERSON.
* Om du använder ID-expansion och vill att alla värden ska rensas för alla träffar på alla identifierade enheter använder du DEL-DEVICE. Du kan använda både etiketterna DEL-DEVICE och DEL-PERSON i det här fallet om du vill, men etiketten DEL-PERSON är inte nödvändig eftersom ID-expansionen innebär att alla rader som matchar ett person-ID också matchar ett enhets-ID.
* Om du inte anger att du ska använda ID-expansion, men vill använda en blandning av enhets- och person-ID för olika begäranden, kanske du vill ange både DELL-DEVICE- och DEL-PERSON-etiketter för variabler som ska tas bort när någon typ av ID används.
* Observera att om en DEL-DEVICE- eller DEL-PERSON-etikett anges för en variabel som inte också används som ett ID för den begäran (inklusive ett utökat ID), kommer unika värden i den variabeln endast att anonymiseras vid träffar där ett angivet (eller utökat) ID inträffar. Om andra träffar innehåller samma värde kommer det inte att uppdateras på de andra platserna. Detta kan leda till att antalet (mätvärden) ändras.

   Om du till exempel har tre träffar som innehåller värdet &quot;foo&quot; i eVar7, men bara ett av dem innehåller ett ID i en annan variabel som matchas för en borttagning, ändras &quot;foo&quot; i den träffen till ett värde som &quot;Data Privacy-123456789&quot;, medan det förblir oförändrat i de andra två träffarna. En rapport som visar antalet unika värden för eVar7 visar nu ett mer unikt värde än det gjorde tidigare. En rapport som visar de högsta värdena för eVars kan innehålla &quot;foo&quot; med endast två instanser (i stället för 3 tidigare), och det nya värdet visas också med en enda instans.

## Bästa tillvägagångssätt för att ange åtkomstetiketter {#section_AC7E216F81C141FCA6A62F8836E06EE7}

Även om det är få fält som har någon av de andra etiketterna är det vanligt att ett stort antal fält har ACC-etiketter. Vilka åtkomstetiketter som är lämpliga beror på vilka ID:n du använder för förfrågningar om dataintegritet.

<table id="table_A5B834CC08C641D99E2691A2361997E4"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Om du använder ... </th> 
   <th colname="col2" class="entry"> ...använd dessa rekommendationer </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Endast enhets-ID </p> </td> 
   <td colname="col2"> <p>Om de enda ID:n du använder är cookie ID:n eller de med ID-DEVICE-etikett, ska du bara använda ACC-ALL-etiketten. </p> <p>Du får ett par filer för varje åtkomstbegäran, en som innehåller en rad för varje matchande träff med alla angivna ACC-ALL-fält och en andra som innehåller en sammanfattning av dessa data. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Person-ID:n utan ID-expansion </p> </td> 
   <td colname="col2"> <p>Om du bara använder anpassade ID:n som har ID-PERSON-etiketten och inte gör ID-expansion bör du använda ACC-PERSON-etiketter. Du behöver dock inte ändra standardetiketterna för ACC-ALL. dessa fält inkluderas automatiskt i åtkomstbegäran. </p> <p>Du får ett par filer för varje åtkomstbegäran, en som innehåller en rad för varje matchande träff med alla angivna fält för ACC-DEVICE och ACC-PERSON och en andra som innehåller en sammanfattning av dessa data. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Blandade ID:n och/eller ID-expansion </p> </td> 
   <td colname="col2"> <p>Om du inkluderar både enhets- och person-ID:n i förfrågningar om dataintegritet, eller om du använder anpassade ID:n (anpassade besökar-ID:n eller ID:n i en prop eller eVar), måste du vara uppmärksam på de ACC-etiketter som du använder. Varje åtkomstbegäran returnerar två par datafiler, ett par som innehåller data från träffar som innehöll ett matchande person-ID och ett andra som innehåller data från träffar som inte matchade ett person-ID, men som matchade ett enhets-ID. </p> <p>"person-ID"-filerna innehåller data om alla träffar som matchade person-ID:n med alla fält som har antingen en ACC-PERSON- eller ACC-ALL-etikett (en fil med alla matchade träffar och den andra som en sammanfattning). </p> <p>Filparet "enhets-ID" innehåller bara fält som har en ACC-ALL-etikett och bara träffar som inte innehöll något matchande person-ID. De här filerna kan innehålla data som har genererats av andra användare av en delad enhet, så du bör noga tänka på de fält som innehåller etiketten ACC-ALL. Standardetiketten i Analytics använder bara den här etiketten för generiska informationsfält som hör till enheten (enhetstyp, operativsystem, webbläsare osv.) plus datum/tid för varje träff. </p> <p>Du kan välja att ta emot både enhets- och personfiluppsättningar från Adobe och sedan bara dela personfilerna, så att du inte delar data som kan ha genererats av andra användare av en delad enhet. Eller så kanske du vill kombinera data från en eller båda uppsättningar med annan information som du känner till om den registrerade och returnera den i ditt eget format. </p> </td> 
  </tr> 
 </tbody> 
</table>

