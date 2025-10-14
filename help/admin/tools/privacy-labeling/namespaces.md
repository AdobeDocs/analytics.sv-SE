---
description: Varje ID som du vill kunna söka efter tilldelas ett namnutrymme, som är en anpassad sträng som identifierar det ID:t i variabeln där det används i alla rapportsviter.
title: Namnutrymmen
feature: Data Governance
role: Admin
exl-id: 421572c2-2789-48bc-b530-d48216799724
source-git-commit: 325a42c080290509309e90c9127138800d5ac496
workflow-type: tm+mt
source-wordcount: '896'
ht-degree: 80%

---

# Namnutrymmen

Varje ID som du vill kunna söka efter tilldelas ett namnutrymme, som är en anpassad sträng som identifierar det ID:t i variabeln där det används i alla rapportsviter.

Namnutrymmessträngen används för att identifiera de fält som du vill söka i när du anger ett ID som en del av en begäran om datasekretess. När en begäran om uppgiftsskydd skickas in, kommer begäran att innehålla ett JSON-avsnitt som anger vilka ID för registrerade som ska användas för begäran. Flera ID:n kan inkluderas som en del av en enda begäran för en registrerade. JSON innehåller:

* Ett namnutrymmesfält som innehåller namnutrymmessträngen.
* Ett typfält som för de flesta Adobe Analytics-begäranden innehåller värdet ”analytics”.
* Ett värdefält som innehåller det ID som Analytics ska söka efter i de associerade namnutrymmesvariablerna från var och en av rapportsviterna.

Mer information och en [lista över standardnamnutrymmen för identiteter](https://experienceleague.adobe.com/docs/experience-platform/privacy/api/overview.html?lang=sv-SE) finns i [API-dokumentationen för Experience Cloud Data Privacy &#x200B;](https://experienceleague.adobe.com/sv/docs/experience-platform/privacy/api/appendix#standard-namespaces). Se [Skapa ett åtkomst-/borttagningsjobb](https://experienceleague.adobe.com/sv/docs/experience-platform/privacy/api/privacy-jobs#access-delete) för en exempelbegäran.

## Cookie-ID

Cookie för spårning av äldre analyser, även känt som Adobe Analytics ID (AAID):

```json
{
   "namespace": "AAID",
   "type": "standard",
   "value": "2CCEEAE88503384F-1188000089CA"
}
```

Värdet måste anges som två hexadecimala tal som avgränsas med ett bindestreck. Alla hexadecimala siffror som är alfabetiska tecken måste anges med versaler. De hexadecimala värdena får inte ha några inledande nollor (observera skillnaden från samma värde som anges i det inaktuella formuläret där inledande nollor krävs).

Det går också att använda `"namespaceId": 10` istället för, eller som tillägg till, `"namespace": "AAID"` och vissa andra Adobe-produkter använder det formuläret.

## Spårningscookie för äldre analyser: borttagen form

```json
{
   "namespace": "visitorId",
   "type": "analytics",
   "value": "2cceeae88503384f-00001188000089ca"
}
```

Värdet ska anges som två 16-siffriga hexadecimala tal eller som två 19-siffriga decimaltal. Siffrorna ska separeras med ett bindestreck, understreck eller kolon. Nollor med inledande nolla ska läggas till om någon av dem inte har tillräckligt många siffror.

## Identitetstjänstens cookie

```json
{
   "namespace": "ECID",
   "type": "standard",
   "value": "00497781304058976192356650736267671594"
}
```

Värdet måste anges som ett 38-siffrigt decimaltal. Om du hämtar det här talet från de två kolumnerna mcvisid\_high/low eller post\_msvisid\_high/low från ett dataflöde eller en Data Warehouse-rapport, måste du nollställa varje nummer till 19 siffror och sedan sammanfoga dem med det höga värdet först.

Det går också att använda `"namespaceId": 4` istället för, eller som tillägg till, `"namespace": "ECID"` och vissa andra Adobe-produkter använder det formuläret.

>[!NOTE]
>
>Experience Cloud-id:t (ECID) kallades tidigare för Marketing Cloud-id (MCID) och kallas fortfarande för det i en del befintlig dokumentation.
>
>Dessa ID:n är de enda ID:n som stöds av Analytics som använder ett annat ”type”-värde än ”analytics”.

Om formatet för värdedelen av något av dessa cookie-ID:n inte överensstämmer med formatet som beskrivs för det ID:t, kommer begäran om datasekretess att misslyckas, och visa felmeddelandet ”Värdet är ej korrekt formaterat”.

Du samlar oftast in dessa cookie-ID:n med det nya [JavaScript för sekretess](https://developer.adobe.com/experience-platform-apis/references/privacy-service/), och förser automatiskt alla relevanta nyckel-/värdepar för dessa JSON-ID:n.

JavaScript-koden fyller i JSON med andra nyckel-/värdepar utöver de som anges ovan (namnutrymme, typ, värde), men fälten som listas ovan är de viktigaste för behandling av datasekretess i Analytics och de enda som du behöver ange om du samlar in ID:n på något annat sätt.

## Anpassat besökar-ID

```json
{
    "namespace": "customVisitorID",
    "type": "analytics",
    "value": "<ID>"
}
```

Namnutrymmet är också fördefinierat för det anpassade besökar-ID:t.

## ID:n i anpassade variabler

```json
{
"namespace":"Email Address",
"type": "analytics", 
"value": "john@xyz.com" 
}, 
{
    "namespace": "CRM ID", 
    "type": "analytics",
    "value": "123456-ABCD" 
}
```

För ID:n i anpassade trafik- eller konverteringsvariabler (props eller eVars), ska du etikettera variabeln med en ID-DEVICE- eller ID-PERSON-etikett och tilldela sedan namnet på ditt eget namnutrymme till den typen av ID. Se [Ange ett namnutrymme när du anger en variabel som ID-DEVICE eller ID-PERSON.](/help/admin/tools/privacy-labeling/labels.md)

Du kan också se namnutrymmen som du tidigare har definierat för andra variabler eller rapportsviter och återanvända en av dem, så att samma namnutrymme enkelt kan användas för alla rapportsviter som lagrar den typen av ID. Det går också att tilldela samma namnutrymme till flera variabler i en rapportsvit. En del kunder lagrar till exempel ett CRM-ID i en trafikvariabel och en konverteringsvariabel (beroende på sidan är det ibland i den ena eller båda), och de kan tilldela båda variablerna namnutrymmet CRM-ID.

>[!TIP]
>
>Undvik att använda ett eget namn för en variabel (namnet som visas i rapportgränssnittet) eller variabelns nummer (till exempel eVar12) när du anger namnutrymmet till API:t för dataintegritet, såvida det inte är det namnutrymme som anges när etiketten ID-DEVICE eller ID-PERSON används. Om du använder ett namnutrymme i stället för ett eget namn kan samma block för användaridentitet ange rätt variabel för flera rapportsviter. Om ID:t till exempel finns i olika eVars i vissa av rapportsviterna, eller om de egna namnen inte stämmer överens (till exempel när det egna namnet har lokaliserats för en viss rapportsvit).

>[!CAUTION]
>
>Namnutrymmena `visitorId` och `customVisitorId` är reserverade för att identifiera den äldre Analytics-spårningscookien och Analytics-kundens besökar-ID. Använd inte dessa namnutrymmen för anpassade trafikvariabler och konverteringsvariabler.

Mer information finns i [Ange ett namnutrymme när du anger en variabel som ID-DEVICE eller ID-PERSON.](/help/admin/tools/privacy-labeling/labels.md)
