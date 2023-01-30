---
description: De ID:n du skickar in omfattar inte alltid alla data för träffar som Analytics kan koppla till den registrerade. Analytics kan skapa en utökad uppsättning ID:n för att inkludera associerade data i begäranden om datasekretess. Du kan begära det här alternativet med en valfri parameter för varje begäran om datasekretess som du skickar, vilken läggs till i JSON-begäran
title: ID-expansion
feature: Data Governance
exl-id: 312a249f-e0e7-44da-bb3d-b19f1bb4c706
source-git-commit: e9fffe62d3e53ae075610b1feec9a9071d925433
workflow-type: tm+mt
source-wordcount: '1327'
ht-degree: 43%

---

# ID-expansion

De ID:n du skickar in omfattar inte alltid alla data för träffar som Analytics kan koppla till den registrerade. Analytics kan skapa en utökad uppsättning ID:n för att inkludera associerade data i begäranden om datasekretess. Du kan begära det här alternativet med en valfri parameter för varje begäran om datasekretess som du skickar, vilken läggs till i JSON-begäran:

```
"expandIds": true
```

Mer information finns i [API-dokumentationen för sekretesstjänsten](https://experienceleague.adobe.com/docs/experience-platform/privacy/api/overview.html).


| Typ | Överväganden |
| --- | --- |
| Cookie-ID-expansion | Många analyskunder använde ursprungligen (äldre) [Analytics Cookie](https://experienceleague.adobe.com/docs/core-services/interface/administration/ec-cookies/cookies-privacy.html?lang=en), men använder nu [Experience Cloud Identity Service (ECID)](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=en). För webbplatsbesökare som först besökte efter övergången finns endast ECID. För dem som först besökte när endast den gamla cookien fanns tillgänglig, men sedan besökt den: vissa av deras data har båda cookies. Äldre data har dock bara Analytics Cookie, och i sällsynta fall har de senaste data bara ett ECID.<p>Se till att du hittar alla data för en besökare som identifieras via en cookie eller ett ECID för analyser (Visitor ID). Om du för närvarande använder ECID och tidigare har använt Analytics Cookie bör du, när du skickar en begäran med någon typ av ID, inkludera båda ID:n i begäran eller ange `expandIds` alternativ. När du anger `expandIds`söker Adobe efter andra ECID:n eller Analytics-cookies som motsvarar de cookie-ID:n du anger. Begäran utökas automatiskt så att den innehåller dessa nyligen identifierade cookie-ID:n. |
| Anpassat ID till cookie-ID-expansion | Det är vanligt att besökare på webbplatser för e-handel söker runt, lägger till saker i kundvagnen och sedan startar utcheckningsprocessen innan de loggar in på webbplatsen. Om det ID som används för att identifiera användare för en datasekretessbegäran lagras i en anpassad variabel endast när användaren är inloggad, är den här förinloggningsaktiviteten inte kopplad till ID:t. Kunderna kan använda Analytics-cookie-ID:t för att associera den surfning som utfördes före inloggningen med köpet efter inloggning, eftersom cookie-ID:t finns kvar vid inloggningen.<p>Låt oss anta att implementeringen lagrar ett användar-ID (CRM-ID, användarnamn, förmånsnummer, e-postadress, o.s.v., eller en hash av något av dessa värden) i en anpassad variabel (prop eller eVar) eller ett anpassat besökar-ID, och sedan använder detta ID för en begäran om datasekretess. Den registrerade kan bli förvånad över att information om all sin surfning inte returneras som en del av en åtkomstbegäran, särskilt om du har befordrat objekt som visats men ännu inte köpts. Behandling av Analytics-datasekretess stöder därför ID-expansion, vilket innebär att Analytics hittar alla cookie-ID:n som finns i samma träff som ett anpassat ID och sedan utökar begäran så att även dessa ID:n inkluderas.<p>När `expandIDs` anges tillsammans med andra namnområden än ett cookie-namnutrymme, utökas begäran så att den innehåller alla cookie-ID:n (ECID eller Analytics Cookie) som finns i träffar som innehåller något av de angivna ID:n. Utökning av cookie-ID, enligt beskrivningen ovan, utförs sedan på alla nyligen hittade cookie-ID:n.<p>När `expandIDs` -alternativet används för en åtkomstbegäran och det angivna ID:t har etiketten ID-PERSON, och två filuppsättningar returneras. Den första uppsättningen (personuppsättningen) innehåller endast data från träffar där det angivna ID:t hittades. Den andra uppsättningen (enhetsuppsättningen) innehåller endast data från träffar från expanderade ID:n, där det angivna ID:t inte fanns. |

{style=&quot;table-layout:auto&quot;}

## När ID-expansion ska användas

Under de första månaderna efter det att dataintegriteten publicerades begärde de allra flesta förfrågningarna om dataintegritet i Analytics inte någon ID-expansion. Det är dock upp till dig att avgöra vilket värde som passar din organisation. Du bör rådfråga ditt juridiska team om huruvida ID-expansion krävs för dina data med de ID som du använder och de data som du samlar in inom Adobe Analytics.

Det viktigaste bör vara att På en delad enhet, från vilken flera användare har besökt din plats, inkluderar ID-expansion data från andra användares träffar på enheten i data som returneras av åtkomstbegäranden (i enhetsfilen). Även om du har följt vedertagna standarder för etikettering (till exempel om inga privata data inkluderas i enhetsfilen, till exempel besökta sidor) innehåller enhetsfilen antalet besökta sidor och tidpunkterna för varje besök. Fråga dig själv: Går det bra att du delar informationen med någon som inte har varit besökare?

När ID-expansion *not* används för en borttagningsbegäran: Om du använder ett icke-cookie-ID (något annat ID än ECID- eller Analytics-cookie) för att identifiera träffar som ska tas bort och det ID:t har en ID-DEVICE-etikett, ändras antalet unika besökare i rapporter. Detta beror på att endast vissa instanser av cookie-ID:n kommer att anonymiseras, medan andra kommer att lämnas oförändrade. Om du inte anger ID-expansion rekommenderar vi att du antingen använder ett cookie-ID för begäranden eller använder ID:n med en ID-PERSON-etikett.

När Adobe utför ID-expansion kan det kräva en ytterligare fullständig datasökning. Detta gör att det tar längre tid för Adobe att slutföra begäran, vilket ofta lägger till en vecka till bearbetningstiden.

## Andra flaggor för begäran om datasekretess

Förutom flaggan ”expandIDs” stöder Analytics två andra flaggor som kan skickas som en del av en begäran om datasekretess. Följande flaggor med standardvärden är:

```
"analyticsDeleteMethod": "anonymize"
"priority": "normal"
```

I framtiden kommer `analyticsDeleteMethod` kan ha stöd för värdet&quot;purge&quot; utöver standardvärdet för&quot;anonymisze&quot;. Om det stöds tas hela träffen bort, i stället för att värdena för träfffält med DELL-etiketter uppdateras.

Förutom standardvärdet `priority` -fältet har också stöd för värdet &quot;low&quot;. Du bör ange det här värdet för begäranden som inte beror på en begäran från en registrerad person och som därför inte måste slutföras inom 30 dagar enligt lagen.

## Användning av Privacy Service-API

>[!IMPORTANT]
>
>Adobe avråder från att använda [Privacy Services-API](https://experienceleague.adobe.com/docs/experience-platform/privacy/api/overview.html) av andra skäl än förfrågningar som initierats av en registrerade. API:t för sekretesstjänsten är inte ett lämpligt verktyg för datarensning eller reparationer och kommer att ha oönskade konsekvenser. Privacy Services-API:t tillhandahölls för att hjälpa er att uppfylla datasekretessbegäranden, som är tidskänsliga. Adobe stöder inte att detta API används för andra syften och det kan påverka Adobes förmåga att tillhandahålla användarinitierade begäranden om datasekretess i god tid för andra Adobe-kunder. Vi ber dig att inte använda API:t för sekretesstjänsten för andra syften, som att rensa data som av misstag har skickats in till stora grupper av besökare.

Du ska också vara medveten om att alla besökare som har en träff som har tagits bort (uppdaterats eller anonymiserats) efter en borttagningsbegäran om datasekretess kommer att få sin tillståndsinformation återställd. Nästa gång besökaren återvänder till webbplatsen blir han eller hon en ny besökare. All eVar-attribuering startar på nytt, liksom information som besöksnummer, referenter, första besökta sidan, o.s.v. Denna bieffekt är inte önskvärd i situationer där du vill ta bort datafält och är en anledning till varför API:t för sekretesstjänsten inte är lämpligt för detta ändamål.

Kontakta er Account Manager (CSM) för att samordna med vårt konsultteam inom Engineering Architect för att få mer information och för att åtgärda eventuella PII- eller dataproblem.
