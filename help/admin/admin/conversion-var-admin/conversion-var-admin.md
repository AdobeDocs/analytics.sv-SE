---
description: Variabeln Custom Insight Conversion (eller eVar) placeras i Adobe-koden på utvalda webbsidor på webbplatsen. Dess främsta syfte är att segmentera framgångsstatistik för konverteringar i anpassade marknadsföringsrapporter. En eVar kan vara besöksbaserad och fungera på liknande sätt som cookies. Värden som skickas till eVar-variabler följer användaren under en förbestämd tidsperiod.
keywords: eVar
title: Konverteringsvariabler (eVar)
topic: Admin tools
uuid: 1eed0cb1-0735-4142-be21-43f264216b50
translation-type: tm+mt
source-git-commit: 327fdfd6a6d6bfe1c7bae9825fc8812b5ac7d095

---


# Konverteringsvariabler (eVars)

Variabeln Custom Insight Conversion (eller eVar) placeras i Adobe-koden på utvalda webbsidor på webbplatsen. Dess främsta syfte är att segmentera framgångsstatistik för konverteringar i anpassade marknadsföringsrapporter. En eVar kan vara besöksbaserad och fungera på liknande sätt som cookies. Värden som skickas till eVar-variabler följer användaren under en förbestämd tidsperiod.

När en eVar är inställd på ett värde för en besökare kommer Adobe automatiskt ihåg det värdet tills det upphör att gälla. Alla lyckade händelser som en besökare stöter på när eVar-värdet är aktivt räknas mot eVar-värdet.

eVars är bäst att använda för att mäta orsak och effekt, till exempel:

* Vilka interna kampanjer som påverkade intäkterna
* Vilka banners som till slut resulterade i en registrering
* Antalet gånger som en intern sökning användes innan en order skapades

Om trafikmätning eller vägning önskas rekommenderas användning av trafikvariabler.

>[!NOTE] Endast ett värde kan lagras i en eVar i en bildbegäran. Om du vill ha flera värden i ett eVar-värde rekommenderar vi att du implementerar [List-variabler (listvariabler)](https://docs.adobe.com/content/help/en/analytics/implementation/vars/page-vars/page-variables.html).

## Konverteringsvariabler - beskrivningar {#section_7C317BB0287A4B8EB0A1A4ECC40627BF}

Beskrivningar av fält som används vid [redigering av konverteringsvariabler](/help/admin/admin/conversion-var-admin/t-conversion-variables-admin.md).

<table id="table_E48D50926E6B492183300CA58A886927"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Element </p> </th> 
   <th colname="col2" class="entry"> <p>Beskrivning </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="uicontrol"> Namn </span> </p> </td> 
   <td colname="col2"> <p>Konverteringsvariabelns egna namn. Det här namnet är det som eVar refereras till i den allmänna rapporteringen och kommer att vara namnet på rapporten i den vänstra menyn. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="uicontrol"> Typ</span> </p> <p>(endast eVar) </p> </td> 
   <td colname="col2"> <p>Variabelvärdets typ: </p> <p> <b>Textsträng</b>:</span> Hämtar textvärden som används på din plats. Det här är den vanligaste typen av eVar och standardinställningen. Den fungerar på liknande sätt som andra variabler, där värdet i den är en statisk textsträng. Om du spårar saker som interna kampanjer eller interna söknyckelord är det här den rekommenderade inställningen. </p> <p> <b>Räknare</b>:</span> Räknar antalet gånger en åtgärd inträffar före händelsen success. Om du till exempel använder en eVar för att spåra interna sökningar på webbplatsen anger du det här värdet som <span class="uicontrol"> Textsträng</span> för att spåra användningen av söktermer. Ange det här värdet som <span class="uicontrol"> Räknare</span> för att räkna antalet sökningar, oavsett vilka söktermer som används. Du kan till exempel använda en räknareVar för att spåra antalet gånger som någon har använt din interna sökning innan han eller hon gör ett köp. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="uicontrol"> Allokering </span> </p> </td> 
   <td colname="col2"> <p>Avgör hur Analytics tilldelar kredit för en success-händelse om en variabel tar emot flera värden före händelsen. Värden som stöds är: </p> <p> <b>Senaste</b>: Det sista eVar-värdet får alltid medarbetare för lyckade händelser tills eVar-värdet förfaller. </p> <p> <b>Originalvärde</b>: Den första eVar får alltid medarbetare för lyckade händelser tills eVar upphör att gälla. </p> <p> <b> Linear</b>:Allokerar lyckade händelser lika i alla eVar-värden. Eftersom linjär allokering endast distribuerar värden inom ett besök bör du använda linjär allokering med eVar-förfallodatum för besök. </p> <p>Obs!  Genom att växla allokering till eller från Linear förhindrar du att historiska data visas. Blandning av allokeringstyper i rapporteringsgränssnittet kan leda till feldata i rapporter. Linjär allokering kan t.ex. dela intäkt över ett antal olika eVar-värden. När du har ändrat tillbaka till Senaste allokering är 100 % av denna intäkt kopplad till det senaste värdet. Den här associationen kan leda till felaktiga slutsatser från användarna. </p> <p>För att undvika risken för förvirring i rapporteringen gör Analytics att historiska data inte är tillgängliga för gränssnittet. Den kan visas om du bestämmer dig för att ändra den angivna eVar tillbaka till den ursprungliga allokeringsinställningen, men du bör inte ändra eVar-allokeringsinställningarna bara för att få tillgång till historiska data. Adobe rekommenderar att du använder en ny eVar när nya allokeringsinställningar är önskade för data som redan har registrerats, i stället för att ändra allokeringsinställningarna för en eVar som redan har en stor mängd historiska data inbyggda. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="uicontrol"> Förfaller efter</span> </p> </td> 
   <td colname="col2"> <p>Anger en tidsperiod eller händelse efter vilken eVar-värdet förfaller (får inte längre kredit för lyckade händelser). Om en success-händelse inträffar efter eVar-förfallodatumet får värdet None krediter för händelsen (ingen eVar var aktiv). </p> <p>Om du väljer en händelse som ett förfallovärde upphör variabeln bara att gälla om händelsen inträffar. Om händelsen inte inträffar upphör aldrig variabeln att gälla. </p> <p>De tillgängliga alternativen för förfallodatum kan delas in i fyra huvudkategorier: </p> 
    <ul id="ul_810A37C9B6624F429F2FB45C18F7B43F"> 
     <li id="li_654D9D9044EC4E61AA7ABA372DBF8A93"><b>På en sidvy eller besöksnivå.</b> Konverteringshändelser utanför sidvyn eller besöket är inte kopplade till eVar. </li> 
     <li id="li_689FBC8B4DAC41B3B0166E6586DD1990"><b>Baserat på en tidsperiod, t.ex. dag, vecka, månad eller år.</b> Konverteringshändelser efter den angivna tidsperioden associeras inte med eVar. Förfalloperioden börjar när variabeln är inställd. Varorna förfaller beroende på den tid de angavs till den andra (minut, timme, dag, månad osv.): 
      <ul id="ul_80C7E3182B6B4356B8A3CA920B81C6D5"> 
       <li id="li_F16F60319CCE406D9EDEFEC0A200BC4D">MINUTE=60 sekunder </li> 
       <li id="li_45F47F3F5691415B84052B235DF3BB54">HOUR=3600 sekunder (60 minuter) </li> 
       <li id="li_5288CE7D168E4C85B3D9BB67A44D32EC">DAY=86400 sekunder (24 timmar) </li> 
       <li id="li_60FC8BCD657745EE87B4E458CBA69583">VECKA=604800 sekunder (7 dagar) </li> 
       <li id="li_7A05A66613C84F929F030310B9567CF5">MONTH=2678400 sekunder (31 dagar) </li> 
       <li id="li_DCD3CABF59E34D5999B03E606B08AD85">QUARTER=8035200 sekunder (93 dagar - 3 månader av 31 dagar) </li> 
       <li id="li_54351D2899454D39A8BA205910D2CCB1">YEAR=31536000 sekunder (365 dagar) </li> 
      </ul> <p> </p> <p>Om ett besök börjar klockan 19.00 måndag och en eVar är inställd inom det besöket kl. 7.15, upphör giltigheten enligt nedan: </p> 
      <ul id="ul_72B311006BE6428698313D251C0940DB"> 
       <li id="li_50925D4A40AD4ACA88704A523138C5B9">Förfallodatum: eVar förfaller kl. 19.15 på tisdag. </li> 
       <li id="li_25846328766D4B4BAF407236C65C956C">Vecka som förfaller: eVar förfaller följande måndag kl. 7:15. </li> 
       <li id="li_82DB2D7F53304623A5E1241D75C7DF94">Månad som förfaller: eVar förfaller 31 dagar från måndag 07:15. </li> 
      </ul> </li> 
     <li id="li_C132C5C5A5344B91BDF5EB6A1C717C37"><b>Specifika konverteringshändelser.</b> Andra konverteringshändelser som utlöses efter den specifika händelse som associeras med eVar. </li> 
     <li id="li_5A782D743FB940649E6CB3E4BEA9B8B6"><b>Aldrig.</b> Så länge <span class="varname"> besökarID</span> -cookien är intakt kan hur lång tid som helst gå mellan eVar och händelse. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="uicontrol"> Status</span> </p> <p>(endast eVar) </p> </td> 
   <td colname="col2"> <p>Definierar eVar-status: </p> <p><b>Inaktiverad</b>:</span> Inaktiverar eVar. Tar bort eVar från konverteringsvariabellistan. </p> <p> <b>Inga underrelationer</b>:</span> Hindrar dig från att bryta ned eVar med en underrelation. </p> <p> <b>Grundläggande underrelationer</b>: Gör att </span>du kan dela upp en eVar-funktion i vilken rapport som helst med fullständiga underrelationer (till exempel Produkter eller Campaign). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="uicontrol"> Återställ</span> </p> </td> 
   <td colname="col2"> <p>Återställer alla befintliga värden i eVar. </p> <p>Använd den här inställningen när du återanvänder en eVar så att du inte blandar ett gammalt värde i en ny rapport. Återställning raderar inte historiska data. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="uicontrol"> Merchandising</span> </p> <p>(endast eVar) </p> </td> 
   <td colname="col2"> <p>Merchandising-variabler kan följa på en av två syntaxer: </p> <p> <b>Produktsyntax</b>:</span> Kopplar eVar-värdet till en produkt. Obs!  Om produktsyntax är markerad är avsnittet om bindningshändelse för marknadsföring inaktiverat och kan inte redigeras. Bindningshändelser gäller inte för den här syntaxen. </p> </p> <p> <b>Konverteringsvariabelsyntax</b>:</span> Associerar eVar med en produkt endast om en bindningshändelse inträffar. I det här fallet väljer du de händelser som fungerar som Bindningshändelser. </p> <p>Om du ändrar den här inställningen utan att uppdatera JavaScript-koden därefter, kommer förlorade data att uppstå. Se <a href="https://docs.adobe.com/content/help/en/analytics/components/variables/merchandising-variables/var-merchandising.html"> Marknadsföring av variabler</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="uicontrol"> Marknadsföringsbindningshändelse</span> </p> <p>(endast eVar) </p> </td> 
   <td colname="col2"> <p>Om Merchandising är inställt på <span class="uicontrol"> Conversion Variable Syntax</span>binder de valda händelserna det aktuella eVar-värdet med en produkt. </p> <p>Om du vill använda en bindningshändelse anger du <span class="uicontrol"> Allocation till Most Recent</span>. Om <span class="uicontrol"> Allocation är Original Value</span>, stannar den första eVar-produktbindningen tills eVar förfaller. </p> </td> 
  </tr> 
 </tbody> 
</table>

**Förfaller**

`eVars` förfaller efter en tidsperiod som du anger. När eVar upphör får den inte längre någon uppskattning för lyckade händelser. eVars kan också konfigureras så att de upphör att gälla vid lyckade händelser. Om du t.ex. har en intern kampanj som upphör efter ett besök, får den interna kampanjen endast kredit för inköp eller registreringar som sker under det besök där de aktiverades.

Det finns två sätt att förfalla en eVar:

* Du kan ange att eVar ska förfalla efter en angiven tidsperiod eller händelse.
* Du kan använda tvinga fram förfallodatumet för en eVar genom att återställa den, vilket är användbart när du återanvänder en variabel.

Om du t.ex. ändrar förfallotiden för en eVar från 30 till 90 dagar, kommer de eVar-värden som samlas in att finnas kvar under den nya förfallotiden (i det här fallet 90 dagar). Systemet tittar bara på den aktuella förfalloinställningen och den sista angivna tidsstämpeln för det eVar-värde som samlats in för att avgöra förfallotiden. Det är bara alternativet som **[!UICONTROL Reset]** förfaller värden och gör det omedelbart.

Ett annat exempel: Om en eVar används i maj för att återspegla interna kampanjer och upphör efter 21 dagar, och i juni används den för att fånga in interna söknyckelord, bör du den 1 juni tvinga fram en förfallotid för, eller återställning av, variabeln. Om du gör det kommer det att bidra till att bevara de interna kampanjvärdena från juni-rapporterna.

**Ärendekänslighet**

Variabler är inte skiftlägeskänsliga, men de visas i den första förekomstens skiftläge. Om till exempel den första instansen av eVar1 är inställd på &quot;Inloggad&quot;, men alla efterföljande instanser skickas som &quot;inloggad&quot;, visar rapporter alltid &quot;Inloggad&quot; som värdet för eVar.

**Räknare**

eVars används oftast för att lagra strängvärden, men de kan också konfigureras för att fungera som räknare. eVars är användbart som räknare när du försöker räkna antalet åtgärder som en användare utför före en händelse. Du kan till exempel använda en eVar för att hämta antalet interna sökningar före köpet. Varje gång en besökare söker ska eVar-objektet innehålla värdet &#39;+1&#39;. Om en besökare söker fyra gånger före ett köp visas en instans för varje totalantal: 1.00, 2.00, 3.00 och 4.00. Endast 4.00 får dock krediter för köphändelsen (beställningar och intäktsstatistik). Endast positiva tal tillåts som värden för en eVar-räknare.