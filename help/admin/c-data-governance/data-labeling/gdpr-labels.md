---
description: Exempel på dataintegritetsetiketter för Adobe Analytics-variabler
title: Datasekretessetiketter för analysvariabler
feature: Data Governance
exl-id: b8c2143a-6e8e-465a-979b-aa8176e8d4e8
source-git-commit: 9e8607691e6b144dd9e7b7a407bb2f02d27fbb1a
workflow-type: tm+mt
source-wordcount: '3673'
ht-degree: 91%

---

# Datasekretessetiketter för analysvariabler

## Varför märka upp era data? {#why-label}

Många av Adobes kunder har jurister som har granskat lagarna om datasekretess (GDPR, CCPA, o.s.v.). Dessa grupper kan ha dragit egna slutsatser om hur data ska hanteras för att följa dataintegritetslagstiftningen. De juridiska tolkningarna kan skilja sig åt mellan olika företag och de önskade inställningarna för datahantering kan också skilja sig åt mellan olika kunder. Eftersom kunderna har olika preferenser för behandling av datasekretess och olika datauppsättningar, låter Adobe sina kunder, som personuppgiftsansvariga, att anpassa sina inställningar för databehandling i samband med datasekretess för sina unika data. På så sätt kan varje unik kund behandla begäranden om datasekretess på det sätt som bäst passar deras varumärke och deras unika datauppsättning.

Adobe Analytics har verktyg som används för att etikettera data utifrån känslighet och avtalsbegränsningar. Etiketter är viktiga och användbara när det gäller att (1) identifiera registrerade, (2) fastställa vilka uppgifter som ska returneras som en del av en begäran om åtkomst och (3) identifiera datafält som måste tas bort som en del av en begäran om radering.

Innan du kan ta reda på vilka etiketter som ska användas på vilka variabler/fält måste du [förstå vilka ID:n](/help/admin/c-data-governance/data-labeling/gdpr-analytics-ids.md) som du hämtar i dina Analytics-data, och du måste bestämma vilka som ska användas för begäranden om datasekretess.

Implementering av datasekretess i Adobe Analytics stöder följande etiketter för identitetsdata, känsliga data och datastyrning.

## DULE-etiketter {#dule-labels}

>[!NOTE]
>
>DULE-ramverket (Data Usage Labeling &amp; Enforcement) är utformat för att tillhandahålla ett enhetligt sätt att i alla Adobe-lösningar/-tjänster/-plattformar samla in, kommunicera och använda metadata om data i hela Adobe Experience Cloud. Metadata hjälper personuppgiftsansvariga att indikera vilka data som är personuppgifter, vilka data som är känsliga och vilka avtalsbegränsningar som är kopplade till data. I den här initiala versionen visar Analytics bara de DULE-etiketter som är relevanta för datasekretess. I takt med att andra Adobe-produkter implementerar stöd för DULE-etiketter, kommer framtida versioner att innehålla ytterligare känsliga dataetiketter, liksom avtalsetiketter, som säkerställer att data som delas mellan produkterna endast används på ett juridiskt tillåtet sätt.

## Identitetsdataetiketter (DULE) {#identity-data-labels}

Identitetsdata ”I”-etiketter används för att kategorisera data som kan identifiera eller kontakta en viss person.

| Etikett | Definition | Andra krav |
| --- | --- | --- |
| I1 | Direkt identifierbar: Data som specifikt kan identifiera eller möjliggöra direktkontakt med en individ, till exempel ett namn eller en e-postadress. | <ul><li>Kan inte anges för händelser</li><li>Kan inte anges för marknadsförande eVars</li></ul> |
| I2 | Indirekt identifierbar: Data som kan användas i kombination med andra data för att identifiera eller möjliggöra direktkontakt med en individ eller enhet.  Tillåter inte identifiering av en enskild person, utan kan kombineras med annan information (som du kanske har tillgång till) för att identifiera någon. Exempel är ett kundlojalitetsnummer eller ett ID som används av ett företags CRM-system och som är unikt för varje kund. | <ul><li>Kan inte anges för händelser</li><li>Kan inte anges för marknadsförande eVars</li></ul> |

{style=&quot;table-layout:auto&quot;}

## Känsliga dataetiketter (DULE) {#sensitive-data-labels}

Känsliga ”S”-etiketter används för att kategorisera känsliga data som geografiska data. Ytterligare etiketter för känsliga data kommer att införas i framtiden för att identifiera andra typer av känslig information.

| Etikett | Definition |
| --- | --- |
| S1 | Exakta geolokaliseringsdata för latitud och longitud som kan användas för att fastställa en enhets exakta placering (högst 100 meter). |
| S2 | Geolokaliseringsdata som kan användas för att fastställa ett brett definierat geostaketområde. |

{style=&quot;table-layout:auto&quot;}

## Dataförvaltningsrubriker (dataintegritet) {#data-governance-labels}

Etiketter för datastyrning ger användarna möjlighet att klassificera data som avspeglar sekretessrelaterade överväganden och avtalsvillkor så att de överensstämmer med regler och företagspolicyer.

### Etiketter för dataintegritet

| Etikett | Definition | Andra krav |
| --- | --- | --- |
| Ingen | Välj det här alternativet om den här variabeln inte innehåller data som måste inkluderas i data som skickas till den registrerade som en del av en begäran om datasekretess. |  |
| ACC-ALL | Värdena i det här fältet ska inkluderas i alla begäranden om datasekretess. Om den här träffen kommer från en enhet som delas av flera personer, kan du i egenskap av personuppgiftsansvarig, genom att tillämpa den här etiketten, indikera att det är acceptabelt att dela data i det här fältet med alla som har åtkomst till den delade enheten. | Fält med den här etiketten returneras för alla begäranden om datasekretess. |
| ACC-PERSON | Värdena i det här fältet ska endast inkluderas för åtkomstbegäranden om datasekretess när vi är någorlunda säkra på att träffen kom från den registrerade, vilket fastställts av ett ID för begärande om datasekretess som matchar värdet för ett ID-PERSON-fält. | Du måste också ha en ID-PERSON-etikett angiven för en viss variabel i den här rapportsviten, och skicka begäranden med det ID:t, annars kommer den här etiketten aldrig att gälla. |

{style=&quot;table-layout:auto&quot;}

Även om få variabler mottar någon av de andra etiketterna, förväntas åtkomstetiketter tillämpas för många av dina variabler. Men det är upp till dig, i samråd med din juridiska avdelning, att avgöra vilka uppgifter du har samlat in som ska delas med de registrerade.

### Ta bort etiketter för datasekretess

Till skillnad från de andra etiketterna utesluter inte dessa borttagningsetiketter varandra. Du kan välja antingen båda eller ingen. En separat [!UICONTROL None] etiketten inte behövs eftersom [!UICONTROL None] markeras genom att du inte markerar något av alternativen för att ta bort.

En borttagningsetikett krävs endast för fält som innehåller ett värde som skulle göra det möjligt att koppla en träff till den registrerade (d.v.s. som skulle göra det möjligt att identifiera den registrerade). Andra personuppgifter (favoriter, webbsurfnings-/inköpshistorik, hälsovillkor, o.s.v.) behöver inte tas bort eftersom associationen med den registrerade kommer att tas bort.

| Etikett | Definition | Andra krav |
| --- | --- | --- |
| DEL-DEVICE | För begäran om borttagning av datasekretess ska värdena i det här fältet endast anonymiseras för begäranden där en angiven ID-DEVICE finns i träffen.  Om samma värde används för andra träffar, som inte tas bort, ändras inte de andra instanserna. Detta resulterar i att antalet ändras för rapporter som beräknar unika antal i det här fältet. Detta kan ta bort identifierare för andra personer på delade enheter, utöver bara den registrerade.  Antalet ändras inte om det här fältet även har en ID-DEVICE-etikett och värdet i det här fältet användes som ID för begäran om datasekretess. | <ul><li>Kräver även etiketten I1, I2 eller S1</li><li>Kan inte anges för händelser</li><li>Kan inte anges för marknadsförande eVars</li></li><li>Kan inte anges för klassificeringar</li><li>Du måste skicka begäranden med en ID-DEVICE eller ange expandID till sant, annars kommer den här etiketten aldrig att gälla.</li></ul> |
| DEL-PERSON | För begäran om borttagning av datasekretess ska värdena i det här fältet endast anonymiseras för begäranden där en angiven ID-PERSON finns i träffen.  Om samma värde används för andra träffar, som inte tas bort, ändras inte de andra värdena. Detta resulterar i att antalet ändras för rapporter som beräknar unika antal i det här fältet. Antalet ändras inte om det här fältet även har en ID-PERSON-etikett och värdet i det här fältet användes som ID för begäran om datasekretess. | <ul><li>Kräver även etiketten I1, I2 eller S1</li><li>Kan inte anges för händelser</li><li>Kan inte anges för marknadsförande eVars</li></li><li>Kan inte anges för klassificeringar</li><li>Du måste skicka begäranden med en ID-PERSON-etikett som har angetts för en viss variabel i den här rapportsviten och skicka begäranden med det ID:t, annars kommer den här etiketten aldrig att gälla.</li></ul> |

{style=&quot;table-layout:auto&quot;}

### Identitetsetiketter för datasekretess

| Etikett | Definition | Andra krav |
| --- | --- | --- |
| Ingen | Den här variabeln innehåller inte något ID som ska användas för begäranden om datasekretess. | Du behöver bara ange en av de andra etiketterna om det här fältet innehåller ett ID som du använder när du skickar begäran om åtkomst eller borttagning via [Privacy Services-API](https://experienceleague.adobe.com/docs/experience-platform/privacy/api/overview.html) eller användargränssnittet. |
| ID-DEVICE | Det här fältet innehåller ett ID som kan användas för att identifiera en enhet för en begäran om datasekretess, men det kan inte skilja mellan olika användare av en delad enhet.  Du behöver inte ange den här etiketten för alla variabler som innehåller ID:n (det vill säga I1/I2-etiketterna). Använd den här etiketten om du skickar begäranden om datasekretess med ID:n som lagras i den här variabeln och vill söka efter det angivna ID:t i variabeln. | Kräver även etiketten I1 eller I2.<ul><li>Kan inte anges för händelser</li><li>Kan inte anges för marknadsförande eVars</li><li>Kan inte anges för klassificeringar</li></ul> |
| ID-PERSON | Det här fältet innehåller ett ID som kan användas för att identifiera en autentiserad användare (en viss person) för en begäran om datasekretess.  Du behöver inte ange den här etiketten för alla variabler som innehåller ID:n (det vill säga I1/I2-etiketterna). Använd den här etiketten om du ska skicka begäranden om datasekretess med ID:n som lagras i den här variabeln och vill söka efter det angivna ID:t i variabeln. | <ul><li>Kräver även etiketten I1 eller I2.</li><li>Kan inte anges för händelser</li><li>Kan inte anges för marknadsförande eVars</li><li>Kan inte anges för klassificeringar</li></ul> |

{style=&quot;table-layout:auto&quot;}

## Ange ett namnutrymme när en variabel taggas som ID-DEVICE eller ID-PERSON {#provide-namespace}

När du etiketterar en variabel som ID-DEVICE eller ID-PERSON uppmanas du att ange ett namnutrymme. Du kan antingen använda ett tidigare definierat namnutrymme eller definiera ett nytt.

### Använda ett tidigare definierat namnutrymme

Du kan välja ett av de befintliga namnutrymmena om du tidigare har tilldelat en ID-etikett till andra variabler i någon av rapportsviterna i ditt inloggningsföretag. Återanvänd namnutrymmet om den här variabeln innehåller samma typ av ID:n som andra variabler som redan är etiketterade med det här namnutrymmet och du vill söka igenom dem alla när du skickar en begäran.

1. Klicka på **[!UICONTROL Select Namespace]** och välj ett av de befintliga namnutrymmena.
1. Klicka på **[!UICONTROL Apply]**.

![](assets/namespace.png)

### Definiera ett nytt namnutrymme

Du kan också definiera ett nytt namnutrymme. Strängar för namnutrymme bör även begränsas till alfanumeriska tecken, samt understreck, bindestreck och blanksteg. De konverteras till små bokstäver.

1. Klicka på **[!UICONTROL Select Namespace]** och ange titeln för namnutrymmet.

   ![](assets/namespace2.png)

1. Tryck på **[!UICONTROL Enter]** för att lägga till det här namnutrymmet. Först nu aktiveras knappen Använd.
1. Klicka på **[!UICONTROL Apply]**.

Strängen som du anger som namnutrymme är samma sträng som du använder när du skickar begäranden via API:t för datasekretess som värdet för parametern ”namnutrymme”. Begäran gör sedan att Adobe Analytics söker igenom alla variabler i alla rapportsviter som delar namnutrymmet för det ID som du angav i begäran.

Du behöver inte ange ID-DEVICE- eller ID-PERSON-etiketter för alla variabler som innehåller ID:n (det är i I1/I2-etiketterna som används). Använd den här etiketten om du ska skicka begäranden om datasekretess med ID:n som lagras i den här variabeln och vill söka efter det angivna ID:t i variabeln. Om eVar1 till exempel kan innehålla en e-postadress och eVar2 kan innehålla ett användarnamn för inloggning, men du bara skickar begäranden med användarnamnet, kan du ge eVar1-etiketten I1, ACC-PERSON, DEL-PERSON, men eVar2 etiketten I2, ACC-PERSON, DEL-PERSON, ID-PERSON med namnutrymmet ”användarnamn”. Du kan sedan skicka en begäran med ett JSON-block för användaravsnitt som:

```
{
     "namespace": "user name",
     "type": "analytics",
     "value": "rocketman123"
}
```

Det är möjligt att använda samma namnutrymme för olika variabler i samma rapportsvit. I vissa anpassade implementeringar lagras till exempel ett CRM-ID i både en prop och en eVar. Om CRM-ID alltid förekommer i en av dem (t.ex. eVar), och endast ibland förekommer i den andra (prop), och aldrig i prop när det inte finns i eVar, kräver endast eVar en ID-etikett och ett namnutrymme, eftersom Adobe bara kan söka i denna eVar för ID:t. Men om CRM-ID ibland förekommer i en variabel och ibland i en annan, ska båda ha samma namnutrymme och Adobe söker i båda variablerna efter förekomster av det ID som anges som en del av en begäran om datasekretess med det här namnutrymmet. Du ska fortfarande ha DEL-etiketter på alla dessa variabler, så att värdet anonymiseras oavsett var det finns.

Ett annat exempel är att du kan ha ett CRM-ID som ibland skickas in via eVar1 och ibland skickas in via prop7. Sedan har du en behandlingsregel som kopierar värdet från eVar1, om det finns, till eVar3. Annars kopieras värdet från prop7 till eVar3. I det här scenariot innehåller eVar3 alltid CRM-ID om det är känt, så endast eVar3 kräver en ID-PERSON-etikett.

>[!CAUTION]
>
>Namnutrymmena ”visitorId” och ”customVisitorId” är reserverade för att identifiera den äldre Analytics-spårningscookien och Analytics-kundens besökar-ID. Använd inte dessa namnutrymmen för anpassade trafikvariabler och konverteringsvariabler.

## Variabeltyper och de dataintegritets-/DULE-etiketter de stöder {#variable-types}

Etiketter för datasekretess/DULE påverkar fyra breda klasser av analysvariabler. Alla variabler har inte stöd för alla etiketter. Tabellen visar vilka variabler som stöder eller inte stöder olika etiketter.

| Variabeltyp | Etiketter som stöds | Etiketter som inte stöds |
|--- |--- |--- |
| <ul><li>Anpassade slutförda händelser</li><li>Marknadsförande eVars</li><li>Multivärdesvariabler (mvVars)</li><li>Hierarkivariabler</li></ul> | <ul><li>S1/S2</li><li>ACC-ALL, ACC-PERSON</li></ul> | <ul><li>I1/I2</li>  <li>ID-DEVICE, ID-PERSON</li><li>DEL-DEVICE, DEL-PERSON</li></ul> |
| Klassificeringar | <ul><li>I1/I2, S1/S2</li><li>ACC-ALL, ACC-PERSON</li></ul> | <ul><li>ID-DEVICE, ID-PERSON</li><li>DEL-DEVICE, DEL-PERSON</li></ul> |
| <ul><li>Trafikvariabler (props)</li><li>Handelsvariabler (icke-marknadsförande eVars)</li></ul> | Alla etiketter | - |
| De flesta andra variablerna  (*Se tabellen nedan för undantag*) | ACC-ALL, ACC-PERSON | <ul><li>I1/I2, S1/S2</li><li>ID-DEVICE, ID-PERSON</li><li>DEL-DEVICE, DEL-PERSON)</li></ul> |

{style=&quot;table-layout:auto&quot;}

## Variabler till vilka andra etiketter än ACC-ALL/ACC-PERSON kan tilldelas/ändras {#variables}

<table id="table_0972910DB2D7473588F23EA47988381D"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Grupp </th> 
   <th colname="col2" class="entry"> Variabler </th> 
   <th colname="col3" class="entry"> Ändringsbara etiketter </th> 
   <th colname="col4" class="entry"> Kommentar </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1" morerows="1"> 
    <ul id="ul_62FA1BAA3B9245909509566D8C03F900"> 
     <li id="li_38F7C4E18ECB42C292370713F502B8EB">Konverteringsdimensioner </li> 
     <li id="li_41CB61F927CB4402AAB4A62E219CD153">Anpassade trafikdimensioner </li> 
    </ul> </td> 
   <td colname="col2"> <p>Alla, utom klassificeringar </p> </td> 
   <td colname="col3"> <p>Alla </p> </td> 
   <td colname="col4"> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>Klassificeringar </p> </td> 
   <td colname="col3"> <p>Ingen/I1/I2 </p> <p>Ingen/S1/S2 </p> </td> 
   <td colname="col4"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Konverteringshändelser </p> </td> 
   <td colname="col2"> <p>Alla </p> </td> 
   <td colname="col3"> <p>Ingen/S1/S2 </p> </td> 
   <td colname="col4"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Lösningsdimensioner och händelser </p> </td> 
   <td colname="col2"> <p>Länk till Activity Map, </p> <p>Sida för Activity Map </p> </td> 
   <td colname="col3"> <p>Ingen/I1/I2 </p> <p>Ingen/DEL-DEVICE / DEL-PERSON </p> </td> 
   <td colname="col4"> <p>Variabler kan innehålla URL-parametrar, som kan innehålla direkt eller indirekt identifierbara data. Om implementeringen inte samlar in direkt eller indirekt identifierbara data i dessa variabler, behöver de inte identitets- eller raderingsetiketter. </p> <p>Observera att radering tar bort URL-parametrarna, men bevarar bas-URL:en. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dimensioner för databehandling </p> </td> 
   <td colname="col2"> <p>Anpassat besökar-ID </p> </td> 
   <td colname="col3"> <p>ID-DEVICE/ID-PERSON </p> <p>DEL-DEVICE/DEL-PERSON </p> </td> 
   <td colname="col4"> <p>Du kan inte ta bort ID- eller DEL-etiketterna (inställda på Ingen), men du kan ändra dem så att de antingen är DEVICE- eller PERSON-varianter, beroende på implementeringen av ditt anpassade ID. </p> <p>Inställningen spelar ingen roll om du inte använder det anpassade besökar-ID:t. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1" morerows="1"> 
    <ul id="ul_5EB0193732D44A20AEA08CE9DFE01DBD"> 
     <li id="li_F70D969F83314A94BD8567449968EE2F">Standarddimensioner </li> 
     <li id="li_6046764B19FF4679B51E55671C2C0ADB">Dimensioner för databehandling </li> 
    </ul> </td> 
   <td colname="col2"> <p>IP-adress </p> <p>IP-adress 2 </p> </td> 
   <td colname="col3"> <p>DEL-DEVICE/DEL-PERSON </p> </td> 
   <td colname="col4"> <p>Du kan inte ta bort DEL-etiketten, men du kan ändra den till antingen DEL-DEVICE eller DEL-PERSON, eller både och. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>ClickMap-åtgärd (äldre), </p> <p>ClickMap Context (äldre), </p> <p>Sida, </p> <p>Sidans URL, </p> <p>URL för ursprunglig startsida, </p> <p>Referent, </p> <p>Besök URL till startsidan </p> </td> 
   <td colname="col3"> <p>Ingen/I1/I2 </p> <p>Ingen/DEL-DEVICE / DEL-PERSON </p> </td> 
   <td colname="col4"> <p>Variabler kan innehålla URL-parametrar, som kan innehålla direkt eller indirekt identifierbara data. Om implementeringen inte samlar in direkt eller indirekt identifierbara data i dessa variabler, behöver de inte identitets- eller raderingsetiketter. </p> <p>Observera att radering tar bort URL-parametrarna, men bevarar bas-URL:en. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Borttagningshantering {#deletion}

Adobe Analytics-stöd för begäranden om borttagning av datasekretess är utformat för att minimera påverkan på rapporter. I de flesta fall ska den metrik som visas i rapporter inte ändras. En historikrapport som kördes före borttagning av datasekretess kommer att matcha samma rapportkörning efter att borttagning har utförts. Detta uppnås genom att de borttagna uppgifterna helt kopplas bort från den registrerade, samtidigt som icke-identifierbara data lämnas kvar så att de rapporterade värdena förblir konsekventa.

Följande tabell beskriver hur olika variabler tas bort. Det här är inte en fullständig lista.

| Variabler | Borttagningsmetod |
| --- | --- |
| <ul><li>Trafikvariabler (props)</li><li>eVars (handelsvariabler)</li></ul> | Befintligt värde ersätts med ett nytt värde i formatet ”Datasekretess-356396D55C4F9C7AB3FBB2F2FA223482”, där det 32-siffriga hexadecimala värdet efter prefixet ”Datasekretess-” är ett kryptografiskt starkt 128-bitars pseudoslumpmässigt nummer.<p>Eftersom det i princip ersätts av en slumpmässig sträng går det inte att fastställa det ursprungliga värdet utifrån det nya värdet och inget sätt att härleda det nya värdet med information om det ursprungliga värdet.  Om det identiska värdet som ersätts för en viss variabel förekommer i andra träffar som också tas bort som en del av samma begäran om datasekretess, kommer alla instanser av det värdet att ersättas med samma nya värde.<p>Om vissa förekomster av ett värde ersätts med en borttagningsbegäran och en senare begäran tar bort andra (nya) förekomster av det ursprungliga värdet, kommer det nya ersättningsvärdet att vara ett annat värde än det ursprungliga ersättningsvärdet. |
| Inköps-ID | Befintligt värde ersätts med ett nytt värde i formatet ”G-7588FCD8642718EC50”, där de 18 hexadecimala siffrorna efter ”G-”-prefixet är de första 18 siffrorna i ett kryptografiskt starkt 128-bitars pseudoslumpmässigt nummer. Alla kommentarer som gäller borttagning av trafikvariabler och handelsvariabler gäller också här.<p>Inköps-ID är ett transaktions-ID vars främsta syfte är att se till att ett inköp inte krediteras två gånger, till exempel när någon uppdaterar sin sida för inköpsbekräftelse. Själva ID:t kan knyta köpet till en rad i din egen databas där köpet registreras. Det är oftast inte nödvändigt att ta bort detta ID, så det tas inte bort som standard.<p>Om du fortfarande kan knyta köpet till en användare efter att ha tagit bort din egen begäran om datasekretess, kan du behöva ta bort det här fältet, så att analysdata för den här besökaren inte kan knytas tillbaka till köparen. |
| Besökar-ID | Värdet är ett 128-bitars heltal och ersätts med ett kryptografiskt starkt 128-bitars pseudoslumpmässigt värde. |
| <ul><li>MCID</li><li>Anpassat besökar-ID</li><li>IP-adress</li><li>IP-adress 2 | Värdet rensas (anges till antingen den tomma strängen eller 0 beroende på variabeltypen). |
| <ul><li>ClickMap-åtgärd (äldre)</li><li>ClickMap Context (äldre)</li><li>Sida</li><li>Sidans URL</li><li>URL för ursprunglig startsida</li><li>Referent</li><li>Besök URL till startsidan</li></ul> | URL-parametrar rensas/tas bort. Om värdet inte ser ut som en URL rensas värdet (anges till den tomma strängen). |
| <ul><li>Latitud</li><li>Longitud</li></ul> | Precisionen minskas till högst 1 km. |

{style=&quot;table-layout:auto&quot;}

## Variabler som inte stöder de förväntade Delete-etiketterna {#no-delete-support}

Det här avsnittet syftar till att förtydliga information om Analytics-variabler som inte stöder borttagning. Ibland tas dessa variabler bort av icke-Analytics-användare (t.ex. det juridiska teamet) som inte förstår vilken typ av data som finns i variabeln och gör felaktiga antaganden baserat på variabelns namn. Här är en lista över några av dessa variabler och varför de inte behöver tas bort, eller varför de inte behöver en viss borttagningsetikett.

| Variabel | Kommentarer |
| --- | --- |
| Nytt besökar-ID | Nytt besökar-ID är ett booleskt värde som är Sant första gången vi ser ett visst besökar-ID. Du behöver inte ta bort det när besökar-ID:t har anonymiserats. Efter anonymisering motsvarar det första gången vi ser detta anonyma ID. |
| Postnummer<p>Geo-postnummer | Postnummer anges endast för träffar med ursprung i USA. De är inte inställda för träffar från EU. Även om de är inställda ger de endast ett brett geografiskt område som gör det svårt att återidentifiera den registrerade. |
| Geo-latitud<p>Geo-longitud | Dessa tillhandahåller en grov uppskattning av platsen som härleds från IP-adressen. Detta är ungefär lika noggrant som ett postnummer, inom ett par dussin kilometer från den faktiska platsen. |
| Användaragent | Användaragenten identifierar vilken version av webbläsaren som användes. |
| Användar-ID | Anger Analytics-rapportsviten (som ett tal) som innehåller data. |
| Rapportsvit-ID | Anger namnet på Analytics-rapportsviten som innehåller data. |
| Besökar-ID<p>MCID/ECID | Dessa ID:n har en DEL-DEVICE-etikett, men det går inte att lägga till etiketten DEL-PERSON. Om du anger [!UICONTROL ID Expansion] för varje begäran kommer dessa ID:n automatiskt att tas bort för alla borttagningsbegäranden, även de som använder ett ID-PERSON.<p>Om du inte använder ID-expansion, men vill att dessa cookie-ID:n anonymiseras i träffar som innehåller ett matchande ID i en prop eller eVar, kan du kringgå den här etikettbegränsningen genom att etikettera prop eller eVar med en ID-DEVICE-etikett, även om den verkligen identifierar en person (alla DEL-PERSON-etiketter måste också ändras till DEL-DEVICE-etiketter). Då ändras den historikrapporteringen eftersom endast vissa instanser av besökar-ID eller ECID anonymiseras. |
| AMO-ID | Adobe Advertising Cloud ID är en lösningsvariabel som inte kan ändras [!UICONTROL DEL-DEVICE] label. Den fylls i från en cookie på samma sätt som besökar-ID och MCID. Den ska tas bort från träffar när dessa andra ID:n tas bort. Mer information finns i beskrivningen av dessa variabler. |

{style=&quot;table-layout:auto&quot;}

## Datumfält för åtkomstbegäranden {#access-requests}

Det finns fem standardvariabler som innehåller tidsstämplar:

| Tidsstämpel | Definition |
| --- | --- |
| Tid för träff i UTC | Den tidpunkt då Adobe Analytics mottog träffen. |
| Anpassad tid för träff i UTC | Tid då träffen inträffade, vilket för vissa mobilappar och andra implementeringar kan vara tidigare än den tidpunkt då den togs emot. Om till exempel en nätverksanslutning inte var tillgänglig när den inträffade, kan programmet hålla träffen och skicka den när en anslutning blir tillgänglig. |
| Datum och tid | Samma värde som anpassad tid för träff i UTC, men i tidszonen för rapportsviten i stället för GMT. |
| Tid för första träff i GMT | Värdet för anpassad tid för träff i UTC för den första träffen som tagits emot för besökar-ID-värdet för den här träffen. |
| Starttid för besök i UTC | Värdet för anpassad tid för träff i UTC för den första träffen som tagits emot för det aktuella besöket för detta besökar-ID. |

{style=&quot;table-layout:auto&quot;}

Koden för att generera de filer som returneras för åtkomstbegäranden om datasekretess kräver att minst en av de tre första tidsstämpelvariablerna inkluderas i åtkomstbegäran (har en ACC-etikett som gäller för typen av begäran). Om ingen av dessa inkluderas behandlas anpassad tid för träff i UTC som om den har en ACC-ALL-etikett.

Den CSV-fil på träffnivå som returneras för datasekretessåtkomstbegäranden konverterar värdena i dessa fält från unika tidsstämplar till datum-/tidsfält i formatet ÅÅÅ-MM-DD HH:MM:SS (t.ex. 2018-05-01 13:49:22). I den sammanfattande HTML-filen trunkeras dessa tidsstämpelvärden så att endast datumet ÅÅÅÅ-MM-DD inkluderas, vilket minskar antalet unika värden som finns för dessa fält.
