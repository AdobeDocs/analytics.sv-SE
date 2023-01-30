---
description: De ID:n du skickar in omfattar inte alltid alla data för träffar som Analytics kan koppla till den registrerade. Analytics kan skapa en utökad uppsättning ID:n för att inkludera associerade data i begäranden om datasekretess. Du kan begära det här alternativet med en valfri parameter för varje begäran om datasekretess som du skickar, vilken läggs till i JSON-begäran
title: ID-expansion
feature: Data Governance
exl-id: 312a249f-e0e7-44da-bb3d-b19f1bb4c706
source-git-commit: 4bbed2efde0574bc9f5f6a78a022a22490e75549
workflow-type: tm+mt
source-wordcount: '1338'
ht-degree: 96%

---

# ID-expansion

De ID:n du skickar in omfattar inte alltid alla data för träffar som Analytics kan koppla till den registrerade. Analytics kan skapa en utökad uppsättning ID:n för att inkludera associerade data i begäranden om datasekretess. Du kan begära det här alternativet med en valfri parameter för varje begäran om datasekretess som du skickar, vilken läggs till i JSON-begäran:

```
"expandIds": true
```

Mer information finns i [API-dokumentationen för sekretesstjänsten](https://experienceleague.adobe.com/docs/experience-platform/privacy/api/overview.html).

<table id="table_A10CA8DC8C1643CF84A4DF30A6740D51"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Typ </th> 
   <th colname="col2" class="entry"> Överväganden </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Cookie-ID-expansion </p> </td> 
   <td colname="col2"> <p>Många Analytics-kunder använde ursprungligen (den äldre) <a href="https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-privacy.html"> Analytics-cookien </a>, men använder nu <a href="https://experienceleague.adobe.com/docs/id-service/using/home.html"> Identity Service (ECID) </a>, som tidigare kallades Marketing Cloud ID Service (MCID). För webbplatsbesökare som först besökte efter övergången finns endast ECID. Men de som besökte för första gången när endast den gamla cookien fanns tillgänglig och sedan dess har besökt igen: vissa av deras data kommer att ha båda cookies, men de äldre data kommer endast att ha Analytics-cookien, och i sällsynta fall har de senaste data bara en ECID. </p> <p>Du måste se till att du hittar alla data för en besökare som identifieras via en cookie eller ett ECID för Analytics (Visitor ID). Om du för närvarande använder ECID och tidigare använde Analytics-cookien. ska du inkludera båda ID:n i begäran eller ange alternativet expandIds när du skickar en begäran med någon typ av ID. När du anger expandIds söker Adobe efter andra ECID:n eller Analytics-cookies som motsvarar de cookie-ID:n du anger. Begäran utökas automatiskt så att den innehåller dessa nyligen identifierade cookie-ID:n. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Anpassat ID till cookie-ID-expansion </p> </td> 
   <td colname="col2"> <p>Det är vanligt att besökare på webbplatser för e-handel söker runt, lägger till saker i kundvagnen och sedan startar utcheckningsprocessen innan de loggar in på webbplatsen. Om ID:t som används för att identifiera användare för en begäran om datasekretess lagras i en anpassad variabel endast när användaren är inloggad, kommer denna förinloggningsaktivitet inte att kopplas till ID:t. Kunderna kan använda Analytics-cookie-ID:t för att associera den surfning som utfördes före inloggningen med köpet efter inloggning, eftersom cookie-ID:t finns kvar vid inloggningen. </p> <p>Låt oss anta att implementeringen lagrar ett användar-ID (CRM-ID, användarnamn, förmånsnummer, e-postadress, o.s.v., eller en hash av något av dessa värden) i en anpassad variabel (prop eller eVar) eller ett anpassat besökar-ID, och sedan använder detta ID för en begäran om datasekretess. Den registrerade kan förvånas över att information om all deras surfning inte returneras som en del av en åtkomstbegäran, särskilt om du har lyft fram artiklar som de tittat på men ännu inte köpt. </p> <p>Behandling av Analytics-datasekretess stöder därför ID-expansion, vilket innebär att Analytics hittar alla cookie-ID:n som finns i samma träff som ett anpassat ID och sedan utökar begäran så att även dessa ID:n inkluderas. </p> <p>När expandID:n anges tillsammans med andra namnutrymmen än ett cookie-namnutrymme, utökas begäran så att den inkluderar alla cookie-ID:n (ECID eller Analytics-cookien) som hittas i träffar som innehåller något av angivna ID:n. Cookie-ID-expansion, enligt beskrivningen ovan, utförs sedan på alla nyligen hittade cookie-ID:n. </p> <p>Två uppsättningar filer returneras när alternativet expandID används för en åtkomstbegäran och det angivna ID:t har etiketten ID-PERSON. Den första uppsättningen (personuppsättningen) innehåller endast data från träffar där det angivna ID:t hittades. Den andra uppsättningen (enhetsuppsättningen) innehåller endast data från träffar från expanderade ID:n, där det angivna ID:t inte fanns. </p> </td> 
  </tr> 
 </tbody> 
</table>

Under de första månaderna efter det att datasekretessen publicerats, begärde de allra flesta begäranden om Analytics-datasekretess inte någon ID-expansion, utan det är upp till dig att avgöra vilket värde som passar din organisation. Rådfråga ditt juridiska team om huruvida ID-expansion krävs för dina data med de ID:n du använder och de data du samlar in i Adobe Analytics. En viktig faktor ska vara att ID-expansion på en delad enhet, från vilken flera användare har besökt platsen, inkluderar data från träffar från andra användare av enheten i data som returneras av åtkomstbegäranden (i enhetsfilen). Även om du har följt god praxis gällande etiketter, så att inga privata data inkluderas i enhetsfilen, t.ex. besökta sidor, innehåller enhetsfilen antalet besökta sidor och tiderna för varje besök. Går det bra om du delar informationen med någon som inte har varit besökare?

Om du använder ett icke-cookie-ID (något annat ID än ECID eller Analytics-cookien) för att identifiera träffar som ska tas bort, och ID:t har en ID-DEVICE-etikett, ändras antalet unika besökare i rapporter, eftersom endast vissa instanser av cookie-ID:n kommer att anonymiseras medan andra kommer att ändras. Om du inte anger ID-expansion ska du antingen använda ett cookie-ID för begäranden eller använda ID:n med en ID-PERSON-etikett.

När Adobe utför en ID-expansion kan det kräva ytterligare en fullständig dataskanning, vilket innebär att det tar längre tid för Adobe att slutföra begäran. Detta innebär ofta att behandlingstiden förlängs med så mycket som en vecka.

## Andra flaggor för begäran om datasekretess

Förutom flaggan ”expandIDs” stöder Analytics två andra flaggor som kan skickas som en del av en begäran om datasekretess. Följande flaggor med standardvärden är:

```
"analyticsDeleteMethod": "anonymize"
"priority": "normal"
```

I framtiden kan ”analyticsDeleteMethod” stöda värdet ”rensa” utöver standardvärdet ”anonymisera”. Om det stöds kommer hela träffen att tas bort i stället för att uppdatera värdena i fälten för träffen som har DEL-etiketter.

Utöver standardvärdet stöder prioritetsfältet även värdet ”låg”. Du bör ange det här värdet för begäranden som inte beror på en begäran från en registrerad person och som därför inte måste slutföras inom 30 dagar enligt lagen. Observera att Adobe avråder från att använda API:t för sekretesstjänster av andra orsaker än begäranden som initierats av registrerade. API:t för sekretesstjänsten är inte ett lämpligt verktyg för datarensning eller reparationer och kommer att ha oönskade konsekvenser.

>[!NOTE]
>
>[API:t för sekretesstjänsten](https://experienceleague.adobe.com/docs/experience-platform/privacy/api/overview.html) har tillhandahållits för att hjälpa dig att uppfylla begäranden om datasekretess, vilka är tidskänsliga. Adobe stöder inte att detta API används för andra syften och det kan påverka Adobes förmåga att tillhandahålla användarinitierade begäranden om datasekretess i god tid för andra Adobe-kunder. Vi ber dig att inte använda API:t för sekretesstjänsten för andra syften, som att rensa data som av misstag har skickats in till stora grupper av besökare.

Du ska också vara medveten om att alla besökare som har en träff som har tagits bort (uppdaterats eller anonymiserats) efter en borttagningsbegäran om datasekretess kommer att få sin tillståndsinformation återställd. Nästa gång besökaren återvänder till webbplatsen blir han eller hon en ny besökare. All eVar-attribuering startar på nytt, liksom information som besöksnummer, referenter, första besökta sidan, o.s.v. Denna bieffekt är inte önskvärd i situationer där du vill ta bort datafält och är en anledning till varför API:t för sekretesstjänsten inte är lämpligt för detta ändamål.

Kontakta din Account Manager (CSM) för att samordna med vårt konsultteam inom Engineering Architect för ytterligare granskning och åtgärder för att lösa eventuella PII- eller dataproblem.
