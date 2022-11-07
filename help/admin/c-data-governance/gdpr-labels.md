---
description: Exempel på dataintegritetsetiketter för Adobe Analytics-variabler
title: Datasekretessetiketter för analysvariabler
feature: Data Governance
exl-id: b8c2143a-6e8e-465a-979b-aa8176e8d4e8
source-git-commit: ac9e4934cee0178fb00e4201cc3444d333a74052
workflow-type: tm+mt
source-wordcount: '3902'
ht-degree: 96%

---

# Datasekretessetiketter för analysvariabler

## Varför sätta etiketter på dina data? {#why-label}

Många av Adobes kunder har jurister som har granskat lagarna om datasekretess (GDPR, CCPA, o.s.v.). Dessa grupper kan ha dragit egna slutsatser om hur data ska hanteras för att följa dataintegritetslagstiftningen. De juridiska tolkningarna kan skilja sig åt mellan olika företag och de önskade inställningarna för datahantering kan också skilja sig åt mellan olika kunder. Eftersom kunderna har olika preferenser för behandling av datasekretess och olika datauppsättningar, låter Adobe sina kunder, som personuppgiftsansvariga, att anpassa sina inställningar för databehandling i samband med datasekretess för sina unika data. På så sätt kan varje unik kund behandla begäranden om datasekretess på det sätt som bäst passar deras varumärke och deras unika datauppsättning.

Adobe Analytics har verktyg som används för att etikettera data utifrån känslighet och avtalsbegränsningar. Etiketter är viktiga och användbara när det gäller att (1) identifiera registrerade, (2) fastställa vilka uppgifter som ska returneras som en del av en begäran om åtkomst och (3) identifiera datafält som måste tas bort som en del av en begäran om radering.

Innan du kan ta reda på vilka etiketter som ska användas på vilka variabler/fält måste du [förstå vilka ID:n](/help/admin/c-data-governance/gdpr-analytics-ids.md) som du hämtar i dina Analytics-data, och du måste bestämma vilka som ska användas för begäranden om datasekretess.

Implementering av datasekretess i Adobe Analytics stöder följande etiketter för identitetsdata, känsliga data och datastyrning.

## DULE-etiketter {#dule-labels}

>[!NOTE]
>
>DULE-ramverket (Data Usage Labeling &amp; Enforcement) är utformat för att tillhandahålla ett enhetligt sätt att i alla Adobe-lösningar/-tjänster/-plattformar samla in, kommunicera och använda metadata om data i hela Adobe Experience Cloud. Metadata hjälper personuppgiftsansvariga att indikera vilka data som är personuppgifter, vilka data som är känsliga och vilka avtalsbegränsningar som är kopplade till data. I den här initiala versionen visar Analytics bara de DULE-etiketter som är relevanta för datasekretess. I takt med att andra Adobe-produkter implementerar stöd för DULE-etiketter, kommer framtida versioner att innehålla ytterligare känsliga dataetiketter, liksom avtalsetiketter, som säkerställer att data som delas mellan produkterna endast används på ett juridiskt tillåtet sätt.

## Etiketter för identitetsdata (DULE) {#identity-data-labels}

Identitetsdata ”I”-etiketter används för att kategorisera data som kan identifiera eller kontakta en viss person.

<table id="table_6B5368D714424E52835D5DFE189BD080"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Etikett </th> 
   <th colname="col2" class="entry"> Definition </th> 
   <th colname="col3" class="entry"> Andra krav </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>I1 </p> </td> 
   <td colname="col2"> <p><b>Direkt identifierbar</b>: Data som specifikt kan identifiera eller möjliggöra direktkontakt med en individ, till exempel ett namn eller en e-postadress. </p> </td> 
   <td colname="col3"> 
    <ul id="ul_4E2AD59D119E40D28B869D0BB63B9FD9"> 
     <li id="li_AC3E99B57E3A4AE2A12BE219680AFC58">Kan inte anges för händelser </li> 
     <li id="li_BB66992863C8402F8D58656293F31E71">Kan inte anges för marknadsförande eVars </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>I2 </p> </td> 
   <td colname="col2"> <p><b>Indirekt identifierbar</b>: Data som kan användas i kombination med andra data för att identifiera eller möjliggöra direktkontakt med en individ eller enhet. </p> <p>Tillåter inte identifiering av en enskild person, utan kan kombineras med annan information (som du kanske har tillgång till) för att identifiera någon. Exempel är ett kundlojalitetsnummer eller ett ID som används av ett företags CRM-system och som är unikt för varje kund. </p> </td> 
   <td colname="col3"> 
    <ul id="ul_A0EF0F3DC5804D4FBE228946D697ABEB"> 
     <li id="li_A592EA6DA82C4D8C80E03F02ADF4E20E">Kan inte anges för händelser </li> 
     <li id="li_46CE7B1E84884CDAB356A6DF89397849">Kan inte anges för marknadsförande eVars </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

## Etiketter för känsliga data (DULE) {#sensitive-data-labels}

Känsliga ”S”-etiketter används för att kategorisera känsliga data som geografiska data. Ytterligare etiketter för känsliga data kommer att införas i framtiden för att identifiera andra typer av känslig information.

<table id="table_A778A508620545CCB37830E5CF1C75B7"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Etikett </th> 
   <th colname="col2" class="entry"> Definition </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>S1 </p> </td> 
   <td colname="col2"> <p> Exakta geolokaliseringsdata för latitud och longitud som kan användas för att fastställa en enhets exakta placering (högst 100 meter). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>S2 </p> </td> 
   <td colname="col2"> <p> Geolokaliseringsdata som kan användas för att fastställa ett brett definierat geostaketområde. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Etiketter för datastyrning (datasekretess) {#data-governance-labels}

Etiketter för datastyrning ger användarna möjlighet att klassificera data som avspeglar sekretessrelaterade överväganden och avtalsvillkor så att de överensstämmer med regler och företagspolicyer.

### Etiketter för datasekretess

<table id="table_663EFF43A454498386F7F3E60875E0F8"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Etikett </th> 
   <th colname="col2" class="entry"> Definition </th> 
   <th colname="col3" class="entry"> Andra krav </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Ingen </p> </td> 
   <td colname="col2"> <p>Välj det här alternativet om den här variabeln inte innehåller data som måste inkluderas i data som skickas till den registrerade som en del av en begäran om datasekretess. </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ACC-ALL </p> </td> 
   <td colname="col2"> <p>Värdena i det här fältet ska inkluderas i <u>alla</u> begäranden om datasekretess. </p> <p>Om den här träffen kommer från en enhet som delas av flera personer, kan du i egenskap av personuppgiftsansvarig, genom att tillämpa den här etiketten, indikera att det är acceptabelt att dela data i det här fältet med alla som har åtkomst till den delade enheten. </p> </td> 
   <td colname="col3"> <p>Fält med den här etiketten returneras för alla begäranden om datasekretess. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ACC-PERSON </p> </td> 
   <td colname="col2"> <p> Värdena i det här fältet ska endast inkluderas för åtkomstbegäranden om datasekretess när vi är någorlunda säkra på att träffen kom från den registrerade, vilket fastställts av ett ID för begärande om datasekretess som matchar värdet för ett ID-PERSON-fält. </p> </td> 
   <td colname="col3"> <p>Du måste också ha en ID-PERSON-etikett angiven för en viss variabel i den här rapportsviten, och skicka begäranden med det ID:t, annars kommer den här etiketten aldrig att gälla. </p> </td> 
  </tr> 
 </tbody> 
</table>

Även om få variabler mottar någon av de andra etiketterna, förväntas åtkomstetiketter tillämpas för många av dina variabler. Men det är upp till dig, i samråd med din juridiska avdelning, att avgöra vilka uppgifter du har samlat in som ska delas med de registrerade.

### Borttagningsetiketter för datasekretess

<table id="table_59DFCE4D90214CB5972BDDE5B7391B4D"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Etikett </th> 
   <th colname="col2" class="entry"> Definition </th> 
   <th colname="col3" class="entry"> Andra krav </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> </td> 
   <td colname="col2"> <p>Till skillnad från de andra etiketterna utesluter inte dessa borttagningsetiketter varandra. Du kan välja antingen båda eller ingen. Det behövs ingen separat Ingen-etikett, eftersom Ingen indikeras om du inte markerar något av Ta bort-alternativen. </p> </td> 
   <td colname="col3"> <p>En borttagningsetikett krävs endast för fält som innehåller ett värde som skulle göra det möjligt att koppla en träff till den registrerade (d.v.s. som skulle göra det möjligt att identifiera den registrerade). </p> <p> Andra personuppgifter (favoriter, webbsurfnings-/inköpshistorik, hälsovillkor, o.s.v.) behöver inte tas bort eftersom associationen med den registrerade kommer att tas bort. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>DEL-DEVICE </p> </td> 
   <td colname="col2"> <p>För begäran om borttagning av datasekretess ska värdena i det här fältet endast anonymiseras för begäranden där en angiven ID-DEVICE finns i träffen. </p> <p>Om samma värde används för andra träffar, som inte tas bort, ändras inte de andra instanserna. Detta resulterar i att antalet ändras för rapporter som beräknar unika antal i det här fältet. Detta kan ta bort identifierare för andra personer på delade enheter, utöver bara den registrerade. </p> <p>Antalet ändras inte om det här fältet även har en ID-DEVICE-etikett och värdet i det här fältet användes som ID för begäran om datasekretess. </p> </td> 
   <td colname="col3"> 
    <ul id="ul_45C3A09E1F05492B97C3F3DEA7C78FBC"> 
     <li id="li_BAB277F92F284ADE9D7B6839BDD716E2">Kräver även etiketten I1, I2 eller S1 </li> 
     <li id="li_6DDFC0571457489CBA9D76F547247F20">Kan inte anges för händelser </li> 
     <li id="li_E79C6DFC6C58478EAA1504E3820D512C">Kan inte anges för marknadsförande eVars </li> 
     <li id="li_B78E273212E447D49D0707E174B66DEC">Kan inte anges för klassificeringar </li> 
     <li id="li_F0F52D0DE7454557A6A97063C1FBC372">Du måste skicka begäranden med en ID-DEVICE eller ange expandID till sant, annars kommer den här etiketten aldrig att gälla. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>DEL-PERSON </p> </td> 
   <td colname="col2"> <p>För begäran om borttagning av datasekretess ska värdena i det här fältet endast anonymiseras för begäranden där en angiven ID-PERSON finns i träffen. </p> <p>Om samma värde används för andra träffar, som inte tas bort, ändras inte de andra värdena. Detta resulterar i att antalet ändras för rapporter som beräknar unika antal i det här fältet. Antalet ändras inte om det här fältet även har en ID-PERSON-etikett och värdet i det här fältet användes som ID för begäran om datasekretess. </p> </td> 
   <td colname="col3"> 
    <ul id="ul_6722E42E036E47B4B5E17DC213636D51"> 
     <li id="li_6C1A64FF68AF428A827D8C6C33E22970">Kräver även etiketten I1, I2 eller S1 </li> 
     <li id="li_8053533FFE874EE795C8B6043A4F73B3">Kan inte anges för händelser </li> 
     <li id="li_D6700CF4D03E44DDA83C4DDBB5B70CC3">Kan inte anges för marknadsförande eVars </li> 
     <li id="li_B6C2B15484B344889DBF29B62E2EA8FD">Kan inte anges för klassificeringar </li> 
     <li id="li_3BBD0C27D9644C2B9618457A0BFC15EF">Du måste också ha en ID-PERSON-etikett angiven för en viss variabel i den här rapportsviten, och skicka begäranden med det ID:t, annars kommer den här etiketten aldrig att gälla. </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

### Identitetsetiketter för datasekretess

<table id="table_F6BBC868457443A19A7B693BD6C55B4B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Etikett </th> 
   <th colname="col2" class="entry"> Definition </th> 
   <th colname="col3" class="entry"> Andra krav </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Ingen </p> </td> 
   <td colname="col2"> <p>Den här variabeln innehåller inte något ID som ska användas för begäranden om datasekretess. </p> </td> 
   <td colname="col3"> <p>Du behöver bara ange en av dessa andra etiketter om det här fältet innehåller ett ID som du använder när du skickar in åtkomst- eller borttagningsbegäranden via [Privacy Service API](https://experienceleague.adobe.com/docs/experience-platform/privacy/api/overview.html) eller användargränssnittet. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID-DEVICE </p> </td> 
   <td colname="col2"> <p>Det här fältet innehåller ett ID som kan användas för att identifiera en enhet för en begäran om datasekretess, men det kan inte skilja mellan olika användare av en delad enhet. </p> <p>Du behöver inte ange den här etiketten för alla variabler som innehåller ID:n (det vill säga I1/I2-etiketterna). Använd den här etiketten om du skickar begäranden om datasekretess med ID:n som lagras i den här variabeln och vill söka efter det angivna ID:t i variabeln. </p> </td> 
   <td colname="col3"> 
    <ul id="ul_618019CB8FCA4A5C94C47636240197B2"> 
     <li id="li_0E5ADED36FF24A348FDD434E2CC8C8EE">Kräver även etiketten I1 eller I2 </li> 
     <li id="li_20BCFF07B2BF468C8E0D477C10B2EF9F">Kan inte anges för händelser </li> 
     <li id="li_0BD73EEF4184475D8E97878CF8DBEB90">Kan inte anges för marknadsförande eVars </li> 
     <li id="li_129851035C4A4BF0922296B4C3BEE39B">Kan inte anges för klassificeringar </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID-PERSON </p> </td> 
   <td colname="col2"> <p>Det här fältet innehåller ett ID som kan användas för att identifiera en autentiserad användare (en viss person) för en begäran om datasekretess. </p> <p>Du behöver inte ange den här etiketten för alla variabler som innehåller ID:n (det vill säga I1/I2-etiketterna). Använd den här etiketten om du ska skicka begäranden om datasekretess med ID:n som lagras i den här variabeln och vill söka efter det angivna ID:t i variabeln. </p> </td> 
   <td colname="col3"> 
    <ul id="ul_0C7EEC8FCB5C4BCDA5D48F3C98770A67"> 
     <li id="li_2E781AE8D7A046A7996C7300CA854B86">Kräver även etiketten I1 eller I2 </li> 
     <li id="li_EB4C6430C218405DAAE81DEE010DCAA2">Kan inte anges för händelser </li> 
     <li id="li_05AA67B45974474F9DA520E8B877BA11">Kan inte anges för marknadsförande eVars </li> 
     <li id="li_8A6BF4B40ED249289EAD46FE1C755FB0">Kan inte anges för klassificeringar </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

| Etikett | Definition | Andra krav |
| --- | --- | --- |
| Ingen | Den här variabeln innehåller inte något ID som ska användas för begäranden om datasekretess. | Du behöver bara ange en av de andra etiketterna om det här fältet innehåller ett ID som du använder när du skickar begäran om åtkomst eller borttagning via [Privacy Services-API](https://experienceleague.adobe.com/docs/experience-platform/privacy/api/overview.html) eller användargränssnittet. |
| ID-ENHET | Det här fältet innehåller ett ID som kan användas för att identifiera en enhet för en begäran om datasekretess, men det kan inte skilja mellan olika användare av en delad enhet.  Du behöver inte ange den här etiketten för alla variabler som innehåller ID:n (det vill säga I1/I2-etiketterna). Använd den här etiketten om du skickar begäranden om datasekretess med ID:n som lagras i den här variabeln och vill söka efter det angivna ID:t i variabeln. | Kräver även etiketten I1 eller I2.<ul><li>Kan inte anges för händelser</li><li>Kan inte anges för marknadsförande eVars</li><li>Kan inte anges för klassificeringar</li></ul> |
| ID-PERSON | Det här fältet innehåller ett ID som kan användas för att identifiera en autentiserad användare (en viss person) för en begäran om datasekretess.  Du behöver inte ange den här etiketten för alla variabler som innehåller ID:n (det vill säga I1/I2-etiketterna). Använd den här etiketten om du ska skicka begäranden om datasekretess med ID:n som lagras i den här variabeln och vill söka efter det angivna ID:t i variabeln. | Kräver även etiketten I1 eller I2.<ul><li>Kan inte anges för händelser</li><li>Kan inte anges för marknadsförande eVars</li><li>Kan inte anges för klassificeringar</li></ul> |

## Ange ett namnutrymme när du anger en variabel som ID-DEVICE eller ID-PERSON {#section_F0A47AF8DA384A26BD56032D0ABFD2D7}

När du etiketterar en variabel som ID-DEVICE eller ID-PERSON uppmanas du att ange ett namnutrymme. Du kan antingen använda ett tidigare definierat namnutrymme eller definiera ett nytt.

### Använd ett tidigare definierat namnutrymme

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

## Variabeltyperna och etiketterna för datasekretess/DULE som de stöder {#section_CE7C3EDE1344466A98BC45E394B40762}

Etiketter för datasekretess/DULE påverkar fyra breda klasser av analysvariabler. Alla variabler har inte stöd för alla etiketter. Tabellen visar vilka variabler som stöder eller inte stöder olika etiketter.

<table id="table_95D4416B3A8A40C28B2610D0003456E6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Variabeltyp </th> 
   <th colname="col2" class="entry"> Etiketter som stöds </th> 
   <th colname="col3" class="entry"> Etiketter som inte stöds </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 
    <ul id="ul_0615B545A5AD43F2A6F25698A47AAD3E"> 
     <li id="li_A4B3E8E241B149C99F2A71B21227AD72">Anpassade slutförda händelser </li> 
     <li id="li_8AEF688AE9B8426C82D199E4B195330D">Marknadsförande eVars </li> 
     <li id="li_DFFCA65DCC6146AEB6D47476B4D4CC3B">Multivärdesvariabler (mvVars) </li> 
     <li id="li_3192D08B12C249D1AAA8AAEEDE2FD7D7">Hierarkivariabler </li> 
    </ul> </td> 
   <td colname="col2"> <p>S1/S2 </p> <p>ACC-ALL, ACC-PERSON </p> </td> 
   <td colname="col3"> <p>I1/I2 </p> <p>ID-DEVICE, ID-PERSON </p> <p>DEL-DEVICE, DEL-PERSON </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Klassificeringar </p> </td> 
   <td colname="col2"> <p>I1/I2, S1/S2 </p> <p>ACC-ALL, ACC-PERSON, </p> </td> 
   <td colname="col3"> <p>ID-ENHET, ID-PERSON </p> <p>DEL-DEVICE, DEL-PERSON </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <ul id="ul_1C2FD4D606664965A88F10818E1C11A9"> 
     <li id="li_590975F5C7304317B22C80B20718E914">Trafikvariabler (props) </li> 
     <li id="li_6E614B7036994434BFDA71A4424529A0">Handelsvariabler (icke-marknadsförande eVars) </li> 
    </ul> </td> 
   <td colname="col2"> <p>Alla etiketter </p> </td> 
   <td colname="col3"> - </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>De flesta andra variablerna </p> <p><i>(Se tabellen nedan för undantag)</i> </p> </td> 
   <td colname="col2"> <p>ACC-ALL, ACC-PERSON </p> </td> 
   <td colname="col3"> <p>I1/I2, S1/S2 </p> <p>ID-ENHET, ID-PERSON </p> <p>DEL-DEVICE, DEL-PERSON </p> </td> 
  </tr> 
 </tbody> 
</table>

## Variabler som andra etiketter än ACC-ALL/ACC-PERSON kan tilldelas/ändras till {#section_4FA003003D1B4E2EBCFCDB1A7CD4A824}

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

## Hantering av borttagning {#section_F3DEE591671A4B16A8E043F91C137ECB}

Adobe Analytics-stöd för begäranden om borttagning av datasekretess är utformat för att minimera påverkan på rapporter. I de flesta fall ska den metrik som visas i rapporter inte ändras. En historikrapport som kördes före borttagning av datasekretess kommer att matcha samma rapportkörning efter att borttagning har utförts. Detta uppnås genom att de borttagna uppgifterna helt kopplas bort från den registrerade, samtidigt som icke-identifierbara data lämnas kvar så att de rapporterade värdena förblir konsekventa.

Följande tabell beskriver hur olika variabler tas bort. Det här är inte en fullständig lista.

<table id="table_A329C2E2645F4685BC208826D070A5F6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Variabler </th> 
   <th colname="col2" class="entry"> Borttagningsmetod </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>• Trafikvariabler (props) </p> <p>• eVars (handelsvariabler) </p> </td> 
   <td colname="col2"> <p>Befintligt värde ersätts med ett nytt värde i formatet ”Datasekretess-356396D55C4F9C7AB3FBB2F2FA223482”, där det 32-siffriga hexadecimala värdet efter prefixet ”Datasekretess-” är ett kryptografiskt starkt 128-bitars pseudoslumpmässigt nummer. Eftersom det i princip ersätts av en slumpmässig sträng går det inte att fastställa det ursprungliga värdet utifrån det nya värdet och inget sätt att härleda det nya värdet med information om det ursprungliga värdet. </p> <p>Om det identiska värdet som ersätts för en viss variabel förekommer i andra träffar som också tas bort som en del av samma begäran om datasekretess, kommer alla instanser av det värdet att ersättas med samma nya värde. </p> <p>Om vissa förekomster av ett värde ersätts med en borttagningsbegäran och en senare begäran tar bort andra (nya) förekomster av det ursprungliga värdet, kommer det nya ersättningsvärdet att vara ett annat värde än det ursprungliga ersättningsvärdet. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Inköps-ID </p> </td> 
   <td colname="col2"> <p>Befintligt värde ersätts med ett nytt värde i formatet ”G-7588FCD8642718EC50”, där de 18 hexadecimala siffrorna efter ”G-”-prefixet är de första 18 siffrorna i ett kryptografiskt starkt 128-bitars pseudoslumpmässigt nummer. Alla kommentarer som gäller borttagning av trafikvariabler och handelsvariabler gäller också här. </p> <p>Inköps-ID är ett transaktions-ID vars främsta syfte är att se till att ett inköp inte krediteras två gånger, till exempel när någon uppdaterar sin sida för inköpsbekräftelse. Själva ID:t kan knyta köpet till en rad i din egen databas där köpet registreras. Det är oftast inte nödvändigt att ta bort detta ID, så det tas inte bort som standard. Om du fortfarande kan knyta köpet till en användare efter att ha tagit bort din egen begäran om datasekretess, kan du behöva ta bort det här fältet, så att analysdata för den här besökaren inte kan knytas tillbaka till köparen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Besökar-ID </p> </td> 
   <td colname="col2"> <p>Värdet är ett 128-bitars heltal och ersätts med ett kryptografiskt starkt 128-bitars pseudoslumpmässigt värde. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>• MCID </p> <p>• Anpassat besökar-ID </p> <p>• IP-adress </p> <p>• IP-adress 2 </p> </td> 
   <td colname="col2"> <p>Värdet rensas (anges till antingen den tomma strängen eller 0 beroende på variabeltypen). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>• ClickMap-åtgärd (äldre) </p> <p>• ClickMap Context (äldre) </p> <p>• Sida </p> <p>• Sidadress </p> <p>• URL för ursprunglig startsida </p> <p>• Referent </p> <p>• Besök URL till startsidan </p> </td> 
   <td colname="col2"> <p>URL-parametrar rensas/tas bort. Om värdet inte ser ut som en URL rensas värdet (anges till den tomma strängen). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>• Latitud </p> <p>• Longitud </p> </td> 
   <td colname="col2"> <p>Precisionen minskas till högst 1 km. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Variabler som inte stöder de förväntade borttagningsetiketterna {#section_956B766EFFEC427E87E6CFF3A4217E86}

Det här avsnittet syftar till att förtydliga information om Analytics-variabler som inte stöder borttagning. Ibland tas dessa variabler bort av icke-Analytics-användare (t.ex. det juridiska teamet) som inte förstår vilken typ av data som finns i variabeln och gör felaktiga antaganden baserat på variabelns namn. Här är en lista över några av dessa variabler och varför de inte behöver tas bort, eller varför de inte behöver en viss borttagningsetikett.

<table id="table_6FECF3D654514862912D371E6BE4143B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Variabel </th> 
   <th colname="col2" class="entry"> Kommentarer </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Nytt besökar-ID </p> </td> 
   <td colname="col2"> <p>Nytt besökar-ID är ett booleskt värde som är Sant första gången vi ser ett visst besökar-ID. Du behöver inte ta bort det när besökar-ID:t har anonymiserats. Efter anonymisering motsvarar det första gången vi ser detta anonyma ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Postnummer </p> <p>Geo-postnummer </p> </td> 
   <td colname="col2"> <p>Postnummer anges endast för träffar med ursprung i USA. De är inte inställda för träffar från EU. Även om de är inställda ger de endast ett brett geografiskt område som gör det svårt att återidentifiera den registrerade. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Geo-latitud </p> <p>Geo-longitud </p> </td> 
   <td colname="col2"> <p>Dessa tillhandahåller en grov uppskattning av platsen som härleds från IP-adressen. Detta är ungefär lika noggrant som ett postnummer, inom ett par dussin kilometer från den faktiska platsen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Användaragent </p> </td> 
   <td colname="col2"> <p>Användaragenten identifierar vilken version av webbläsaren som användes. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Användar-ID </p> </td> 
   <td colname="col2"> <p> Anger Analytics-rapportsviten (som ett tal) som innehåller data. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Rapportsvit-ID </p> </td> 
   <td colname="col2"> <p> Anger namnet på Analytics-rapportsviten som innehåller data. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Besökar-ID </p> <p>MCID/ECID </p> </td> 
   <td colname="col2"> <p> De har en DEL-DEVICE-etikett, men det går inte att lägga till etiketten DEL-PERSON. Om du anger <a href="/help/admin/c-data-governance/gdpr-id-expansion.md">ID-expansion</a> för varje begäran tas dessa ID:n automatiskt bort för alla borttagningsbegäranden, även de som använder ett ID-PERSON. </p> <p>Om du inte använder ID-expansion, men vill att dessa cookie-ID:n anonymiseras i träffar som innehåller ett matchande ID i en prop eller eVar, kan du kringgå den här etikettbegränsningen genom att etikettera prop eller eVar med en ID-DEVICE-etikett, även om den verkligen identifierar en person (alla DEL-PERSON-etiketter måste också ändras till DEL-DEVICE-etiketter). Då ändras den historikrapporteringen eftersom endast vissa instanser av besökar-ID eller ECID anonymiseras. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>AMO-ID </p> </td> 
   <td colname="col2"> <p> Adobe Advertising Cloud ID är en lösningsvariabel som har en oföränderlig DEL-DEVICE-etikett. Den fylls i från en cookie på samma sätt som besökar-ID och MCID. Den ska tas bort från träffar när dessa andra ID:n tas bort. Mer information finns i beskrivningen av dessa variabler. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Datumfält för åtkomstbegäranden {#section_6678FB4FF42B481C9B78E64F61782397}

Det finns fem standardvariabler som innehåller tidsstämplar:

<table id="table_49A9255366254F799E1682C30CBD98EB"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Tidsstämpel </th> 
   <th colname="col2" class="entry"> Definition </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Tid för träff i UTC </p> </td> 
   <td colname="col2"> <p>Den tidpunkt då Adobe Analytics mottog träffen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Anpassad tid för träff i UTC </p> </td> 
   <td colname="col2"> <p>Tid då träffen inträffade, vilket för vissa mobilappar och andra implementeringar kan vara tidigare än den tidpunkt då den togs emot. Om till exempel en nätverksanslutning inte var tillgänglig när den inträffade, kan programmet hålla träffen och skicka den när en anslutning blir tillgänglig. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Datum och tid </p> </td> 
   <td colname="col2"> <p>Samma värde som anpassad tid för träff i UTC, men i tidszonen för rapportsviten i stället för GMT.</p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Tid för första träff i GMT </p> </td> 
   <td colname="col2"> <p>Värdet för anpassad tid för träff i UTC för den första träffen som tagits emot för besökar-ID-värdet för den här träffen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Starttid för besök i UTC </p> </td> 
   <td colname="col2"> <p>Värdet för anpassad tid för träff i UTC för den första träffen som tagits emot för det aktuella besöket för detta besökar-ID.</p> </td> 
  </tr> 
 </tbody> 
</table>

Koden för att generera de filer som returneras för åtkomstbegäranden om datasekretess kräver att minst en av de tre första tidsstämpelvariablerna inkluderas i åtkomstbegäran (har en ACC-etikett som gäller för typen av begäran). Om ingen av dessa inkluderas behandlas anpassad tid för träff i UTC som om den har en ACC-ALL-etikett.

Den CSV-fil på träffnivå som returneras för datasekretessåtkomstbegäranden konverterar värdena i dessa fält från unika tidsstämplar till datum-/tidsfält i formatet ÅÅÅ-MM-DD HH:MM:SS (t.ex. 2018-05-01 13:49:22). I den sammanfattande HTML-filen trunkeras dessa tidsstämpelvärden så att endast datumet ÅÅÅÅ-MM-DD inkluderas, vilket minskar antalet unika värden som finns för dessa fält.
