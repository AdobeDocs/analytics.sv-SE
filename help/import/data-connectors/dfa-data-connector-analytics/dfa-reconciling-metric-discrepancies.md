---
description: Ibland kan vissa mätvärden inte ligga inom en acceptabel skillnad när Adobe Analytics-värden jämförs med DFA-värden. Nedan finns en lista med måttdefinitioner och möjliga orsaker till avvikelser.
keywords: DFA
title: Stämma av avvikelser i mätvärden
feature: Data Connectors
uuid: aa3ca006-d3cf-410e-a000-781ab17fb9e3
exl-id: bfe0f9cb-1bbc-40f9-b996-0002d5143889
translation-type: tm+mt
source-git-commit: 78412c2588b07f47981ac0d953893db6b9e1d3c2
workflow-type: tm+mt
source-wordcount: '1270'
ht-degree: 0%

---

# Stämma av avvikelser i mätvärden{#reconciling-metric-discrepancies}

Ibland kan vissa mätvärden inte ligga inom en acceptabel skillnad när Adobe Analytics-värden jämförs med DFA-värden. Nedan finns en lista med måttdefinitioner och möjliga orsaker till avvikelser.

Detta avsnitt innehåller följande ämnen:

## Måttdefinitioner{#metric-definitions}

Adobe använder följande termer när de pratar om mått för DFA-integrering:

**Impressions**: Impressions avser det antal gånger en annons visats. Impressions rapporteras per annons, men kan också samlas i annonsgrupper eller andra grupper med flera annonser. Avsiktsmåtten i Analytics importeras från DFA via en import från datakällor på natten.

**Klicka**: Klickningar avser det antal gånger en annons klickades, enligt en rapport från DFA. Klickningar registreras på DFA:s omdirigeringssida innan besökaren landar på kundens webbplats. I likhet med visningar importeras klickmätvärdena i Analytics från DFA via import från en nightly datakälla.

**Klickningsförflyttningar**: Klicka-för-klick anger hur många gånger användaren har kommit till landningssidan efter att ha klickat på en annons. Det här måttet kan skilja sig något från klickningar.

**Visa-Över**: Visa-Över anger hur många gånger en besökare kom till kundens webbplats efter att ha tittat på en annons, men inte klickat på annonsen. Besökaren måste bege sig till webbplatsen inom det genomskinliga fönstret, som som standard är inställt på 30 dagar. Det här intrycket måste ha inträffat senare än den senaste klickningen. Genomvisningar registreras en gång per kampanj och besök och räknas när eVar fyller i genomgången med DFA-kampanj-ID:t och händelsen view-through ställs in.

## Möjliga orsaker till avvikelser{#possible-reasons-for-discrepancies}

Visar en lista med orsaker till varför datameddelanden kan uppstå mellan Adobe Analytics- och DFA-rapporter.

### Användare i Safari-webbläsaren och andra webbläsare som blockerar cookies från tredje part {#section-4b0dc429a54a4744a33976b0bb2d1b2a}

Godkännande av cookies från tredje part är vanligtvis den största orsaken till diskrepans mellan Adobe Analytics och DFA. Safari och vissa andra webbläsare blockerar cookies från tredje part som standard. Det innebär att Safari som standard accepterar cookie-filen från första part som används av de flesta analysimplementationer, men avvisar den cookie-fil från tredje part som används av DFA.

Ett urval data från våra 15-betakunder i Analytics visade att färre än 0,5 % av användarna normalt avvisar cookies från första part, medan 5-12 % avvisar cookies från tredje part (många av dessa avvisningar beror troligen på standardinställningarna för webbläsaren).

Denna avvikelse kan leda till stora skillnader i de data som samlas in av Analytics och DFA.

### Varför kan exponeringar som rapporteras i DFA vara högre än vad som rapporteras i Adobe Analytics? {#section-db0ad070a65a4985bcc589b2d0d30b90}

* DFA skickar data till Adobe datainsamlingsservrar i en kvällsbatch, så att visningsdata i Analytics kan ligga upp till 2 dagar efter DFA-rapporterna.
* Adobe använder SAINT-klassificeringar för att klassificera importerade DFA-spårningskoder i olika nivåer av aggregeringar (kampanjnamn, placeringsnamn, annonsnamn osv.) Om diskrepansen uppstår när du kör en klassificeringsrapport gör du ett enkelt test för att se om klassificeringarna ännu inte har fastnat i importerade värden:

   * Leta reda på ett radobjekt med namnet &quot;Ingen&quot; i klassificeringsrapporten.
   * Gör en uppdelning av den här radobjektet med samma variabel, med hjälp av DFA ID-rapporten (till exempel Campaign ID).
   * I den här rapporten ska du notera alla oklassificerade DFA-spårningskoder som är i formatet `DFA:XXXXX:XXXXX`.
   * Om det finns många av dessa spårningskoder ska du undersöka klassificeringsprocessen för SAINT på natten.

### Varför är DFA:s klick högre än Adobe Analytics klickningar? {#section-2fce4608ed044bdc9cf812cb719d5d35}

* DFA registrerar ett klick innan besökaren kommer till kundwebbplatsen. Analysmaterialet registrerar Click-Thovers när landningssidan har lästs in och kör JavaScript-beacon för Adobe. Olikheter beror oftast på att besökaren inte kommer till landningssidan efter att DFA har spårat ett klick, eller på att `s.maxDelay`-timern möts.
* Kontrollera att alla placeringar och kreatörer i Floodlight Configuration innehåller clickThroughParam i URL:en för landningssidan (till exempel &quot;`?CID=1`&quot;). Om du inte anger den här parametern kommer Adobe Analytics JavaScript att sakna klickningar som inträffar efter besökets första träff.
* Se till att alla placeringar och kreatörer har en landningssida som är taggad med JavaScript och har DFA-integreringsmodulen, och att flyttalets konfigurations-ID på den landningssidan matchar FlowLight-konfigurations-ID:t för de hanterade annonserna. Skillnader kan ofta uppstå på grund av att startsidan för annonser är inställd på tredjepartswebbplats eller de annonser som skickas.
* Om du använder Rich Media-annonser eller Flash-annonser (swf-annonser) måste du se till att besökarens webbläsare även dirigeras om till landningssidan när du trycker på DFA-klickspåraren, där `clickThroughParam` ingår i frågesträngen. Om du inte omdirigerar webbläsaren kommer inte en klickfrekvens att spelas in.
* Timeout är instanser där DFA-data kan ha varit tillgängliga, men JavaScript fick inget svar i tid. När en besökare kommer till landningssidan begär Adobe JavaScript besökarens information från DFA:s tjänst fls.doubleclick.net. Parametern `s.maxDelay` avgör hur länge JavaScript väntar på FLS-data (Floodlight Service). Om `s.maxDelay` är för hög kan besökare lämna webbplatsen innan Adobe samlar in träffdata; vilket innebär att inga klickdata registreras. Om `s.maxDelay` är för lågt kan inte besökarens internetanslutning hämta FLS-data i tid; vilket innebär att träffen skickas till Adobe utan DFA-klickinformation.
* Punkttrafik kan öka antalet DFA-klickningar. Bots kan ha funktioner för att klicka på en annons, men de kanske inte är så komplicerade att de kör en Analytics-fyr eller utlöser den synkrona script-taggen för att läsa in Floodlight-servrarnas data. Om de här klippen inte tas bort från Clicks-figuren kan det bero på en diskrepans.
* Besökare som lämnar sidan innan `s.maxDelay` upphör att gälla och DFA-data returneras kommer att gå förlorade. inga DFA- eller besöksdata samlas in för dem.
* Analyserna försöker identifiera och ta bort dubbla klickningar så att de bara räknas en gång per kampanj och besök. DFA räknar besökare som klickar på Bakåt och går igenom annonsen flera gånger som ytterligare ACM-klick, medan Analytics inte räknar dessa som flera klickningar.
* DFA Floodlight-taggar är inte beroende av JavaScript aktiverat, medan Analytics gör det. På grund av detta kan det finnas fall där DFA registrerar en träff när Analytics inte gör det. Identifiera om detta kan vara ett problem genom att använda JavaScript-rapporten Analytics på menyn Besökarprofil.

### Varför är DFA:s efterhandsvisningsaktiviteter högre än Adobe Analytics? {#section-5daa91039c404df48b6a3447c20406f7}

* Analyserna försöker identifiera och ta bort dubbla klickningar så att de bara räknas en gång per kampanj och besök. DFA räknar besökare som klickar på Bakåt och går igenom annonsen flera gånger som ytterligare ACM-klick, medan Analytics inte räknar dessa som flera klickningar.
* DFA Floodlight-taggar är inte beroende av JavaScript inaktiverat, medan Analytics gör det. På grund av detta kan det finnas fall där DFA registrerar en träff när Analytics inte gör det.
* DFA räknar aktiviteter efter intrycket när man använder Floodlight-taggar, som kan placeras på klientens webbplats. Analytics räknar antalet visningar efter att JavaScript-beacon (bildbegäran) körs. Kodplacering på webbsidan kan avgöra om en avbruten sida läses in som en aktivitet efter intrycket eller som en genomgång.

### Vad händer om avvikelserna ligger långt utanför ett acceptabelt intervall och de möjliga orsakerna ovan inte är tillämpliga? {#section-ca50eb75dd5d4d0396f4668b44d7547c}

Kontakta din integrationskonsult, eller Adobe Client Care, för att dokumentera diskrepanserna och rapportera dem till dataanslutarnas tekniker. För att underlätta er begäran har ni 2-3 dagars data där mätvärdena jämförs (på kampanjkodnivå). Identifiera alla åtgärder som du redan har vidtagit för att stämma av avvikelsen i din begäran.
