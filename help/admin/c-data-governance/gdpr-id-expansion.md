---
description: 'De ID:n du skickar in omfattar inte alltid alla träffdata som Analytics kan koppla till den registrerade. Analytics kan skapa en utökad uppsättning ID:n för att inkludera associerade data i förfrågningarna om dataintegritet. Du kan begära det här alternativet med en valfri parameter för varje datasekretessbegäran som du skickar, som läggs till i JSON-begäran '
title: ID-expansion
uuid: 2672d17d-c957-4e08-8dd9-16d54bf2be18
translation-type: tm+mt
source-git-commit: 12a7452337307ca019c005dc20e3b551d96e1289

---


# ID-expansion

De ID:n du skickar in omfattar inte alltid alla träffdata som Analytics kan koppla till den registrerade. Analytics kan skapa en utökad uppsättning ID:n för att inkludera associerade data i förfrågningarna om dataintegritet. Du kan begära det här alternativet med en valfri parameter till varje begäran om dataskydd som du skickar, som läggs till i JSON-begäran:

```
"expandIds": true
```

JSON-exempelbegäran [innehåller ett exempel på hur du tar med det här alternativet i](/help/admin/c-data-governance/gdpr-submit-access-delete.md#sample-json-request) begäran. Mer information finns i API-dokumentationen för [sekretesstjänsten](https://www.adobe.io/apis/experienceplatform/gdpr.html).

<table id="table_A10CA8DC8C1643CF84A4DF30A6740D51"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Typ </th> 
   <th colname="col2" class="entry"> Överväganden </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Utökning av cookie-ID </p> </td> 
   <td colname="col2"> <p>Många analyskunder använde ursprungligen (äldre) <a href="https://marketing.adobe.com/resources/help/en_US/whitepapers/cookies/cookies_analytics.html"> Analytics Cookie </a>men använder nu <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/"> Identity Service (ECID) </a>, som tidigare kallades Marketing Cloud ID Service (MCID). För webbplatsbesökare som först besökte efter övergången finns endast ECID. För dem som först besökte när endast den gamla cookien fanns tillgänglig, men sedan besökt den: vissa av deras data kommer att ha båda cookies, men de äldre data kommer endast att ha Analytics Cookie, och i sällsynta fall har de senaste data bara ett ECID. </p> <p>Du måste se till att du hittar alla data för en besökare som identifieras via en cookie eller ett ECID för Analytics (Visitor ID). Om du för närvarande använder ECID och tidigare använde Analytics Cookie bör du därför, när du skickar en begäran med någon typ av ID, inkludera båda ID:n i begäran eller ange alternativet expandIds. När du anger expandIds söker Adobe efter andra ECID:n eller Analytics-cookies som motsvarar de cookie-ID:n du anger. Begäran utökas automatiskt så att den innehåller dessa nyligen identifierade cookie-ID:n. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Expandering av anpassat ID till cookie-ID </p> </td> 
   <td colname="col2"> <p>På webbplatser för e-handel är det inte ovanligt att en besökare bläddrar runt på webbplatsen, lägger till saker i kundvagnen och sedan startar utcheckningsprocessen innan de loggar in på webbplatsen. Om ID:t som används för att identifiera användare för en datasekretessbegäran lagras i en anpassad variabel endast när användaren är inloggad, kommer denna förinloggningsaktivitet inte att kopplas till ID:t. Genom att använda Analytics-cookie-ID:t kan kunderna välja att associera den surfning som utfördes före inloggningen med köpet efter inloggning, eftersom cookie-ID:t finns kvar vid inloggningen. </p> <p>Låt oss anta att implementeringen lagrar ett användar-ID (CRM-ID, användarnamn, förmånsnummer, e-postadress osv., eller en hash av något av dessa värden) i en anpassad variabel (prop eller eVar) eller ett anpassat besökar-ID, och sedan använder detta ID för en begäran om dataintegritet. Den registrerade kan bli förvånad över att information om all sin surfning inte returneras som en del av en åtkomstbegäran, särskilt om du har befordrat objekt som visas men ännu inte har köpts. </p> <p>Analytics Data Privacy Processing stöder därför ID Expansion, där Analytics hittar alla cookie-ID:n som finns i samma träff som ett anpassat ID och sedan utökar begäran så att även dessa ID:n inkluderas. </p> <p>När expandID:n anges tillsammans med andra namnområden än en cookie-namnrymd, utökas begäran så att den inkluderar alla cookie-ID:n (ECID eller Analytics Cookie) som hittas i träffar som innehåller något av de angivna ID:n. Utökning av cookie-ID, enligt beskrivningen ovan, utförs sedan på alla nyligen hittade cookie-ID:n. </p> <p>När alternativet expandID används för en åtkomstbegäran och det angivna ID:t har etiketten ID-PERSON, returneras två uppsättningar filer. Den första uppsättningen (personuppsättningen) innehåller endast data från träffar där det angivna ID:t hittades. Den andra uppsättningen (enhetsuppsättningen) innehåller endast data från träffar från expanderade ID:n, där det angivna ID:t inte fanns. </p> </td> 
  </tr> 
 </tbody> 
</table>

Under de första månaderna efter det att dataintegriteten publicerades begärde de allra flesta förfrågningar om dataintegritet i Analytics inte någon ID-expansion, men det är upp till dig att avgöra vilket värde som passar din organisation. Du bör rådfråga ditt juridiska team om huruvida ID-expansion krävs för dina data med de ID:n du använder och de data du samlar in i Adobe Analytics. En viktig faktor bör vara att på en delad enhet, från vilken flera användare har besökt platsen, kommer ID-expansion att inkludera data från träffar från andra användare av enheten i data som returneras av åtkomstbegäranden (i enhetsfilen). Även om du har följt god praxis när det gäller etiketter, så att inga privata data inkluderas i enhetsfilen, t.ex. besökta sidor, innehåller enhetsfilen antalet besökta sidor och tiderna för varje besök. Går det bra att du delar informationen med någon som inte har varit besökare?

Om du använder ett icke-cookie-ID (något annat ID än ECID eller Analytics-cookie) för att identifiera träffar som ska tas bort, och ID:t har en ID-DEVICE-etikett, ändras antalet unika besökare i rapporter, eftersom endast vissa instanser av cookie-ID:n kommer att anonymiseras medan andra kommer att ändras. Om du inte anger ID-expansion bör du antingen använda ett cookie-ID för begäranden eller använda ID:n med en ID-PERSON-etikett.

När Adobe utför en ID-expansion kan det kräva ytterligare en fullständig datagranskning, vilket ökar den tid det tar för Adobe att slutföra begäran, ofta med en vecka längre.

## Flaggor för begäran om annan dataintegritet

Förutom flaggan&quot;expandIDs&quot; stöder Analytics två andra flaggor som kan skickas som en del av en begäran om dataintegritet. Följande flaggor med standardvärden är:

```
"analyticsDeleteMethod": "anonymize"
"priority": "normal"
```

I framtiden kan &quot;analyticsDeleteMethod&quot; ha stöd för värdet &quot;purge&quot; förutom standardvärdet för &quot;anonymisze&quot;. Om det stöds kommer hela träffen att tas bort i stället för att bara värdena för träfffält som har DELL-etiketter uppdateras.

Förutom standardvärdet stöder fältet priority även värdet &quot;low&quot;. Du bör ange det här värdet för förfrågningar som inte är ett resultat av en begäran från en registrerad och som därför inte har något rättsligt krav på att slutföras inom 30 dagar. Observera att Adobe avråder från att använda API:t för integritetstjänster av andra orsaker än förfrågningar som initierats av registrerade. Sekretesstjänstens API är inte ett lämpligt verktyg för datarensning eller -reparationer och kommer att få oönskade konsekvenser.

> [!NOTE] API:t för [sekretesstjänsten](https://www.adobe.io/apis/experienceplatform/gdpr.html) har tillhandahållits för att hjälpa dig att uppfylla datasekretessbegäranden, som är tidskänsliga. Att använda detta API för andra syften stöds inte av Adobe och kan påverka Adobes förmåga att tillhandahålla vältajmade, användarinitierade förfrågningar om dataintegritet för andra Adobe-kunder. Vi ber dig att inte använda API:t för sekretesstjänster för andra syften, till exempel att radera data som av misstag har skickats in över stora grupper av besökare.

Du bör också vara medveten om att alla besökare som har en träff som har tagits bort (uppdaterats eller anonymiserats) som ett resultat av en begäran om borttagning av datasekretess kommer att få sin tillståndsinformation återställd. Nästa gång besökaren återvänder till webbplatsen blir han eller hon en ny besökare. All eVar-attribuering kommer att starta igen, liksom information som besöksnummer, referenter, besökt första sidan osv. Den här biverkningen är inte önskvärd i situationer där du vill ta bort datafält och visar en anledning till varför API:t för sekretesstjänsten inte är lämpligt för den här användningen.

Kontakta er Account Manager (CSM) för att samordna med vårt konsultteam inom Engineering Architect för ytterligare granskning och åtgärder för att ta bort eventuella PII- eller dataproblem.

