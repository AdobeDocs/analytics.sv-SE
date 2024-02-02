---
description: Frågor och svar om Advertising Analytics.
title: Frågor och svar om reklamanalyser
feature: Advertising Analytics
exl-id: 664a5641-1c79-439f-a9fb-2ff134574412
source-git-commit: 591b82e271cc7474e9b413015804d4fe37d9050c
workflow-type: tm+mt
source-wordcount: '1307'
ht-degree: 0%

---

# Vanliga frågor

## Åtkomst/tillstånd {#access}

+++ Måste jag vara kund hos Adobe Advertising Cloud eller Adobe Advertising Cloud (AMO) för att få tillgång till den här funktionen?

Nej, den här funktionaliteten är tillgänglig för kunder utanför Advertising Cloud och AMO. </p> <p>AMO-kunder kan utnyttja den befintliga integreringen mellan Analytics och AMO; de kommer inte att kunna använda Ad Analytics.

+++

+++ Vilka Adobe Analytics-SKU:er berättigar dig till Advertising Analytics?

Advertising Analytics finns för Adobe Analytics

* [Välj](https://www.adobe.com/se/data-analytics-cloud/analytics/select.html)

* [Prime](https://www.adobe.com/se/data-analytics-cloud/analytics/prime.html)

* [Ultimate](https://www.adobe.com/se/data-analytics-cloud/analytics/ultimate.html)

+++

+++ Måste jag betala extra för att använda Advertising Analytics?

Nej, vid sidan av rätt SKU-etablering medför Advertising Analytics inte någon extra kostnad.

+++

+++ Räknas Advertising Analytics med användning av serversamtal?

Nej, Advertising Analytics använder en särskild typ av datakälla som inte medför kostnader för serveranrop.

+++

+++ Om jag redan använder Advertising Cloud/AMO, kan jag då ändå använda Advertising Analytics-funktionen?

Alla kompatibla sökmotorkonton skickas till Advertising Analytics och visas som skrivskyddade. Alla redigeringar och uppdateringar ska hanteras i Advertising Cloud/AMO.

+++

+++ Jag äger rätt SKU, men jag har inte tillgång till Advertising Analytics, varför är det?

Advertising Analytics är endast tillgängligt för Adobe Analytics-administratörer, men administratörer kan bevilja åtkomst till icke-administratörer. Kontakta administratören om du behöver åtkomstbehörighet.

+++

## Använda Advertising Analytics {#using}

+++ Vilka sökmotorkonton ingår i Advertising Analytics?

Sökmotorkonton innehåller Google AdWords och Microsoft Bing.

+++

+++ Var kan jag gå och få tillgång till Advertising Analytics?

När du har loggat in på Adobe Analytics går du till [!UICONTROL Admin]. Välj sedan [!UICONTROL Advertising Analytics] för att lägga till dina sökmotorkonton.

+++

+++ Hur samlas data in och överförs till Analytics?

Advertising Analytics använder en serie anpassade API:er för att skicka data från sökmotorer via Adobe Advertising Cloud till Analytics.

+++

+++ Vilka sökdata får jag med den här integreringen?

Du får

* Impressions
* Klickningar
* Kostnader
* Kvalitetspoäng
* Genomsnittlig position direkt från sökmotorerna, samt
* AMO ID-instanser (klicka på instanser).

+++

+++ Kan jag dela upp mina Advertising Analytics-data efter andra analysdata (mått/mått)?

Nej, de råa sökdata kommer in som en oberoende datauppsättning. Det finns dock en instansversion av klickdata som kan delas upp av andra analysdata.

+++ Vad är definitionen av de olika statusindikatorerna för mina konton (Väntande, Aktiv, Pausad osv.)? Var och en av dessa statusindikatorer identifierar livscykelstadiet för varje sökmotorkonto.

* [!UICONTROL Pending]
* [!UICONTROL Paused] betyder att kontot tidigare har konfigurerats men har försatts i ett inaktivt läge.
* [!UICONTROL Active] betyder att kontot har konfigurerats fullständigt och hämtar sökdata.

+++

+++ Jag försöker mappa mina Advertising Analytics-konton till en specifik rapportsserie, men den är inte tillgänglig i modalmetoden för Report Suite. Varför?

Innan du kan tilldela ett Advertising Analytics-konto en rapportssvit måste du [tillhandahålls för Advertising Analytics-rapportering](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-provision-rs.md)
Detta görs via en separat admin-sida som är tillgänglig från: Admin > Rapportsviter > [välj rapportsvit] > Redigera inställningar > Advertising Analytics-konfiguration.

+++

+++ Går det att tilldela ett Advertising Analytics-konto en virtuell rapportsserie?

Virtuella rapportsviter samlar inte in data, så du kan inte direkt mappa ett Advertising Analytics-konto till en Virtual Report Suite. Du kan dock mappa Advertising Analytics-kontot till den överordnade rapportsviten i den virtuella rapportsviten som du vill visa data i. Sökmotorns mått (click/cost/imponsions) kanske inte visas i den virtuella rapportsviten om du inte inkluderar ett &quot;or&quot;-villkor i segmentlogiken baserat på AMO-ID (eller dess klassificering). Exempel: Om du lägger till&quot;alla träffar där det finns ett AMO-ID&quot; inkluderas sökmotorns mått i segmentet.

+++

+++ Rapporteras Advertising Analytics-statistik i <b>Marknadsföringskanaler</b> rapportera?

Nej, de ingår inte i rapporten om marknadsföringskanaler.

+++

+++ När hämtas sökdata till Analytics?

Sökdata hämtas från sökmotorerna runt 6.00 (06.00) i tidszonen i datacentret för Analytics. Detta är när AMO-data samlas in och infogas i rapportsviten. Den konverteras sedan till rapportsvitens tidszon som en del av infogningen av data i Analytics.

+++

+++ Vad kan <b>som tagits före klickningen</b>? Ger vi intryck, kostnader, genomsnittlig position osv. även utan att klicka? </p> </td>

AMO-ID:t hämtar sökmotorns mått: Impressions, Cost, Clicks, Average Position och Average Quality Score. Om det inte finns några klick, men det finns intryck, skickas fortfarande data för utfall/position/kvalitet till Analytics. Vanligtvis kostar det inget om du inte klickar.

+++

+++ På vilken nivå hämtas dessa data? <b>Besökare? Träffa?</b>

Sökmotorns mätvärden hämtas på träffnivå och kopplas till AMO-ID:t (och dess klassificeringar). Det är data på sammanfattningsnivå och är inte kopplat till besök/besökare. Därför kan sökmotorns mått bara användas i segment som är träffnivåomfång och som baseras på AMO-ID (eller dess klassificeringar).

AMO-ID:t registreras också på landningssidan i träffen för den sidan (som kopplar det till besöket/besökaren) och kommer att finnas kvar längre fram för att få kredit för andra analysvärden (tills det går ut eller skrivs över av ett nytt AMO-ID). Den är helt integrerad i datauppsättningen på samma sätt som all annan eVar.

+++

+++ Kan vi bara hämta google.com eller <b>landversioner</b> (som google.co.uk, google.it, google.fr eller google.de) också?

Ad Platform-klassificeringen fångar följande värden:&quot;Google Adwords&quot; och&quot;Bing Ads&quot;. Ett vanligt tillvägagångssätt är att inkludera landskoden som en del av namngivningen av kampanjer. Du kan sedan filtrera ned eller segmentera (t.ex. om alla kampanjer börjar med countrycode_ och sedan skapar du ett segment där Campaigns (AMO-ID) börjar med &quot;UK_&quot;, vilket ger dig endast data för Storbritannien).

+++

+++ Mätvärdet &quot;AMO-kostnad&quot; är den kostnad som betalas för varje nyckelord/annons som rapporteras av sökmotorn. Är detta nettokostnad eller bruttokostnad?

&quot;AMO-kostnad&quot; är bara den kostnad som betalas till sökmotorerna. De inkluderar inga avgifter för myndigheter eller sökoptimerings-/hanteringsplattformar.

+++

+++ Finns det några planer på att inkludera andra annonskanaler som <b>Visa</b> eller <b>Social</b>?

Nej, för närvarande har vi inga planer på dessa andra kanaler på färdplanen.

+++


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
   <td colname="col2"> <p>S: 
     <ul id="ul_59EFF4A2ECE947EBBDB6A9FF6D072FE0"> 
      <li id="li_8731E4B7D6ED4F0996B3630A35D5BAC4">I det automatiska läget görs ett försök att lägga till URL-parametrar i slutet av spårningsmallarna/mål-URL:erna i rätt format. <b>Det är dock ditt ansvar att se till att de URL-parametrar som läggs till behålls korrekt på den slutliga landningssidan. </b> </li> 
      <li id="li_1202FE1FC88342378A60E8FE65E5426B">I det automatiska läget kan nyckelord infogas i landnings-URL:en, och webbservern kanske inte stöder nyckelord med specialtecken. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>F: Om jag först ställer in manuell eller automatisk spårning, <b>kan jag växla</b> till det andra spårningsläget senare? Vilka följder får det? </p> </td> 
   <td colname="col2"> <p>S: Ja, du kan växla, men du måste ta bort den gamla spårningslogiken innan du kan byta. Detta kan resultera i en viss driftstopp för spårning på den dag som switchen görs (särskilt om man går från manuell till automatisk). Därför bör du inte byta om det inte är absolut nödvändigt. </p> 
    <ul id="ul_3F3CADD1C97B4947A13837CEE63A599D"> 
     <li id="li_CB9265951FD040388AEAB9EAD790A36E"><b>Växla från manuell till automatisk</b>: Ta bort de manuella tilläggen i spårningsmallarna och växla sedan från manuell till automatisk i Advertising Analytics-gränssnittet och spara inställningen. Observera att det kan ta upp till x timmar för systemet att fylla i de automatiska spårningskoderna. </li> 
     <li id="li_2B6ED1342E2D443B8AF26D03532AB8E4"><b>Växla från Automatiskt till Manuellt</b>: Uppdatera växlingen från manuell till automatisk i Advertising Analytics installationsgränssnitt och distribuera sedan de manuella spårningskoderna så snabbt som möjligt. När du distribuerar de manuella spårningskoderna ska du ta bort dem om du ser de automatiska spårningskoderna i sökmotorns spårningsmallar. </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>
