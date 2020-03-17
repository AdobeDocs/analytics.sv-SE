---
description: Datakällor har stöd för följande variabler när data bearbetas som ett standardserveranrop (Allmänt > Fullständig bearbetning).
subtopic: Data sources
title: Fullständig bearbetning
topic: Developer and implementation
uuid: 590ae89c-6e17-453b-b701-ce1adbea6fa4
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Fullständig bearbetning

Datakällor har stöd för följande variabler när data bearbetas som ett standardserveranrop (Allmänt > Fullständig bearbetning).

Fullständig databearbetning av datakälldata bearbetas som om de togs emot av Adobe-servrar vid den angivna tidpunkten (varje träff innehåller en tidsstämpel).

* [Besökarprofil](/help/import/c-data-sources/c-datasrc-types/datasrc-full-processing.md#section_6065627D0C144506965F562C80AE67F8)
* [Kolumnreferens](/help/import/c-data-sources/c-datasrc-types/datasrc-full-processing.md#section_92BAE76639E3404E97276B1BE0581078)

## Besökarprofil {#section_6065627D0C144506965F562C80AE67F8}

Data från datakällor bearbetas i sin helhet med hjälp av separata besökarprofiler, så även om besökar-ID:t i överförda data matchar data som samlats in med JavaScript eller något annat AppMeasurement-bibliotek kopplas inte besökarprofilerna från ett eVar-allokeringsperspektiv.

En användare med besökar-ID:t för `"user@example.com"` besök på webbplatsen från en marknadsföringskampanj med namnet&quot;Spring Sale&quot;, som lagras i kampanjvariabeln. Om du senare överför en transaktion med samma besökar-ID får kampanjen &quot;Spring Sale&quot; ingen kredit för några intäkt- eller lyckade händelser som överförts med hjälp av fullständiga bearbetningsdatakällor.

## Kolumnreferens {#section_92BAE76639E3404E97276B1BE0581078}

<table id="table_AAC04491D643467B9C80FDEF88130B13"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> JavaScript-variabel </th> 
   <th colname="col2" class="entry"> Kolumnvariabel för fullständig bearbetning </th> 
   <th colname="col3" class="entry"> Beskrivning </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>kampanj </p> </td> 
   <td colname="col2"> <p>kampanj </p> </td> 
   <td colname="col3"> <p>Spårningskod för konverteringskampanj. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>kanal </p> </td> 
   <td colname="col2"> <p>kanal </p> </td> 
   <td colname="col3"> <p>Kanalsträng (till exempel Sport Section). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>currencyCode </p> </td> 
   <td colname="col2"> <p>currencyCode </p> <p>Obs!  Den här variabeln stöds även av standarddatakällor som <code> currency code </code>. </p> </td> 
   <td colname="col3"> <p>Valutakod för intäkt (till exempel USD). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>tidsstämpel </p> </td> 
   <td colname="col2"> <p>datum </p> </td> 
   <td colname="col3"> <p>Använd datumformatet ISO 8601 för <code> YYYY-MM-DDThh:mm:ss±UTC_offset </code> (till exempel <code> 2013-09-01T12:00:00-07:00 </code>) eller Unix Time-format (antalet sekunder som gått sedan 1 januari 1970). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><i>eVarN</i> </p> </td> 
   <td colname="col2"> <p><i>eVarN</i>, dvs. &lt;eVar2&gt;..&lt;/eVar2&gt; </p> </td> 
   <td colname="col3"> <p>Konvertera eVar-namn. Du kan ha upp till 75 eVars ( <span class="varname"> eVar1 </span> - <span class="varname"> eVar75 </span>). </p> <p>Du kan ange eVar-namnet (eVar12) eller ett eget namn (Ad Campaign 3). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>händelser </p> </td> 
   <td colname="col2"> <p>händelser </p> </td> 
   <td colname="col3"> <p>Händelsesträng, formaterad med samma syntax som <a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/events.html"  > s.events- </a> variabeln. </p> <p>Exempel: </p> 
    <code>
      scAdd,event1,event7 
    </code> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><i>hierN</i> </p> </td> 
   <td colname="col2"> <p><i>hierN</i>, dvs. &lt;hier2&gt;..&lt;/hier2&gt; </p> </td> 
   <td colname="col3"> <p>Hierarkinamn. Du kan ha upp till 5 hierarkier ( <span class="varname"> hier1 </span> - <span class="varname"> hier5 </span>). </p> <p>Du kan ange standardnamn för hierarkin ( <span class="varname"> hier2 </span>) eller ett eget namn ( <span class="term"> Yankees </span>). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>linkName </p> </td> 
   <td colname="col2"> <p>linkName </p> </td> 
   <td colname="col3"> <p>Namn på länk. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>linkType </p> </td> 
   <td colname="col2"> <p>linkType </p> </td> 
   <td colname="col3"> <p>Typ av länk. Värden som stöds är: </p> 
    <ul id="ul_E441013055A9447AB6C3FB05B6099F7D"> 
     <li id="li_A33F66F30B60479284F72AE3AD4BF499"> <b>d</b>: Hämta länk </li> 
     <li id="li_182F695AA2D044DAB036BAFE38BC3915"> <b>e</b>: Avsluta länk </li> 
     <li id="li_4FD4D542D1774607860BEF41C1B090D1"> <b>o</b>: Anpassad länk. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>linkURL </p> </td> 
   <td colname="col2"> <p>linkURL </p> </td> 
   <td colname="col3"> <p>HREF of link. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>pageName </p> </td> 
   <td colname="col2"> <p>pageName </p> </td> 
   <td colname="col3"> <p>Sidnamn </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>pageType </p> </td> 
   <td colname="col2"> <p>pageType </p> </td> 
   <td colname="col3"> <p>Sidtyp ("Felsida"). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>pageURL </p> </td> 
   <td colname="col2"> <p>pageURL </p> </td> 
   <td colname="col3"> <p>Sidans URL (till exempel <code>https://www.mysite.com/index.html)</code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>produkter </p> </td> 
   <td colname="col2"> <p>produkter </p> </td> 
   <td colname="col3"> <p>Produktlista (till exempel <code> "Sports;Ball;1;5.95") </code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>prop1 - prop75 </p> </td> 
   <td colname="col2"> <p><i>propN</i>, dvs. &lt;prop2&gt;..&lt;/prop2&gt; </p> </td> 
   <td colname="col3"> <p>Property# string (t.ex. <span class="term"> Sports Section </span>). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>purchaseID </p> </td> 
   <td colname="col2"> <p>purchaseID </p> </td> 
   <td colname="col3"> <p>Inköps-ID-nummer. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>s_account </p> </td> 
   <td colname="col2"> <p>reportSuiteID </p> </td> 
   <td colname="col3"> <p>Rapportera det eller de Suite-ID som träffen ska tilldelas. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>server </p> </td> 
   <td colname="col2"> <p>server </p> </td> 
   <td colname="col3"> <p>Serversträng. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>läge </p> </td> 
   <td colname="col2"> <p>läge </p> </td> 
   <td colname="col3"> <p>Conversion state string. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>zip </p> </td> 
   <td colname="col2"> <p>zip </p> </td> 
   <td colname="col3"> <p>Postnummer för konvertering. </p> </td> 
  </tr> 
 </tbody> 
</table>

Följande tabell innehåller trafikvariabler som fylls i automatiskt när JavaScript-bibliotek används. Dessa egenskaper har inga associerade variabler, men kan importeras med hjälp av datakällor.

<table id="table_FDBC5BD225644AA09078C0570BE709FE"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Kolumnvariabel för fullständig bearbetning </p> </th> 
   <th colname="col2" class="entry"> <p>Beskrivning </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>browserHeight </p> </td> 
   <td colname="col2"> <p>Webbläsarhöjd i pixlar (till exempel 768). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>browserWidth </p> </td> 
   <td colname="col2"> <p>Webbläsarbredd i pixlar (till exempel 1024). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>charSet </p> </td> 
   <td colname="col2"> <p>Den teckenuppsättning som stöds för din webbplats. Exempel: UTF-8, ISO-8859-1 osv. </p> <p>En fullständig lista finns i <a href="https://marketing.adobe.com/resources/help/en_US/whitepapers/multibyte/index.html"  > Multi-Byte Character Sets </a> (Internationalization). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>clickAction </p> </td> 
   <td colname="col2"> <p>Objektidentifierare för besökarens klickkarta (oid) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>clickActionType </p> </td> 
   <td colname="col2"> <p>Objektidentifierartyp för klickkarta för besökare (oidt) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>clickContext </p> </td> 
   <td colname="col2"> <p>Sididentifierare för besökarens klickkarta (pid) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>clickContextType </p> </td> 
   <td colname="col2"> <p>Sididentifierartyp för klickkarta (pidt) för besökare </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>clickSourceID </p> </td> 
   <td colname="col2"> <p>Källindex för besökarens klickkarta (oi) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>clickTag </p> </td> 
   <td colname="col2"> <p>Objekttaggsnamn för besökarens klickkarta (inte) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>colorDepth </p> </td> 
   <td colname="col2"> <p>Övervaka färgdjup i bitar (till exempel 24). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>connectionType </p> </td> 
   <td colname="col2"> <p>Besökarens anslutningstyp ( <span class="term"> lan </span> eller <span class="term"> modem </span>). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>cookiesEnabled </p> </td> 
   <td colname="col2"> <p>J eller N för om besökaren stöder sessionscookies från första part. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>currencyCode </p> </td> 
   <td colname="col2"> <p>Standardvalutakoden som används på webbplatsen. </p> <p>Exempel: USD=U.S. dollar, euro = euro, JPY = japanska yen osv. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>homePage </p> </td> 
   <td colname="col2"> <p>Y eller N - är den aktuella sidan för besökarens hemsida. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>javaEnabled </p> </td> 
   <td colname="col2"> <p>J eller N - har besökaren Java aktiverat. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>javaScriptVersion </p> </td> 
   <td colname="col2"> <p>JavaScript-version (till exempel 1.3). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>plugin-program </p> </td> 
   <td colname="col2"> <p>Semikolonavgränsad lista med namn på webbläsarplugin-program. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>propN </p> </td> 
   <td colname="col2"> <p>Egenskapsvärden för dina egenskaper. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>hänvisare </p> </td> 
   <td colname="col2"> <p>URL för sidreferenten. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>upplösning </p> </td> 
   <td colname="col2"> <p>Bildskärmsupplösning (till exempel 1 024 × 768). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>scXmlVer </p> </td> 
   <td colname="col2"> <p>Marknadsföringen rapporterar XML-begärans versionsnummer (till exempel 1.0). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>tidszon </p> </td> 
   <td colname="col2"> <p>Besökarens tidszonsförskjutning från GMT i timmar (till exempel -8). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>visitorID </p> </td> 
   <td colname="col2"> <p>Besökarens ID-nummer. </p> </td> 
  </tr> 
 </tbody> 
</table>

