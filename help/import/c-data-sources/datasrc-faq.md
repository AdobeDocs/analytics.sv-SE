---
description: Det här avsnittet innehåller svar på vanliga frågor.
subtopic: Data sources
title: Vanliga frågor om datakällor
topic: Developer and implementation
uuid: 394a627f-093c-400a-bfb3-c2aa24568deb
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Vanliga frågor om datakällor

Det här avsnittet innehåller svar på vanliga frågor.

## Hur knyter vi offlinedata till online-event? {#section_F48A9474A70D4CB8B449DE305F199AD6}

För att datakällor för transaktions-ID ska kunna koppla offlinedata till online-händelser måste du aktivera registrering av transaktions-ID. Mer information finns i Inspelning av [transaktions-ID](/help/import/c-data-sources/datasrc-integrating-offline-data.md#section_30D6D47AEC0F4A36B87EBFE4C858F20C) .

## Hur mycket kostar det att använda funktionen Datakälla? {#section_0B84E3E8891B45E8970EA9D8AAD1ADEC}

Datakällor medför inga ytterligare avgifter utöver det vanliga serveranropet. Avgifterna för serveranrop gäller endast för datakälltyper med fullständig bearbetning, där individuella träffar skickas som datarader. Datakällor på trafik- och aggregeringsnivå medför inte merkostnader.

## Hur inkluderar jag kommentarer i datakällfiler? {#section_AA42152C7B30425EA541A7BA274E78ED}

Varje rad i en datakällfil som börjar med ett nummertecken (#) behandlas som en kommentar.

## Måste jag inkludera en datumkolumn i mina kalkylbladsdata? {#section_EA37F5FFB13446C497B3C64943F7084E}

Ja. Eftersom många marknadsföringsrapporter skrivs från datumkolumnen kräver datakällor en datumkolumn.

## Kan jag lagra data i befintliga variabler som jag redan använder? {#section_AB557C2997D04EAFBDC61398B13D13C6}

Adobe rekommenderar att du väljer nya, oanvända variabler för att importera data med hjälp av datakällor. Om du är osäker på hur datafilen är konfigurerad eller vill förstå riskerna med att återanvända variabler bättre kontaktar du kundtjänst.

## Kan jag ta bort data som har importerats med datakällor? {#section_DB73BC06BD774738BF019B347D9DED96}

Nej. Data som överförts till rapporter med datakällor kan inte tas bort, inte ens av Adobe-tekniker, när de väl har importerats. Den infogas permanent i dina befintliga data och kan inte särskiljas från data som matas in via traditionella datainsamlingsmetoder (t.ex. JavaScript, ActionSource, API för datainfogning). Därför rekommenderar Adobe starkt att du överför data från datakällor till en testrapportssvit innan du överför dem till en produktionssvit.

## Hur mycket data kan jag importera samtidigt? {#section_7A76D59E2C5B434D9BDBD2ABD2873168}

Bearbetningen pausas om storleken överstiger 50 MB och inte återupptas förrän summan är under 50 MB. Om du vill begränsa fördröjningar när du skapar rapporter ska du inte överföra mer än 90 dagars data per dag.

## Skrivs befintliga data över när jag importerar data via datakällor? {#section_BDBD16D0AFD54D55AFDB8AC77D35FE77}

Data för datakällor skriver aldrig över befintliga rapportdata. I stället läggs data som överförs med datakällor till i befintliga data.

## När jag överför mina data via datakällor, varför får jag inte också mina mätvärden? {#section_33176B39744F4F5A861E69AD87B99B78}

När du överför data från datakällor överför du de mätvärden som är tillgängliga i rapportgränssnittet.

Om du till exempel överför Call Center Revenue för produkter du säljer på din webbplats kan du ha denna Call Center Revenue i samma rapport som Online Revenue. Du kommer dock inte att kunna använda den tillsammans med Besök, eftersom du inte överförde antalet Besök med den. Adobe kan bara rapportera mätvärden och element som du har överfört via datakällor (utöver de vanliga mätvärdena för marknadsföringsrapporter).

## Vad händer om jag skickar negativa värden till rapportering via datakällor? {#section_77E5F37F3CFB4407BA32A91E6F3132B2}

Värdet minskas därefter.

## Vad är skillnaden mellan en trafikdatakälla och en generisk datakälla för konvertering? {#section_A34C952490814D4FB802F22D9FB3E9F8}

Traffic Data Source laddas upp mycket snabbare eftersom det bara uppdaterar sammanfattningsvärdena till lämpliga tabeller. Den allmänna datakällan med konverteringsdata (händelser osv.) skapar en träff för varje värde i kolumnen som ska bearbetas.

Exempelfil:

<table id="table_D5408E0BDB984229B4C60A66BB53CEBB"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> Date </code> </p> </td> 
   <td colname="col2"> <p> <code> Event15 </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> 01/01/2013 </code> </p> </td> 
   <td colname="col2"> <p> <code> 553 </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

I exemplet ovan skapas 553 träffar som ska bearbetas i cachesystemet.

## Tar datakällor underrelationer, korrelationer och lagerhantering i beaktande? {#section_7ABAE2F3C4DD48E18FB8CB20AE8AFD14}

Eftersom processen för datakälla (för allmän DS, icke-trafik) skapar enskilda träffar som bearbetas av cache, används delrelationsprocessen, men inte korrelationsprocessen. Pathing has the potential to be processed, but each hit will be its own visit, so no pathing is generated. Sökdata genereras för webbloggimporter.

## Är filtilläggen skiftlägeskänsliga för en överföring av datakälla eller en klassificeringsfil? {#section_710787BA4D8C403D8326D666807832B8}

Om tilläggen för en överförd datakällfil eller en klassificeringsfil har inledande versal kommer filerna inte att bearbetas. Filtillägg för överföring av datakälla måste vara gemener. Till exempel [!DNL file.TXT] och [!DNL file.FIN] kommer inte att bearbetas. På samma sätt [!DNL .TAB] kommer och [!DNL .FIN] kommer inte att bearbetas. Men [!DNL .txt] och [!DNL .fin] bearbetas.

## Kan jag lägga till ytterligare händelser i den genererade mallen eller är jag begränsad till tre? {#section_F184913926DD43B1872956CED308ADB5}

Du kan lägga till så många händelser du vill. Guiden tillåter dock endast tre händelser. När mallfilen har skapats kan du lägga till fler händelser efter behov.

## Vad händer med en datakällfil där en eller flera av posterna inte har samma antal kolumner som rubrikposten? {#section_2666949CB11B49768774C904C93A16D4}

Om du har en datakällfil där en eller flera av posterna inte har samma antal kolumner som rubrikposten, kommer följande att inträffa.

* Ett e-postmeddelande skickas till den som skapat datakällan och meddelar dem om ett fel.
* Filen bearbetas inte på grund av kolumnmatchningsfel.

## Samlas information om datakällor in? {#section_E0E44C55A84245918E7CF5A4232F5C88}

Information om datakällor kan sammanfogas. Adobe Customer Care måste dock bearbeta sammanslagningen på nytt från det tidigare datumet för att inkludera historiska data. Om det aktuella datumet till exempel är den 31 oktober 2015 och du överför data för 1-15 augusti 2015 med Datakällor, måste sammanslagningen ställas in på att bearbeta om från och med den 1 augusti 2015, så att de nyimporterade data inkluderas.

Observera också att data aldrig ska överföras direkt till en sammanslagningsrapportsserie med datakällor. Om du behöver dessa data i en sammanslagning bör de importeras till en standardrapport, som även kallas en *`child suite`* till sammanslagningen. Kontakta Adobes kundtjänst om du vill ha mer information.

## Varför visar inte sidvisningsrapporten några datakällsdata för en enstaka dag, men rätt data visas för en vecka? {#section_E361A93AFDE1487989B4B0C4438EEDF7}

Datakällor rapporterar inte data per timme. När du försöker köra en rapport för en viss dag kan data bara delas upp efter timmen, så inget visas i rapporten. Du kan bara visa data när de har delats upp efter en nivå av daglig eller högre granularitet, som du kan göra genom att köra en rapport varje vecka eller månad.

## Hur beräknas unika besökare i en webbserverlogg över datakällor? {#section_477FEDFD1DBE45278E7D09AFBD59CDAC}

Antalet unika besökare i en webbserverlogg beräknas som olika distinkta kombinationer av *`IP Address`* och *`User Agent`* i webbloggen. Varje unik kombination av dessa två objekt beräknas som en unik besökare. Om kolumnen är tom (eller inte ingår i webbloggen) går det inte att identifiera antalet unika besökare, och hela överföringen räknas bara som en unik besökare (även om det finns flera IP-adresser). [!UICONTROL User Agent]

## I Datakällor, hur vet jag vilken inloggning som tillhör vilken rapportsvit? {#section_8EF9D22D5BE14C218724B06E78EF7DF4}

I Datakällor är rapportsvitens ID den första delen av inloggningen som läggs till med ett slumpmässigt nummer som identifierar den specifika datakälla som har konfigurerats. Exempel, `RSID-drmossdev5 Login-drmossdev5_0001343430`.

## Hur påverkar version 15 och segmentering datakällor? {#section_7E9E541DB73C49CDAADC031B678F8678}

I version 15 beter sig datakällorna olika beroende på källtypen:

* Datakällor för fullständig bearbetning, webblogg och transaktions-ID visas som vanligt. När segment används filtreras data enligt segmentreglerna.
* Standard- eller konverteringsdatakällor (annonskampanjer, CRM, kundnöjdhet, webbplatsprestanda, generiska sammanfattningsdata, onlineköp, leads och offerter samt offlinekanaldata) visas i version 15. Eftersom dessa datakällor inte är knutna till besök eller besökare filtreras de bort när segment tillämpas.

## Är mätvärden som importeras med ett transaktions-ID tillgängliga i Clickstream-dataflöden och datalager? {#section_01CD14CA3E11490CB2CBA433C649029E}

Datafeeden innehåller alla transaktions-ID-mått som har tagits emot. Om du däremot överför transaktions-ID-data för ett tidigare datum är det enda sättet att hämta dessa data att hämta dataflödet igen för den dagen.

## Är eVars som för närvarande finns kvar i besökarprofilen allokerade till mått som överförts med datakällor? {#section_1748BD5C6A12467F8082E07D6A9CD595}

Nej för fullständig bearbetning, ja för transaktions-ID. Datakällor med fullständig bearbetning bearbetas med separata besökarprofiler, så även om besökar-ID:n matchar varandra kommer de inte att kopplas ihop från ett eVar-allokeringsperspektiv. Datakällor för transaktions-ID är knutna till huvudbesökarprofilen, så beständiga eVars-variabler tilldelas händelser som överförs med transaktions-ID.

## Bevaras eVars som överförs med datakällor för senare onlinebeteende? {#section_0B490CEAAB604826AFD3E8B2531C8F2D}

Nej. eVaror som överförs via datakällor för transaktions-ID läser bara från den lagrade profilinformationen, inte från profilen.
Nej. eVars är de enda variabler som sparas i ögonblicksbilden av besökarprofilen.
