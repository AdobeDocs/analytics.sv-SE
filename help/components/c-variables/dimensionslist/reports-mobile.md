---
description: Visar information om webbplatsåtkomst från en mobil enhet. Mobilrapporter förbättrar besökaridentifieringen genom att samla in data om mobila enheter som används för att visa webbplatsen. Mobilrapporter kan identifiera en enhets tillverkare och funktioner, som skärmstorlekar, video-, ljud- och cookie-stöd och andra mätvärden. Mobilrapporter finns för alla rapportsviter.
title: Mobil
topic: Reports
uuid: ec8f6977-da92-478e-a934-c32cf5889526
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Mobil

Visar information om webbplatsåtkomst från en mobil enhet. Mobilrapporter förbättrar besökaridentifieringen genom att samla in data om mobila enheter som används för att visa webbplatsen. Mobilrapporter kan identifiera en enhets tillverkare och funktioner, som skärmstorlekar, video-, ljud- och cookie-stöd och andra mätvärden. Mobilrapporter finns för alla rapportsviter.

## Mobil {#topic_D306EA4558194488AC47A45B9C570150}

Visar information om webbplatsåtkomst från en mobil enhet. Mobilrapporter förbättrar besökaridentifieringen genom att samla in data om mobila enheter som används för att visa webbplatsen. Mobilrapporter kan identifiera en enhets tillverkare och funktioner, som skärmstorlekar, video-, ljud- och cookie-stöd och andra mätvärden. Mobilrapporter finns för alla rapportsviter.

> [!NOTE] Mobilrapporter visar endast webbtrafik för mobiler. Mobilappsdata som samlats in med iOS, Android och andra SDK:er visas i Mobile App Reports och visas endast när de är aktiverade i Admin Tools.

Följande mobilrapporter är tillgängliga:

<table id="table_900BB8F2F3A746B6B97DC629B39910DA"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Rapport </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Enheter </p> </td> 
   <td colname="col2"> <p>Visar antalet besökare som har kommit åt din webbplats via mobila enheter, till exempel enheter som kör iOS eller Android. Den här rapporten kan hjälpa er att förstå effekten av mobilsatsningar så att ni kan planera utifrån detta. Du kan använda den här rapporten för att: </p> <p> 
     <ul id="ul_8CC40461C2944A63AED561E384275D24"> 
      <li id="li_4667815ED7384DE9824FB47F02040374"> <p>Utveckla strategier för mobilanvändare </p> </li> 
      <li id="li_12C1F430E5464FB4AC29C2D970165935"> <p>Identifiera målgruppens preferenser </p> </li> 
      <li id="li_BFECB3B1F5A345BA82FC22BF99E8E418"> <p>Spåra uppkomsten av trådlösa och mobila användare </p> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Tillverkare </td> 
   <td colname="col2"> Grupperar mobilenhetsträffar på er webbplats av mobilenhetstillverkaren. Rapporten visar typ av tillverkare, antal visningar för varje tillverkare och motsvarande procentandelar. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Skärmstorlek </td> 
   <td colname="col2"> <p> Grupperar mobilenhetsträffar på webbplatsen efter enhetens skärmstorlek. Rapporten visar varje skärmstorlek, antalet besökare på webbplatsen som använde varje skärmstorlek och varje skärmstorlek som en procentandel av det totala antalet visningar. I rapporten Skärmstorlek visas både skärmstorlekens höjd och bredd jämfört med rapporten Skärmhöjd och rapporten Skärmbredd. </p> <p>Rapporten om mobilskärmsstorlek är för närvarande statisk per enhet. Oavsett skärmorientering har varje enhet en fast skärmupplösning i rapporten. Du kan se detta genom att bryta ned Skärmstorlek efter mobil enhet. </p><img placement="break" align="center"  src="assets/mobile-screen-sizes.png" id="image_A6DB4558376042A5822B892C7CEA1A7C" /> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Skärmhöjd </td> 
   <td colname="col2"> <p> Visar skärmhöjden för olika mobila enheter och antalet vyer för varje skärmhöjd. Du kan också visa rapporten <span class="wintitle"> Skärmstorlek</span> för att se både skärmhöjd och -bredd. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Skärmbredd </td> 
   <td colname="col2"> <p> Visar skärmbredden för olika mobila enheter och antalet vyer för varje skärmbredd. Du kan också visa rapporten <span class="wintitle"> Skärmstorlek</span> för att se både skärmhöjd och -bredd. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Cookie-stöd </td> 
   <td colname="col2"> <p>Grupperar träffar på mobila enheter utifrån om de stöder cookies eller inte. Besökarna delas in i grupper med supportcookies och grupper som inte gör det. Typen av mobil enhet identifieras i användaragentsträngen. Adobe har en lista över mobila enheter som har stöd för cookies. Om den mobila enhet som anges i användaragentsträngen också finns med i Adobes lista över mobila enheter ökas radposten <span class="term"> som stöds</span> i rapporten <span class="wintitle"> Cookie-stöd</span> . I annat fall ökas radobjektet <span class="term"> Stöds</span> inte i rapporten. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Bildstöd </td> 
   <td colname="col2"> <p> Grupperar mobila enheter baserat på de typer av bilder de stöder. </p> <p>Om till exempel en besökares telefon som stöder <span class="filepath"> .jpeg</span> -bilder kommer åt en webbplats, ökas rapporten <span class="wintitle"> Bildstöd</span> med minst en. Om telefonen har stöd för mer än ett bildformat kan ett besök på en webbplats resultera i flera steg för det besöket. Med andra ord, om telefonen har stöd för <span class="filepath"> .jpeg</span>-, <span class="filepath"> .png</span>- och <span class="filepath"> .gif</span> -format ökas var och en av grupperna i rapporten. Summan av grupperna kan därför vara större än summan som visas längst ned i rapporten. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Färgdjup </td> 
   <td colname="col2"> <p> Grupperar träffar på mobila enheter efter det antal färger som stöds. Rapporten visar det totala antalet besökare på webbplatsen som använde en mobil enhet och delar upp dem i grupper baserat på antalet färger som konfigurerats i deras mobila enheter. </p> <p>Om besökarens mobiltelefon t.ex. har stöd för 24 färger ökas radobjektet med 24 färger. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Ljudstöd </td> 
   <td colname="col2"> <p> Grupperar mobila enheter baserat på de typer av ljudformat de stöder. </p> <p>Om till exempel en besökares telefon stöder <span class="filepath"> .mp3</span> -formatet ökas ljudsupportrapporten med minst ett steg. Om telefonen har stöd för mer än ett bildformat kan ett besök på en webbplats resultera i ökningar för varje ljudtyp som stöds. Med andra ord, om en telefon har stöd för <span class="filepath"> .mp3</span>-, <span class="filepath"> .aac</span>- och <span class="filepath"> .amr</span> -format ökas var och en av grupperna i rapporten. Summan av grupperna kan därför vara större än summan som visas längst ned i rapporten. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Stöd för video </td> 
   <td colname="col2"> <p> Grupperar mobila enheter baserat på de typer av videoformat de stöder. </p> <p>Om till exempel en besökares mobila enhet stöder <span class="filepath"> .mp4</span>ökas videosupportrapporten med minst ett när den kommer åt webbplatsen. Om telefonen har stöd för flera bildformat (till exempel <span class="filepath"> .mp4</span> och <span class="filepath"> .wmv</span>) ökas varje grupp i rapporten. Därför kan summan av grupperna vara större än summan som visas längst ned i rapporten. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> DRM </td> 
   <td colname="col2"> <p> Grupperar mobila enheter baserat på den typ av DRM (Digital Rights Management) som de stöder. DRM-grupper omfattar <span class="term"> Forward Lock</span>, <span class="term"> combined Delivery</span>, <span class="term"> Separate Delivery</span>och <span class="term"> Unknown.</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Nettoprotokoll </td> 
   <td colname="col2"> <p> Grupperar mobila enheter baserat på de nätverksprotokoll (GPRS, värdepapperscentraler, EDGE, HSCSD och så vidare) som de stöder. Rapporten innehåller även en okänd grupp för oidentifierade nätverksprotokoll. </p> <p>När en besökare använder en mobil enhet för att få tillgång till din webbplats ökar Net Protokoll-rapporten med minst ett steg. Om telefonen har stöd för flera nätverksprotokoll ökar rapportens alla grupper. Därför kan summan av grupperna vara större än summan som visas längst ned i rapporten. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Operativsystem (borttaget) </td> 
   <td colname="col2"> <p> Grupperar mobila enheter baserat på det mobila operativsystem som körs på enheten. Mobila operativsystem inkluderar Windows, RIM, iOS, Symbian och så vidare. Rapporten innehåller även en okänd grupp för oidentifierade mobila operativsystem. </p> <p>Obs! Den här rapporten togs bort när rapporten Technology &gt; <a href="/help/components/c-variables/dimensionslist/reports-operating-system.md"  > Operating Systems</a> uppdaterades så att den omfattar alla operativsystem, inklusive mobiler. Du kan skapa ett segment där det finns en"mobil enhet" och använda det i rapporten Technology &gt; Operating Systems (Teknik &gt; Operativsystem) för att endast visa mobila operativsystem. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Java-version </td> 
   <td colname="col2"> <p> Grupperar mobila enheter baserat på den Java-version som de stöder. Java-versionsrapporten identifierar den Java-version som stöds av den Java Specification Request (JSR) som stöds av enheten. Rapporten innehåller även en okänd grupp för oidentifierade mobila operativsystem. </p> <p>På webbplatsen för Java Community Process <a href="https://jcp.org/en/jsr/overview"  ></a> finns mer information om en viss JSR. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> URL-längd för bokmärke </td> 
   <td colname="col2"> <p> Grupperar mobila enheter baserat på den maximala längden (i tecken) för en bokmärkes-URL. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Längd på e-post-URL </td> 
   <td colname="col2"> <p> Grupperar mobila enheter baserat på den maximala längd (i tecken) som stöds av en e-post-URL. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Webbläsarens URL-längd </td> 
   <td colname="col2"> <p> Grupperar mobila enheter baserat på den maximala längd (i tecken) som stöds av en webbläsar-URL. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Överföring av enhetsnummer (PÅ/AV) </td> 
   <td colname="col2"> <p> Grupperar mobila enheter baserat på om Device Number Transmit stöds. Rapporten innehåller även en okänd grupp för de enheter där stöd för överföring av enhetsnummer inte kan fastställas. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> PTT </td> 
   <td colname="col2"> <p> Grupperar mobila enheter baserat på om enheten stöder Push To Talk (PTT). Rapporten innehåller också en <span class="term"> okänd</span> grupp för de enheter där PTT-stöd inte kan fastställas. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Stöd för dekoration av e-post </td> 
   <td colname="col2"> <p> Grupperar mobila enheter baserat på om enheten stöder DecoMail, som gör att användaren kan dekorera sin post med grafik och animeringar. Rapporten innehåller även en <span class="term"> okänd</span> grupp för de enheter där stöd för dekoration av e-post inte kan fastställas. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Informationstjänster </td> 
   <td colname="col2"> <p> Grupperar mobila enheter baserat på nyhetstjänsterna (Channel I/B, EZ News Flash, W+INFO osv.). som de stöder. När en besökare använder en mobil enhet med stöd för nyhetstjänster för att få tillgång till din webbplats ökar rapporten för <span class="wintitle"> informationstjänster</span> med minst en. Om telefonen har stöd för flera nyhetstjänster ökar rapportens storlek för var och en av grupperna. Därför kan summan av grupperna vara större än summan som visas längst ned i rapporten. </p> </td> 
  </tr> 
 </tbody> 
</table>

