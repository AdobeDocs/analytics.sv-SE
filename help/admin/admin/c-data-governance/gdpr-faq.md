---
description: Vanliga frågor om datahantering i Adobe Analytics
title: Frågor och svar om datahantering
feature: Data Governance
role: Admin
exl-id: 57399c1b-cf08-405b-8c1b-9d23e4c38716
source-git-commit: 43c39b99cbae3e714b7f017dec14dd02fa350790
workflow-type: tm+mt
source-wordcount: '2042'
ht-degree: 38%

---

# Frågor och svar

+++ **Hur stöder Adobe Analytics åtkomst- och borttagningsbegäranden för slutanvändare (registrerade) som validerats av kunder (personuppgiftsansvariga)?**

När olika dataskyddsregler (GDPR, CCPA) börjar gälla kommer Adobe Analytics att stödja behandling av verifierade begäranden som skickas av datakontrollanter till API:t för dataintegritet i Experience Cloud för att möjliggöra en mer automatiserad process. Adobes API för datasekretess är utformat för att underlätta behandling av enskilda begäranden om rättigheter (t.ex. begäranden om åtkomst och borttagning) för våra kunders data som lagras i Adobe Experience Cloud-lösningar. Det är flexibelt och skalas efter antalet dataåtkomstbegäranden och borttagningsbegäranden som ditt företag får från registrerade.

Privacy Services-API:t gör det även möjligt för kunden att kontrollera status för hur förfrågningar om dataåtkomst och -borttagning uppfylls. Mer information finns i dokumentationen för [Privacy Service-API](https://developer.adobe.com/experience-platform-apis/references/privacy-service/).

+++

+++ **Vem ansvarar för att ta emot, godkänna och uppfylla begäranden om datasekretess från slutanvändare?**

Datakontrollanten har det enda ansvaret för att ta emot och godkänna begäranden. Datakontrollen validerar den registrerade personens identitet och uppfyller sedan begäran. En del av detta ansvar kan inbegripa att kontakta Adobe med de registrerade personernas ID som kan kopplas till data som lagras i Adobe Analytics.

Som databehandlare måste Adobe ge styrenheten rimlig hjälp att behandla verifierade förfrågningar inom en acceptabel tidsperiod.

+++

+++ **Hur får Adobe-kunder (personuppgiftsansvariga) reda på vilka begäranden om datasekretess som mappas till vilka ID:n i Adobe Analytics för datasekretess?**

Datakontrollanterna avgör hur identiteten för förfrågningar från de registrerade ska lösas. Överväg att distribuera taggen för hämtning av Adobe-data-ID. Utvecklingsteamen sparar tid genom att använda vår hämtningstagg för dataskydd för att hämta användar-ID:n (cookie-ID:n). De kan sedan använda vårt API för datasekretess för att skicka dessa användar-ID:n till de relevanta lösningarna i Adobe Experience Cloud för behandling av förfrågningar om dataskydd. API:t för datasekretess har stöd för ett brett urval av kund-ID:n för flera Adobe-lösningar.

Om en registrerade skickar en begäran tillsammans med en identifierare (anpassad variabel - prop eller eVar) skannar Adobe Analytics igenom hela den lagrade historiken för de data som samlats in för den angivna identifieraren. Mer information om hur du konfigurerar anpassade ID:n som lagras i Analytics-utkast eller eVars finns i [Analytics-dokumentationen för namnutrymmen](/help/admin/admin/c-data-governance/data-labeling/gdpr-namespaces.md).

+++

+++ **Hur kan Adobe Analytics datastyrning hjälpa dig att behandla begäranden om datasekretess?**

Datastyrning är ett nytt verktyg i Adobe Analytics som ger datakontroller möjlighet att använda datakontroller och klassificeringar i sina Analytics-data. Detta nya verktyg ger Adobe-kunder möjlighet att anpassa behandlingen av sina begäranden om datasekretess och databorttagning. I konsolen Datastyrning kan administratörer definiera önskade inställningar som ska tillämpas på olika datakolumner som finns i Adobe Analytics. När etiketterna är definierade tillgodoser och behandlar Adobe alla begäranden om åtkomst eller radering längre fram i kedjan enligt kundens önskade etikettinställningar. Det är den personuppgiftsansvariges ansvar att granska och rådfråga sina juridiska representanter om dessa etikettinställningar.

Verktyget för datastyrning innehåller följande dataetiketter:

* **Identitetsdataetiketter**: Används för att klassificera data som kan identifiera en individ antingen direkt eller i kombination med andra data. (Ingen, I1, I2)

* **Känsliga dataetiketter**: Används för att klassificera data som data som kan definieras som känsliga enligt tillämplig lag. (Inga, S1, S2) Observera att användningen av känsliga data i Adobe Analytics i dagsläget är generellt sett förbjuden, med undantag för exakta geolokaliseringsdata som erhållits på korrekt sätt enligt tillämplig lag, och som kan anses vara känsliga data i vissa jurisdiktioner.

* **Dataetiketter för datasekretess**: Används för att definiera fält som kan innehålla personliga identifierare för användning i datasekretessbegäranden eller som ska tas bort som en del av en begäran om borttagning av datasekretess. Dessa etiketter kan i vissa fall överlappa etiketterna Identitet och Känsliga data.

Mer information om datastyrningsetiketter finns i [Dataintegritetsetiketter för analysvariabler](/help/admin/admin/c-data-governance/data-labeling/gdpr-labels.md).

+++

+++ **Hur verifierar jag att Privacy Servicen fungerar som den ska när jag tar bort data från Adobe Analytics?**

Vanligtvis skapar Analytics-kunder en del testrapportsviter för att verifiera funktionaliteten innan de släpps till allmänheten. Webbplatser eller appar för förproduktion skickar data till dessa test-/dev/QA-rapportsviter för att utvärdera hur saker kommer att fungera när koden släpps innan riktig trafik skickas till produktionsrapportsviterna.

Men med en normal konfiguration kan behandling av GPDR-begäran inte först testas på dessa testrapportsviter innan begäranden tillämpas på produktionsrapportsviter. Detta beror på att en begäran om dataskydd automatiskt tillämpas på alla rapporteringsprogram i Experience Cloud-organisationen, som ofta alla rapporteringsprogram för ditt företag.

Det finns dock några sätt att testa din dataintegritet innan du kan använda den i alla dina rapportsviter:

* Ett alternativ är att skapa en separat Experience Cloud-organisation som bara innehåller testrapportsviter. Använd sedan den här Experience Cloud-organisationen för att testa ditt test av datasekretess och din normala Experience Cloud-organisation för faktisk behandling av datasekretess.

* Ett annat alternativ är att tilldela olika namnutrymmen till ID:n i testrapportsviterna jämfört med dem i produktionsrapportsviterna. Du kan till exempel infoga prefix för varje namnutrymme med ”qa-” i testrapportsviterna. När du skickar in begäranden om datasekretess med endast namnutrymmen med qa-prefixet, kommer dessa begäranden endast att köras mot testrapportsviterna. När du senare skickar in begäranden utan qa-prefix gäller de även för dina produktionsrapportsviter. **Detta är det rekommenderade tillvägagångssättet om du inte använder namnutrymmena visitorId, AID, ECID eller customVisitorId. Dessa namnutrymmen är hårdkodade och du kan inte ange alternativa namn för dem i testrapportsviterna.**

+++

+++ **Hur blir jag redo för datasekretess med Adobe Analytics?**

En stegvis genomgång för att göra dig redo för datasekretessregler finns i [Adobe Analytics arbetsflöde för datasekretess](/help/admin/admin/c-data-governance/an-gdpr-workflow.md).

+++

+++ **Hur ska Data Controllers tänka på samtycke när det gäller användarinteraktion?**

GDPR och CCPA är goda möjligheter att ompröva er strategi och praxis för samtyckeshantering. Detta innefattar att avgöra när samtycke krävs och att tänka på användarens värdeförslag. Ta en titt på det värdeskapande som konsumentsekretess innebär, vilket kan bidra till ökad konvertering och lojalitet. Utrymmet för hantering av samtycke (t.ex. verktyg, standarder, bästa praxis) utvecklas snabbt och är ett område som ska observeras. För att minimera påverkan på användarinteraktionen bör kontrollanter arbeta med leverantörer på detta område samt med sina juridiska rådgivare för att se till att de följer nya lagar och riktlinjer om samtycke och cookies. Det är en god strategi att överväga ”upplevelsesekretess” genom att använda en varumärkesupplevelse som är relevant för sammanhanget och som fastställer värdeförslaget i dina datainsamlingsaktiviteter.

Som Data Controller ansvarar du för att få uttryckligt medgivande från dina registrerade innan du samlar in data om dem (eventuellt inklusive Adobe Analytics-data) och för att implementera en [avanmälningsmekanism](https://www.adobe.com/privacy/opt-out.html#customeruse) på din webbplats. På så sätt kan de registrerade avanmäla sig från framtida datainsamling från Adobe Experience Cloud.

+++

+++ **Hur ska Data Controllers tänka på datalagring när det gäller dataintegritet?**

Personuppgifter bör i allmänhet inte lagras längre än nödvändigt för att uppnå det syfte för vilket de samlades in. Adobe allmänna villkor tillämpar en 25-månaders standardplan för datalagring, såvida inte en annan avtalsperiod för datalagring har överenskommits. Kunderna måste ange sin datalagringspolicy innan Adobe kan behandla en begäran om dataskydd.

Varje rapportsvits aktuella policy för datalagring visas i det nya användargränssnittet för datastyrningsadministratörer. Kunderna bör kontakta sin Adobe-representant om de behöver ändra sin datalagringspolicy. Se [Vanliga frågor om datalagring i Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/technotes/data-retention.html?lang=sv-SE).

+++

+++ **Kan en kund förkorta eller förlänga standardperioden för datalagring?**

Kunder kan begära att deras data raderas tidigare än 25 månader genom att ringa kundtjänst. Kunderna kan också utöka datalagringen till mer än 25 månader genom att köpa en förlängning. Det finns förlängningar i steg om 1 ytterligare år, upp till maximalt 8 ytterligare år (totalt 10 år). Dessa tillägg kräver uppdaterade avtalsvillkor och tilläggsavgifter.

+++

+++ **Vilka sekretessöverväganden ska ett Data Controller-konto hantera när personuppgifter exporteras från Adobe Analytics?**

Om en kund använder Adobe Analytics dataflöden för att exportera data från Analytics till sitt datalager eller till andra system utanför Adobe, är det kundens (den personuppgiftsansvariges) ansvar att se till att borttagningsbegäranden tillämpas på dessa data. Detta gäller även för lokala implementeringar av Adobe Data Workbench, där en pågående Adobe Analytics-datafeed fyller Datans Workbench data. Adobe kan tillhandahålla verktyg som gör det enklare att hitta och ta bort poster från vissa typer av dataflöden, inklusive de som används för Data Workbench, men det är fortfarande kundens (den personuppgiftsansvarige) ansvar att se till att data tas bort i enlighet med deras egna, interna policyer för datalagring och radering.

Ta även hänsyn till fall där medarbetarna har laddat ned Adobe Analytics-rapporter som innehåller personuppgifter. Dessa rapporter kan behöva uppdateras eller tas bort om en begäran om borttagning av dataintegritet tas emot med ett ID som finns i rapporten. Kunderna bör arbeta med företagets juridiska rådgivare för att fastställa lagringsperioder och sekretess- och säkerhetskrav som ska tillämpas på dessa typer av dokument.

+++

+++ **Vissa data som vi inte borde samla in skickades av misstag till Adobe Analytics. Kan vi använda API:t för datasekretess för att rensa bort dessa data?**

[API:t för Privacy Service av data](https://developer.adobe.com/experience-platform-apis/references/privacy-service/) har tillhandahållits för att hjälpa dig att uppfylla datasekretessbegäranden, som är tidskänsliga. Adobe stöder inte att detta API används för andra syften och kan påverka Adobe förmåga att tillhandahålla välprioriterade, användarinitierade förfrågningar om dataskydd för andra Adobe-kunder.

Vi ber dig att inte använda API:t för datasekretess för andra syften, som att radera data som av misstag har skickats in över stora grupper av besökare. Du ska också vara medveten om att alla besökare som har en träff som har tagits bort (uppdaterats eller anonymiserats) efter en borttagningsbegäran om datasekretess kommer att få sin tillståndsinformation återställd. Nästa gång besökaren återvänder till webbplatsen blir han eller hon en ny besökare. All eVar-attribuering startar på nytt, liksom information som besöksnummer, referenter, första besökta sidan, o.s.v. Denna bieffekt är inte önskvärd i situationer där du vill ta bort datafält och är en anledning till varför API:t för datasekretess inte är lämpligt för detta ändamål.

Kontakta ert Adobe-kontoteam för att samordna med vårt konsultteam för ingenjörsarkitekter för att få mer information och möjlighet att åtgärda eventuella PII- eller dataproblem.

+++

+++ **Vårt juridiska team har fastställt att de värden vi har samlat in i en variabel i åratal inte längre följer vår uppdaterade sekretesspolicy. Kan vi använda API:t för datasekretess för att ta bort alla värden från den här variabeln?**

[API:t för Privacy Service av data](https://developer.adobe.com/experience-platform-apis/references/privacy-service/) har tillhandahållits för att hjälpa dig att uppfylla datasekretessbegäranden, som är tidskänsliga. Adobe stöder inte att detta API används för andra syften och det kan påverka Adobes förmåga att tillhandahålla användarinitierade begäranden om datasekretess i god tid för andra Adobe-kunder. Vi ber dig att inte använda API:t för datasekretess för andra syften, som att rensa data som av misstag har skickats in till stora grupper av besökare.

Du ska också vara medveten om att alla besökare som har en träff som har tagits bort (uppdaterats eller anonymiserats) efter en borttagningsbegäran om datasekretess kommer att få sin tillståndsinformation återställd. Nästa gång besökaren återvänder till webbplatsen blir han eller hon en ny besökare. All eVar-attribuering startar på nytt, liksom information som besöksnummer, referenter, första besökta sidan, o.s.v. Denna bieffekt är inte önskvärd i situationer där du vill ta bort datafält och är en anledning till varför API:t för datasekretess inte är lämpligt för detta ändamål.

Kontakta ert Adobe-kontoteam för att samordna med vårt konsultteam för ingenjörsarkitekter för att få mer information och möjlighet att åtgärda eventuella PII- eller dataproblem.

+++

Ytterligare resurser för datasekretess:

* [Allmänna villkor för GDPR](https://landing.adobe.com/dam/uploads/2018/in/adobe_gdpr_commonterms.pdf)
* [Care Package](https://landing.adobe.com/dam/uploads/2018/in/adobe_gdpr_carepackage.pdf) för Experience Cloud-datasekretess
* [Blogginlägg](https://theblog.adobe.com/experiential-privacy-an-investment-opportunity-for-the-experience-business/) om Experience-sekretess
