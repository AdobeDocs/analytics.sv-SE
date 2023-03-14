---
description: Frågor och svar om Advertising Analytics.
title: Frågor och svar om reklamanalyser
feature: Advertising Analytics
exl-id: 664a5641-1c79-439f-a9fb-2ff134574412
source-git-commit: 10ff98f7ca4697afe5c2dae66be415c0d68c4aac
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

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
   <td colname="col1"> <p>F: Måste jag vara en <b>Adobe Advertising Cloud- eller Adobe Advertising Cloud-kund (AMO)</b> för att få tillgång till den här funktionen? </p> </td> 
   <td colname="col2"> <p>S: Nej, den här funktionaliteten är tillgänglig för kunder utanför Advertising Cloud och AMO. </p> <p>AMO-kunder kan utnyttja den befintliga integreringen mellan Analytics och AMO. kommer de inte att kunna använda annonser. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>F: som <b>Adobe Analytics SKU</b> ger dig rätt att använda Advertising Analytics? </p> </td> 
   <td colname="col2"> <p>S: Advertising Analytics finns för Adobe Analytics <a href="https://www.adobe.com/se/data-analytics-cloud/analytics/select.html"  > Välj </a>, <a href="https://www.adobe.com/se/data-analytics-cloud/analytics/prime.html"  > Prime </a>och <a href="https://www.adobe.com/se/data-analytics-cloud/analytics/ultimate.html"  > Ultimate </a> SKU:er. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>F: Måste vi <b>lönetillägg</b> för att använda Advertising Analytics? </p> </td> 
   <td colname="col2"> <p>S: Nej, vid sidan av rätt SKU-etablering medför Advertising Analytics inte någon extra kostnad. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>F: Kommer Advertising Analytics att räkna med <b>användning av serversamtal</b>? </p> </td> 
   <td colname="col2"> <p>S: Nej, Advertising Analytics använder en särskild typ av datakälla som inte medför kostnader för serveranrop. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>F: Om jag <b>använder redan Advertising Cloud/AMO</b>kan jag fortfarande använda Advertising Analytics-funktionerna? </p> </td> 
   <td colname="col2"> <p>S: Alla kompatibla sökmotorkonton skickas till Advertising Analytics och visas som skrivskyddade. Alla redigeringar och uppdateringar ska hanteras i Advertising Cloud/AMO. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>F: Jag äger rätt SKU, men jag <b>kan inte komma åt</b> Advertising Analytics, varför är det? </p> </td> 
   <td colname="col2"> <p>S: Advertising Analytics finns endast för Adobe Analytics administratörer. Administratörer kan dock bevilja icke-administratörer åtkomst. Kontakta administratören om du behöver åtkomstbehörighet. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Använda Advertising Analytics {#section_3A70C6C4D5A842B2981F0257A01F95FF}

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
   <td colname="col1"> <p>F: som <b>sökmotorkonton</b> ingår i Advertising Analytics? </p> </td> 
   <td colname="col2"> <p>S: Sökmotorkonton innehåller Google AdWords och Microsoft Bing. </p> <p>Obs! Yahoo Gemini absorberades av Microsoft Bing den 31 mars 2019. Detta innebär att annonskontoalternativet Yahoo Gemini inte längre är tillgängligt. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>F: Var ska jag gå? <b>åtkomst</b> Advertising Analytics? </p> </td> 
   <td colname="col2"> <p>S: När du har loggat in på Adobe Analytics går du till <span class="uicontrol"> Administratör </span> -menyn. Välj sedan det nya menyalternativet <span class="uicontrol"> Advertising Analytics </span> för att lägga till dina sökmotorkonton. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>F: Hur är <b>data som samlas in och skickas till Analytics</b>? </p> </td> 
   <td colname="col2"> <p>S: Advertising Analytics använder en serie anpassade API:er för att skicka data från sökmotorer via Adobe Advertising Cloud till Analytics. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>F: Vad <b>sökdata</b> Får jag med den här integreringen? </p> </td> 
   <td colname="col2"> <p>S: Du får 1) Impressions, 2) Click, 3) Costs, 4) Quality Score och 5) Average Position direkt från sökmotorerna samt 6) AMO ID Instance (Click Instances). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>F: Får jag <b>bryta ned mina Advertising Analytics-data</b> av andra analysdata (mått)? </p> </td> 
   <td colname="col2"> <p>S: Nej, de råa sökdata kommer in som en oberoende datauppsättning. Det finns dock en instansversion av klickdata som kan delas upp av andra analysdata. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>F: Vad är definitionen av de olika <b>statusindikatorer</b> för mina konton (Väntande, Aktiv, Pausad osv.)? </p> </td> 
   <td colname="col2"> <p>S: Var och en av dessa statusindikatorer identifierar livscykelstadiet för varje sökmotorkonto. </p> 
    <ul id="ul_F68AD377B2F04A47B20355B2FF4CF345"> 
     <li id="li_05F8D7C6D00E4742A65373BE6FAA0448"><b>Väntande</b> betyder att kontot har konfigurerats, men data hämtas ännu inte. </li> 
     <li id="li_42B1557A8AEC41008B85AF6E3F625CAB"><b>Pausad</b> betyder att kontot tidigare har konfigurerats men har försatts i ett inaktivt läge. </li> 
     <li id="li_30B72CC171874F308A2B8CE552EA6930"><b>Aktiv</b> betyder att kontot har konfigurerats fullständigt och hämtar sökdata. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>F: Jag försöker <b>mappa mina Advertising Analytics-konton till en specifik rapportsserie</b>, men det är inte tillgängligt i Report Suite modal. Varför? </p> </td> 
   <td colname="col2"> <p>S: Innan du kan tilldela ett Advertising Analytics-konto en rapportssvit måste den önskade rapportsviten vara <a href="/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-provision-rs.md"  > tillhandahålls för Advertising Analytics-rapportering </a>. </p> <p>Detta görs via en separat admin-sida som är tillgänglig från: <span class="ignoretag"> <span class="uicontrol"> Administratör </span>  &gt; <span class="uicontrol"> Rapportsviter </span>  &gt; <span class="uicontrol"> [select Experience Cloud-enabled report suite] </span>  &gt; <span class="uicontrol"> Redigera inställningar </span>  &gt; <span class="uicontrol"> Advertising Analytics Configuration </span> </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>F: Är det möjligt att tilldela en <b>Virtual Report Suite</b> (VRS) till ett Advertising Analytics-konto? </p> </td> 
   <td colname="col2"> <p>S: Virtual Report Suites samlar inte in data, så du kan inte direkt mappa ett Advertising Analytics-konto till ett VRS. </p> <p>Du kan mappa Advertising Analytics-kontot till den överordnade rapportsviten för det VRS som du vill visa data i. </p> <p>Sökmotorns mått (click/cost/imponsions) kanske inte visas i VRS om du inte inkluderar ett "or"-villkor i segmentlogiken baserat på AMO-ID (eller dess klassificering). Exempel: Om du lägger till"alla träffar där det finns ett AMO-ID" inkluderas sökmotorstatistik i segmentet. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>F: Rapporteras Advertising Analytics-statistik i <b>Marknadsföringskanaler</b> rapportera? </p> </td> 
   <td colname="col2"> <p>S: Nej, de ingår inte i rapporten om marknadsföringskanaler. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>F: <b>När</b> hämtas sökdata till Analytics? </p> </td> 
   <td colname="col2"> <p>S: Sökdata hämtas från sökmotorerna runt 6.00 (06.00) i tidszonen i datacentret för Analytics. Detta är när AMO-data samlas in och infogas i rapportsviten. Den konverteras sedan till rapportsvitens tidszon som en del av infogningen av data i Analytics. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>F: Vad kan <b>som tagits före klickningen</b>? Ger vi intryck, kostnader, genomsnittlig position osv. även utan att klicka? </p> </td> 
   <td colname="col2"> <p>S: AMO-ID:t hämtar sökmotorns mått: Impressions, Cost, Clicks, Average Position och Average Quality Score. Om det inte finns några klick, men det finns intryck, skickas fortfarande data för utfall/position/kvalitet till Analytics. Vanligtvis kostar det inget om du inte klickar. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>F: På vilken nivå hämtas dessa data? <b>Besökare? Träffa?</b> </p> </td> 
   <td colname="col2"> <p>S: Sökmotorns mätvärden hämtas på träffnivå och kopplas till AMO-ID:t (och dess klassificeringar). Det är data på sammanfattningsnivå och är inte kopplat till besök/besökare. Därför kan sökmotorns mått bara användas i segment som är träffnivåomfång och som baseras på AMO-ID (eller dess klassificeringar). </p> <p>AMO-ID:t registreras också på landningssidan i träffen för den sidan (som kopplar det till besöket/besökaren) och kommer att finnas kvar längre fram för att få kredit för andra analysvärden (tills det går ut eller skrivs över av ett nytt AMO-ID). Den är helt integrerad i datauppsättningen som alla andra eVar. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>F: Fångar vi bara google.com eller <b>landversioner</b> (som google.co.uk, google.it, google.fr eller google.de) också? </p> </td> 
   <td colname="col2"> <p>S: Klassificeringen av annonsplattformen fångar följande värden: "Google Adwords" och "Bing Ads". </p> <p>Ett vanligt tillvägagångssätt är att inkludera landskoden som en del av namngivningen av kampanjer. Du kan sedan filtrera ned eller segmentera (t.ex. om alla kampanjer börjar med countrycode_ och sedan skapar du ett segment där Campaigns (AMO-ID) börjar med "UK_", vilket ger dig endast data för Storbritannien). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>F: Mätvärdet "AMO-kostnad" är den kostnad som betalas för varje nyckelord/annons som rapporteras av sökmotorn. Är detta nettokostnad eller bruttokostnad? </p> </td> 
   <td colname="col2"> <p>S: "AMO-kostnad" är bara den kostnad som betalas till sökmotorerna. De inkluderar inga avgifter för myndigheter eller sökoptimerings-/hanteringsplattformar. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>F: Finns det några planer på att inkludera andra annonskanaler som <b>Visa</b> eller <b>Social</b>? </p> </td> 
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
   <td colname="col1"> <p>F: När mitt Advertising-konto konfigureras anges följande:<b> Automatisk spårning</b> kan leda till oavsiktliga konsekvenser. Vilka typer av följder kan inträffa? </p> </td> 
   <td colname="col2"> <p>A: 
     <ul id="ul_59EFF4A2ECE947EBBDB6A9FF6D072FE0"> 
      <li id="li_8731E4B7D6ED4F0996B3630A35D5BAC4">I det automatiska läget görs ett försök att lägga till URL-parametrar i slutet av spårningsmallarna/mål-URL:erna i rätt format. <b>Det är dock ditt ansvar att se till att de URL-parametrar som läggs till behålls korrekt på den slutliga landningssidan. </b> </li> 
      <li id="li_1202FE1FC88342378A60E8FE65E5426B">I det automatiska läget kan nyckelord infogas i landnings-URL:en, och webbservern kanske inte stöder nyckelord med specialtecken. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>F: Om jag först ställer in manuell eller automatisk spårning, <b>kan jag växla</b> till det andra spårningsläget senare? Vilka följder får det? </p> </td> 
   <td colname="col2"> <p>S: Ja, du kan växla, men du måste ta bort den gamla spårningslogiken innan du kan byta. Detta kan resultera i en viss driftstopp för spårning på den dag som switchen görs (särskilt om man går från manuell till automatisk). Därför bör du inte byta om det inte är absolut nödvändigt. </p> 
    <ul id="ul_3F3CADD1C97B4947A13837CEE63A599D"> 
     <li id="li_CB9265951FD040388AEAB9EAD790A36E"><b>Växla från manuell till automatisk</b>: Ta bort de manuella tilläggen i spårningsmallarna och växla sedan från manuell till automatisk i Advertising Analytics-användargränssnittet och spara inställningen. Observera att det kan ta upp till x timmar för systemet att fylla i de automatiska spårningskoderna. </li> 
     <li id="li_2B6ED1342E2D443B8AF26D03532AB8E4"><b>Växla från automatiskt till manuellt</b>: Uppdatera växlingen från manuell till automatisk i Advertising Analytics installationsgränssnitt och distribuera sedan de manuella spårningskoderna så snabbt som möjligt. När du distribuerar de manuella spårningskoderna ska du ta bort dem om du ser de automatiska spårningskoderna i sökmotorns spårningsmallar. </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>
