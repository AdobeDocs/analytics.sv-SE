---
description: Det här avsnittet innehåller svar på vanliga frågor.
subtopic: Data sources
title: Vanliga frågor om Data Sources
topic-fix: Developer and implementation
feature: Data Sources
exl-id: 2a5d38fe-5c5b-4275-bc44-e9cb02ec2f5d
source-git-commit: 79294cfc6f86e5a41a39504099cd730f53668725
workflow-type: tm+mt
source-wordcount: '1494'
ht-degree: 0%

---

# Vanliga frågor om Data Sources

Det här avsnittet innehåller svar på vanliga frågor.

## Hur knyter vi offlinedata till online-event? {#offline}

För att datakällor för transaktions-ID ska kunna koppla offlinedata till online-händelser måste du aktivera registrering av transaktions-ID. Se [Inspelning av transaktions-ID](/help/import/c-data-sources/datasrc-integrating-offline-data.md#section_30D6D47AEC0F4A36B87EBFE4C858F20C) för mer information.

## Hur mycket kostar det att använda funktionen Datakälla? {#cost}

Datakällor medför inga ytterligare avgifter utöver det vanliga serveranropet. Avgifterna för serveranrop gäller endast för datakälltyper med fullständig bearbetning, där individuella träffar skickas som datarader. Datakällor på trafik- och aggregeringsnivå medför inte merkostnader.

## Hur inkluderar jag kommentarer i datakällfiler? {#comments}

Varje rad i en datakällfil som börjar med ett nummertecken (#) behandlas som en kommentar.

## Måste jag inkludera en datumkolumn i mina kalkylbladsdata? {#date}

Ja. Eftersom många marknadsföringsrapporter skrivs från datumkolumnen kräver datakällor en datumkolumn.

## Kan jag lagra data i befintliga variabler som jag redan använder? {#variables}

Adobe rekommenderar att du väljer nya, oanvända variabler för att importera data med hjälp av datakällor. Om du är osäker på hur datafilen är konfigurerad eller vill förstå riskerna med att återanvända variabler bättre kontaktar du kundtjänst.

## Kan jag ta bort data som har importerats med datakällor? {#imported}

Nej. Data som överförts till rapporter med datakällor kan inte tas bort, inte ens av Adobe-tekniker, när de väl har importerats. Den infogas permanent i dina befintliga data och kan inte särskiljas från data som matas in via traditionella datainsamlingsmetoder (t.ex. JavaScript, ActionSource, API för datainfogning). Därför rekommenderar Adobe starkt att du överför data från datakällor till en testrapportssvit innan du överför dem till en produktionssvit.

## Hur mycket data kan jag importera samtidigt? {#amount}

Bearbetningen pausas om storleken överstiger 50 MB och inte återupptas förrän summan är under 50 MB. Om du vill begränsa fördröjningar när du skapar rapporter ska du inte överföra mer än 90 dagars data per dag.

## Skrivs befintliga data över när jag importerar data via datakällor? {#overwrite}

Data för datakällor skriver aldrig över befintliga rapportdata. I stället läggs data som överförs med datakällor till i befintliga data.

## När jag överför mina data via datakällor, varför får jag inte också mina mätvärden? {#metrics}

När du överför data från datakällor överför du de mätvärden som är tillgängliga i rapportgränssnittet.

Om du till exempel överför Call Center Revenue för produkter du säljer på din webbplats kan du ha denna Call Center Revenue i samma rapport som Online Revenue. Du kommer dock inte att kunna använda den tillsammans med Besök, eftersom du inte överförde antalet Besök med den. Adobe kan bara rapportera mätvärden och element som du har överfört via datakällor (utöver de vanliga mätvärdena i marknadsföringsrapporten).

## Vad händer om jag skickar negativa värden till rapportering via datakällor? {#negative}

Värdet minskas därefter.

## Vad är skillnaden mellan en trafikdatakälla och en generisk datakälla för konvertering? {#traffic}

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

## Tar datakällor underrelationer, korrelationer och lagerhantering i beaktande? {#breakdown}

Eftersom processen för datakälla (för allmän DS, icke-trafik) skapar enskilda träffar som bearbetas av cache, används delrelationsprocessen, men inte korrelationsprocessen. Pathing has the potential to be processed, but each hit will be its own visit, so no pathing is generated. Sökdata genereras för webbloggimporter.

## Är filtilläggen skiftlägeskänsliga för en överföring av datakälla eller en klassificeringsfil? {#case}

Om tilläggen för en överförd datakällfil eller en klassificeringsfil har inledande versal kommer filerna inte att bearbetas. Filtillägg för överföring av datakälla måste vara gemener. Till exempel: [!DNL file.TXT] och [!DNL file.FIN] kommer inte att bearbetas. På samma sätt [!DNL .TAB] och [!DNL .FIN] kommer inte att bearbetas. Men [!DNL .txt] och [!DNL .fin] bearbetas.

## Kan jag lägga till ytterligare händelser i den genererade mallen eller är jag begränsad till tre? {#template}

Du kan lägga till så många händelser du vill. Guiden tillåter dock endast tre händelser. När mallfilen har skapats kan du lägga till fler händelser efter behov.

## Vad händer med en datakällfil där en eller flera av posterna inte har samma antal kolumner som rubrikposten? {#header}

Om du har en datakällfil där en eller flera av posterna inte har samma antal kolumner som rubrikposten, kommer följande att inträffa.

* Ett e-postmeddelande skickas till den som skapat datakällan och meddelar dem om ett fel.
* Filen bearbetas inte på grund av kolumnmatchningsfel.

## Samlas information om datakällor in? {#rollup}

Information om datakällor kan sammanfogas. Adobe Customer Care måste dock bearbeta sammanslagningen på nytt från det historiska datumet för att inkludera historiska data. Om det aktuella datumet till exempel är den 31 oktober 2015 och du överför data för 1-15 augusti 2015 med Datakällor, måste sammanslagningen ställas in på att bearbeta om från och med den 1 augusti 2015, så att de nyimporterade data inkluderas.

Observera också att data aldrig ska överföras direkt till en sammanslagningsrapportsserie med datakällor. Om du behöver dessa data i en sammanslagning bör de importeras till en standardrapport, som även kallas en *`child suite`* till sammanslagningen. Kontakta Adobe kundtjänst om du vill ha mer information.

## Varför visar inte sidvisningsrapporten några datakällsdata för en enstaka dag, men rätt data visas för en vecka? {#week}

Datakällor rapporterar inte data per timme. När du försöker köra en rapport för en viss dag kan data bara delas upp efter timmen, så inget visas i rapporten. Du kan bara visa data när de har delats upp efter en nivå av daglig eller högre granularitet, som du kan göra genom att köra en rapport varje vecka eller månad.

## Hur beräknas unika besökare i en webbserverlogg över datakällor? {#unique}

Antalet unika besökare i en webbserverlogg beräknas som olika distinkta kombinationer av *`IP Address`* och *`User Agent`* i webbloggen. Varje unik kombination av dessa två objekt beräknas som en unik besökare. Om [!UICONTROL User Agent] kolumnen är tom (eller inte inkluderad i webbloggen) kan vi inte identifiera antalet unika besökare och hela överföringen räknas som bara en unik besökare (även om det finns flera IP-adresser).

## I Datakällor, hur vet jag vilken inloggning som tillhör vilken rapportsvit? {#login}

I Datakällor är rapportsvitens ID den första delen av inloggningen som läggs till med ett slumpmässigt nummer som identifierar den specifika datakälla som har konfigurerats. Exempel, `RSID-drmossdev5 Login-drmossdev5_0001343430`.

## Hur påverkar version 15 och segmentering datakällor? {#segmentation}

I version 15 beter sig datakällorna olika beroende på källtypen:

* Datakällor för fullständig bearbetning, webblogg och transaktions-ID visas som vanligt. När segment används filtreras data enligt segmentreglerna.
* Standard- eller konverteringsdatakällor (annonskampanjer, CRM, kundnöjdhet, webbplatsprestanda, generiska sammanfattningsdata, onlineköp, leads och offerter samt offlinekanaldata) visas i version 15. Eftersom dessa datakällor inte är knutna till besök eller besökare filtreras de bort när segment tillämpas.

## Finns det data som importeras med ett transaktions-ID i Clickstream-dataflöden och data warehouse? {#clickstream}

Datafeeden innehåller alla transaktions-ID-mått som har tagits emot. Om du däremot överför transaktions-ID-data för ett tidigare datum är det enda sättet att hämta dessa data att hämta dataflödet igen för den dagen.

## Är eVars som för närvarande finns kvar i besökarprofilen allokerade till mått som överförts med datakällor? {#visitor}

Nej för fullständig bearbetning, ja för transaktions-ID. Datakällor med fullständig bearbetning bearbetas med separata besökarprofiler, så även om besökar-ID:n matchar varandra kommer de inte att kopplas ihop från ett eVar-allokeringsperspektiv. Datakällor för transaktions-ID är knutna till huvudbesökarprofilen, så beständiga eVars-variabler tilldelas händelser som överförs med transaktions-ID.

## Bevaras eVars som överförs med datakällor för senare onlinebeteende? {#evars}

Nej. eVaror som överförs via datakällor för transaktions-ID läser bara från den lagrade profilinformationen, inte från profilen.
Nej. eVars är de enda variabler som sparas i ögonblicksbilden av besökarprofilen.

## Hur fungerar numeriska händelser och valutakurser med datakällor? {#numeric}

Fullständig bearbetning stöder endast äldre händelselistformat förutom händelsevärdet numeric/currency/Counter (mer än 1) direkt i händelselistan, det vill säga `"eventNN,eventKK"` not `"eventNN=#.##"`. Det betyder att det bara stöder en räknarhändelse om den skickas i händelsekolumnen i datakällfilen och den ökar med 1.

Om numeriska händelser, valutatecken eller räknarhändelser (fler än 1) krävs, använd produktlistan:

```js
s.products="Footwear;Running Shoes;1;99.99;event1=4.50";
s.products="Footwear;Running Shoes;1;99.99;event1=4.50|event4=1.99";
```
