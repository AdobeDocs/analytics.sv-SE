---
description: 'null'
title: Frågor och svar
uuid: 1cd41253-d74f-4b92-92e6-56f9afa3df85
translation-type: tm+mt
source-git-commit: 12a7452337307ca019c005dc20e3b551d96e1289

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
   <td colname="col1"> <p><b>Hur stöder Adobe Analytics åtkomst- och borttagningsförfrågningar för slutanvändare (registrerade) som validerats av kunder (Data Controllers)?</b> </p> </td> 
   <td colname="col2"> <p>När olika dataskyddsregler (GDPR, CCPA) börjar gälla kommer Adobe Analytics att stödja behandling av verifierade begäranden som skickas av datakontroller till Experience Cloud Data Privacy API för att möjliggöra en mer automatiserad process. Adobes API för datasekretess är utformat för att hjälpa till att behandla enskilda förfrågningar om rättigheter (t.ex. förfrågningar om åtkomst och borttagning) för våra kunders data som lagras i Adobe Experience Cloud-lösningar. Den är flexibel och skalbar efter antalet dataåtkomstbegäranden och raderingsförfrågningar från registrerade. Med API:t för datasekretess kan kunden även kontrollera status för hur förfrågningar om dataåtkomst och borttagning uppfylls. </p> <p>Mer information finns i dokumentationen <a href="https://www.adobe.io/apis/cloudplatform/gdpr.html"> för API:t för dataskydd. </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Vem ansvarar för att ta emot, godkänna och uppfylla förfrågningar om dataintegritet från slutanvändare?</b> </p> </td> 
   <td colname="col2"> <p>Datakontrollanten (dvs. Adobes kund) har det enda ansvaret för att ge de registrerade personuppgifter som svar på en begäran om individuella rättigheter under Dataintegritet. Datakontrollanten har också det enda ansvaret för att ta emot förfrågningar och godkänna förfrågningar - validera den registrerade personens identitet och sedan slutföra begäran, som till en del kan inbegripa att kontakta Adobe med de registrerade ID:n som kan kopplas till data som lagras i Adobe Analytics. Som databehandlare måste Adobe ge den personuppgiftsansvarige rimlig hjälp att behandla verifierade begäranden inom en acceptabel tidsperiod. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Hur kommer Adobe-kunder (Data Controllers) att ta reda på vilka dataintegritetsförfrågningar som mappas till vilka ID:n i Adobe Analytics för dataintegritet?</b> </p> </td> 
   <td colname="col2"> <p>De personuppgiftsansvariga kommer att avgöra hur de ska lösa identiteten på förfrågningar från de registrerade. Överväg att distribuera <a href="https://www.adobe.io/apis/cloudplatform/gdpr/services/allservices.htm"> Adobes tagg för hämtning av dataintegritetspolicy. </a> Utvecklingsteamen sparar tid genom att använda vår hämtningstagg för dataintegritetsID för att hämta användar-ID:n (cookie-ID:n) och sedan använda vår API för dataintegritet för att skicka dessa användar-ID:n till relevanta lösningar i bearbetningen av begäran om dataskydd i Adobe Experience Cloud. </p> <p>API:t för datasekretess har stöd för ett brett urval av kund-ID:n för flera Adobe-lösningar. Om en registrerade skickar en begäran tillsammans med en identifierare (anpassad variabel - prop eller eVar), kommer Adobe Analytics att söka igenom hela den lagrade historiken för de data som samlats in för den angivna identifieraren. Mer information om hur du konfigurerar anpassade ID:n som lagras i Analytics-utkast eller eVars finns i Analytics-dokumentationen för <a href="/help/admin/c-data-governance/gdpr-namespaces.md"> Namespaces.</a>
    </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Hur kan Adobe Analytics datastyrning hjälpa er att behandla förfrågningar om dataintegritet?</b> </p> </td> 
   <td colname="col2"> <p>Styrning av data är ett nytt verktyg i Adobe Analytics som ger datakontroller möjlighet att tillämpa datakontroller och klassificeringar i sina Analytics-data. Detta nya verktyg ger Adobe-kunder möjlighet att anpassa behandlingen av sina förfrågningar om dataintegritet och databorttagning. I Data Governance-konsolen kan administratörer definiera önskade inställningar som ska tillämpas på olika datakolumner som finns i Adobe Analytics. När etiketterna är definierade kommer Adobe att efterleva och bearbeta eventuella begäran om åtkomst eller radering längre fram i kedjan enligt kundens önskade etikettinställningar. Det är den personuppgiftsansvariges ansvar att granska och rådfråga sina juridiska representanter om dessa etikettinställningar. Adobe Analytics uppmuntrar kunderna att ställa in datamärkning korrekt före GDPR-startdatumet, som är den 25 maj 2018, för att tillåta anpassning av begäran med hjälp av API:t för dataintegritet. </p> <p>Datastyrningsverktyget innehåller följande dataetiketter: </p> 
    <ul id="ul_F25B00EB020B4A639628FB884D0CB4F9"> 
     <li id="li_C295A396685340369D730D696FE6FC13"> <a href="/help/admin/c-data-governance/gdpr-labels.md#identity-data-labels"> Identitetsdataetiketter: Används </a> för att klassificera data som kan identifiera en individ antingen direkt eller i kombination med andra data. (Ingen, I1, I2) </li> 
     <li id="li_6D9A25139D3342CA82AAA64BC01AD368"> <a href="/help/admin/c-data-governance/gdpr-labels.md#sensitive-data-labels"> Känsliga dataetiketter: </a> Används för att klassificera data som data som kan definieras som känsliga enligt tillämplig lag. (Inga, S1, S2) Observera att användningen av känsliga data i Adobe Analytics i dagsläget i allmänhet är förbjuden, med undantag för exakta geolokaliseringsuppgifter som erhållits korrekt enligt tillämplig lag, som kan anses vara känsliga data i vissa jurisdiktioner. </li> 
     <li id="li_C69935AAC36741D8A902D14F75E896D6"> <a href="/help/admin/c-data-governance/gdpr-labels.md#data-governance-labels"> Dataintegritet - etiketter: Används </a> för att definiera de fält som kan innehålla personliga identifierare för användning i förfrågningar om dataintegritet eller som ska tas bort som en del av en begäran om borttagning av dataskydd. Dessa etiketter kan i vissa fall överlappa etiketterna Identitet och Känsliga data. </li> 
    </ul> <p>Mer information om datastyrningsetiketter finns i Dataintegritetsetiketter för analysvariabler <a href="/help/admin/c-data-governance/gdpr-labels.md#data-governance-labels"> . </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Var kommer jag igång med att förbereda mig för dataintegritet med Adobe Analytics?</b> </p> </td> 
   <td colname="col2"> <p>En steg-för-steg-genomgång för att förbereda sekretessregler för data finns i <a href="/help/admin/c-data-governance/an-gdpr-workflow.md"> Adobe Analytics-arbetsflöde för dataintegritet. </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Hur ska personuppgiftsansvariga tänka på samtycke när det gäller användarinteraktion?</b> </p> </td> 
   <td colname="col2"> <p>GDPR och CCPA är goda möjligheter att ompröva er strategi och praxis för samtyckeshantering, inklusive att fastställa när samtycke krävs och överväga användarens värdeförslag. Ta en titt på det värdeskapande som konsumentsekretess innebär, vilket kan bidra till ökad konvertering och lojalitet. </p> <p>Medgivandehanteringsutrymmet (t.ex. verktyg, standarder, bästa praxis) utvecklas snabbt och är ett område att titta på. För att minimera påverkan på användarinteraktionen bör kontrollanter arbeta med leverantörer på detta område och med sina rådgivare och följa EU:s nya lagar och riktlinjer om samtycke och cookies. Att tänka på"upplevelsesekretess" genom att använda en upplevelse som är relevant för varumärket och som anger värdepaketet i era datainsamlingsaktiviteter är en bra strategi. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Hur bör personuppgiftsansvariga tänka på datalagring när det gäller dataintegritet?</b> </p> </td> 
   <td colname="col2"> <p>I allmänhet föreskrivs det att personuppgifter i allmänhet inte bör lagras längre än nödvändigt för att uppnå det syfte för vilket de samlades in. </p> <p>Så som beskrivs i Adobes kundkommunikation i februari kommer vi att tillämpa en 25-månaders datalagringsplan för de flesta kunder, såvida inte andra arrangemang har gjorts (med förbehåll för kundmeddelande och tillstånd). Kunderna måste ange sin datalagringspolicy innan Adobe kan behandla en begäran om dataintegritet. </p> <p>Adobe Analytics kräver att kunderna ställer in sin datalagring för att behandla sina förfrågningar om dataintegritet. Varje rapportsvit aktuella datalagringspolicy visas i det nya användargränssnittet för datastyrningsadministratörer. Kunderna bör kontakta sin Adobe-representant om de behöver ändra sina regler för datalagring. Se Vanliga frågor och svar om datalagring i Adobe Analytics. <a href="https://marketing.adobe.com/resources/help/en_US/reference/data-retention-client-table-faq.html"> </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Kan en kund minska eller förlänga standardperioden för datalagring?</b> </p> </td> 
   <td colname="col2"> <p>Kunderna kan begära att deras data raderas tidigare än 25 månader genom att ringa kundtjänst. Kunderna kan utöka datalagringen till mer än 25 månader genom att köpa en förlängning.</p><p>
   Tillägg finns tillgängliga i steg om 1 (ett) till år, upp till maximalt 8 (åtta) ytterligare år (totalt 10 år). Dessa tillägg kan kräva uppdaterade avtalsvillkor och ytterligare avgifter.
 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b> Vilka sekretessöverväganden ska ett Data Controller-konto hantera när personuppgifter exporteras från Adobe Analytics?</b> </p> </td> 
   <td colname="col2"> <p>Om en kund använder Adobe Analytics Data Feeds för att exportera data från Analytics till sitt datalager eller till andra system utanför Adobe är det kundens (Data Controller) ansvar att se till att raderingsbegäranden tillämpas på data. Detta gäller även lokala implementeringar av Adobe Data Workbench (Insight), där en pågående Adobe Analytics-datafeed fyller i data från Data Workbench. Adobe kan tillhandahålla verktyg som hjälper till att hitta och ta bort poster från vissa typer av dataflöden, inklusive de som används för Data Workbench, men det är fortfarande kundens (Data Controller) ansvar att se till att data tas bort i enlighet med deras egna, interna policyer för datalagring och radering. </p> <p>Ta även hänsyn till fall där medarbetarna kan ha laddat ned Adobe Analytics-rapporter som innehåller personuppgifter. Dessa rapporter kan behöva uppdateras eller tas bort om en begäran om borttagning av dataskydd tas emot med ett ID som kan finnas i rapporten. Kunderna bör samarbeta med företagets juridiska rådgivare för att fastställa lagringsperioder och sekretess- och säkerhetskrav som ska gälla för dessa typer av dokument. </p> </td> 
  </tr> <tr> 
   <td colname="col1"> <p><b> Vissa data som vi inte skulle samla in skickades av misstag till Adobe Analytics. Kan vi använda API:t för datasekretess för att rensa dessa data?</b> </p> </td><td colname="col2"> <p>API:t för datasekretess har tillhandahållits för att hjälpa dig att uppfylla datasekretessbegäranden, som är tidskänsliga. Att använda detta API för andra syften stöds inte av Adobe och kan påverka Adobes förmåga att tillhandahålla vältajmade, användarinitierade förfrågningar om dataintegritet för andra Adobe-kunder. Vi ber dig att inte använda API:t för datasekretess för andra syften, som att radera data som av misstag har skickats in över stora grupper av besökare.</p> <p>Du bör också vara medveten om att alla besökare som har en träff som har tagits bort (uppdaterats eller anonymiserats) som ett resultat av en begäran om borttagning av datasekretess kommer att få sin tillståndsinformation återställd. Nästa gång besökaren återvänder till webbplatsen blir han eller hon en ny besökare. All eVar-attribuering kommer att starta igen, liksom information som besöksnummer, referenter, besökt första sidan osv. Den här biverkningen är inte önskvärd i situationer där du vill ta bort datafält och visar en anledning till varför API:t för dataintegritet inte är lämpligt för den här användningen. </p> <p>Kontakta er Account Manager (CSM) för att samordna med vårt konsultteam inom Engineering Architect för ytterligare granskning och åtgärder för att ta bort eventuella PII- eller dataproblem.</p></td></tr> <tr> 
   <td colname="col1"> <p><b> Vårt juridiska team har fastställt att de värden vi har samlat in i en variabel i åratal inte längre följer vår uppdaterade integritetspolicy. Kan vi använda API:t för datasekretess för att ta bort alla värden från den här variabeln?</b> </p> </td><td colname="col2"> <p>API:t för datasekretess har tillhandahållits för att hjälpa dig att uppfylla datasekretessbegäranden, som är tidskänsliga. Att använda detta API för andra syften stöds inte av Adobe och kan påverka Adobes förmåga att tillhandahålla vältajmade, användarinitierade förfrågningar om dataintegritet för andra Adobe-kunder. Vi ber dig att inte använda API:t för datasekretess för andra syften, som att radera data som av misstag har skickats in över stora grupper av besökare.</p> <p>Du bör också vara medveten om att alla besökare som har en träff som har tagits bort (uppdaterats eller anonymiserats) som ett resultat av en begäran om borttagning av datasekretess kommer att få sin tillståndsinformation återställd. Nästa gång besökaren återvänder till webbplatsen blir han eller hon en ny besökare. All eVar-attribuering kommer att starta igen, liksom information som besöksnummer, referenter, besökt första sidan osv. Den här biverkningen är inte önskvärd i situationer där du vill ta bort datafält och visar en anledning till varför API:t för dataintegritet inte är lämpligt för den här användningen. </p> <p>Kontakta er Account Manager (CSM) för att samordna med vårt konsultteam inom Engineering Architect för ytterligare granskning och åtgärder för att ta bort eventuella PII- eller dataproblem.</p></td>
 </tbody> 
</table>

Ytterligare datasekretessresurser:

* [Allmänna villkor för GDPR](https://landing.adobe.com/dam/uploads/2018/in/adobe_gdpr_commonterms.pdf)
* Experience Cloud Data Privacy [Care-paket](https://landing.adobe.com/dam/uploads/2018/in/adobe_gdpr_carepackage.pdf)
* Experience Privacy [Blog Post](https://theblog.adobe.com/experiential-privacy-an-investment-opportunity-for-the-experience-business/)
