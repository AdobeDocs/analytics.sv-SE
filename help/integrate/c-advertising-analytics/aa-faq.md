---
description: 'null'
title: Vanliga frågor
uuid: 05724f56-cf98-4ad8-ad0d-83a5a4b1944a
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Vanliga frågor

## Åtkomst/tillstånd {#section_5F558C5981F747F0AF375A9E4B75C93C}

<table id="table_6713C3B0B6734F768370F974EB5AC5E8"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Fråga </th> 
   <th colname="col2" class="entry"> Svar </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>F: Måste jag vara kund <b>till</b> Adobe Advertising Cloud eller Adobe Advertising Cloud (AMO) för att få tillgång till den här funktionen? </p> </td> 
   <td colname="col2"> <p>S: Nej, den här funktionaliteten är tillgänglig för kunder som inte använder Advertising Cloud och AMO. </p> <p>AMO-kunder kan utnyttja den befintliga integreringen mellan Analytics och AMO. kommer de inte att kunna använda annonser. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>F: Vilka SKU:er för <b>Adobe Analytics</b> ger er rätt att använda Advertising Analytics? </p> </td> 
   <td colname="col2"> <p>S: Advertising Analytics finns för Adobe Analytics <a href="https://www.adobe.com/data-analytics-cloud/analytics/select.html"  > Select </a>, <a href="https://www.adobe.com/data-analytics-cloud/analytics/prime.html"  > Prime </a>och <a href="https://www.adobe.com/data-analytics-cloud/analytics/ultimate.html"  > Ultimate </a> SKU:er. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>F: Behöver vi <b>betala extra</b> för att använda Advertising Analytics? </p> </td> 
   <td colname="col2"> <p>S: Nej, utanför korrekt SKU-etablering medför inte extra kostnader. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>F: Räknas Advertising Analytics med hur mitt <b>serversamtal används</b>? </p> </td> 
   <td colname="col2"> <p>S: Nej, Advertising Analytics använder en särskild datakälltyp som inte medför kostnader för serveranrop. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>F: Om jag <b>redan använder Advertising Cloud/AMO</b>, kan jag då fortfarande använda funktionen Advertising Analytics? </p> </td> 
   <td colname="col2"> <p>S: Alla kompatibla sökmotorkonton skickas till Advertising Analytics och visas som skrivskyddade. Alla redigeringar eller uppdateringar ska hanteras i Advertising Cloud/AMO. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>F: Jag äger rätt SKU, men jag <b>kan inte komma åt</b> Advertising Analytics, varför är det? </p> </td> 
   <td colname="col2"> <p>S: Reklamanalys är bara tillgängligt för Adobe Analytics-administratörer. Administratörer kan dock bevilja icke-administratörer åtkomst. Kontakta administratören om du behöver åtkomstbehörighet. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Använda annonsanalys {#section_3A70C6C4D5A842B2981F0257A01F95FF}

<table id="table_4EC69262B7AB4DF49E736CF3B0362302"> 
 <thead> 
  <tr> 
   <th colname="col01" class="entry"> </th> 
   <th colname="col1" class="entry"> Fråga </th> 
   <th colname="col2" class="entry"> Svar </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>F: Vilka <b>sökmotorkonton</b> ingår i Advertising Analytics? </p> </td> 
   <td colname="col2"> <p>S: Sökmotorkonton innehåller Google AdWords och Microsoft Bing. </p> <p>Obs! Yahoo Gemini absorberades av Microsoft Bing den 31 mars 2019. Detta innebär att annonskontoalternativet Yahoo Gemini inte längre är tillgängligt. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>F: Var kan jag <b>komma åt</b> annonsanalys? </p> </td> 
   <td colname="col2"> <p>S: Navigera till Admin- <span class="uicontrol"> </span> menyn när du har loggat in på Adobe Analytics. Välj sedan det nya menyalternativet <span class="uicontrol"> Advertising Analytics </span> för att lägga till dina sökmotorkonton. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>F: Hur samlas <b>data in och överförs till Analytics</b>? </p> </td> 
   <td colname="col2"> <p>S: Advertising Analytics använder en serie anpassade API:er för att skicka data från sökmotorer via Adobe Advertising Cloud till Analytics. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>F: Vilka <b>sökdata</b> får jag med den här integreringen? </p> </td> 
   <td colname="col2"> <p>S: Du får 1) Impressions, 2) Click, 3) Costs, 4) Quality Score och 5) Average Position direkt från sökmotorerna samt 6) AMO ID Instance (Click Instances). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>F: Kan jag <b>bryta ned</b> mina Advertising Analytics-data efter andra analysdata (mått/mått)? </p> </td> 
   <td colname="col2"> <p>S: Nej, de råa sökdata kommer in som en oberoende datauppsättning. Det finns dock en instansversion av klickdata som kan delas upp av andra analysdata. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>F: Vad är definitionen av de olika <b>statusindikatorerna</b> för mina konton (Väntande, Aktiv, Pausad osv.)? </p> </td> 
   <td colname="col2"> <p>S: Var och en av dessa statusindikatorer identifierar livscykelstadiet för varje sökmotorkonto. </p> 
    <ul id="ul_F68AD377B2F04A47B20355B2FF4CF345"> 
     <li id="li_05F8D7C6D00E4742A65373BE6FAA0448"><b>Väntande</b> innebär att kontot har konfigurerats, men data hämtas ännu inte. </li> 
     <li id="li_42B1557A8AEC41008B85AF6E3F625CAB"><b>Pausad</b> innebär att kontot tidigare har konfigurerats men har försatts i ett inaktivt läge. </li> 
     <li id="li_30B72CC171874F308A2B8CE552EA6930"><b>Aktivt</b> innebär att kontot har konfigurerats fullständigt och att sökdata hämtas. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>F: Jag försöker <b>mappa mina Advertising Analytics-konton till en viss rapportsserie</b>, men den är inte tillgänglig i modalkoden för Report Suite. Varför? </p> </td> 
   <td colname="col2"> <p>S: Innan du kan tilldela ett Advertising Analytics-konto en rapportsvit måste den önskade rapportsviten <a href="/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-provision-rs.md"  > tillhandahållas för Advertising Analytics-rapportering </a>. </p> <p>Detta görs via en separat admin-sida som är tillgänglig från: <span class="ignoretag"> Admin <span class="uicontrol"> &gt; </span> Report Suites <span class="uicontrol"> &gt; </span> [select Experience Cloud-enabled report suite] <span class="uicontrol"> &gt; </span> Edit Settings <span class="uicontrol"> &gt; </span> <span class="uicontrol"> </span> </span>Advertising Analytics Configuration¥. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>F: Går det att tilldela ett <b>VRS-konto (Virtual Report Suite</b> ) till ett Advertising Analytics-konto? </p> </td> 
   <td colname="col2"> <p>S: Virtual Report Suites samlar inte in data, så du kan inte direkt mappa ett Advertising Analytics-konto till ett VRS. </p> <p>Du kan dock mappa Advertising Analytics-kontot till den överordnade rapportsviten för det VRS som du vill se data i. </p> <p>Sökmotorns mått (click/cost/imponsions) kanske inte visas i VRS om du inte inkluderar ett "or"-villkor i segmentlogiken baserat på AMO-ID (eller dess klassificering). Exempel: Om du lägger till"alla träffar där det finns ett AMO-ID" inkluderas sökmotorstatistik i segmentet. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>F: Är analysstatistik för annonsering rapporteringsbar i rapporten om <b>marknadsföringskanaler</b> ? </p> </td> 
   <td colname="col2"> <p>S: Nej, de ingår inte i rapporten om marknadsföringskanaler. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>F: <b>När</b> hämtas sökdata till Analytics? </p> </td> 
   <td colname="col2"> <p>S: Sökdata hämtas från sökmotorerna runt 6.00 (06.00) i tidszonen i datacentret för Analytics. Detta är när AMO-data samlas in och infogas i rapportsviten. Den konverteras sedan till rapportsvitens tidszon som en del av infogningen av data i Analytics. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>F: Vad kan du <b>fånga innan du klickar</b>? Ger vi intryck, kostnader, genomsnittlig position osv. även utan att klicka? </p> </td> 
   <td colname="col2"> <p>S: AMO-ID:t hämtar sökmotorns mått: Impressions, Cost, Clicks, Average Position och Average Quality Score. Om det inte finns några klick, men det finns intryck, skickas fortfarande data för utfall/position/kvalitet till Analytics. Vanligtvis kostar det inget om du inte klickar. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>F: På vilken nivå hämtas dessa data? <b>Besökare? Träffa?</b> </p> </td> 
   <td colname="col2"> <p>S: Sökmotorns mätvärden hämtas på träffnivå och kopplas till AMO-ID:t (och dess klassificeringar). Det är data på sammanfattningsnivå och är inte kopplat till besök/besökare. Därför kan sökmotorns mått bara användas i segment som är träffnivåomfång och som baseras på AMO-ID (eller dess klassificeringar). </p> <p>AMO-ID:t registreras också på landningssidan i träffen för den sidan (som kopplar det till besöket/besökaren) och kommer att finnas kvar längre fram för att få kredit för andra analysvärden (tills det går ut eller skrivs över av ett nytt AMO-ID). Den är helt inkorporerad i datauppsättningen som alla andra eVar. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>F: Fångar vi bara Google.com- eller <b>landsversioner</b> (som google.co.uk, google.it, google.fr eller google.de)? </p> </td> 
   <td colname="col2"> <p>S: Klassificeringen av annonsplattformen fångar följande värden: "Google Adwords" och "Bing Ads". </p> <p>Ett vanligt tillvägagångssätt är att inkludera landskoden som en del av namngivningen av kampanjer. Du kan sedan filtrera ned eller segmentera (t.ex. om alla kampanjer börjar med countrycode_ och sedan skapar du ett segment där Campaigns (AMO-ID) börjar med "UK_", vilket ger dig endast data för Storbritannien). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>F: Mätvärdet "AMO-kostnad" är den kostnad som betalas för varje nyckelord/annons som rapporteras av sökmotorn. Är detta nettokostnad eller bruttokostnad? </p> </td> 
   <td colname="col2"> <p>S: "AMO-kostnad" är bara den kostnad som betalas till sökmotorerna. De inkluderar inga avgifter för myndigheter eller sökoptimerings-/hanteringsplattformar. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>F: Finns det några planer på att inkludera andra annonskanaler som <b>Display</b> eller <b>Social</b>? </p> </td> 
   <td colname="col2"> <p>S: Nej, för närvarande har vi inga planer på dessa andra kanaler på färdplanen. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Automatisk kontra manuell spårning {#section_7437C4698A6D482EB7ED94A948390119}

<table id="table_9738FF8459574ED2937A860A665BE739"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Fråga </th> 
   <th colname="col2" class="entry"> Svar </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>F: När jag konfigurerar mitt Advertising-konto anges att<b> automatisk spårning</b> kan leda till oönskade konsekvenser. Vilka typer av följder kan inträffa? </p> </td> 
   <td colname="col2"> <p>S: 
     <ul id="ul_59EFF4A2ECE947EBBDB6A9FF6D072FE0"> 
      <li id="li_8731E4B7D6ED4F0996B3630A35D5BAC4">I det automatiska läget görs ett försök att lägga till URL-parametrar i slutet av spårningsmallarna/mål-URL:erna i rätt format. <b>Det är dock ditt ansvar att se till att de URL-parametrar som läggs till behålls korrekt på den slutliga landningssidan. </b> </li> 
      <li id="li_1202FE1FC88342378A60E8FE65E5426B">I det automatiska läget kan nyckelord infogas i landnings-URL:en, och webbservern kanske inte stöder nyckelord med specialtecken. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>F: Om jag ställer in manuell eller automatisk spårning från början, <b>kan jag då växla</b> till det andra spårningsläget senare? Vilka följder får det? </p> </td> 
   <td colname="col2"> <p>S: Ja, du kan växla, men du måste ta bort den gamla spårningslogiken innan du kan byta. Detta kan resultera i en viss driftstopp för spårning på den dag som switchen görs (särskilt om man går från manuell till automatisk). Därför bör du inte byta om det inte är absolut nödvändigt. </p> 
    <ul id="ul_3F3CADD1C97B4947A13837CEE63A599D"> 
     <li id="li_CB9265951FD040388AEAB9EAD790A36E"><b>Växla från manuell till automatisk</b>: Ta bort de manuella tilläggen i spårningsmallarna och växla sedan från manuell till automatisk i gränssnittet för Advertising Analytics och spara inställningen. Observera att det kan ta upp till x timmar för systemet att fylla i de automatiska spårningskoderna. </li> 
     <li id="li_2B6ED1342E2D443B8AF26D03532AB8E4"><b>Växla från automatiskt till manuellt</b>: Uppdatera växlingen från manuell till automatisk i konfigurationsgränssnittet för Advertising Analytics och distribuera sedan de manuella spårningskoderna så snabbt som möjligt. När du distribuerar de manuella spårningskoderna ska du ta bort dem om du ser de automatiska spårningskoderna i sökmotorns spårningsmallar. </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

