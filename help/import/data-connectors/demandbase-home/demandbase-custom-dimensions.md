---
description: Visar valfria dimensionsidentifierare som kan anges i steg 4 i Adobe Integration Wizard.
title: Anpassade dimensioner för Demandbase
uuid: d1621046-3aa2-46b9-a536-4a8fb792b69f
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Anpassade dimensioner för Demandbase{#demandbase-custom-dimensions}

Visar valfria dimensionsidentifierare som kan anges i steg 4 i Adobe Integration Wizard.

Om du är osäker på vilket API-ID du ska använda i guiden kontaktar du din Demandbase-representant.

>[!IMPORTANT]
>
>Vi rekommenderar att du INTE tar med IP-adressen som en anpassad dimension. Det extremt stora antalet unika värden kan orsaka prestandaproblem vid rapportering. Dessutom erbjuds IP-adressen redan som ett rapporteringsalternativ via Adobe datalagerrapportering.

<table id="table_3B44A18BE5FE45BC83389F89B48D9B97"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Dimension </th> 
   <th colname="col2" class="entry"> API-ID:n </th> 
   <th colname="col3" class="entry"> Beskrivning </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> ISP </td> 
   <td colname="col2"> isp </td> 
   <td colname="col3"> Anger om den identifierade organisationen klassificeras som en Internet-leverantör. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Marknadsföringsalias </td> 
   <td colname="col2"> marketing_alias </td> 
   <td colname="col3"> Rensat och/eller förkortat organisationsnamn (högst 32 tecken) för användning i annonser, meddelanden eller marknadsföringskopia. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Bevakade taggar för konto </td> 
   <td colname="col2"> watch_list (custom) </td> 
   <td colname="col3">Obegränsad uppsättning taggar som definieras av klienten och som kan läggas till i API-svarsdata, per organisation. <p><b>Exempel</b>: om du har en bevakningstagg med namnet Q4 Target blir API-fältet </p> <code> watch_list_q4_target</code> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Fortune 1000 </td> 
   <td colname="col2"> förmögenhet_1000 </td> 
   <td colname="col3"> Anger om organisationen finns med i Fortune 1000-listan. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Forbes 2000 </td> 
   <td colname="col2"> forbes_2000 </td> 
   <td colname="col3"> Anger om organisationen finns med i Forbes 2000-listan. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Antal anställda </td> 
   <td colname="col2"> employee_count </td> 
   <td colname="col3"> Antalet anställda i organisationen. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Årsförsäljning </td> 
   <td colname="col2"> annual_sales </td> 
   <td colname="col3"> För offentliga organ baseras årsomsättningen på företagsrapporterade offentliga uppgifter för det globala högkvarteret på alla platser. För privatägda organisationer baseras detta på en uppskattning av den årliga omsättningsintäktssumman. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Telefonnummer </td> 
   <td colname="col2"> telefon </td> 
   <td colname="col3"> Telefonnumret till den identifierade organisationen. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Gatuadress </td> 
   <td colname="col2"> street_address </td> 
   <td colname="col3"> Organisationens gatuadress. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Ort </td> 
   <td colname="col2"> stad </td> 
   <td colname="col3"> Organisationens ort. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Läge </td> 
   <td colname="col2"> läge </td> 
   <td colname="col3"> Organisationens status identifierad. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Landskod </td> 
   <td colname="col2"> country_code </td> 
   <td colname="col3"> ISO-landskoden för två tecken för den identifierade organisationen. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Land </td> 
   <td colname="col2"> country_name </td> 
   <td colname="col3"> Strängvärdets landsnamn för landet för den identifierade organisationen. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Postnummer </td> 
   <td colname="col2"> zip </td> 
   <td colname="col3"> Postnumret för det land/den stat där den identifierade organisationen finns. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Webbplats </td> 
   <td colname="col2"> web_site </td> 
   <td colname="col3"> Den URL som används av den identifierade organisationen. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Stock-väljaren </td> 
   <td colname="col2"> stock_ticker </td> 
   <td colname="col3"> Aktiebörsnoteraren om den identifierade organisationen är börsnoterad. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Primär SIC-kod </td> 
   <td colname="col2"> primär_sic </td> 
   <td colname="col3"> SIC-kod för konsensus som tilldelats den identifierade organisationen. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Latitud </td> 
   <td colname="col2"> latitud </td> 
   <td colname="col3"> Latitud för platsen för den identifierade organisationen. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Longitud </td> 
   <td colname="col2"> longitud </td> 
   <td colname="col3"> Longitud för platsen för den identifierade organisationen. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Trafik </td> 
   <td colname="col2"> trafik </td> 
   <td colname="col3"> Antalet webbplatser, som uppskattas till låg, medelhög eller hög eller mycket hög. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> B2B </td> 
   <td colname="col2"> b2b </td> 
   <td colname="col3"> Anger att det identifierade företaget främst säljer till andra företag. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> B2C </td> 
   <td colname="col2"> b2c </td> 
   <td colname="col3"> Anger att det identifierade företaget främst säljer till konsumenter eller enskilda. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Technology Insight </td> 
   <td colname="col2"> ??? </td> 
   <td colname="col3"> Upp till 75 teknikkategorier som definieras av kunder via kategori, leverantör och produkter för användning av riktade annonser och/eller anpassade annonser, meddelanden eller marknadsföringskopia. </td> 
  </tr> 
 </tbody> 
</table>

