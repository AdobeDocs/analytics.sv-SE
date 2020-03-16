---
description: Nya funktioner på Analysis Workspace.
keywords: Analysis Workspace
title: Nyheter på Analysis Workspace
topic: Reports and analytics
uuid: ff50ef9f-e5b8-442e-bfa6-2f224ba9f111
translation-type: tm+mt
source-git-commit: 06d2e64fc72c911828f089de5c487117251e060e

---


# Nyheter på Analysis Workspace

## Februari 2020

Nya funktioner släpptes 20 februari 2020.

| Funktion | Beskrivning |
|--- |--- |
| Stöd för flera rapportsviter i Workspace | Nu kan du samla in data från flera rapportsviter i ett enda projekt och visa dem sida vid sida. Från och med 20 februari 2020 kommer funktionen att lanseras för alla kunder under flera veckor. [Läs mer...](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/build-workspace-project/multiple-report-suites.html) |
| Ny arbetsytemall för organisationer som använder enhetsövergripande analys | Den här mallen visar hur effektivt CDA är att sammanfoga besök och utbildar dig om CDA-exklusiva dimensioner och mätvärden. En rapportsvit med CDA krävs. Mer information finns i [Konfigurera enhetsövergripande analys](https://docs.adobe.com/content/help/en/analytics/components/cda/cda-setup.html) . |
| Nya snabbtangenter i arbetsytan | <ul><li>Komprimera/expandera alla paneler: `alt + m`</li><li>Visa/dölj aktiv panel: `alt + ctrl + m`</li><li>Sök i vänster kant: `ctrl + /`</li><li>Flytta till nästa panel: `alt + Right Key`</li><li>Flytta till föregående panel: `alt + Left Key`</li></ul>[Läs mer...](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/build-workspace-project/fa-shortcut-keys.html) |
| Andra förbättringar av arbetsytan | <ul><li>När en panel eller visualisering släpps på arbetsytan kommer den vänstra listen nu att automatiskt växla till komponenter för ett smidigare arbetsflöde.</li><li>Mallkomponenter kan nu åtgärdas (t.ex. taggade, favoriter, godkända).</li><li>Filtrerade mätvärden och segmentlistor innehåller plusknappen för att lägga till en ny komponent om du inte hittar det du behöver.</li></ul> |
| Felsökning för arbetsyta | Felsökaren för arbetsytan har lagts till på Hjälp-menyn, vilket ger dig ett smidigare sätt att aktivera den för felsökning av arbetsytebegäranden. [Läs mer...](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/reporting-tricks.md) |

## Januari 2020

Ny funktion släppt 16 januari 2020.

| Funktion | Beskrivning |
|--- |--- |
| [Frihandsformstabellverktyget](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/visualizations/freeform-table.html) | Med Table Builder aktiverat kan du dra och släppa i många dimensioner, uppdelningar, mätvärden och segment för att skapa tabeller som besvarar mer komplexa affärsfrågor. Data uppdateras inte omedelbart. I stället uppdateras de när du klickar **[!UICONTROL Build]** och du sparar tid när du vet vilken tabell du vill skapa. Dessutom erbjuder den här funktionen:<ul><li>**Förhandsgranska**: Du kan förhandsgranska tabellformatet innan du lägger tid på att återge verkliga data.</li><li>**Inställningar** för flexibel rad och uppdelning: Du kan ange rad- och uppdelningsnivåer för varje dimensionsrad. Tidigare hade Workspace infört standardvärden som inte kunde ändras förrän data returnerades.</li><li>**Uppdelning efter position**: Du kan ange att dimensioneringsrader alltid ska _delas upp efter position_ i stället för _efter en viss artikel_ (standard).</li><li>**Manuell statisk radordning**: Du kan ordna statiska rader manuellt så att tabellraderna visas exakt som du vill ha dem. Tidigare kunde statiska rader bara sorteras efter en måttkolumn eller i bokstavsordning.</li></ul> |

## Oktober 2019

Förbättringar släpptes 10 oktober 2019.

| Förbättring | Beskrivning |
|--- |--- |
| Uppdatera till registersummor för frihand | Frihandstabeller innehåller nu två summor, a **[!UICONTROL Table total]** och a **[!UICONTROL Grand total]**. Radkonton för tabellsummor för [rapportfilter](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/build-workspace-project/pagination-filtering-sorting.html) som används. Tidigare påverkade bara segmentering summorna. [Läs](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/build-workspace-project/workspace-totals.html)<br/>merDessutom **[!UICONTROL Show Totals]** och **[!UICONTROL Show Grand Total]** alternativ har lagts till **[!UICONTROL Column Settings]**.<br/>Med den här förändringen i Frihand uppdateras beroende visualiseringar (t.ex. länkade **[!UICONTROL Summary Number]** visualiseringar) samt exporterade CSV- och PDF-data. |
| Alternativ för att ta bort ospecificerad/ingen | Möjligheten att enkelt ta bort&quot;ospecificerad (ingen)&quot; har lagts till som ett alternativ för att rapportera filter. |
| Borttagning av komponenter för lila granularitet | Lila granularitetstidskomponenter (Minute, Hour, Day, Week, Month, Quarter, Year) har tagits bort. De lila tidskomponenterna har alltid uppfört sig exakt som sina motsvarigheter i orange dimensioner, vilket förenklar upplevelsen. **Du behöver inte vidta någon åtgärd** om du tidigare har använt en av de lila tidskomponenterna.<br/>Den här ändringen innebär att även det lila **[!UICONTROL Time]** avsnittet har bytt namn till **[!UICONTROL Date Ranges]**. |

## Augusti 2019

Förbättring släppt den 8 augusti 2019.

| Förbättring | Beskrivning |
|--- |--- |
| Öka objektgränsen för nedrullningsfilter från 50 till 200 | Vi höjde gränsen för objekt som kan placeras i ett nedrullningsbart filter från 50 till 200. Den här förbättringen har stöd för en rad olika användningsfall, t.ex. tillägg av alla länder (195) till ett filter, eller alla delstater och provinser i USA (52). |

## Juli 2019

Förbättringar släpptes 18 juli 2019.

| Förbättring | Beskrivning |
|--- |--- |
| Förbättrad kohortanalys | Nya inställningar [för](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/visualizations/cohort-table/t-cohort.html) kohortanalys har lagts till: <ul><li>Visa endast procent</li><li>Avrunda procent till närmaste heltal</li><li>Visa en genomsnittlig procentrad</li></ul> |
| Visa objekt från de senaste 18 månaderna | På den vänstra listen har användarna nu möjlighet att _visa objekt från de senaste 18 månaderna_. Tidigare var uppslagsperioden högst 6 månader. Detta gör det enklare att jämföra med sidor eller kampanjer från förra året, upp till 18 månader sedan. |
| Ny Analysis Workspace-mall | Vi lade till en ny mall med namnet [&quot;Magento: Marknadsföring och handel&quot;](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/build-workspace-project/starter-projects.html) till analysarbetsytan. Det är särskilt utformat för e-handelskunder från Magento, men alla återförsäljare kan använda det för att få unika insikter i sin e-handelsverksamhet. |

## Juni 2019

Förbättring släppt den 13 juni 2019.

| Förbättring | Beskrivning |
|--- |--- |
| Nya färdiga filter | Nya färdiga filter har lagts till i den vänstra fältsökningen. Utöver vad du ser idag (Dimensions, Metrics, Approved, etc.) finns det nya filter som Calculated Metrics, Customer Attributes, eVars, Props, Video, etc. har lagts till för att göra det enklare att hitta de komponenter du behöver. |

## Maj 2019

Förbättring släppt den 9 maj 2019.

| Förbättring | Beskrivning |
|--- |--- |
| En ny inställning har lagts till i inställningarna för Flödesvisualisering: Inkludera upprepningsinstanser. | [Flödesinställningar](/help/analyze/analysis-workspace/visualizations/c-flow/flow-settings.md) |

## April 2019

Förbättring släppt den 11 april 2019.

| Förbättring | Beskrivning |
|--- |--- |
| Förbättringar av bästa praxis för optimering | [Optimera prestanda](/help/analyze/analysis-workspace/new-features-in-analysis-workspace.md) |

## Januari 2019

Nya funktioner och förbättringar som släpptes 17 januari 2019.

| Funktion | Beskrivning |
|--- |--- |
| [Kohortanalys](/help/analyze/analysis-workspace/visualizations/cohort-table/cohort-analysis.md) | Större förbättringar av kohortanalysen gör att du kan:<ul><li>Lägg in segmentinkludering och returnera mätvärden separat. </li><li>Visa bortfall i stället för kvarhållande.</li><li>Visa latenstabeller (förfluten tid före och efter en inkluderingshändelse).</li><li>Anpassa kohortdimensionen (gruppera besökare baserat på en eVar, inte bara tid).</li><li>Gör en rullande kohortberäkning: beräkna kvarhållning/bortfall baserat på tidigare tidsperiod, inte på ursprunglig kohort. </li><li>Lägg in flera mätvärden i inkluderings- och returfälten samt tillämpa segment. (Beräknade mått stöds inte)</li></ul> |
| [Visa densitet](/help/analyze/analysis-workspace/build-workspace-project/view-density.md) | Med den här nya inställningen kan du visa mer data på en enda skärm genom att minska den lodräta utfyllnaden av den vänstra listen, frihandstabeller och kohorttabeller. Tillgängligt via Projekt > Projektinformation och inställningar. |
| [Stöd för flervärdesvariabler i Attribution IQ](attribution-iq.md) | Vissa dimensioner i Analytics kan innehålla flera värden för en enda träff, till exempel listVars, produktvariabeln, listprops eller försäljning av eVars. Med Analysis Workspace kan du använda attribuerings-IQ på någon av dessa typer av variabler på träffnivån. |
| Prestandaförbättringar | Snabba upp förbättringar av visualiseringar vid nedbrytning - projekt med många uppdelningar läses in snabbare. |

## November 2018

Nya funktioner och förbättringar som släpptes 1 november 2018.

| Funktion | Beskrivning |
|--- |--- |
| [VRS och projektkurser - förbättringar](/help/analyze/analysis-workspace/curate-share/curate-projects-vrs.md) | Dessa ändringar infördes i själva verket i oktober 2018. Ändringar har gjorts som komponentadministratörer och icke-administratörer kan se i förvaltade arbetsyteprojekt och förvaltade virtuella rapportsviter (VRS). <br> Tidigare kunde alla se komponenter som inte är kuraterade när de klickade på Visa alla komponenter. Den uppdaterade kurationsfunktionen ger bättre kontroll över vilka komponenter som är synliga.</br> |

## Oktober 2018

Nya funktioner och förbättringar som släpptes 11 oktober 2018.

<table id="table_3DDC812B2F66416F868004416D248BF3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Funktion </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>Panelhantering</b> </p> </td> 
   <td colname="col2"> <p>Vi har gjort några ändringar i hanteringen av panellistrutor, som introducerades i september-rapporten. När du högerklickar på listrutan kan du nu </p> 
    <ul id="ul_4BDEC66EEB2243628FE32B43E377E5BD"> 
     <li id="li_EF8277BE972540D3B2604D82BC7C0918">Ta bort en listruta (det här alternativet finns alltid). </li> 
     <li id="li_6A991208F2744274817DBE1E9D1B443F">Ta bort en etikett (om en etikett visas.) </li> 
     <li id="li_5C1CFC465C2E41D2B35E8841EFDC82AA">Lägg till en etikett (om ingen etikett visas.) </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Länkar i paneler och visualiseringsverktygstips</b> </p> </td> 
   <td colname="col2"> <p>Vi har lagt till länkar till relevanta videoklipp och dokumentation till paneler och visualiseringstips. </p> </td> 
  </tr> 
 </tbody> 
</table>

## September 2018

Nya funktioner och förbättringar som släpptes 13 september 2018.

<table id="table_137719BFA03C44A78FDE872DF8B228A4"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Funktion </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>Panellistrutor</b> </p> </td> 
   <td colname="col2"> <p>Panelens listrutezon har nu funktioner för nedrullningsbara menyer. Med nedrullningsbara listor kan slutanvändarna interagera med data i ett projekt på ett kontrollerat sätt. Exempel: Anta att du har flera versioner av ett projekt för landsspecifik rapportering. Nu kan du komprimera dessa projekt till ett enda projekt och lägga till i en nedrullningsbar lista i stället. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Färgpaletter</b> </p> </td> 
   <td colname="col2"> <p>Nu kan du ändra färgschemat som används i Arbetsyta genom att välja från en annan färgpalett eller genom att ange en egen palett. Detta påverkar många saker i Workspace, bland annat de flesta visualiseringar. Det påverkar <b>INTE</b> Sammanfattningsändring, villkorsstyrd formatering i friformstabeller och Kartvyllning. </p> <p>Obs!  Stöd för färgpaletter har inte aktiverats för Internet Explorer 11. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Ny mall: Ljudförbrukning</b> </p> </td> 
   <td colname="col2"> <p>Se <a href="https://marketing.adobe.com/resources/help/en_US/sc/appmeasurement/hbvideo/media-workspace-templates.html"  > Ljudanalys </a>. </p> </td> 
  </tr> 
 </tbody> 
</table>
# augusti 2018

Nya funktioner och förbättringar som släpptes den 9 augusti 2018.

<table id="table_DD77C02344414DCD9AC0A6A22E648B72"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Funktion </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>Stödlinjer för släppzoner</b> </p> </td> 
   <td colname="col2"> <p>Dessa guider hjälper dig att enklare förstå vad varje dra och släpp-åtgärd kommer att göra. Om du till exempel håller markören över en kolumn visas saker som Lägg till, Ersätt, Filtrera efter och Brytning. </p> <p>Vi har även lagt till gula/röda stödlinjer som varnar dig när du vidtar en åtgärd som inte är rekommenderad eller förbjuden, till exempel att stapla två mätvärden ovanpå varandra (vilket leder till ogiltiga data). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Alternativ för Lägg till tom panel</b> </p> </td> 
   <td colname="col2"> <p>Vi lade till en +-symbol under startpanelen för att göra det enklare att lägga till fler paneler. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Juli 2018

Nya funktioner och förbättringar som släpptes 19 juli 2018.

<table id="table_336E121310204DC492EA004F40830B0F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Funktion </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b> <a href="attribution-iq.md"  > Attributions-IQ </a></b> </p> </td> 
   <td colname="col2"> <p>Med attribuerings-IQ kan ni utföra mer sofistikerade och intelligenta analyser av marknadsföringens prestanda. Nya attribueringsmodeller kan användas på mätvärden i Analysis Workspace (på valfri tabell eller vid valfri uppdelning) och i beräknade mätvärden. En ny attribueringspanel ger bättre visualisering och jämförelse. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b> Förbättringar av vänster järnväg </b> </p> </td> 
   <td colname="col2"> <p>Förbättrade vänstra spår som gör den mer intuitiv och lättanvänd: </p> 
    <ul id="ul_087BEDF4338946DA857CD82CB69F98C2"> 
     <li id="li_C751AACAC60442DC93118F0819F8EEA7"> Funktionen Skapa (+) för komponenter (mått, segment, datum) är inline med rubrikerna. </li> 
     <li id="li_DE2EB184A02D4CE58C23F518DB85EFDD"> "+ Se alla" har lagts till längst ned i varje avsnittslista för att visa att det finns fler än fem alternativ. </li> 
     <li id="li_5208F3C6026647B09F4A85131B175175">Ansiktliga åtgärder (som tagg, favorit) med ikoner när komponenter väljs. </li> 
     <li id="li_11E601488A844515928231E09889BC54">Gör estetiska förbättringar i användargränssnittet. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Summor för beräknade värden </b> </p> </td> 
   <td colname="col2"> <p>När det är möjligt visas nu summor för beräknade värden, inklusive procentvärden </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Ny <a href="/help/analyze/analysis-workspace/components/calendar-date-ranges/calendar.md"  > förinställning </a>för datumintervall </b> </p> </td> 
   <td colname="col2"> <p>De senaste 13 fullständiga veckorna har lagts till i förinställningarna för datumintervall i Analysis Workspace. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Juni 2018

Nya funktioner och förbättringar som släpptes 14 juni 2018.

<table id="table_57035A06D99447A6BE6ED825A648ED3F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Funktion </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b> <a href="/help/analyze/analysis-workspace/components/dimensions/view-dimensions.md"  > Dynamiska dimensionskolumner </a></b> </p> </td> 
   <td colname="col2"> <p>Tidigare, när en dimension släpptes på en kolumn, visade vi de 5 högsta värdena för icke-tidsdimensioner (och 15 för tidsdimensioner) och höll dessa värden statiska (dvs. de 5 valda värdena ändrades aldrig). </p> <p>Från och med nu visas som standard dynamiska värden i stället för statiska, med möjlighet att omvandla dem till statiska värden. Andra saker att notera: </p> 
    <ul id="ul_C802BC32CB084E30B4E58E9E90B9A63D"> 
     <li id="li_452466AB416F4737B532849C604BD4CC">Klicka på (i) för den dynamiska dimensionen så visas rankningen (första av 5) och dimensionstypen. </li> 
     <li id="li_588F6199E38D47869AC855A4C2A4D1B7">När dina data uppdateras uppdateras de dynamiska dimensionskolumnerna så att de aktuella 5/15 dimensionsobjekten visas. </li> 
     <li id="li_19D47638D4D94416B0DAD2B2FB835ABE">En kolumn för dynamiska dimensioner som kopieras eller flyttas blir statisk. </li> 
     <li id="li_B95411689AE04774B7B9BA128F2DB96F">När du hovrar en statisk dimensionskolumn visas en låsikon som anger att dimensionen är statisk. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Ny arbetsyta - modal </b> </p> </td> 
   <td colname="col2"> <p>På samma sätt som Dagens tips som introducerades förra månaden visar den här modala funktionen för nya arbetsytor första gången du loggar in på arbetsytan efter en ny version. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Maj 2018

Nya funktioner och förbättringar släpptes 10 maj 2018.

<table id="table_EE4C690A178B4F80BDAF2BB4424D6020"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Funktion </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>Dagens tips</b> </p> </td> 
   <td colname="col2"> <p>Vi tillhandahåller Dagens tips (tillsammans med en kort video) längst ned till höger i gränssnittet. De här tipsen är avsedda att bekanta dig med en mängd olika funktioner för Analysis Workspace. Du kan när som <span class="uicontrol"> helst stänga de här tipsen eller öppna dem via </span> Hjälp <span class="uicontrol"> &gt; </span> Tips. </p> <p><img  src="assets/tip_of_day.png" width="300px" id="image_44A2AA712E4242EC92A180380E66AD7D" /> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b> <a href="/help/analyze/analysis-workspace/components/t-freeform-project-segment.md"  > Segmentmallar </a> och mallar för <a href="/help/analyze/analysis-workspace/components/apply-create-metrics.md"  > beräknade värden </a></b> </p> </td> 
   <td colname="col2"> <p>Den vänstra listen visar nu segmentmallar och mallar för beräknade värden. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Möjlighet att rulla när du drar komponenter</b> </p> </td> 
   <td colname="col2"> <p>Nu kan du rulla uppåt och nedåt medan du drar komponenter till en ny plats. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Ytterligare information om <a href="/help/analyze/analysis-workspace/virtual-analyst/c-anomaly-detection/view-anomalies.md"  > avvikelser </a></b> </p> </td> 
   <td colname="col2"> <p>När du hovrar över en avvikelse i ett linjediagram visas nu datumet och det råa värdet för avvikelsen. </p> </td> 
  </tr> 
 </tbody> 
</table>

## April 2018

Nya funktioner och förbättringar som släpptes 12 april 2018.

<table id="table_B9E784CD14A1453EB360FCCDC612250F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Funktion </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <a href="/help/analyze/analysis-workspace/build-workspace-project/column-row-settings/column-settings.md"  > Radbryt rubriktext är aktiverat som standard </a> </p> </td> 
   <td colname="col2"> <p>Kolumninställningen <span class="uicontrol"> Radbryt rubriktext </span> är nu aktiverad som standard för frihandstabeller. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="/help/analyze/analysis-workspace/build-workspace-project/column-row-settings/table-settings.md"  > Ny radinställning </a> </p> </td> 
   <td colname="col2"> <p>Med den nya inställningen <span class="uicontrol"> Beräkna procent per rad </span> tvingas friformstabellen att beräkna cellprocenten över raden i stället för nedåt i kolumnen. Detta är särskilt användbart när du vill ändra procentvärden, t.ex. hur ett dimensionsvärde blandas med resten över tiden. Det är aktiverat som standard när du klickar på <span class="uicontrol"> ikonen Visa </span> . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md#section_D3BB5042A92245D8BF6BCF072C66624B"  > Visualiseringsinställning för"100 % staplad" </a> </p> </td> 
   <td colname="col2"> <p>En ny visualiseringsinställning för liggande/liggande ytor/staplade/horisontella staplade visualiseringar gör att diagrammet blir en"100 % staplade" visualisering så att du kan mäta relativa proportioner. </p> <p><img placement="break"  src="assets/stacked_100_percent.png" width="500px" id="image_ED9C94CE5EAF4500B1EF71BE8701B6D2" /> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="/help/analyze/analysis-workspace/virtual-analyst/overview.md"  > Analys av avvikelseidentifiering och bidrag är </a> nu endast tillgängligt via Analysis Workspace </p> </td> 
   <td colname="col2"> <p>Analysidentifiering och bidragsanalys har tagits bort från funktionerna Rapporter och analyser och är nu bara tillgängliga via Analysis Workspace. </p> <p>Observera att kunder som använder Adobe Analytics Select och Adobe Analytics Foundation bara har tillgång till"daglig granularitetsidentifiering" i Workspace. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Mars 2018

Nya funktioner och förbättringar som släpptes den 8 mars 2018.

<table id="table_580CF2C1322E4FB78870BE2B1F497B2F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Funktion </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <a href="/help/analyze/analysis-workspace/build-workspace-project/column-row-settings/column-settings.md"  > Figursättning av rubriktext </a> </p> </td> 
   <td colname="col2"> <p>Nu kan du radbryta rubriktexten i frihandstabeller för att göra rubrikerna mer läsbara och lättare att dela. Vi har lagt till ett alternativ i kolumninställningarna som kallas"Radbryt rubriktext". Detta är särskilt användbart för .pdf-återgivning och för mått med långa namn. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="/help/analyze/analysis-workspace/components/apply-create-metrics.md"  > Högerklicka för att skapa mått </a> </p> </td> 
   <td colname="col2"> <p>För att det ska bli enklare att snabbt skapa beräknade värden <span class="uicontrol"> </span> har Skapa mått från markering lagts till på högerklicksmenyn i frihandstabeller. Det här alternativet visas när en eller flera rubrikkolumnceller är markerade. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="/help/analyze/analysis-workspace/visualizations/map-visualization.md"  > Förbättringar av kartvisualisering </a> </p> </td> 
   <td colname="col2"> <p>För att kunna visa jämförelser över perioden (t.ex. år för år) i kartvisualiseringen har vi lagt till följande förbättringar: </p> 
    <ul id="ul_F570E6AB174C45788620CF50E2742A08"> 
     <li id="li_746E329037764644A9CCF79161C26350">Kartvyn kan nu visa negativa tal. Om du till exempel ritar upp ett årligt mått kan kartan visa -33 % över New York. </li> 
     <li id="li_E05F0380627044E6A4E8A60C98494BF7">Med mätvärden som är av typen "percent" beräknar du procentvärdena tillsammans. </li> 
     <li id="li_44C04306EA1B413E91B8256B340D5296">Ett nytt färgschema: Positiv/negativ (grön/röd) </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="/help/analyze/analysis-workspace/build-workspace-project/starter-projects.md"  > Anpassade malluppdateringar </a> </p> </td> 
   <td colname="col2"> <p>För de senast släppta anpassade mallarna har vi </p> 
    <ul id="ul_787F48253F454163B99F6DD50F199FE2"> 
     <li id="li_828DD547DDB54A81B9FFB9FE92790F6C">En mallikon har lagts till högst upp i projektet (nära titeln) för att göra det lättare att skilja redigeringsmallläget från att använda en mall som startpunkt för ett projekt. </li> 
     <li id="li_EEAA4D115CB74A57BABD524B2561E0CC">Tillåt icke-administratörer att skapa (spara som) och redigera projektmallar för arbetsytan, förutsatt att de har beviljats behörigheten Skapa/Kurvera projekt i arbetsytan för analys. ( <span class="ignoretag"> Admin <span class="uicontrol"> &gt; </span> Användarhantering <span class="uicontrol"> &gt; </span> Grupper <span class="uicontrol"> &gt; </span> Redigera all rapportåtkomst <span class="uicontrol"> </span> <span class="uicontrol"> </span> <span class="uicontrol"> </span> </span>&gt; Anpassa analysverktyg &gt; Skapa/Kurera projekt i Analysis Workspace¥). </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

## Februari 2018

Nya funktioner och förbättringar som släpptes den 8 februari 2018.

<table id="table_824BBE4A554B4DB092ADA9044383D0FA"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Funktion </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <a href="/help/analyze/analysis-workspace/build-workspace-project/starter-projects.md#create-custom-template"  > Anpassade arbetsytemallar </a> </p> </td> 
   <td colname="col2"> <p>Nu kan du skapa egna arbetsytemallar och spara dem så att andra användare i organisationen kan börja med data som är relevanta för dem. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="/help/analyze/analysis-workspace/build-workspace-project/t-freeform-project.md"  > Ny startspärr för projekt </a> </p> </td> 
   <td colname="col2"> <p>När du klickar på"nytt projekt" öppnas en ny skärm där du kan välja att börja från </p> 
    <ul id="ul_FE90E6B9AF334A029D66A43901F8FA0B"> 
     <li id="li_F1DFD9AE140C4E5B849D4C522D5968DB">ett tomt projekt, eller </li> 
     <li id="li_23BD391D68674C299858A97BFE10598B">en standardmall (inbyggd) för arbetsytan, eller </li> 
     <li id="li_04D84FE375B84BF88843AA0D43A234BF">en anpassad arbetsytemall (se ovan) </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Högerklicka på stödet för kopiering </p> </td> 
   <td colname="col2"> <p>Vi har lagt till ett högerklicksalternativ,"Kopiera till Urklipp", så att du kan kopiera celler/tabeller på ett konsekvent sätt. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="/help/analyze/analysis-workspace/build-workspace-project/column-row-settings/column-settings.md"  > Förbättring av kolumn % </a> </p> </td> 
   <td colname="col2"> <p>Procentandelen av totalen som visas i kolumner begränsades till 100 %, även när vissa scenarier leder till att rader är mer än 100 % av totalsumman (till exempel med medelvärden). </p> <p>Vi visar nu procenttal som är större än 100 %, för att vara mer korrekta. Vi flyttar också det övre gränsvärdet till 1 000 % för att säkerställa att kolumnerna blir för stora. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="/help/analyze/analysis-workspace/build-workspace-project/column-row-settings/column-settings.md#section_3DD847151DA14914888A70FC4FD7BDFB"  > Villkorsstyrd formatering aktiverad för uppdelningar </a> </p> </td> 
   <td colname="col2"> <p>Användning av villkorsstyrd formatering (färger, etc.) i frihandstabeller aktiveras nu automatiskt vid uppdelningar, såvida inte"Anpassade" gränser har valts. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ändrar till <a href="/help/analyze/analysis-workspace/components/calendar-date-ranges/calendar.md"  > standardkalenderns </a> vy </p> </td> 
   <td colname="col2"> <p>Som standard visas den aktuella månaden och den sista månaden i arbetsytekalendern, i stället för den aktuella månaden och nästa månad. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Förbättrade hovring-/markeringsfärger i arbetsyttabeller </p> </td> 
   <td colname="col2"> <p>Skillnaden i färger när du hovrar över en frihandstabellcell jämfört med att klicka på en cell har blivit tydligare. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Januari 2018

Nya funktioner och förbättringar som släpptes 18 januari 2018.

<table id="table_7A2E678577F94BDABB1276C826E6554F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Funktion </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Fler filtreringsalternativ <a href="/help/analyze/analysis-workspace/build-workspace-project/pagination-filtering-sorting.md"  > för dimensionsobjekt </a> i frihandstabeller </p> </td> 
   <td colname="col2"> <p>Dessa (avancerade) filtreringsalternativ för dimensionsobjekt har lagts till (förutom de befintliga alternativen"contains" och"does not contain"): </p> 
    <ul id="ul_869B3E943E304C0282D56AD96BB79E18"> 
     <li id="li_81A49BA0CA3041C7AB892FAD2D129E5A">Innehåller alla termer </li> 
     <li id="li_2AB564F917844F82839A91949D0B684A">Innehåller alla termer </li> 
     <li id="li_16C7938EDC8F422EA006FB63F2881EF1">Innehåller frasen </li> 
     <li id="li_5130EBE9A7A54CCFA313F3C3C268B367">Innehåller inga termer </li> 
     <li id="li_861825154EDC49EBA57514FD0A2AE462">Innehåller inte frasen </li> 
     <li id="li_5364BFB73ECF4B92A6663693ABD4BCF5">Lika med </li> 
     <li id="li_1EBF3119B6364842A35D39BAD645F4AF">Är inte lika med </li> 
     <li id="li_487886E0A6EC4245A0E85D2E8B4A20FB">Börjar med </li> 
     <li id="li_A73F54DFBAAB44D4A4134342A3124E47">Slutar med </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md#section_05B7914D4C9E443F97E2BFFDEC70240C"  > Kopiera och klistra in visualiseringar/paneler </a> i paneler och projekt </p> </td> 
   <td colname="col2"> <p>Du kan nu högerklicka och kopiera en visualisering eller panel och sedan klistra in ("infoga") det kopierade elementet på en annan plats i projektet eller i ett annat projekt. </p> <p>Du kan använda den här funktionen för att skapa"byggstenar" - fördefinierade visualiseringar/paneler - som kan kopieras till andra projekt för att komma igång snabbare, med data som är specifika för ditt företag. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="/help/analyze/analysis-workspace/build-workspace-project/starter-projects.md"  > Nya mobilmallar för"Meddelanden" och"Plats" </a> </p> </td> 
   <td colname="col2"> <p>Två nya projektmallar har lagts till: </p> 
    <ul id="ul_2F5976C849474A2B8A6BCDA2559F2855"> 
     <li id="li_51B7830E062A4CFDBDF219C56249A733">En ny Mobile-projektmall för"Meddelanden" som fokuserar på prestanda i appen och push-meddelanden. </li> 
     <li id="li_D2FB258EF3AF4EB19CEB258D08F4EBBE">En ny Mobile-projektmall för Plats som innehåller en karta med platsuppgifter. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Förbättrad kolumnstorleksändring </p> </td> 
   <td colname="col2"> <p>När du ändrar storlek på den vänstra kolumnen behåller arbetsytan nu breddprocenten för resten av kolumnerna (inte bara justerar nästa kolumnbredd till höger). Den här ändringen gör att det går snabbare att skapa tabeller för både analys och delning. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Visa <a href="/help/analyze/analysis-workspace/visualizations/freeform-table.md"  > 400 rader </a> i en tabell </p> </td> 
   <td colname="col2"> <p>Nu kan du visa 400 rader i en tabell (upp från 200), vilket möjliggör 365-dagarstrender. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="/help/analyze/analysis-workspace/visualizations/map-visualization.md"  > Stöd för kartvisualisering </a> i PDF </p> </td> 
   <td colname="col2"> <p>Kartvyn, som introducerades i oktober 2017, kan nu återges i PDF-format. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="/help/analyze/analysis-workspace/build-workspace-project/t-freeform-project.md"  > Relativa länkar mellan länkar </a> vid kopiering/sparande som projekt </p> </td> 
   <td colname="col2"> <p>Tidigare när du kopierade ett projekt eller sparade som, ledde alla länkar som sparades i projektet till det ursprungliga projektet, inte till det kopierade projektet. </p> <p>Länkarna är nu relativa till det projekt de bor i efter att du har kopierat/sparat som. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Bidragsanalys: <a href="https://marketing.adobe.com/resources/help/en_US/analytics/contribution/ca_main.html"  > Tokenmeddelande </a> </p> </td> 
   <td colname="col2"> <p>Om ditt företag har ett begränsat antal token för bidragsanalys visas nu ett meddelande i gränssnittet för analysarbetsytan när du använder en token. Här ser du hur många variabler du har kvar.&amp;nbsp; </p> <p>(Administratörsanvändare: Du kan begränsa vem som kan använda dessa variabler genom att redigera gruppbehörigheten. Behörigheten kallas för avvikelseidentifiering och bidragsanalys under <span class="uicontrol"> Analytics </span> &gt; <span class="uicontrol"> Admin </span> &gt; <span class="uicontrol"> User Management </span>&gt; <span class="uicontrol"> Edit Groups </span> &gt; <span class="uicontrol"> Edit All Report Access </span> <span class="uicontrol"> </span> <span class="uicontrol"> </span>&gt;¥ Customize Report Suite Tools¥ &gt;¥ Tools And Reports. ) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>CSV-filer med tecken med flera faror </p> </td> 
   <td colname="col2"> CSV-filer som innehåller flerbytetecken kan nu öppnas i MS Excel. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ändringar av händelsenummer, eVar# och prop# </p> </td> 
   <td colname="col2"> <p>Event#, eVar# och prop#, som lades till i dimensionsnamn i den vänstra listen (2017), visas bara när du <b>söker</b> efter komponenten. </p> <p>(Gäller även Virtual Report Suite Builder.) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ändringar av Ingen/ospecificerad </p> </td> 
   <td colname="col2"> <p>Ändrade hur Ingen/ospecificerad fungerar i Analysis Workspace så att den överensstämmer med Rapporter och analyser, Segment Builder och menyn för dimensionsvärden i Analysis Workspace. </p> <p>Det innebär att värdet visas som"Ospecificerad" i stället för som"Ingen" i de flesta projekt i Analysis Workspace. </p> </td> 
  </tr> 
 </tbody> 
</table>

## November 2017

Ny funktion släppt den 9 november 2017.

<table id="table_C502E81253634E6CBAE7F12C7B62F7B6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Funktion </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Lista över inkompatibla komponenter </p> </td> 
   <td colname="col2"> <p>Ibland ingår inte alla komponenter i ett projekt i rapportsviten. Det resulterande meddelandet"Inkompatibel rapportsvit" som visas när du läser in ett projekt eller växlar till en rapportsvit visar nu vilka komponenter som inte är kompatibla. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Oktober 2017

Nya funktioner släpptes 26 oktober 2017.

<table id="table_892279F2B4AF4DB38C64AA9AFC5657A7"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Funktion </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <a href="/help/analyze/analysis-workspace/visualizations/map-visualization.md"  > Visualisering av karta </a> </p> </td> 
   <td colname="col2"> <p>Med den nya &amp;stämpeln;nbsp;kartvisualisering&amp;nbsp;kan du enkelt visa dina kundinteraktioner i det sammanhang där de finns. Från en makrovy (global) till en mikro vy (stad) - du kan enkelt zooma in och ut ur olika hierarkinivåer i visualiseringen för att se användargrupper i olika regioner. </p> <p>Du kan visualisera platsdata via IP-adressen (för icke-mobila datauppsättningar) eller så kan du ge liv åt latitud- och &amp;nbsp;longituddata (för kunder som använder Mobile SDK) i Analysis Workspace.&amp;nbsp; </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="/help/analyze/analysis-workspace/visualizations/line.md"  > Granularitetsväljare för trendvisualiseringar </a> </p> </td> 
   <td colname="col2"> <p>Nu kan du enkelt växla mellan tidsgranularitet när dimensionen i datakällan är en tidsdimension. Du kan växla granularitet från en listruta i visualiseringsinställningarna. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="/help/analyze/analysis-workspace/components/t-freeform-project-segment.md"  > Fullständiga dimensioner och händelser i segmentsläppzonen </a> </p> </td> 
   <td colname="col2"> <p>Tidigare kunde du bara släppa dimensionsobjekt, datumintervall eller segment i släppzoner. Du kan nu släppa en hel dimension eller händelse i segmentets släppzon. I båda fallen kommer Analysis Workspace att skapa"exists"-träffsegment. </p> <p>Exempel: "Tryck där eVar1 finns" eller "Tryck där event1 finns". </p> <p>Obs!  Du kan inte släppa beräknade värden i en segmentzon. Endast de dimensioner/mått som du kan skapa segment för kvalificerar för segmentzonen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="/help/analyze/analysis-workspace/visualizations/t-sync-visualization.md"  > Anslutna visualiseringar listade i inställningarna för datakälla </a> </p> </td> 
   <td colname="col2"> <p>Om det finns visualiseringar anslutna till en frihands- eller kohorttabell visas de anslutna visualiseringarna nu i den övre vänstra punkten (Inställningar för datakälla). Vid hovring markeras den länkade visualiseringen och om du klickar på den kommer du till den. </p> <p>Dessutom finns kryssrutan Visa/dölj datatabell där du kan visa eller dölja datatabellen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="/help/analyze/analysis-workspace/build-workspace-project/t-freeform-project.md"  > Händelsenummer har lagts till i händelsenamn för vänsterspåret </a> </p> </td> 
   <td colname="col2"> <p>Före oktober 2017 bifogades evar# och prop# till dimensionsnamnen, och du kunde söka på dessa siffror. Samma funktionalitet är nu tillgänglig för händelser. </p> <p>Exempel: "Prenumerationer" visas nu i det vänstra fältet som "Prenumerationer (händelse1)". </p> <p>Kom ihåg: </p> 
    <ul id="ul_5DF85C65F7004539949DDC4F23922296"> 
     <li id="li_A685834B4914460D87568583BB39C474">Händelsenumret visas inte i tabellen (för att titlarna ska vara korta). </li> 
     <li id="li_D742D04470244633900335B7F5A79FD9">Av konsekvensskäl visar inte längre utkast och eVars siffror i tabeller heller. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="/help/analyze/analysis-workspace/build-workspace-project/t-freeform-project.md"  > Färdiga dimensioner sorterade i logisk ordning som standard </a> </p> </td> 
   <td colname="col2"> <p>Standardsorteringsordningen för vissa färdiga dimensioner har uppdaterats i följande fall: </p> 
    <ul id="ul_B9C0C761F39E43A4977EC028F4D4525C"> 
     <li id="li_FE72ADDCD32A4FF7907462726D6E7758">När de dras till en frihandstabell. </li> 
     <li id="li_5D78DD0DCB7347AC85E260F53109010C">När de visas i den vänstra listen. </li> 
    </ul> <p>Om till exempel"Timme på dagen" släpps i en tabell sorteras den från 12:00-11:00. Du kan fortfarande sortera efter en måttkolumn. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="/help/analyze/analysis-workspace/virtual-analyst/c-anomaly-detection/view-anomalies.md"  > Möjlighet att tillåta konfidensintervall genom att skala om ett diagram </a> </p> </td> 
   <td colname="col2"> <p>Intervallet för avvikelseidentifiering - konfidensintervall skalar inte automatiskt y-axeln i en visualisering så att diagrammet kan bli mer läsbart. </p> <p>Du kan nu välja att tillåta konfidensintervallet för att skala diagrammet. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="/help/components/c-alerts/alert-manager.md"  > Varningar: Lagt till <b>förnyelsealternativ</b></a> </p> </td> 
   <td colname="col2"> <p>När en eller flera aviseringar har valts i Varningshanteraren kan de förnyas genom att klicka på <span class="uicontrol"> Förnya </span>. </p> <p>Detta förlänger deras förfallodatum till ett år från den dag då användaren <span class="uicontrol"> </span> klickade på Förnya, oavsett deras ursprungliga förfallodatum. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Förbättringar av användargränssnittet </p> </td> 
   <td colname="col2"> 
    <ul id="ul_645B43AC6F554353B887DD58F0AA86E8"> 
     <li id="li_05B16A84008E4DA3A5DE91AF3C942D55">Tom panel: Vi börjar nu med att markera alla visualiseringar du kan lägga till i panelen, till exempel karta, utrullning, flöde, histogram, kohort och Venn. Du kan välja att spara den här panelen som standardstartläge för projektet. </li> 
     <li id="li_9F1ED138DB0E453DA6BD4B4A512492CC">Den nya formateringen för den vänstra listen gör paneler, visualiseringar och komponenter på den vänstra listen mer synliga och användbara. </li> 
     <li id="li_5DF6177F0EFD4D4D9D432768DEA3F37D">Frihandstabell: Tomma friformstabeller visar nu en animerad GIF-fil som demonstrerar dra och släpp-paradigmen för Analysis Workspace. </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

## September 2017

Nya funktioner släpptes 21 september 2017.

<table id="table_DC0DA93B8A3B481080FCB2BA8F985753"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Funktion </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <a href="/help/analyze/analysis-workspace/components/dimensions/time-parting-dimensions.md"  > Tidsdelningsdimensioner i analysarbetsytan </a> </p> </td> 
   <td colname="col2"> <p>Dimensioner baserade på tidsstämpel har lagts till i Analysis Workspace. Dimensionerna är: </p> 
    <ul id="ul_9BDBC0B344504E85840040E493873A47"> 
     <li id="li_826A8CBF4FDB4C98AC176C7145C09DB2">Timme på dagen (t.ex. 01, 12, 15, 23) </li> 
     <li id="li_FD6AAD4D3F544224A757D8124F973BE5">AM/PM (t.ex. AM PM) </li> 
     <li id="li_5CAE35FB8E3E490A8FCF72DF8AC619CC">Veckodag (t.ex. måndag, tisdag, onsdag) </li> 
     <li id="li_930DFC6BFCC740A392EC7FA859FF0E73">Veckodag/Veckodag (t.ex. Veckoslut, Veckodag) </li> 
     <li id="li_C09F8BF8C598498392732C183C5BB720">Dag i månaden (t.ex. 1, 2, .... 30, 31) </li> 
     <li id="li_E80A8932C32B4410A9BC703090FB5CFF">Månad på året (t.ex. januari, februari, mars) </li> 
     <li id="li_67620F09B58244B2B17317E0DB97067A">Dag på året (t.ex. Dag 1, Dag 2 osv.) </li> 
     <li id="li_A96CD77357064FC19D92EFA8244560D6">Kvartal på året (t.ex. Q1, Q2 osv.) </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="/help/analyze/analysis-workspace/build-workspace-project/column-row-settings/column-settings.md"  > Hantera flera kolumner samtidigt i frihandstabeller </a> </p> </td> 
   <td colname="col2"> <p>Du kan nu ändra inställningarna för flera kolumner samtidigt. Markera bara flera kolumner och klicka på inställningsikonen för någon av dessa kolumner. Alla ändringar du gör gäller för alla kolumner där celler är markerade. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="/help/analyze/analysis-workspace/visualizations/c-flow/multi-dimensional-flow.md"  > Flöde: Intredimensionell märkning </a> </p> </td> 
   <td colname="col2"> <p>En ny dimensionsetikett högst upp i varje Flow-kolumn gör det mer intuitivt att använda flera dimensioner i en flödesvisualisering. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="/help/analyze/analysis-workspace/visualizations/histogram.md#section_09D774C584864D4CA6B5672DC2927477"  > Räkningsmetod för träff i histogram </a> </p> </td> 
   <td colname="col2"> <p>Tidigare fanns det två beräkningsmetoder i en histogramvisualisering: Besök och besökare (standard). </p> <p>Nu kan du använda en tredje beräkningsmetod, "Hit", som segmentbehållare. "Förekomster" används som y-axelmått i friformstabellen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="uicontrol"> Rensa </span>knappen Alla för segmentjämförelse och konfiguration av bidragsanalys </p> </td> 
   <td colname="col2"> <p>I stället för att ta bort varje element manuellt kan du nu rensa alla element i följande arbetsyteområden: </p> 
    <ul id="ul_73E06D64CDCA4E83B9FEC2FD99D41CD3"> 
     <li id="li_A51EF8FADFA04CC19FD79C1675597659"> <a href="/help/analyze/analysis-workspace/virtual-analyst/contribution-analysis/run-contribution-analysis.md#section_F6932F4BF74544B5872164E7B1E0C6FC"  > Exkluderade komponenter för bidragsanalys </a> </li> 
     <li id="li_30E612D5A7584484967260931DB9E30E"> <a href="/help/analyze/analysis-workspace/c-panels/c-segment-comparison/segment-comparison.md"> Uteslutna komponenter för segmentjämförelse </a> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="/help/analyze/analysis-workspace/visualizations/summary-number-change.md"  > Uppdaterade namn för visningstyperna Sammanfattningsändring </a> </p> </td> 
   <td colname="col2"> <p>Två aktuella alternativ för Sammanfattningsändring har bytt namn för att klargöra deras innebörd: </p> 
    <ul id="ul_7301D1C73E72424F911EE8DAAD9247A0"> 
     <li id="li_89D94632E0C94263A84887AF5B360E27">Visa Ändra &gt; Visa procentuell ändring </li> 
     <li id="li_D48EB4055019449DAF2998CB9A5D23DF">Visa differens &gt; Visa Raw-differens </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="/help/analyze/analysis-workspace/visualizations/summary-number-change.md"  > Utökade decimaler för förkortat sammanfattningsnummer/ändringar </a> </p> </td> 
   <td colname="col2"> <p>Tidigare visade förkortade visualiseringar av summering/ändring 0 decimaler. </p> <p>Du kan nu välja 0-3 decimaler för att förbättra dina rapporter. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Augusti 2017

Nya funktioner släpptes 17 augusti 2017.

<table id="table_C29887097C894B1C91AD7086F0DAEC73"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Funktion </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <a href="/help/analyze/analysis-workspace/build-workspace-project/t-freeform-project.md"  > Tagga ett projekt under Spara </a> </p> </td> 
   <td colname="col2"> <p>Du kan nu lägga till taggar i ett projekt medan du sparar projektet. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="/help/analyze/analysis-workspace/build-workspace-project/freeform-overview.md"  > Tagg-kolumnen på sidan Projektlista </a> </p> </td> 
   <td colname="col2"> <p>En <span class="wintitle"> tagg- </span> kolumn har lagts till på listsidan för arbetsytans projekt. I den här kolumnen visas taggarna för varje projekt. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="/help/analyze/analysis-workspace/visualizations/c-flow/flow.md"  > Exportera Flödesvisualiseringar som .CSV-filer </a> </p> </td> 
   <td colname="col2"> <p>Du kan hämta Flow-visualiseringar som .csv-filer, vilket gör att du kan analysera Flödesresultat i Microsoft Excel (visualiserat som en tabell) eller någon annanstans. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="/help/components/c-alerts/intellligent-alerts.md"  > Intelligenta aviseringar: Ytterligare konfidensintervall </a> </p> </td> 
   <td colname="col2"> <p>För avvikelsedetektionsbaserade aviseringar har två nya konfidensnivåer (99,75% och 99,9%) lagts till. Standardvärdena för vissa granularitetsmarkeringar har också ändrats: </p> 
    <ul id="ul_EB1F07A4D2204D57B2DDD9838CE4F5D9"> 
     <li id="li_542AAACE703F4EBFBD91F11F5ABC2929">Timme: nu 99,75 % </li> 
     <li id="li_D01E4598FB33473FAAC5D60441FD081B"> varje dag: nu 99 % </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

## Juli 2017

Nya funktioner släpptes 20 juli 2017.

<table id="table_64E3A9960F314E2F9FFC738696EACDF7"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Funktion </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b> <a href="/help/analyze/analysis-workspace/visualizations/text.md"  > RTF-redigerare </a></b> </p> </td> 
   <td colname="col2"> <p>Gör att du kan ändra teckensnittsinställningarna (fet, kursiv stil och så vidare) och hyperlänken i textrutevisualiseringar och beskrivningar av panel/visualisering. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b> <a href="/help/analyze/analysis-workspace/analysis-workspace-features.md#section_253EA04E067F4A29A8B54CE2B7631086"  > Intra-linking (Quick-visualize links) </a></b> </p> </td> 
   <td colname="col2"> <p><b>Med Intra-linking</b> kan du länka till specifika paneler och visualiseringar i ett projekt från en textruta, t.ex. för att skapa en projektinnehållsförteckning. Du kan dela dessa länkar på samma sätt som du delar en projektlänk för att dirigera någon till en viss visualisering eller panel i ett projekt. Nya högerklicksalternativ med namnen Hämta panellänk och Hämta visualiseringslänk har lagts till. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b> Redigera <a href="/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md#section_94F1988CB4B9434BA1D9C6034062C3DE"  > förklaringsetikett </a></b> </p> </td> 
   <td colname="col2"> <p>Gör att du kan byta namn på serienamn i visualiseringsteckenförklaringar (Utfall, Område, Staplad, Stapel, Staplad stapel, Donut, Histogram, Vågrät stapel, Staplad linje, Spridning och Venndiagram) så att du lättare kan se bilderna. </p> <p>Redigering av förklaringar <b>gäller inte</b> för: Treemap, Bullet, Summary Change or Number, Text, Freeform, Histogram, Kohort eller Flow-visualiseringar. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b> <a href="/help/analyze/analysis-workspace/visualizations/t-sync-visualization.md"  > Uppdateringar av Hantera datakällor </a></b> </p> </td> 
   <td colname="col2"> <p>Vi har omutvecklat hur datakällor (som driver visualiseringarna) hanteras. Det finns inte längre separata, dolda tabeller när du låser datakällan till en tabell. </p> <p>I stället behåller vi den visuella återgivningen kopplad till tabellen som du skapade den från. Detta löser också ett fel med live-länkade tabeller, där du ändrar granulariteten och sedan återgår till den gamla granulariteten vid nästa inläsning av projektet. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b> Möjlighet <a href="/help/analyze/analysis-workspace/virtual-analyst/contribution-analysis/run-contribution-analysis.md"  > att markera en viss avvikelse </a></b> </p> </td> 
   <td colname="col2"> <p>Vi belyser nu avvikelsen med en blå punkt i bidragsanalysen och de intelligenta varningsprojekten som är kopplade till den. Detta ger en tydligare indikation på den avvikelse som analyseras. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Hämta projektlänk för Experience Cloud-inloggningar</b> </p> </td> 
   <td colname="col2"> <p>Om du tidigare loggade in med dina Experience Cloud-inloggningsuppgifter och navigerade till Analytics, kunde du inte använda <span class="ignoretag"> Dela <span class="uicontrol"> &gt; </span> Hämta projektlänk <span class="uicontrol"></span> </span> . Vi har åtgärdat det här problemet. Du måste fortfarande spara projektet innan det här alternativet kan klickas. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b> Filtret <a href="/help/analyze/analysis-workspace/curate-share/schedule-projects.md"  > "Utgångna projekt" i hanteraren för schemalagda projekt </a></b> </p> </td> 
   <td colname="col2"> <p>Du kan nu filtrera projekt som har upphört att gälla i den schemalagda projektledaren. Du kan sedan bestämma om du vill starta om eller ta bort dessa projekt. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Juni 2017

Nya funktioner släpptes 8 juni 2017.

<table id="table_5B859A64363A44A98FC55E7AFB3C1D0C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Funktion </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b> <a href="/help/analyze/analysis-workspace/visualizations/fallout/configuring-fallout.md"  > Utfallsförbättringar </a></b> </td> 
   <td colname="col2"> 
    <ul id="ul_8A979BC0BE0F4D008F68B019A2D83A08"> 
     <li id="li_C8093834980B43A094FA9E2A7906E135">Obegränsade segment för jämförelse </li> 
     <li id="li_45D709C9B04F4E6A9BD94FD03E0C80FA">Möjlighet att namnge och enklare hantera kontaktpunktsgrupper (lägga till, ta bort, flytta osv.) </li> 
     <li id="li_BC609CDFD9AA4EB081987922DB318040">Högerklicka &gt; <span class="uicontrol"> Trend Touchpoint % </span>: trender för den totala bortfallsprocenten </li> 
     <li id="li_C72BB725368644DDA3FCE479A918CDB3">Högerklicka &gt; <span class="uicontrol"> Trend All Touchpoint % </span>: trendar alla procentsatser för kontaktpunkter i utfallet (förutom för <span class="wintitle"> Alla besök </span> om det ingår) i samma diagram. </li> 
     <li id="li_40D0A8B481B04F21BEC0A4E421C77865">Möjlighet att begränsa enskilda kontaktytor till nästa träff (i motsats till så småningom) i banan </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <a href="/help/analyze/analysis-workspace/visualizations/c-flow/flow-settings.md"  > <b>Förbättrade</b> </a> flöden </td> 
   <td colname="col2"> 
    <ul id="ul_54675DB3F59E4B24AF0C8F6E6AB2F3C1"> 
     <li id="li_DEF7D9BF03CD4A2D86A4BDD89FB3731A">En ny visualiseringsinställning med namnet <span class="wintitle"> Inaktivera etiketttrunkering har lagts till </span> (standard = avmarkerad). </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b> <a href="/help/analyze/analysis-workspace/components/calendar-date-ranges/calendar.md"  > Kalenderändringar </a></b> </td> 
   <td colname="col2"> Ändrar kalendern så att den överensstämmer med kalendern för rapporter och analyser: 
    <ul id="ul_BD706B07369F4339BF4925F22FEC1C7F"> 
     <li id="li_33A47BAAD3C04C8784D2FC00A6F6782E">Första klickningen startar ett datumintervallval. Markera sedan intervallet i någon av riktningarna fram till den andra klickningen, som markerar datumintervallets slut. Om Skift-tangenten hålls nedtryckt (eller högerklickning används) när du klickar på det första datumet läggs det till i intervallet. </li> 
     <li id="li_C3BEC56ABCED482C82A41EA0550B3077">Utökade summeringsperioder för de olika delarna av rullande datum (t.ex. tillåt dagar att gå tillbaka upp till två år) </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Förbättrad sökning efter dimensionsobjekt</b> </p> </td> 
   <td colname="col2"> 
    <ul id="ul_E955585818FF4553A869003B94DDB697"> 
     <li id="li_A37D2DB6290842578FE752DD8E712B73">Högre hastighet </li> 
     <li id="li_BADFD0FF3D574F1C8F19EFB37F95969C">A <span class="uicontrol"> Show Top Items from the Last 6 Months </span> option that pullin more data, if necessary </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b> Kryssrutan <a href="/help/analyze/analysis-workspace/build-workspace-project/column-row-settings/column-settings.md"  > Använd procentgränser </a></b> </p> </td> 
   <td colname="col2"> 
    <ul id="ul_7B6B794EDF874A4D87770AB9BAB42F33"> 
     <li id="li_0B403D892320434FBAD9A7F7B808947C"> En kryssruta har lagts till för att ange procentavdrag, särskilt för procentbaserade mått (fungerar även med icke-procentbaserade mått). </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Komponenthanterarens </b>förbättringar </p> </td> 
   <td colname="col2"> 
    <ul id="ul_BB22F84ABFB04685A9752AD4BDE6E60A"> 
     <li id="li_B3D460C15C454911A9D7254F50815355">Lagt till förfallodatum för aviseringar och schemalagda projekt </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b> <a href="/help/components/c-alerts/alert-manager.md"  > Förbättringar av </a> </b>Varningshanteraren </p> </td> 
   <td colname="col2"> 
    <ul id="ul_72464DC499744290BA37DB3B1E143F74"> 
     <li id="li_C687F0A3A99F4CC39B482BDA0F7B75DD">Lagt till möjlighet att aktivera/inaktivera aviseringar. </li> 
     <li id="li_F7415EE7DF29417FAF416594E36A38A4">En aktiverad/inaktiverad kolumn har lagts till. </li> 
     <li id="li_61B3A60A2AFB4BD0AA4D83803AB95B1E">Ett filter för aktiverade/inaktiverade aviseringar har lagts till. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Nya <b><a href="/help/analyze/analysis-workspace/build-workspace-project/fa-shortcut-keys.md"  > snabbtangenter </a></b> </p> </td> 
   <td colname="col2"> <p>Följande snabbtangenter har lagts till: </p> 
    <ul id="ul_5AE965D910DA4883BC2067CDFDBBA75A"> 
     <li id="li_6DBD6DFB9CA54F89B9A0627F3B1D5928">alt + Skift + 1 = Gå till rutan Paneler </li> 
     <li id="li_1B7E7C1115A84DB8A1BC07EA1C3AB15F">alt + Skift + 2 = Gå till panelen Visualiseringar </li> 
     <li id="li_1BDB09DDEEDC4E7DB0D1C08A4E02A613">alt + Skift + 3 = Gå till komponentpanelen </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

## April 2017

Nya funktioner släpptes 20 april 2017.

<table id="table_53EEFB870ED943F5BFD71FAB2DBCE49B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Funktion </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <a href="/help/analyze/analysis-workspace/build-workspace-project/starter-projects.md"  > Personmall </a> </p> </td> 
   <td colname="col2"> <p>Obs!  Mallen Personer och tillhörande personmått är bara tillgängliga för användning som en del av <a href="https://marketing.adobe.com/resources/help/en_US/mcdc/mcdc-people.html"  > Adobe Experience Cloud Device Co-op </a>. </p> <p>Mallen är baserad på personmåttet, som är en deduplicerad version av det unika besökarmåttet. Personmåttet är ett mått på hur ofta konsumenter som använder flera enheter interagerar med ert varumärke. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Förbättringar av alternativet Ångra/Gör om </p> </td> 
   <td colname="col2"> <p>De här listorna visar vad du kan och inte kan <a href="/help/analyze/analysis-workspace/build-workspace-project/undo-redo.md"  > ångra/göra om i Analysis Workspace </a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Februari 2017

Ny funktion släppt 16 februari 2017:

<table id="table_227D3668E9FD4FF4A1906FC619DCAFBF"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Funktion </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <a href="/help/analyze/analysis-workspace/build-workspace-project/column-row-settings/table-settings.md"  > Uppdelning efter position </a> </p> </td> 
   <td colname="col2"> <p>Tillåter uppdelning efter tabellposition. Exempel: "Jag vill alltid att de sju översta raderna i en frihandstabell ska brytas ned." Nu finns det en kryssruta när du skapar en frihandsritabell där du kan aktivera "Uppdelning efter position". Den här inställningen är inaktiverad som standard. </p> <p>Tidigare var listan med värden i neddelningen "låst". Detta ledde till en situation där du, om du t.ex. gjorde en uppdelning av <span class="wintitle"> Datum </span> efter <span class="wintitle"> sida </span>, fick en lista över de 50 översta sidorna för det valda datumintervallet. </p> <p>Om du sparade rapporten och sedan körde den en månad senare, hade troligen de 50 översta sidorna ändrats. Analysarbetsytan "litade" dock på resultaten från den ursprungliga uppdelningen och returnerade samma sidor, men med den aktuella månaden som datumintervall. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Januari 2017

Ny funktion släppt 19 januari 2017:

<table id="table_0AB06B81BFA34521A9BF1150E64663C3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Funktion </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <a href="/help/analyze/analysis-workspace/curate-share/download-send.md"  > Skicka och ladda ned en PDF-fil utan att behöva spara projektet </a> </p> </td> 
   <td colname="col2"> <p>Du kan nu skicka och hämta en PDF-fil i Workspace utan att behöva spara projektet. Namnet på PDF-filen matchar projektets aktuella namn. Den hämtade PDF-filen innehåller ändringarna som inte sparats i projektet. Observera att du inte kan schemalägga osparade projekt. (Du kan också skicka och hämta osparade CSV-filer, men du kan inte schemalägga dem.) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="/help/analyze/analysis-workspace/curate-share/curate.md"  > Dela projektkomponenter automatiskt </a> </p> </td> 
   <td colname="col2"> <p>Nu kan du dela projektkomponenter automatiskt (segment, beräknade värden och datumintervall) med alla mottagare. När komponenterna har delats visas de i komponentlistrutan på mottagarens arbetsyta. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Bortfallsvisualisering i CSV-format </p> </td> 
   <td colname="col2"> <p>Stöd för utfallsvisualisering i CSV-format har lagts till. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="/help/analyze/analysis-workspace/components/t-freeform-project-segment.md"  > Datumintervall i segment </a> </p> </td> 
   <td colname="col2"> <p>Du kan släppa datumintervall i släppzoner för segment (till exempel släppzoner för panelsegment, släppzoner för utfallsvisualisering av segment och så vidare). Datumintervallen konverteras automatiskt till segment. Datumintervallen kan vara anpassade och icke-anpassade men inte detaljerade, som timme/dag/vecka/månad/kvartal/år. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="/help/analyze/analysis-workspace/components/calendar-date-ranges/time-comparison.md"  > Lägg till en tidsperiod för varje kolumn i en tabell </a> </p> </td> 
   <td colname="col2"> <p>Nu kan du lägga till en tidsperiod för varje kolumn i en tabell, så att du kan lägga till en annan tidsperiod än den som du har angett för kalendern. Den här funktionen är ett annat sätt att jämföra datum. Du kan också justera datum från varje kolumn så att alla börjar på samma rad. </p> </td> 
  </tr> 
 </tbody> 
</table>

## November 2016

Ny funktion släppt 10 november 2016:

<table id="table_9B2B9CC7A3574A99A716BF1C9745E32B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Funktion </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <a href="/help/analyze/analysis-workspace/components/calendar-date-ranges/time-comparison.md"  > Datumjämförelse </a> </p> </td> 
   <td colname="col2"> <p>Med den nya funktionen Datumjämförelse kan du ta valfri kolumn och skapa en gemensam datumjämförelse, till exempel: år över år, kvartal över kvartal, månad över månad och så vidare. </p> <p>Datumjämförelser innehåller automatiskt en Differens-kolumn, som visar den procentuella ändringen. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Oktober 2016

Nya funktioner som släpptes 20 oktober 2016:

<table id="table_56258080C60F480AA83E1D5DE7D2C782"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Ny funktion </th> 
   <th colname="col2" class="entry"> Hur du kan använda den </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b> <a href="/help/analyze/analysis-workspace/visualizations/fallout/fallout-flow.md"  > Utfallsanalys </a></b> </td> 
   <td colname="col2"> <p>Den nya utfallsfunktionen kommer att ge marknadsföringstrattfunktionalitet till Analysis Workspace. Med en tratt kan ni identifiera var kunderna överger en marknadsföringskampanj eller avviker från en definierad konverteringsväg när ni interagerar med er webbplats eller flerkanalskampanj. Med bortfallsanalys kan ni bygga robusta funktioner med nya visualiseringar och den flexibilitet som Analysis Workspace ger för att identifiera konverteringar för viktiga framgångsmått. Med bortfallsanalys kan du </p> <p> </p> 
    <ul id="ul_E7C8255BA5D84F74ABBC6CC0E148DFB0"> 
     <li id="li_B7AC104F2A9348DCB2BCAA2FC9D3F3E6">Dra, släpp och ordna om trattsteg (kontaktytor) </li> 
     <li id="li_CC85524BC64546CD84794CC02C24CF21">Analysera flerdimensionella utfall (blanda och matcha värden från olika dimensioner och mätvärden) </li> 
     <li id="li_FA59CEE0211E4894B9109FF6A2FA3F80">Identifiera nästa steg för att ta reda på vart kunderna tar vägen direkt efter att de faller bort </li> 
    </ul> <p><img placement="break"  src="assets/fallout2.png" width="500px" id="image_193B0E7870734DAFA063BBFA121A3E34" /> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b> <a href="/help/analyze/analysis-workspace/visualizations/c-flow/flow.md"  > Flödesvisualisering </a></b> </td> 
   <td colname="col2"> <p>Med den nya flödesfunktionen kan ni visa kundflödet/kundresan genom webbplatser/appar via nya, uppdaterade och flexibla visualiseringar i Analysis Workspace för att identifiera hur kunderna rör sig och utvecklas genom sina webbplatser/appar. Med Flow kan du </p> <p> </p> 
    <ul id="ul_F1D4A99743664CB3B17E9485CF5E72FC"> 
     <li id="li_0F7AF953EAB746DC95032FF9A533E560">Visualisera kundresan genom resurser </li> 
     <li id="li_697A47BE06CF4284ACA3DBE4CA4012BF">Analysera omedelbara steg från ingång, avslut eller en viss dimensionspost i kundresan </li> 
     <li id="li_D13AD928AC434D599D43836FB334B14D">Skapa ett användarsegment dynamiskt genom att ange en specifik punkt i en vald bana </li> 
    </ul> <p><img placement="break"  src="assets/flow.png" width="500px" id="image_8ED88B5EDAA046978170F8BBB4018DA2" /> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b> <a href="/help/components/c-alerts/intellligent-alerts.md"  > Intelligenta aviseringar </a></b> </td> 
   <td colname="col2"> <p>Som det nya varningssystemet för alla Adobe Analytics kan ni med intelligenta aviseringar skapa och hantera aviseringar på Analysis Workspace, med förhandsgranskning av aviseringar och regelbidrag. Du kan: </p> <p> </p> 
    <ul id="ul_02BD64D3047942009880B8F1DA1F2A40"> 
     <li id="li_01504AABBC514DF38354683843222541">Skapa aviseringar baserade på avvikelser (tröskelvärden på 90 %, 95 % eller 99 %), % förändring, ovanför/nedanför). </li> 
     <li id="li_9BFE2B4C429D441287F1A37A08E62A40">Förhandsgranska hur ofta en varning utlöses. </li> 
     <li id="li_08D310196581483DB499C00358835B73">Skicka aviseringar via e-post eller SMS med länkar till automatiskt genererade Analysis Workspace-projekt. </li> 
     <li id="li_2ADF9465EE474CDB839ED867662CCE6F">Skapa"staplade" aviseringar som fångar in flera mätvärden i en enda avisering. </li> 
    </ul> <p><img placement="break"  src="assets/intel-alerts.png" width="400px" id="image_10069C33B6B1437CA578B8194FC75AD8" /> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b> Analys <a href="/help/analyze/analysis-workspace/virtual-analyst/c-anomaly-detection/anomaly-detection.md"  > av avvikelseidentifiering och bidrag </a></b> </td> 
   <td colname="col2"> <p>Låter dig veta om en ändring i trenddata är väsentlig och vad som orsakade den. </p> <p>Både avvikelseidentifiering och bidragsanalys är nu centrala arbetsflöden i Analysis Workspace. </p> <p>Viktigt:  Contribute Analysis är bara tillgängligt för Adobe Analytics Premium-kunder. </p> <p>Du kan: </p> <p> </p> 
    <ul id="ul_9CEE47788F3640838D8598F2E2C020D6"> 
     <li id="li_787236BB5EA545B8833B311C06C24337">Identifiera automatiskt statistiskt signifikanta dataavvikelser i dina data. </li> 
     <li id="li_2FB3D94DEEF14DD5ADA6AD69E15F243D">Kör Contribute Analysis mot eventuella avvikelser per dag och bädda in dem i Analysis Workspace-projektet. </li> 
    </ul> <p><img placement="break"  src="assets/anomaly_linechart.png" width="500px" id="image_DFAF4034E2AC4B4AAB140EA004112722" /> </p> <p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b> <a href="/help/analyze/analysis-workspace/build-workspace-project/starter-projects.md"  > Startprojekt </a></b> </td> 
   <td colname="col2"> För att förenkla för användarna att komma igång med Analysis Workspace har vi skapat några färdiga projektmallar för vanliga affärsproblem, som <p> </p> 
    <ul id="ul_603F5ACC16F74D53AEB9F762FAC91656"> 
     <li id="li_6B3F2E5D4B044EC19D45E5501E33DB91">Bevarar användare </li> 
     <li id="li_7240EE8852FC4642B3AD4837C990A775">Förvärv av mobilappar </li> 
    </ul> <p><img placement="break"  src="assets/starter.png" width="500px" id="image_A62AFD39812E43DCBF30D5E072A7E892" /> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b> Visualisering av <a href="/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md"> histogram </a></b> </td> 
   <td colname="col2"> <p>Med histogram kan användarna se hur användarna distribueras vid alla lyckade händelser. Du kan anpassa bucketerna och bucketstorlekarna så att de passar alla distributioner och för att identifiera värdefulla och värdefulla användare. </p> <p><img placement="break"  src="assets/histogram3.png" width="500px" id="image_E3277073B50140E0A3FD7C1601CF9661" /> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Diverse uppdateringar </td> 
   <td colname="col2"> 
    <ul id="ul_2585F74DC7754C819017F280E16BF06F"> 
     <li id="li_412446013E7F42DBB1BF50F9E2C4D92F"> 
      <!--AN-124610: -->Added "Count Repeat Instances" as a project-level setting ( <span class="uicontrol"> Project </span> &gt; <span class="uicontrol"> Project Info &amp; Settings </span>). Den här inställningen anger om upprepade instanser räknas i rapporter. Om du har flera sekventiella värden för samma variabel kan du räkna dem som en eller flera instanser av variabeln. </li> 
     <li id="li_480E1B307C62418CBC2F50ADE32B9EE9">En ny knapp med namnet "Använd på alla paneler" har lagts till bredvid "Avbryt" och "Kör" i kalendern. Ändrade Kör till Använd. Om du klickar på den nya knappen ändras inte bara det markerade datumintervallet för den aktuella panelen, utan även för alla andra paneler i projektet. </li> 
     <li id="li_4D10DFE307344D06AA60792FABE5B57E"> 
      <!--AN-124168: -->En åtgärdsknapp på den vänstra navigeringslisten med följande funktioner: Tagg, Favorit, Godkänn, <b>Dela (nytt!)</b>, <b>Ta bort (nytt!)</b>. </li> 
     <li id="li_946EC05568D4447193E9307546DF6F9B">Ett filter har lagts till i sökfältet där du kan filtrera efter taggar, favoriter, godkända objekt och komponenter. </li> 
     <li id="li_4EA118ACCD3B4F88B0ECF72717F631FA">En förhandsvisningsikon har lagts till för manuella rader (inte för dynamiska rader som listar dimensionsobjekt) där du kan förhandsgranska segment, mätvärden och datumintervall. </li> 
     <li id="li_81D5241EA3FD49CEA0E9F412837D87A8"> 
      <!--AN-128702: -->YouTube-länken för Analysis Workspace-självstudiekurser har uppdaterats för att: <a href="https://www.youtube.com/playlist?list=PL2tCx83mn7GuNnQdYGOtlyCu0V5mEZ8sS"  > https://www.youtube.com/playlist?list=PL2tCx83mn7GuNnQdYGOtlyCu0V5mEZ8sS </a>. </li> 
     <li id="li_D81DB98C49664D2884CCCC1DB0058CD8"> 
      <!--AN-124004:-->För visualiseringar har vi lagt till ett högerklicksalternativ som heter Starta över <span class="uicontrol"> </span> på snabbmenyn (fungerar för Flöde, Venn, Histogram), som tar bort konfigurationen för den aktuella visualiseringen och öppnar en ny panel där du kan konfigurera om den. </li> 
     <li id="li_84632BFCE1794B49A31FF45067FA04B7">Med en ny visualiseringsinställning som heter "Förklaring synlig" kan du dölja filterinformationstexten för visualiseringen av Sammanfattningsnummer/Sammanfattningsändring. </li> 
     <li id="li_EE8C48642DD54A04B08F4222F9565BF6">Med en ny visualiseringsinställning för visualisering av sammanfattningsändringar kan du visa skillnaden mellan två procenttal. Om du väljer alternativet "Visa skillnad" för värden som inte är procent visas ett tal. </li> 
     <li id="li_17AAABCA7B3A477182FB70453CA2EEBB">Justerade antalet rader för tidsdimensioner. </li> 
     <li id="li_35A91D50CD514CD0B939C24AEEC64BF4">Utseendet och känslan hos den vänstra navigeringslisten i segmentbyggaren och Beräknad metrisk Builder har uppdaterats så att den ser ut som Analysis Workspace. </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

## Juni 2016

Nya funktioner som släpptes 16 juni 2016:

* [Ny gruppbehörighet](https://marketing.adobe.com/resources/help/en_US/reference/groups.html) som tillåter administratörer att tillåta eller neka åtkomst till **[!UICONTROL Analytics]** >- **[!UICONTROL Workspace]** fliken för användare. Från och med den 16 juni 2016 har alla användare behörighet att komma åt den här fliken. Om du vill neka åtkomst tar du bara bort användare från Analysis Workspace Access-gruppen.
* Panelerna för [segmentjämförelse](/help/analyze/analysis-workspace/c-panels/c-segment-comparison/segment-comparison.md)visar de mest statistiskt signifikanta skillnaderna mellan två segment genom en automatiserad analys av varje enskilt mått och dimension som du har tillgång till.
* [Ny projektmenystruktur](/help/analyze/analysis-workspace/build-workspace-project/freeform-overview.md) som ordnar om den övre menyn och gör den mer utbyggbar. Om du till exempel skapar en **ny kohortpanel** nu måste du skapa en tom panel och dra i en kohorttabellvisualisering.
* [Ny vänster räl](/help/analyze/analysis-workspace/build-workspace-project/freeform-overview.md): Paneler, visualiseringar, komponenter
* En ny [Vennvisualiseringstyp](/help/analyze/analysis-workspace/visualizations/venn.md) som gör att du kan dra in upp till tre segment och ett mätvärde och skapa ett Venndiagram.
* [Trend Selection](/help/analyze/analysis-workspace/analysis-workspace-features.md#section_34930C967C104C2B9092BA8DCF2BF81A) (linjediagram) för en rankad tabell är nu länkat.
* [Ikonen](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md)&quot;Skapa visuell&quot;: Om du klickar på den här ikonen får du en smart gissning vid nästa åtgärd (stapeldiagram, Venn...).
* Utökad [funktion för](/help/analyze/analysis-workspace/build-workspace-project/column-row-settings/manual-vs-dynamic-rows.md) manuella rader
* [Lägg till](/help/analyze/analysis-workspace/components/t-freeform-project-segment.md) släppzon för segment
* Mindre uppdateringar:

   * Möjlighet att ta bort alla visualiseringar i en panel och alla paneler i ett projekt. (Tidigare var du tvungen att behålla minst en visualisering eller en panel.)
   * Ändringar av [kortkommandon](/help/analyze/analysis-workspace/build-workspace-project/fa-shortcut-keys.md) (snabbtangenter) som kan underlätta arbetet med Analysis Workspace.
   * Formatändringar: Mindre teckensnitt i visualiseringar färgrutor på rader, flyttade datumväljaren nedåt (på paneler).

## April 2016

Nya funktioner som släpptes 21 april 2016:

<table id="table_2649645FDED84B71952F741ABB3FC20E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Funktion </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Skicka fil </td> 
   <td colname="col2"> <p>Skicka ett Analysis Workspace-projekt via e-post eller schemalägg det för leverans. Se <a href="/help/analyze/analysis-workspace/curate-share/t-schedule-report.md"  > Skicka fil - Schemalägg ett projekt för leverans </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Hämta PDF </td> 
   <td colname="col2"> <p>På Åtgärd-menyn kan du hämta ett Analysis Workspace-projekt i PDF-format (ungefär som när du hämtar i CSV-format). </p> </td> 
  </tr> 
 </tbody> 
</table>

## Januari 2016

Nya funktioner släpptes 21 januari 2016.

* [Ångra åtgärder](/help/analyze/analysis-workspace/new-features-in-analysis-workspace.md#section_12890C393D5E4FC8A3CF050318BD8482)
* [Länka till det här projektet](/help/analyze/analysis-workspace/new-features-in-analysis-workspace.md#section_453E70F7409F4501B8E976A0D18C9A46)
* [Visualiseringar av punktdiagram, punktdiagram och treemap](/help/analyze/analysis-workspace/new-features-in-analysis-workspace.md#section_B19EA50EBF5546E99D3A142827153FD6)
* [Spara som för segment, mått och datum](/help/analyze/analysis-workspace/new-features-in-analysis-workspace.md#section_04C8B10A0751453AAE5F1BC35938C6CE)
* [Knappen Lägg till nytt segment](/help/analyze/analysis-workspace/new-features-in-analysis-workspace.md#section_85CC88C02C79456EA2B41F2BFBB64FC4)
* [Villkorsstyrd formatering](/help/analyze/analysis-workspace/new-features-in-analysis-workspace.md#section_5775B505D83041408B8C3EAEC5D7C32B)
* [Förhandsgranska dimension](/help/analyze/analysis-workspace/new-features-in-analysis-workspace.md#section_F519EBF889B244E8B25BB6BA2833325A)
* [Förklaring synlig](/help/analyze/analysis-workspace/new-features-in-analysis-workspace.md#section_28D10D86CAE343AB838808C1DD2E7983)
* [Fästpunkt Y-axel vid noll](/help/analyze/analysis-workspace/new-features-in-analysis-workspace.md#section_83DF5DE79EF04F9F8DCB3154F5E799B3)
* [Projektnamn på fliktitel](/help/analyze/analysis-workspace/new-features-in-analysis-workspace.md#section_497C61A030984BCCA2CEA553312C3226)
* [Överför projektägarskap](/help/analyze/analysis-workspace/new-features-in-analysis-workspace.md#section_989C2CCB80B5408EB85E6B12C8D943E3)


## Ångra åtgärder {#section_12890C393D5E4FC8A3CF050318BD8482}

Du kan nu ångra de flesta åtgärder du utför i Analysis Workspace.

Ångra genom att klicka **[!UICONTROL Undo]** på funktionsmakromenyn.

![](assets/undo.png)

Du kan också använda Windows- och Mac- [kortkommandon](/help/analyze/analysis-workspace/build-workspace-project/fa-shortcut-keys.md) (Ctrl eller Cmd + z) för Ångra.

*`Undo`* är särskilt användbart när du ångrar brytningar i tabellen.

Åtgärder som inte kan *`not`* ångras:

* Ändra konfigurationen för en [!UICONTROL Cohort Table] (till exempel dra mätvärden, ändra värden). Du kan dock klicka **[!UICONTROL Undo]** efter att du klickat **[!UICONTROL Run]**.

* Ändra storlek på eller flytta paneler och underpaneler.

Åtgärder som rensar ångra-historiken:

* Sparar projektet.
* Ändrar rapportsviten.

## Länka till det här projektet {#section_453E70F7409F4501B8E976A0D18C9A46}

I ett projekt klickar du på **[!UICONTROL Link to This Project]** Åtgärder-menyn för att skicka ett sparat projekts URL till andra användare. Administrativa mottagare kan redigera och spara ett projekt som delas på det här sättet. I annat fall är dessa projekt skrivskyddade.

![](assets/link-to-this-project.png)

> [!NOTE] Delningsrapportlänkar är inte tillgängliga om ditt företag använder enkel inloggning (både den äldre enkla inloggningen och när du loggar in via Experience Cloud).

## Visualiseringar av punktdiagram, punktdiagram och treemap {#section_B19EA50EBF5546E99D3A142827153FD6}

Följande nya visualiseringar är tillgängliga i januari 2016-versionen.

**Punktdiagram**

Du kan se hur ett värde som du är intresserad av jämförs med eller mäter mot andra prestandaintervall (mål).

![](assets/bullet-image.png)

Punktdiagrammet innehåller ett enda primärt mått (till exempel dagens intäkter), som jämför det måttet med en eller flera andra åtgärder för att förstärka dess betydelse (till exempel jämfört med en målintäkt) och visar det i ett sammanhang av kvalitativa resultatintervall, till exempel hög, mitten och låg. Du kan ange målintervall i [!UICONTROL Visualization Settings].

**Scatterplot**

![](assets/scatter.png)

Visar hur många visningar som använts och hur många unika användare som har sett dessa intryck. Storleken på varje datapunkt ger en visuell indikation på det genomsnittliga antalet gånger som ett visningsprogram exponerades för en annons. Storleken och data varierar beroende på de dimensioner, datumintervall och filter du väljer.

> [!NOTE] En tabell som är associerad med ett Scatterplot-diagram kräver minst två kolumner. Den första kolumnen definierar X-axeln och den andra kolumnen definierar Y-axeln. Om det finns en tredje kolumn tillgänglig används den för att bestämma punktens radie. Kolumnerna *1*, *2* och *3* mappas med andra ord till *X*, *Y*** och¥dot radius¥.

**Treemap**

Visar hierarkiska (trädstrukturerade) data som en uppsättning kapslade rektanglar. Varje förgrening i trädet får en rektangel som sedan visas sida vid sida med mindre rektanglar som representerar undergrenar.

![](assets/treemap.png)

När färg- och storleksmåtten på något sätt korrelerar med trädstrukturen kan man ofta se mönster som är svåra att dekorera på andra sätt, t.ex. om en viss färg är särskilt relevant. En annan fördel med treemaps är att de genom sin konstruktion utnyttjar utrymmet på ett effektivt sätt.

## Spara som för segment, mått och datum {#section_04C8B10A0751453AAE5F1BC35938C6CE}

När du redigerar ett befintligt (sparat) segment i segmentbyggaren för Analysis Workspace klickar du **[!UICONTROL Save As]** för att skapa en kopia.

![](assets/segment-save-as.png)

Det nya segmentet visas i [!UICONTROL Segments] gruppen på [!UICONTROL Components] panelen.

*`Save As`* finns även för [!UICONTROL Calculated Metric Builder] och [!UICONTROL Date Range Builder].

## Knappen Lägg till nytt segment {#section_85CC88C02C79456EA2B41F2BFBB64FC4}

Knappen har lagts till på den plats där du drar och släpper segment i ett projekt. **[!UICONTROL Add New Segment]**

![](assets/add-new-segment.png)

Den här förbättringen är användbar om du föredrar att skapa segment direkt när du arbetar i ett projekt, i stället för att använda [!UICONTROL Segment] panelen för att skapa segment.

## Villkorsstyrd formatering {#section_5775B505D83041408B8C3EAEC5D7C32B}

I Kolumninställningar kan du använda villkorsstyrd formatering för celldata.

![](assets/conditional-formatting.png)

<table id="table_4285E6982FBD4B66AC95AAF6C5C7B347"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Element </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Villkorsstyrd formatering </td> 
   <td colname="col2"> <p> Tillämpar följande färger på celler baserat på datavärden: </p> 
    <ul id="ul_97E3AD5F6B41460C882D8B4EE0A8C77A"> 
     <li id="li_88874B4250224DE781C03E4A5931D6A2">Grön: höga värden </li> 
     <li id="li_B4863F967C7544D7AA2847696FB85525">Gul: mittpunktsvärden </li> 
     <li id="li_5B06D7CD0C39437898DA55EA653A1124">Röd: låga värden </li> 
    </ul> <p>Om du ersätter en dimension i tabellen återställs de villkorliga formateringsgränserna. Om du ersätter ett mätvärde räknas gränserna för den kolumnen om (där ett mätvärde finns på X-axeln och ett mått finns på Y-axeln). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Automatiskt genererad </td> 
   <td colname="col2"> <p>Genererar automatiskt gränser för villkorsstyrd formatering. Den övre gränsen är det största värdet i den här kolumnen. Den undre gränsen är den lägsta och mittpunkten är medelvärdet av de övre och nedre gränserna. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Egen </td> 
   <td colname="col2"> <p>Du kan manuellt tilldela värdena för <span class="uicontrol"> fälten </span>Övre <span class="uicontrol"> , </span>Mittpunkt <span class="uicontrol"> och </span> Nedre gräns för villkorlig formatering. Detta ger dig flexibilitet att avgöra när ett kolumnvärde blir bra, medelvärde eller dåligt. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Förhandsgranska dimension {#section_F519EBF889B244E8B25BB6BA2833325A}

I komponentpanelen kan du hovra över informationsikonen bredvid en dimension och se en förhandsvisning som är högst fem. [!UICONTROL Dimensions]

![](assets/dimension-preview.png)

## Förklaring synlig {#section_28D10D86CAE343AB838808C1DD2E7983}

I [!UICONTROL Visualization Settings] det här **[!UICONTROL Legend Visible]** alternativet visas eller döljs en visualiserings förklaring.

![](assets/legend-visible.png)

## Fästpunkt Y-axel vid noll {#section_83DF5DE79EF04F9F8DCB3154F5E799B3}

Beroende på vad siffrorna är för en linje och ett ytdiagram kan det hända att Y-axelns nederkant inte är noll. Aktivering **[!UICONTROL Anchor Y Axis at Zero]** i [!UICONTROL Visualization Settings] tvingar Y-axeln till noll för en mer korrekt bild av trender. I följande exempel visas hur ett intäktsdiagram ändras när den här inställningen är aktiverad och inaktiverad:

**Fästpunkt Y-axel vid noll inaktiverad**

![](assets/anchor_Y_axis_off.png)

**Fästpunkt Y-axel vid noll aktiverad**

![](assets/anchor_Y_axis.png)

## Projektnamn på fliktitel {#section_497C61A030984BCCA2CEA553312C3226}

När du sparar ett projekt visas rubriken på webbläsarfliken som&quot;`<Project Name>` - Analysis Workspace&quot;. Den här förbättringen är användbar om du öppnar flera projekt på flera webbläsarflikar.

## Överför projektägarskap {#section_989C2CCB80B5408EB85E6B12C8D943E3}

Administratörer kan överföra [!UICONTROL Analysis Workspace] projekt från en användare till en annan.

Navigera till **[!UICONTROL Admin]** > **[!UICONTROL User Management]** > **[!UICONTROL Transfer]** för att överföra projekt.
