---
description: Vanliga frågor om datahantering i Adobe Analytics
title: Frågor och svar om datahantering
feature: Data Governance
exl-id: 57399c1b-cf08-405b-8c1b-9d23e4c38716
source-git-commit: 4bbed2efde0574bc9f5f6a78a022a22490e75549
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Frågor och svar

+++ **Hur stöder Adobe Analytics åtkomst- och borttagningsbegäranden för slutanvändare (registrerade) som validerats av kunder (personuppgiftsansvariga)?**

När olika dataskyddsregler (GDPR, CCPA) börjar gälla kommer Adobe Analytics att stödja behandling av verifierade begäranden som skickas av datakontrollanter till API:t för dataintegritet i Experience Cloud för att möjliggöra en mer automatiserad process. Adobes API för datasekretess är utformat för att underlätta behandling av enskilda begäranden om rättigheter (t.ex. begäranden om åtkomst och borttagning) för våra kunders data som lagras i Adobe Experience Cloud-lösningar. Det är flexibelt och skalbart efter antalet begäranden om åtkomst till och radering av data från registrerade.

Med Privacy Services-API:t kan kunden också kontrollera status för hur förfrågningar om dataåtkomst och borttagning uppfylls. Mer information finns i [Privacy Services-API](https://developer.adobe.com/experience-platform-apis/references/privacy-service/) dokumentation.

+++

+++ **Vem ansvarar för att ta emot, godkänna och uppfylla begäranden om datasekretess från slutanvändare?**

Datakontrollanten (dvs. Adobe-kunden) har det enda ansvaret för att ge de registrerade personuppgifter som svar på en begäran om individrättigheter under Dataintegritet. Den personuppgiftsansvarige är även ensam ansvarig för att ta emot begäranden och godkänna begäranden – validera den registrerade personens identitet och sedan slutföra begäran, som delvis kan innefatta att kontakta Adobe med de registrerade ID:n som kan kopplas till data som lagras i Adobe Analytics.

Som personuppgiftsbiträde måste Adobe ge den personuppgiftsansvarige rimlig hjälp med att behandla verifierade begäranden inom en acceptabel tidsperiod.

+++

+++ **Hur får Adobe-kunder (personuppgiftsansvariga) reda på vilka begäranden om datasekretess som mappas till vilka ID:n i Adobe Analytics för datasekretess?**

Datakontrollörerna kommer att avgöra hur identiteten ska matchas för förfrågningar från de registrerade. Överväg att distribuera  Adobes hämtningstagg för datasekretess-ID. Utvecklingsteamen sparar tid genom att använda vår hämtningstagg för datasekretess-ID för att hämta användar-ID:n (cookie-ID:n) och sedan använda vår API för datasekretess för att skicka dessa användar-ID:n till relevanta lösningar i Adobe Experience Cloud för behandling av begäran om datasekretess. API:t för datasekretess stöder ett brett urval av kund-ID:n för flera Adobe-lösningar.

Om en registrerad person skickar en begäran tillsammans med en identifierare (anpassad variabel – prop eller eVar), kommer Adobe Analytics att söka igenom hela den lagrade historiken för de data som samlats in för den angivna identifieraren. Mer information om hur du konfigurerar anpassade ID:n som lagras i skissbilder eller eVars finns i [Analysdokumentation om namnutrymmen](/help/admin/c-data-governance/data-labeling/gdpr-namespaces.md).

+++

+++ **Hur kan Adobe Analytics datastyrning hjälpa dig att behandla begäranden om datasekretess?**

Datastyrning är ett nytt verktyg i Adobe Analytics som ger den personuppgiftsansvarige möjligheten att tillämpa datakontroller och klassificeringar i sina Analytics-data. Detta nya verktyg ger Adobe-kunder möjlighet att anpassa behandlingen av sina begäranden om datasekretess och databorttagning. I konsolen Datastyrning kan administratörer definiera önskade inställningar som ska tillämpas på olika datakolumner som finns i Adobe Analytics. När etiketterna är definierade tillgodoser och behandlar Adobe alla begäranden om åtkomst eller radering längre fram i kedjan enligt kundens önskade etikettinställningar. Det är den personuppgiftsansvariges ansvar att granska och rådfråga sina juridiska representanter om dessa etikettinställningar. Adobe Analytics uppmuntrar kunderna att ställa in datamärkning korrekt före GDPR-startdatumet, som är den 25 maj 2018 för att tillåta anpassning av begäran med API:t för dataintegritet.

Verktyget för datastyrning innehåller följande dataetiketter:

* Etiketter för identitetsdata:  Används för att klassificera data som kan identifiera en individ, antingen direkt eller i kombination med andra data. (Ingen, I1, I2)

* Etiketter för känsliga data:  Används för att klassificera data som data som kan definieras som känsliga enligt tillämplig lag. (Inga, S1, S2) Observera att användningen av känsliga data i Adobe Analytics i dagsläget är generellt sett förbjuden, med undantag för exakta geolokaliseringsdata som erhållits på korrekt sätt enligt tillämplig lag, och som kan anses vara känsliga data i vissa jurisdiktioner.

* Dataetiketter för datasekretess:  Används för att definiera de fält som kan innehålla personliga identifierare för användning i begäranden om datasekretess eller som ska tas bort som en del av en borttagningsbegäran om datasekretess. Dessa etiketter kan i vissa fall överlappa etiketterna Identitet och Känsliga data.

Mer information om etiketter för datastyrning finns i [ Datasekretessetiketter för analysvariabler](/help/admin/c-data-governance/data-labeling/gdpr-labels.md).

+++

+++ **Hur verifierar jag att sekretesstjänstförfrågningarna fungerar som de ska när jag tar bort data från Adobe Analytics?**

Vanligtvis skapar Analytics-kunder en del testrapportsviter för att verifiera funktionaliteten innan de släpps till allmänheten. Webbplatser eller appar för förproduktion skickar data till dessa rapportsviter för test/utveckling/kvalitetssäkring för att utvärdera hur saker kommer att fungera när koden släpps innan faktisk trafik skickas till produktionsrapportsviterna.

Men med en normal konfiguration kan behandling av GPDR-begäran inte först testas på dessa testrapportsviter innan begäranden tillämpas på produktionsrapportsviter. Det beror på att en begäran om datasekretess automatiskt tillämpas på alla rapportsviter i Experience Cloud-organisationen, som ofta alla är rapportsviter för ditt företag.

Det finns ett par olika sätt att testa din behandling av datasekretess innan du tillämpar den på alla dina rapportsviter:

* Ett alternativ är att skapa en separat Experience Cloud-organisation som bara innehåller testrapportsviter. Använd sedan den här Experience Cloud-organisationen för att testa ditt test av datasekretess och din normala Experience Cloud-organisation för faktisk behandling av datasekretess.

* Du kan även tilldela olika namnutrymmen till ID:n i testrapportsviterna jämfört med dem i produktionsrapportsviterna. Du kan till exempel infoga prefix för varje namnutrymme med ”qa-” i testrapportsviterna. När du skickar in begäranden om datasekretess med endast namnutrymmen med qa-prefixet, kommer dessa begäranden endast att köras mot testrapportsviterna. När du senare skickar in begäranden utan qa-prefix gäller de även för dina produktionsrapportsviter. **Detta är det rekommenderade tillvägagångssättet, såvida du inte använder namnutrymmena visitorId, AID, ECID eller customVisitorId. Dessa namnutrymmen är hårdkodade och du kan inte ange alternativa namn för dem i testrapportsviterna.**

+++

+++ **Hur blir jag redo för datasekretess med Adobe Analytics?**

En stegvis genomgång för att bli redo för datasekretessregler finns i [ Adobe Analytics arbetsflöde för datasekretess](/help/admin/c-data-governance/an-gdpr-workflow.md).

+++

+++ **Hur ska personuppgiftsansvariga se på samtycke när det gäller användarinteraktion?**

GDPR och CCPA är goda möjligheter att ompröva er strategi och praxis för samtyckeshantering, inklusive att fastställa när samtycke krävs och överväga användarens värdeförslag. Överväg värdeförslaget i fråga om konsumentsekretess, vilket kan bidra till ökad konvertering och lojalitet.  Utrymmet för hantering av samtycke (t.ex. verktyg, standarder, bästa praxis) utvecklas snabbt och är ett område som ska observeras. Personuppgiftsansvariga kan minimera påverkan på användarinteraktionen genom att arbeta med leverantörer kring detta område och med sina rådgivare samt följa EU:s nya lagar och riktlinjer om samtycke och cookies. Det är en god strategi att överväga ”upplevelsesekretess” genom att använda en varumärkesupplevelse som är relevant för sammanhanget och som fastställer värdeförslaget i dina datainsamlingsaktiviteter.

Som registeransvarig ansvarar du för att få uttryckligt medgivande från de registrerade innan du samlar in uppgifter om dem (eventuellt inklusive Adobe Analytics-uppgifter) och för att implementera en [avanmälningsmekanism](https://www.adobe.com/privacy/opt-out.html#customeruse) på din webbplats. På så vis kan era registrerade personer avanmäla sig från framtida datainsamling i Adobe Experience Cloud.

+++

+++ **Hur ska personuppgiftsansvariga se på datalagring när det gäller datasekretess?**

Datasekretess kräver i allmänhet att personuppgifter inte lagras längre än nödvändigt för att uppnå det syfte för vilket de samlades in.  Enligt Adobes kundkommunikation från februari kommer vi att tillämpa en plan för 25 månaders datalagring för de flesta kunder, såvida inte andra arrangemang har gjorts (med förbehåll för kundmeddelande och tillstånd). Kunderna måste ange sin policy för datalagring innan Adobe kan behandla en begäran om datasekretess.

Adobe Analytics kräver att kunderna anger sin datalagring till att behandla sina begäranden om datasekretess. Varje rapportsvits aktuella policy för datalagring visas i det nya användargränssnittet för datastyrningsadministratörer. Kunderna ska kontakta sin Adobe-representant om de behöver ändra sina regler för datalagring. Se [Vanliga frågor om Adobe Analytics datalagring](https://experienceleague.adobe.com/docs/analytics/technotes/data-retention.html?lang=en).

+++

+++ **Kan en kund minska eller förlänga standardperioden för datalagring?**

Kunderna kan begära att deras data raderas tidigare än 25 månader genom att ringa kundtjänst. Kunderna kan utöka datalagringen till mer än 25 månader genom att köpa en förlängning. Tillägg finns tillgängliga i steg om 1 (ett) ytterligare år, upp till maximalt 8 (åtta) ytterligare år (totalt 10 år). Dessa tillägg kan kräva uppdaterade avtalsvillkor och ytterligare avgifter.

+++

+++ **Vilka sekretessöverväganden ska en personuppgiftsansvarig ta hänsyn till när personuppgifter exporteras från Adobe Analytics?**

Om en kund använder Adobe Analytics dataflöden för att exportera data från Analytics till sitt datalager eller till andra system utanför Adobe, är det kundens (den personuppgiftsansvariges) ansvar att se till att borttagningsbegäranden tillämpas på dessa data. Detta gäller även för lokala implementeringar av Adobe Data Workbench, där en pågående Adobe Analytics-datafeed fyller Datans Workbench data. Adobe kan tillhandahålla verktyg som gör det enklare att hitta och ta bort poster från vissa typer av dataflöden, inklusive de som används för Data Workbench, men det är fortfarande kundens (den personuppgiftsansvarige) ansvar att se till att data tas bort i enlighet med deras egna, interna policyer för datalagring och radering.

Ta även hänsyn till fall där anställda kan ha laddat ned Adobe Analytics-rapporter som innehåller personuppgifter. Dessa rapporter kan behöva uppdateras eller tas bort om en borttagningsbegäran om datasekretess tas emot med ett ID som kan finnas i rapporten. Kunderna ska samarbeta med företagets juridiska rådgivare för att fastställa lagringsperioder samt sekretess- och säkerhetskrav som ska gälla för dessa typer av dokument.

+++

+++ **Vissa data som vi inte skulle samla in skickades av misstag till Adobe Analytics. Kan vi använda API:t för datasekretess för att rensa dessa data?**

The [API för Privacy Service](https://developer.adobe.com/experience-platform-apis/references/privacy-service/) har tillhandahållits för att hjälpa er att uppfylla förfrågningar om dataintegritet, som är tidskänsliga. Adobe stöder inte att detta API används för andra syften och det kan påverka Adobes förmåga att tillhandahålla användarinitierade begäranden om datasekretess i god tid för andra Adobe-kunder. Vi ber dig att inte använda API:t för datasekretess för andra syften, som att rensa data som av misstag har skickats in till stora grupper av besökare. Du ska också vara medveten om att alla besökare som har en träff som har tagits bort (uppdaterats eller anonymiserats) efter en borttagningsbegäran om datasekretess kommer att få sin tillståndsinformation återställd. Nästa gång besökaren återvänder till webbplatsen blir han eller hon en ny besökare. All eVar-attribuering startar på nytt, liksom information som besöksnummer, referenter, första besökta sidan, o.s.v. Denna bieffekt är inte önskvärd i situationer där du vill ta bort datafält och är en anledning till varför API:t för datasekretess inte är lämpligt för detta ändamål.

Kontakta din Account Manager (CSM) för att samordna med vårt konsultteam inom Engineering Architect för ytterligare granskning och åtgärder för att lösa eventuella PII- eller dataproblem.

+++

+++ **Vårt juridiska team har fastställt att de värden vi har samlat in i en variabel i åratal inte längre följer vår uppdaterade sekretesspolicy. Kan vi använda API:t för datasekretess för att ta bort alla värden från den här variabeln?**

The [API för Privacy Service](https://developer.adobe.com/experience-platform-apis/references/privacy-service/) har tillhandahållits för att hjälpa er att uppfylla förfrågningar om dataintegritet, som är tidskänsliga. Adobe stöder inte att detta API används för andra syften och det kan påverka Adobes förmåga att tillhandahålla användarinitierade begäranden om datasekretess i god tid för andra Adobe-kunder. Vi ber dig att inte använda API:t för datasekretess för andra syften, som att rensa data som av misstag har skickats in till stora grupper av besökare.

Du ska också vara medveten om att alla besökare som har en träff som har tagits bort (uppdaterats eller anonymiserats) efter en borttagningsbegäran om datasekretess kommer att få sin tillståndsinformation återställd. Nästa gång besökaren återvänder till webbplatsen blir han eller hon en ny besökare. All eVar-attribuering startar på nytt, liksom information som besöksnummer, referenter, första besökta sidan, o.s.v. Denna bieffekt är inte önskvärd i situationer där du vill ta bort datafält och är en anledning till varför API:t för datasekretess inte är lämpligt för detta ändamål.

Kontakta er Account Manager (CSM) för att samordna med vårt konsultteam inom Engineering Architect för att få mer information och för att åtgärda eventuella PII- eller dataproblem.

+++


Ytterligare resurser för datasekretess:

* [Allmänna villkor för GDPR](https://landing.adobe.com/dam/uploads/2018/in/adobe_gdpr_commonterms.pdf)
* [Care Package](https://landing.adobe.com/dam/uploads/2018/in/adobe_gdpr_carepackage.pdf) för Experience Cloud-datasekretess
* [Blogginlägg](https://theblog.adobe.com/experiential-privacy-an-investment-opportunity-for-the-experience-business/) om Experience-sekretess
