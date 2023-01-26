---
description: Vanliga frågor om datahantering i Adobe Analytics
title: Frågor och svar om datahantering
feature: Data Governance
exl-id: 57399c1b-cf08-405b-8c1b-9d23e4c38716
source-git-commit: aa794220b464b7665e89345a116a263189dcc3fa
workflow-type: tm+mt
source-wordcount: '1805'
ht-degree: 96%

---

# Frågor och svar

<table id="table_FA37A4B3960C4181B9CCDB569A476936"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Fråga </th> 
   <th colname="col2" class="entry"> Svar </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>Hur stöder Adobe Analytics åtkomst- och borttagningsbegäranden för slutanvändare (registrerade) som validerats av kunder (personuppgiftsansvariga)?</b> </p> </td> 
   <td colname="col2"> <p>När olika regler för datasekretess (GDPR, CCPA) börjar gälla kommer Adobe Analytics att stödja behandling av verifierade begäranden som skickas av personuppgiftsansvariga till API:t för Experience Cloud-datasekretess för att möjliggöra en mer automatiserad process. Adobes API för datasekretess är utformat för att underlätta behandling av enskilda begäranden om rättigheter (t.ex. begäranden om åtkomst och borttagning) för våra kunders data som lagras i Adobe Experience Cloud-lösningar. Det är flexibelt och skalbart efter antalet begäranden om åtkomst till och radering av data från registrerade. Med Privacy Services-API:t kan kunden också kontrollera status för hur förfrågningar om dataåtkomst och borttagning uppfylls. </p> <p>Mer information finns i <a href="https://developer.adobe.com/experience-platform-apis/references/privacy-service/"> Privacy Services-API-dokumentation. </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Vem ansvarar för att ta emot, godkänna och uppfylla begäranden om datasekretess från slutanvändare?</b> </p> </td> 
   <td colname="col2"> <p>Den personuppgiftsansvarige (d.v.s. Adobes kund) är ensam ansvarig för att ge de registrerade personuppgifter som svar på en begäran om individuella rättigheter i enlighet med datasekretess. Den personuppgiftsansvarige är även ensam ansvarig för att ta emot begäranden och godkänna begäranden – validera den registrerade personens identitet och sedan slutföra begäran, som delvis kan innefatta att kontakta Adobe med de registrerade ID:n som kan kopplas till data som lagras i Adobe Analytics. Som personuppgiftsbiträde måste Adobe ge den personuppgiftsansvarige rimlig hjälp med att behandla verifierade begäranden inom en acceptabel tidsperiod. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Hur får Adobe-kunder (personuppgiftsansvariga) reda på vilka begäranden om datasekretess som mappas till vilka ID:n i Adobe Analytics för datasekretess?</b> </p> </td> 
   <td colname="col2"> <p>De personuppgiftsansvariga avgör hur de ska lösa identiteten på begäranden från de registrerade. Överväg att distribuera <a href="https://developer.adobe.com/experience-platform-apis/references/privacy-service/"> Adobes hämtningstagg för datasekretess-ID. </a> Utvecklingsteamen sparar tid genom att använda vår hämtningstagg för datasekretess-ID för att hämta användar-ID:n (cookie-ID:n) och sedan använda vår API för datasekretess för att skicka dessa användar-ID:n till relevanta lösningar i Adobe Experience Cloud för behandling av begäran om datasekretess. </p> <p>API:t för datasekretess stöder ett brett urval av kund-ID:n för flera Adobe-lösningar. Om en registrerad person skickar en begäran tillsammans med en identifierare (anpassad variabel – prop eller eVar), kommer Adobe Analytics att söka igenom hela den lagrade historiken för de data som samlats in för den angivna identifieraren. Mer information om hur du konfigurerar anpassade ID:n som lagras i Analytics-utkast eller eVars finns i Analytics-dokumentationen om <a href="/help/admin/c-data-governance/data-labeling/gdpr-namespaces.md"> namnutrymmen.</a>
    </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Hur kan Adobe Analytics datastyrning hjälpa dig att behandla begäranden om datasekretess?</b> </p> </td> 
   <td colname="col2"> <p>Datastyrning är ett nytt verktyg i Adobe Analytics som ger den personuppgiftsansvarige möjligheten att tillämpa datakontroller och klassificeringar i sina Analytics-data. Detta nya verktyg ger Adobe-kunder möjlighet att anpassa behandlingen av sina begäranden om datasekretess och databorttagning. I konsolen Datastyrning kan administratörer definiera önskade inställningar som ska tillämpas på olika datakolumner som finns i Adobe Analytics. När etiketterna är definierade tillgodoser och behandlar Adobe alla begäranden om åtkomst eller radering längre fram i kedjan enligt kundens önskade etikettinställningar. Det är den personuppgiftsansvariges ansvar att granska och rådfråga sina juridiska representanter om dessa etikettinställningar. Adobe Analytics uppmuntrade kunderna att ställa in dataetikettering korrekt före GDPR-startdatumet, som var den 25 maj 2018, för att möjliggöra anpassning av begäranden med hjälp av API:t för datasekretess. </p> <p>Verktyget för datastyrning innehåller följande dataetiketter: </p> 
    <ul id="ul_F25B00EB020B4A639628FB884D0CB4F9"> 
     <li id="li_C295A396685340369D730D696FE6FC13"> <a href="/help/admin/c-data-governance/data-labeling/gdpr-labels.md#identity-data-labels"> Etiketter för identitetsdata: </a> Används för att klassificera data som kan identifiera en individ, antingen direkt eller i kombination med andra data. (Ingen, I1, I2) </li> 
     <li id="li_6D9A25139D3342CA82AAA64BC01AD368"> <a href="/help/admin/c-data-governance/data-labeling/gdpr-labels.md#sensitive-data-labels"> Etiketter för känsliga data: </a> Används för att klassificera data som data som kan definieras som känsliga enligt tillämplig lag. (Inga, S1, S2) Observera att användningen av känsliga data i Adobe Analytics i dagsläget är generellt sett förbjuden, med undantag för exakta geolokaliseringsdata som erhållits på korrekt sätt enligt tillämplig lag, och som kan anses vara känsliga data i vissa jurisdiktioner. </li> 
     <li id="li_C69935AAC36741D8A902D14F75E896D6"> <a href="/help/admin/c-data-governance/data-labeling/gdpr-labels.md#data-governance-labels"> Dataetiketter för datasekretess: </a> Används för att definiera de fält som kan innehålla personliga identifierare för användning i begäranden om datasekretess eller som ska tas bort som en del av en borttagningsbegäran om datasekretess. Dessa etiketter kan i vissa fall överlappa etiketterna Identitet och Känsliga data. </li> 
    </ul> <p>Mer information om etiketter för datastyrning finns i <a href="/help/admin/c-data-governance/data-labeling/gdpr-labels.md#data-governance-labels"> Datasekretessetiketter för analysvariabler. </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Hur blir jag redo för datasekretess med Adobe Analytics?</b> </p> </td> 
   <td colname="col2"> <p>En stegvis genomgång för att bli redo för datasekretessregler finns i <a href="/help/admin/c-data-governance/an-gdpr-workflow.md"> Adobe Analytics arbetsflöde för datasekretess. </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Hur ska personuppgiftsansvariga se på samtycke när det gäller användarinteraktion?</b> </p> </td> 
   <td colname="col2"> <p>GDPR och CCPA är goda möjligheter att ompröva er strategi och praxis för samtyckeshantering, inklusive att fastställa när samtycke krävs och överväga användarens värdeförslag. Överväg värdeförslaget i fråga om konsumentsekretess, vilket kan bidra till ökad konvertering och lojalitet. </p> <p>Utrymmet för hantering av samtycke (t.ex. verktyg, standarder, bästa praxis) utvecklas snabbt och är ett område som ska observeras. Personuppgiftsansvariga kan minimera påverkan på användarinteraktionen genom att arbeta med leverantörer kring detta område och med sina rådgivare samt följa EU:s nya lagar och riktlinjer om samtycke och cookies. Det är en god strategi att överväga ”upplevelsesekretess” genom att använda en varumärkesupplevelse som är relevant för sammanhanget och som fastställer värdeförslaget i dina datainsamlingsaktiviteter. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Hur ska personuppgiftsansvariga se på datalagring när det gäller datasekretess?</b> </p> </td> 
   <td colname="col2"> <p>Datasekretess kräver i allmänhet att personuppgifter inte lagras längre än nödvändigt för att uppnå det syfte för vilket de samlades in. </p> <p>Enligt Adobes kundkommunikation från februari kommer vi att tillämpa en plan för 25 månaders datalagring för de flesta kunder, såvida inte andra arrangemang har gjorts (med förbehåll för kundmeddelande och tillstånd). Kunderna måste ange sin policy för datalagring innan Adobe kan behandla en begäran om datasekretess. </p> <p>Adobe Analytics kräver att kunderna anger sin datalagring till att behandla sina begäranden om datasekretess. Varje rapportsvits aktuella policy för datalagring visas i det nya användargränssnittet för datastyrningsadministratörer. Kunderna ska kontakta sin Adobe-representant om de behöver ändra sina regler för datalagring. Se <a href="https://experienceleague.adobe.com/docs/analytics/technotes/latency.html"> Vanliga frågor och svar om datalagring i Adobe Analytics. </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Kan en kund minska eller förlänga standardperioden för datalagring?</b> </p> </td> 
   <td colname="col2"> <p>Kunderna kan begära att deras data raderas tidigare än 25 månader genom att ringa kundtjänst. Kunderna kan utöka datalagringen till mer än 25 månader genom att köpa en förlängning.</p><p>
   Tillägg finns tillgängliga i steg om 1 (ett) ytterligare år, upp till maximalt 8 (åtta) ytterligare år (totalt 10 år). Dessa tillägg kan kräva uppdaterade avtalsvillkor och ytterligare avgifter.
 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b> Vilka sekretessöverväganden ska en personuppgiftsansvarig ta hänsyn till när personuppgifter exporteras från Adobe Analytics?</b> </p> </td> 
   <td colname="col2"> <p>Om en kund använder Adobe Analytics dataflöden för att exportera data från Analytics till sitt datalager eller till andra system utanför Adobe, är det kundens (den personuppgiftsansvariges) ansvar att se till att borttagningsbegäranden tillämpas på dessa data. Detta gäller även lokala implementeringar av Adobe Data Workbench (Insight), där ett pågående Adobe Analytics-dataflöde fyller i data från Data Workbench. Adobe kan tillhandahålla verktyg som gör det enklare att hitta och ta bort poster från vissa typer av dataflöden, inklusive de som används för Data Workbench, men det är fortfarande kundens (den personuppgiftsansvarige) ansvar att se till att data tas bort i enlighet med deras egna, interna policyer för datalagring och radering. </p> <p>Ta även hänsyn till fall där anställda kan ha laddat ned Adobe Analytics-rapporter som innehåller personuppgifter. Dessa rapporter kan behöva uppdateras eller tas bort om en borttagningsbegäran om datasekretess tas emot med ett ID som kan finnas i rapporten. Kunderna ska samarbeta med företagets juridiska rådgivare för att fastställa lagringsperioder samt sekretess- och säkerhetskrav som ska gälla för dessa typer av dokument. </p> </td> 
  </tr> <tr> 
   <td colname="col1"> <p><b> Vissa data som vi inte skulle samla in skickades av misstag till Adobe Analytics. Kan vi använda API:t för datasekretess för att rensa dessa data?</b> </p> </td><td colname="col2"> <p>API:t för datasekretess har tillhandahållits för att hjälpa dig att uppfylla begäranden om datasekretess, vilka är tidskänsliga. Adobe stöder inte att detta API används för andra syften och det kan påverka Adobes förmåga att tillhandahålla användarinitierade begäranden om datasekretess i god tid för andra Adobe-kunder. Vi ber dig att inte använda API:t för datasekretess för andra syften, som att rensa data som av misstag har skickats in till stora grupper av besökare.</p> <p>Du ska också vara medveten om att alla besökare som har en träff som har tagits bort (uppdaterats eller anonymiserats) efter en borttagningsbegäran om datasekretess kommer att få sin tillståndsinformation återställd. Nästa gång besökaren återvänder till webbplatsen blir han eller hon en ny besökare. All eVar-attribuering startar på nytt, liksom information som besöksnummer, referenter, första besökta sidan, o.s.v. Denna bieffekt är inte önskvärd i situationer där du vill ta bort datafält och är en anledning till varför API:t för datasekretess inte är lämpligt för detta ändamål. </p> <p>Kontakta din Account Manager (CSM) för att samordna med vårt konsultteam inom Engineering Architect för ytterligare granskning och åtgärder för att lösa eventuella PII- eller dataproblem.</p></td></tr> <tr> 
   <td colname="col1"> <p><b> Vårt juridiska team har fastställt att de värden vi har samlat in i en variabel i åratal inte längre följer vår uppdaterade sekretesspolicy. Kan vi använda API:t för datasekretess för att ta bort alla värden från den här variabeln?</b> </p> </td><td colname="col2"> <p>API:t för datasekretess har tillhandahållits för att hjälpa dig att uppfylla begäranden om datasekretess, vilka är tidskänsliga. Adobe stöder inte att detta API används för andra syften och det kan påverka Adobes förmåga att tillhandahålla användarinitierade begäranden om datasekretess i god tid för andra Adobe-kunder. Vi ber dig att inte använda API:t för datasekretess för andra syften, som att rensa data som av misstag har skickats in till stora grupper av besökare.</p> <p>Du ska också vara medveten om att alla besökare som har en träff som har tagits bort (uppdaterats eller anonymiserats) efter en borttagningsbegäran om datasekretess kommer att få sin tillståndsinformation återställd. Nästa gång besökaren återvänder till webbplatsen blir han eller hon en ny besökare. All eVar-attribuering startar på nytt, liksom information som besöksnummer, referenter, första besökta sidan, o.s.v. Denna bieffekt är inte önskvärd i situationer där du vill ta bort datafält och är en anledning till varför API:t för datasekretess inte är lämpligt för detta ändamål. </p> <p>Kontakta din Account Manager (CSM) för att samordna med vårt konsultteam inom Engineering Architect för ytterligare granskning och åtgärder för att lösa eventuella PII- eller dataproblem.</p></td>
 </tbody> 
</table>

Ytterligare resurser för datasekretess:

* [Allmänna villkor för GDPR](https://landing.adobe.com/dam/uploads/2018/in/adobe_gdpr_commonterms.pdf)
* [Care Package](https://landing.adobe.com/dam/uploads/2018/in/adobe_gdpr_carepackage.pdf) för Experience Cloud-datasekretess
* [Blogginlägg](https://theblog.adobe.com/experiential-privacy-an-investment-opportunity-for-the-experience-business/) om Experience-sekretess
