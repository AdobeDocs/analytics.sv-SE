---
description: Visar de områden på din webbplats som besökarna mest har åtkomst till. Platsavsnitt kan innehålla produktgrupper, ungefär som kategorier, som du definierar. Du kan till exempel ha en grupp med kameror, en grupp med datorer och så vidare. Data för Conversion Site Sections-rapporten importeras från Site Section-rapporten i Traffic-gruppen, som tar emot information från kanalvariabeln i spårningskoden. Du kan använda den här rapporten för att identifiera den största effekten på webbplatsstatistik från objekt i olika avsnitt på webbplatsen.
title: Platsavsnitt
topic: Reports
uuid: 6839c566-f88f-4979-9cf5-52a77c0b0416
translation-type: tm+mt
source-git-commit: 3fe3442eae1bdd8b90acffc9c25d184714613c16

---


# Platsavsnitt

Visar de områden på din webbplats som besökarna mest har åtkomst till. Platsavsnitt kan innehålla produktgrupper, ungefär som kategorier, som du definierar. Du kan till exempel ha en grupp med kameror, en grupp med datorer och så vidare. Data för Conversion Site Sections-rapporten importeras från Site Section-rapporten i Traffic-gruppen, som tar emot information från kanalvariabeln i spårningskoden. Du kan använda den här rapporten för att identifiera den största effekten på webbplatsstatistik från objekt i olika avsnitt på webbplatsen.

* Den här rapporten refererar till data direkt från [s.channel](https://docs.adobe.com/content/help/en/analytics/implementation/vars/page-vars/channel.html) -variabeln som implementeras på din webbplats.
* Den här rapporten kan visas i både trand- och rankningsformat.
* Den här rapporten kan använda ett sökfilter för att hitta specifika radobjekt.
* Klassificeringar kan användas i den här rapporten, så att du kan byta namn på och konsolidera radobjekt.
* Korrelationer kan skapas med andra trafikvariabler via Admin Tools.
* Den här rapporten kan använda följande mått:

   * **Sidor**: antalet gånger som [pageName](https://docs.adobe.com/content/help/en/analytics/implementation/vars/page-vars/pagename.html) -variabeln eller URL:en har definierats (anges som standardmått)

   * **Alla sökmått**: Besök, Genomsnittligt siddjup, Genomsnittlig tid spenderad på sida, Inlägg, Avsluta, Läs in igen och Enkel åtkomst
   * Beroende på organisationens inställningar och rapportsviten: Dagliga, Veckovisa, Månadsvisa och Kvartalsvisa unika besökare kan aktiveras i den här rapporten.
   * **Alla standardiserade e-handelsvärden**: Intäkter, beställningar, enheter, kundvagnar, kundvagnsvyer, utcheckningar, tillägg till kundvagnen och kundvagnsborttagningar
   * **Alla anpassade händelser**: Händelser 1-80 och Händelser 81-100 om H22-koden eller senare används.

Alla konverteringshändelser i den senaste [!UICONTROL Site Sections Report] allokeringen. Konverteringen delas upp på sidor som inte innehåller några lyckade händelser i implementeringen. Detta skiljer sig från [sidrapporten](/help/components/c-variables/dimensionslist/reports-pages.md), som använder linjär allokering.

**Produktspecifik information**

<table id="table_525FDF95C8ED4BF2A1E25BE2DA971EFB"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Gränssnitt </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Rapporter och analyser </td> 
   <td colname="col2"> <p> <span class="uicontrol"> Webbplatsinnehåll</span> &gt; <span class="uicontrol"> Webbplatsavsnitt</span> </p> <p>Förutom korrelationer kan den här rapporten använda följande uppdelningar: </p> 
    <ul id="ul_9CD009D89B134C53807332E3C88D3C44"> 
     <li id="li_566417EB074D425C9A1F4FB28AA7FAB4"> 
      <ul id="ul_3795C7AAE6DA4B7E96FCDC7F3211DFBB"> 
       <li id="li_50B295E961724CFB83D222DE9B4C7FF2">Alla klassificerade rapporter baserade på denna rapport </li> 
       <li id="li_697682892D8841BC8120BEC0E1AE9753"> <span class="wintitle"> Rapport över spårningskoder</span> </li> 
       <li id="li_F6D893FCBA7A4B3EB04715833CA41022"> <span class="wintitle"> Produkter</span> och <span class="wintitle"> kategorier</span> - rapporter </li> 
       <li id="li_9F379E61DB4F4753AE1FFFC8F9C17347"> <span class="wintitle"> Kundlojalitetsrapport</span> </li> 
       <li id="li_64A6A06F9265410ABB425DA4AF50C440">Alla heldelsrelaterade konverteringsvariabler </li> 
       <li id="li_907DDFCC35AB48EEA5B169B4A2598FB1"> <span class="wintitle"> Marknadsföringskanaler, första och sista beröring</span> </li> 
       <li id="li_B08A0DCB40154152AF1033B7629A5B5A"> <span class="uicontrol"> Mål</span> &gt; <span class="uicontrol"> Kampanjrapport</span> (om aktiverad) </li> 
       <li id="li_6D4E65DD6E2B49C9A8C12181D23F185A">Tilldelad tid per besök </li> 
       <li id="li_C6D3AD5A534243A8A6E17C663FEBA6BA">SiteSections </li> 
       <li id="li_E1F46EED5CE2425D83200A2FCB686EE5">Inmatningssidor </li> 
       <li id="li_1201EE0EBF13476C9A9525E0700F30F3">De flesta trafikkällor rapporterar </li> 
       <li id="li_563E07858FB1473BB22C2B191E8BE620">Besök nummer </li> 
       <li id="li_1CAD77ABA6A2454282A4DA7E88C047E8">Profilrapporter för många besökare </li> 
       <li id="li_D3A04E4CD8EC4646AAB90BF19F0AFA8A">Alla konverteringsvariabler och listvariabler </li> 
       <li id="li_01C194CE0F3E4C0694A34B4C6697F385">Besök samt Daily, Weekly, Monthly, Quarterly och Arbitrary Unique Visitors finns tillgängliga. </li> 
      </ul> </li> 
    </ul> <p>Den här rapporten kan använda segment. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Ad hoc-analys </td> 
   <td colname="col2"> 
    <ul id="ul_DFF9BFC01FC1424B8905C2D2C0EFD156"> 
     <li id="li_65FDF1C165C84F729E0EE84FF671B5E4">Ad hoc-analys kan dela upp rapporten för platsavsnitt genom att i princip alla andra rapporter inom marknadsföringsrapportgränssnittet. </li> 
     <li id="li_2159DE10C52D40AA89E4C934FC184641">Förutom alla tidigare nämnda händelser kan man använda alla konverterings- och trafikvärden samt använda olika allokeringar för alla konverteringsvärden. </li> 
     <li id="li_3A23C6286D314B5D814612469F4F77C5">Den här rapporten kan använda flera mycket avancerade segment. </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

