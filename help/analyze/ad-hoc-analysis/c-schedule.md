---
description: Du kan anpassa leveransschemat för rapporter. Du kan stoppa leveransen vid en viss tidpunkt eller ange hur många gånger du vill skicka en rapport. Nya scheman använder det datumintervall som definieras i rapporten. Om du till exempel skapar en rapport för de senaste 90 dagarna och schemalägger att den ska köras dagligen, får du en rapport för de senaste 90 dagarna varje dag. Om du skapar en rapport med ett statiskt datumintervall från kalendern visas samma rapport varje gång den skickas.
title: Schemaläggningshanteraren
topic: Ad hoc analysis
uuid: 82a054ef-109d-414d-a6e1-e09ee57c163f
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Schemaläggningshanteraren

Du kan anpassa leveransschemat för rapporter. Du kan stoppa leveransen vid en viss tidpunkt eller ange hur många gånger du vill skicka en rapport. Nya scheman använder det datumintervall som definieras i rapporten. Om du till exempel skapar en rapport för de senaste 90 dagarna och schemalägger att den ska köras dagligen, får du en rapport för de senaste 90 dagarna varje dag. Om du skapar en rapport med ett statiskt datumintervall från kalendern visas samma rapport varje gång den skickas.

## Schemaläggningshanteraren {#concept_A1CDE14B72A54DD6AE17B816092CAB8B}

Du kan anpassa leveransschemat för rapporter. Du kan stoppa leveransen vid en viss tidpunkt eller ange hur många gånger du vill skicka en rapport. Nya scheman använder det datumintervall som definieras i rapporten. Om du till exempel skapar en rapport för de senaste 90 dagarna och schemalägger att den ska köras dagligen, får du en rapport för de senaste 90 dagarna varje dag. Om du skapar en rapport med ett statiskt datumintervall från kalendern visas samma rapport varje gång den skickas.

> [!NOTE] När ett användarkonto är inaktiverat pausas alla schemalagda rapportleveranser som skapas av den användaren.

Om du vill vara säker på att radobjekt i en uppdelning är beständiga i sparade och schemalagda rapporter använder du **[!UICONTROL Edit Items]** funktionen i [tabellverktyget](/help/analyze/ad-hoc-analysis/c-tablebuilder.md) för att skapa fasta dimensionslistor i uppdelningar.

>[!IMPORTANT]
>
>Med ad hoc-analys kan ni snabbt definiera och schemalägga rapporter för specifika, aktuella behov av ad hoc-rapportering. Den är inte avsedd för fullständig export av data med ett stort antal rader, kolumner, mätvärden eller omfattande uppdelningar med hjälp av dataextraheringar.
>
>Praktiska begränsningar för schemalagd rapportering i ad hoc-analyser bygger på denna princip: Om rapporten inte byggs inom tio minuter (tidsgränsen för Ad Hoc-analys) är rapporten troligen för komplex.
>
>Din rapport har förmodligen för många mätvärden, för många uppdelningar av dimensionselement, för många rader eller kolumner, eller andra extrema element som gör den för lång som en rapportgenereringsprocess för Ad Hoc-analys. Den här typen av rapporter måste köras i datalagret, en Adobe Analytics-funktion som är utformad för fullständig dataextrahering som körs offline med rapportgenerering som kan ta många timmar eller dagar.
>
>Ad hoc-analys kan till exempel hantera 50 000 rader data, men om data delas upp för tio webbläsartyper betyder det 50 000 gånger 10, en exponentiell ökning som kan vara för komplex för ett ad hoc-rapporteringsverktyg. Ytterligare uppdelningar ökar raderna exponentiellt. Det går inte att definiera det faktiska antalet rader, kolumner och uppdelningar som ska begränsas för Ad hoc-analysrapporter i tydliga termer, men det är en kombination av alla dessa faktorer.

## Schemalägg en leveransrapport {#task_7A3165C8C5C349718FE3B2B0C727ACFD}

Steg som beskriver hur du schemalägger en leveransrapport.

<!-- 

t_schedule_delivery.xml

 -->

1. Klicka **[!UICONTROL Tools]** och sedan på **[!UICONTROL Schedule Manager]**.
1. Klicka på [!UICONTROL Schedule Manager]**[!UICONTROL New.]**

## Leveransalternativ - definitioner {#reference_CA49AC560258471AAE959BCA243F170C}

Definitioner för inställningarna för Leveransalternativ.

<!-- 

r_delivery_options.xml

 -->

Du kan skicka information som den visas i den markerade rapporten till det format du väljer. Du kan skicka det en gång eller ställa in ett leveransschema och ange vilket filformat du vill ha. Du kan skapa och skicka en digital signatur för att försäkra mottagaren om att filen är autentisk. Du kan skicka filen till en e-postadress eller överföra den till en FTP-server.

<table id="table_C18A0F1C9E214EB585A29801BA2400F8"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Fält </p> </th> 
   <th colname="col2" class="entry"> <p>Definition </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Namn </p> </td> 
   <td colname="col2"> <p> Rapportens konfigurerbara namn. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID </p> </td> 
   <td colname="col2"> <p>Anger rapport-ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Filformat </p> </td> 
   <td colname="col2"> 
    <ul id="ul_711C2D9B216C48359F7B42521D927872"> 
     <li id="li_36E8DEFDA1B84890A4204A6DFF4E0267">Excel: Presenterar rapporten i ett kalkylblad, inklusive alla bilder. Redigerbar i Microsoft Excel. </li> 
     <li id="li_C918FA3AE8194BD2B59E554DAC7CBBE2">CSV: Visar rapporten med kommaseparerade värden. Redigerbar i en enkel textredigerare (t.ex. Anteckningar) eller en kalkylbladsredigerare (t.ex. Excel). Innehåller inga bilder. </li> 
     <li id="li_B7C8C098C5264B349C21077A0DEFE059">PDF: Presenterar rapporten i Portable Document Format. Kan inte redigeras och visas i Adobe Acrobat eller Adobe Reader. </li> 
     <li id="li_B1183DB25DE34B689FBD0E5B44691F49">HTML: Rapporten skrivs ut som en bilaga i formatet Hypertext Markup Language. Det här formatet är det som de flesta webbplatser består av. Kan inte redigeras om du inte är bekant med HTML-kod. </li> 
     <li id="li_5ED5F1862AB1490A9FF5695FF9F52C5E">Ord: Presenterar rapporten i RTF-format, inklusive alla bilder. Redigerbart i Microsoft Word eller WordPad. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Avancerat </p> </td> 
   <td colname="col2"> <p> Se <a href="/help/analyze/ad-hoc-analysis/c-schedule.md"   > Avancerade formatinställningar</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Filmål </p> </td> 
   <td colname="col2"> <p>E-post: Inställningar som ska skickas via e-post. </p> <p>FTP: Inställningar för överföring till en FTP-server. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Rapportintervall och leveransschema </p> </td> 
   <td colname="col2"> <p>Anger när rapporten ska skickas. Nya scheman använder det datumintervall som definieras i rapporten. Om du till exempel skapar en rapport för de senaste 90 dagarna och schemalägger att den ska köras dagligen, får du en rapport för de senaste 90 dagarna varje dag. Om du skapar en rapport med ett statiskt datumintervall från kalendern visas samma rapport varje gång den skickas. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Avancerade formatinställningar - definitioner {#reference_F99B65BF7C9746638D8147EED147015B}

Definitioner för inställningarna i Avancerade formatinställningar.

<!-- 

r_advanced_format_settings_dsc.xml

 -->

<table id="table_CD0888E8390745F4B83DF6AC69CB0854"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Fält </p> </th> 
   <th colname="col2" class="entry"> <p>Definition </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Filnamn </p> </td> 
   <td colname="col2"> <p>Ett användardefinierat filnamn. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Bifoga ID till filnamn </p> </td> 
   <td colname="col2"> <p>Lägger automatiskt till rapport-ID:t till filnamnet. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Lägg till datum till filnamn </p> </td> 
   <td colname="col2"> <p> Lägger automatiskt till rapportdatumet till filnamnet. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Språk </p> </td> 
   <td colname="col2"> <p> Här kan du välja ett språk för rapporten. Du kan skicka rapporten på följande språk oavsett vilket språk du använder </p> 
    <ul id="ul_BD3D331B0D6146F79A6D254136E43920"> 
     <li id="li_0EE6A371B1BB4627BD3F64BD0EF07E44">Engelska </li> 
     <li id="li_5EF76261928543FDB36D99E4C89DE994">Spanska </li> 
     <li id="li_FABF47E8CD64486BA1567E02460422C5">Förenklad kinesiska </li> 
     <li id="li_8A6BC2DE92DB47DA9397B8931D8DCC6E">Traditionell kinesiska </li> 
     <li id="li_EDA24D700BE040E8B839B82E31DABC28">Franska </li> 
     <li id="li_A8D41DCCC91542BB8D0A522EC99575E8">Tyska </li> 
     <li id="li_E9F73C93C94A46B78BCE85A7261CEDD4">Japanska </li> 
     <li id="li_699B97050AA54D818659C191F4594E4E">Portugisiska </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Kodning </p> </td> 
   <td colname="col2"> <p>Anger en kodningstyp. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Skicka rapport som en komprimerad fil </p> </td> 
   <td colname="col2"> <p> Komprimerar filen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Skicka digital signaturfil </p> </td> 
   <td colname="col2"> <p>Skapar en digital signatur som ska skickas med e-postmeddelandet. </p> </td> 
  </tr> 
 </tbody> 
</table>

