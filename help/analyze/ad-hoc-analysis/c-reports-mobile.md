---
description: Visar information om webbplatsåtkomst från en mobil enhet. Mobilrapporter förbättrar besökaridentifieringen genom att samla in data om mobila enheter som används för att visa webbplatsen. Mobilrapporter kan identifiera en enhets tillverkare och funktioner, som skärmstorlekar, video-, ljud- och cookie-stöd och andra mätvärden. Mobilrapporter finns för alla rapportsviter.
title: Mobilrapporter
uuid: feb1fc34-3541-4b2d-b9cb-84d2e91d9539
translation-type: tm+mt
source-git-commit: 5d96a2868bee48e2294ec2fb27e0340a3bcc50ae
workflow-type: tm+mt
source-wordcount: '1392'
ht-degree: 0%

---


# Mobilrapporter

>[!IMPORTANT]
>
>Adobe flyttar Ad Hoc Analysis till livets slut den 1 mars 2021. [Läs mer](https://adobe.ly/discoverworkspace)

Visar information om webbplatsåtkomst från en mobil enhet. Mobilrapporter förbättrar besökaridentifieringen genom att samla in data om mobila enheter som används för att visa webbplatsen. Mobilrapporter kan identifiera en enhets tillverkare och funktioner, som skärmstorlekar, video-, ljud- och cookie-stöd och andra mätvärden. Mobilrapporter finns för alla rapportsviter.

## Mobilrapporter {#concept_08B95A72D0BA45EDAE9F56D0161EDC8C}

Visar information om webbplatsåtkomst från en mobil enhet. Mobilrapporter förbättrar besökaridentifieringen genom att samla in data om mobila enheter som används för att visa webbplatsen. Mobilrapporter kan identifiera en enhets tillverkare och funktioner, som skärmstorlekar, video-, ljud- och cookie-stöd och andra mätvärden. Mobilrapporter finns för alla rapportsviter.

Om du vill förbättra besökaridentifieringen för mobila enheter måste du vara med på transportföretagets lista (tillåtelselista) för att kunna skicka prenumerations-ID:n till en domän. (Du kan visa transportföretaget i **[!UICONTROL Visitor Profile]** >- **[!UICONTROL Domains]** rapporten.)

>[!NOTE]
>
>Om du vill visa rapporter på en mobil enhet loggar du in på [Experience Cloud](https://login.experiencecloud.adobe.com).

Mer information om mobilspårning finns på webbplatsen [Mobile Analytics](https://www.adobe.com/experience-cloud/topics/mobile-analytics.html) .

<table id="table_8862E941EF5A41EFB0E7FADEEA86C37D"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Rapport </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Enheter - rapport </p> </td> 
   <td colname="col2"> <p>Visar antalet besökare som har kommit åt din webbplats via mobila enheter, till exempel enheter som kör iOS eller Android. Den här rapporten kan hjälpa er att förstå effekten av mobilsatsningar så att ni kan planera utifrån detta. </p> <p>Du kan använda den här rapporten för att: </p> 
    <ul id="ul_76899F0390C64BF7BC8B3763E5E77CE9"> 
     <li id="li_0DB05A8459634EE59833540F67773298"> Utveckla strategier för mobilanvändare </li> 
     <li id="li_8B3381798A24476DBEF1C55B01D53FEF"> Identifiera målgruppens preferenser </li> 
     <li id="li_83A72B8277F6497CBE070DD46586C7E0"> Spåra uppkomsten av trådlösa och mobila användare </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Tillverkarrapport </p> </td> 
   <td colname="col2"> <p>Grupperar mobilenhetsträffar på er webbplats av mobilenhetstillverkaren. Rapporten visar typ av tillverkare, antal visningar för varje tillverkare och motsvarande procentandelar. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Rapport om skärmstorlek </p> </td> 
   <td colname="col2"> <p>Grupperar mobilenhetsträffar på webbplatsen efter enhetens skärmstorlek. Rapporten visar varje skärmstorlek, antalet besökare på webbplatsen som använde varje skärmstorlek och varje skärmstorlek som en procentandel av det totala antalet visningar. I rapporten <span class="wintitle"> Skärmstorlek</span> visas både skärmstorlekens höjd och bredd i förhållande till rapporten <span class="wintitle"> Skärmhöjd</span> och <span class="wintitle"> rapporten om skärmbredd</span> . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Skärmhöjd - rapport </p> </td> 
   <td colname="col2"> <p>Visar skärmhöjden för olika mobila enheter och antalet vyer för varje skärmhöjd. Du kan också visa rapporten <span class="wintitle"> Skärmstorlek</span> för att se både skärmhöjd och -bredd. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Skärmbreddsrapport </p> </td> 
   <td colname="col2"> <p>Visar skärmbredden för olika mobila enheter och antalet vyer för varje skärmbredd. Du kan också visa rapporten <span class="wintitle"> Skärmstorlek</span> för att se både skärmhöjd och -bredd. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Cookie-supportrapport </p> </td> 
   <td colname="col2"> <p>Grupperar träffar på mobila enheter utifrån om de stöder cookies eller inte. Besökarna delas in i grupper med supportcookies och grupper som inte gör det. Typen av mobil enhet identifieras i användaragentsträngen. Adobe har en lista över mobila enheter som har stöd för cookies. Om den mobila enhet som anges i användaragentsträngen också finns med i Adobe lista över mobila enheter, ökas raden som stöds i rapporten <span class="wintitle"> Cookie-stöd</span> . I annat fall ökas radobjektet Stöds inte i rapporten. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Bildsupportrapport </p> </td> 
   <td colname="col2"> <p>Grupperar mobila enheter baserat på de typer av bilder de stöder. Om till exempel en besökares telefon som stöder <span class="filepath"> .jpg</span> -bilder kommer åt en webbplats, ökas rapporten <span class="wintitle"> Bildstöd</span> med minst en. Om telefonen har stöd för mer än ett bildformat kan ett besök på en webbplats resultera i flera steg för det besöket. Med andra ord, om telefonen har stöd för <span class="filepath"> .jpg</span>-, <span class="filepath"> .png</span>- och <span class="filepath"> .gif</span> -format ökas var och en av grupperna i rapporten. Summan av grupperna kan därför vara större än summan som visas längst ned i rapporten. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Färgdjupsrapport </p> </td> 
   <td colname="col2"> <p>Grupperar träffar på mobila enheter efter antalet färger som stöds. Rapporten visar det totala antalet besökare på webbplatsen som använde en mobil enhet och delar upp dem i grupper baserat på antalet färger som konfigurerats i deras mobila enheter. Om besökarens mobiltelefon t.ex. har stöd för 24 färger ökar marketing reports and analytics det radobjekt som motsvarar 24 färger. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Rapport om stöd för ljud </p> </td> 
   <td colname="col2"> <p>Grupperar mobila enheter baserat på de typer av ljudformat de stöder. Om till exempel en besökares telefon stöder <span class="filepath"> .mp3</span> -formatet ökas rapporten <span class="wintitle"> Ljudsupport</span> med minst ett. Om telefonen har stöd för mer än ett bildformat kan ett besök på en webbplats resultera i ökningar för varje ljudtyp som stöds. Med andra ord, om en telefon har stöd för <span class="filepath"> .mp3</span>-, <span class="filepath"> .aac</span>- och <span class="filepath"> .amr</span> -format ökas var och en av grupperna i rapporten. Summan av grupperna kan därför vara större än summan som visas längst ned i rapporten. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Videosupportrapporter </p> </td> 
   <td colname="col2"> <p>Grupperar mobila enheter baserat på de typer av videoformat de stöder. Om till exempel en besökares mobila enhet stöder <span class="filepath"> .mp4</span>, ökar <span class="wintitle"> Video Support</span> -rapporten med minst ett när den kommer åt din webbplats. Om telefonen har stöd för flera bildformat (till exempel <span class="filepath"> .mp4</span> och <span class="filepath"> .wmv</span>) ökas varje grupp i rapporten. Därför kan summan av grupperna vara större än summan som visas längst ned i rapporten. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>DRM-rapport </p> </td> 
   <td colname="col2"> <p>Grupperar mobila enheter baserat på den typ av Digital Rights Management (DRM) som de stöder. DRM-grupper omfattar <span class="term"> Forward Lock</span>, <span class="term"> combined Delivery</span>, <span class="term"> Separate Delivery</span>och <span class="term"> Unknown</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Nettoprotokollrapport </p> </td> 
   <td colname="col2"> <p>Grupperar mobila enheter baserat på de nätverksprotokoll (GPRS, värdepapperscentraler, EDGE, HSCSD och så vidare) som de stöder. Rapporten innehåller även en okänd grupp för oidentifierade nätverksprotokoll. </p> <p>När en besökare använder en mobil enhet för att få åtkomst till din webbplats ökar rapporten om <span class="wintitle"> Net-protokoll</span> med minst en. Om telefonen har stöd för flera nätverksprotokoll ökar rapportens alla grupper. Därför kan summan av grupperna vara större än summan som visas längst ned i rapporten. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Rapport över operativsystem </td> 
   <td colname="col2"> <p>Grupperar mobila enheter baserat på det mobila operativsystem som körs på enheten. Mobila operativsystem inkluderar Windows, RIM, iOS, Symbian och så vidare. Rapporten innehåller även en okänd grupp för oidentifierade mobila operativsystem. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Java-versionsrapport </td> 
   <td colname="col2"> <p>Grupperar mobila enheter baserat på den Java-version som de stöder. Java-versionsrapporten identifierar den Java-version som stöds av den Java Specification Request (JSR) som stöds av enheten. Rapporten innehåller även en okänd grupp för oidentifierade mobila operativsystem. </p> <p>På webbplatsen för Java Community Process <a href="https://jcp.org/en/jsr/overview"  ></a> finns mer information om en viss JSR. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> URL-längdrapport för bokmärke </td> 
   <td colname="col2"> <p>Grupperar mobila enheter baserat på den maximala längden (i tecken) för en bokmärkes-URL. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Rapport om URL-längd för e-post </td> 
   <td colname="col2"> <p>Grupperar mobila enheter baserat på den maximala längd (i tecken) som stöds av en e-post-URL. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Webbläsarens URL-längdrapport </td> 
   <td colname="col2"> <p>Grupperar mobila enheter baserat på den maximala längd (i tecken) som stöds av en webbläsar-URL. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Rapport om överföring av enhetsnummer </td> 
   <td colname="col2"> <p>Grupperar mobila enheter baserat på om Device Number Transmit stöds. Rapporten innehåller även en okänd grupp för de enheter där stöd för överföring av enhetsnummer inte kan fastställas. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> PTT-rapport </td> 
   <td colname="col2"> <p>Grupperar mobila enheter baserat på om enheten stöder Push To Talk (PTT). Rapporten innehåller också en <span class="term"> okänd</span> grupp för de enheter där PTT-stöd inte kan fastställas. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Supportrapport för dekoration av e-post </td> 
   <td colname="col2"> <p>Grupperar mobila enheter baserat på om enheten stöder DecoMail, som gör att användaren kan dekorera sin post med grafik och animeringar. Rapporten innehåller även en <span class="term"> okänd</span> grupp för de enheter där stöd för dekoration av e-post inte kan fastställas. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Information Services-rapport </td> 
   <td colname="col2"> <p>Grupperar mobila enheter baserat på nyhetstjänster (kanal I/B, EZ News Flash, W+INFO osv.) som de stöder. När en besökare använder en mobil enhet med stöd för nyhetstjänster för att få tillgång till din webbplats ökar rapporten om informationstjänster med minst en. Om telefonen har stöd för flera nyhetstjänster ökar rapportens storlek för var och en av grupperna. Därför kan summan av grupperna vara större än summan som visas längst ned i rapporten. </p> </td> 
  </tr> 
 </tbody> 
</table>

