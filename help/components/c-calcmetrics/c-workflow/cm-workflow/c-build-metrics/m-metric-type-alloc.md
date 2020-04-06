---
description: Om du väljer kugghjulsikonen bredvid ett mätresultat kan du ange mättyp och attribueringsmodell.
title: Mättyp och attribut
uuid: 64649698-df2a-42c3-bb31-938f766e1d1f
translation-type: tm+mt
source-git-commit: e6aaf2754c6a5c33fbe3e093b4d7ca5a375c41e7

---


# Mättyp och attribut

Om du väljer kugghjulsikonen bredvid ett mätresultat kan du ange mättyp och attribueringsmodell.

* [Mätningstyp](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/m-metric-type-alloc.md#section_34A86FB402F94E988724232283BF18B7)
* [Kolumnattributmodell](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/m-metric-type-alloc.md#section_F9690FD1943B403AB28E2FAC54EFE032)
* [How Linear Allocation works (from 19 juli 2018)](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/m-metric-type-alloc.md#section_EDBB2E14A6C248C5A79C0913C02D7CA1)

## Mätningstyp {#section_34A86FB402F94E988724232283BF18B7}

![](assets/cm_type_alloc.png)

| Mätningstyp | Definition |
|---|---|
| Standard | Dessa värden är samma värden som används i [!DNL Analytics] standardrapporter. Om en formel består av ett enda standardmått visas data som är identiska med den icke-beräknade metriska motsvarigheten. Standardvärden är användbara när du vill skapa beräknade värden som är specifika för varje enskilt radobjekt. Exempel: [Beställningar] / [besök] tar order för det specifika radobjektet och dividerar det med antalet besök för det specifika radobjektet. |
| Totalt | Använd summan för rapporteringsperioden i varje radartikel. Om en formel består av ett enda totalt mätvärde visas samma totala antal på varje radartikel. Totala värden är användbara när du vill skapa beräknade värden som jämför med webbplatsens totala data. Exempel: [Beställningar] / [Totalt besök] visar hur stor andel av beställningarna som gäller för ALLA besök på platsen, inte bara besöken för den specifika radobjektet. |

## Kolumnattributmodell {#section_F9690FD1943B403AB28E2FAC54EFE032}

>[!IMPORTANT]
>
>I juli 2018 [!DNL Analytics] infördes [attribuerings-IQ](https://marketing.adobe.com/resources/help/en_US/analytics/analysis-workspace/attribution.html), som reviderade hur allokeringsmodeller i beräknade värden utvärderas. Som en del av denna ändring migrerades beräknade värden som använder en icke-standardallokeringsmodell till nya förbättrade attribueringsmodeller:
>
>* En fullständig lista över icke-standardattribueringsmodeller och uppslagsfönster som stöds finns i dokumentationen för [Attribution IQ](https://marketing.adobe.com/resources/help/en_US/analytics/analysis-workspace/attribution.html) .
>* Allokeringsmodellerna&quot;sista beröringen i marknadsföringskanalen&quot; och&quot;Första beröringen i marknadsföringskanalen&quot; migreras till de nya attribueringsmodellerna&quot;Sista beröringen&quot; respektive&quot;Första beröringen&quot; (Obs! &quot;Marknadsföringskanaler&quot; kommer inte att bli inaktuella - bara de två allokeringsmodellerna som visas i beräknade värden kommer att vara det).
>* Dessutom kommer vi att korrigera hur linjär allokering beräknas. För kunder som använder beräknade värden med linjär allokering kan rapporterna ändras något för att återspegla den nya, korrigerade attribueringsmodellen. Den här ändringen av beräknade värden återspeglas i Analysis Workspace, Reports &amp; Analytics, Reporting API, Report Builder och Ad Hoc Analysis. Mer information finns i **How Linear Allocation works (fr.o.m. 19 juli 2018**) nedan.
>



## How Linear Allocation works (from 19 juli 2018)

I juli 2018 ändrade Adobe hur linjär allokering rapporteras för beräknade värden. Den här ändringen påverkar Analysis Workspace, Ad Hoc Analysis, Reports &amp; Analytics, Report Builder, Activity Map och API:erna för rapportering. Ändringen påverkar i första hand eVars och andra dimensioner som är beständiga. Observera att dessa ändringar endast gäller för beräknade värden och inte påverkar andra rapporter som använder linjär allokering (till exempel sidrapporten i Rapporter och analyser). Andra rapporter där linjär allokering används kommer även fortsättningsvis att använda den befintliga metoden för linjär allokering.

I följande exempel visas hur beräknade värden med linjär allokering kommer att ändras i rapporteringen:

<table id="table_E66D066A3E7B4232BBC220775F8B985A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> </th> 
   <th colname="col2" class="entry"> Träff 1 </th> 
   <th colname="col3" class="entry"> Träff 2 </th> 
   <th colname="col4" class="entry"> Träff 3 </th> 
   <th colname="col5" class="entry"> Träff 4 </th> 
   <th colname="col6" class="entry"> Träff 5 </th> 
   <th colname="col7" class="entry"> Träff 6 </th> 
   <th colname="col8" class="entry"> Träff 7 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Data skickade </p> </td> 
   <td colname="col2"> PROMO A </td> 
   <td colname="col3"> - </td> 
   <td colname="col4"> PROMO A </td> 
   <td colname="col5"> PROMO B </td> 
   <td colname="col6"> - </td> 
   <td colname="col7"> PROMO C </td> 
   <td colname="col8"> $10 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Senaste beröring eVar </p> </td> 
   <td colname="col2"> PROMO A </td> 
   <td colname="col3"> PROMO A </td> 
   <td colname="col4"> PROMO A </td> 
   <td colname="col5"> PROMO B </td> 
   <td colname="col6"> PROMO B </td> 
   <td colname="col7"> PROMO C </td> 
   <td colname="col8"> $10 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>First Touch eVar </p> </td> 
   <td colname="col2"> PROMO A </td> 
   <td colname="col3"> PROMO A </td> 
   <td colname="col4"> PROMO A </td> 
   <td colname="col5"> PROMO A </td> 
   <td colname="col6"> PROMO A </td> 
   <td colname="col7"> PROMO A </td> 
   <td colname="col8"> $10 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Exempel </p> </td> 
   <td colname="col2"> PROMO A </td> 
   <td colname="col3"> - </td> 
   <td colname="col4"> PROMO A </td> 
   <td colname="col5"> PROMO B </td> 
   <td colname="col6"> - </td> 
   <td colname="col7"> PROMO C </td> 
   <td colname="col8"> $10 </td> 
  </tr> 
 </tbody> 
</table>

I det här exemplet skickades värdena A, B och C till en variabel på träffar 1, 3, 4 och 6 innan ett köp på $10 gjordes på träffnummer 7. På den andra raden kvarstår dessa värden för alla träffar på grund av senaste beröringsbesök. Den tredje raden visar hur obestridliga besöken är. Slutligen visar den sista raden hur data skulle registreras för en prop som inte är beständig.

## Hur linjär tilldelning fungerade före juli 2018

Före den 19 juli 2018 beräknades linjär attribuering efter att en första beröring eller sista beröringspartiklar redan hade gjorts. Detta innebar att för den sista beröringen eVar ovan skulle $10 fördelas enligt följande: A = 10 * (3/6) = $5, B = 10 * (2/6) = $3,33, C = 10 * (1/6) = $1,67.

För den första beröringen eVar ovan ges A alla $10. För propen: A = 10 * (2/4) = $5, B = 10 * (1/4) = $2,50 och C = 10 * (1/4) = $2,50. Så här sammanfattar du linjär allokering som den fungerade tidigare:

| Värden | Aktuell eVar för senaste beröring | Aktuell eVar för första beröring | Aktuellt uttryck |
|---|---|---|---|
| PROMO A | $5.00 | $10.00 | $5.00 |
| PROMO B | $3.33 | $0 | $2.50 |
| PROMO C | $1.67 | $0 | $2.50 |
| Totalt | $10.00 | $10.00 | $10.00 |

**Sammanfattning av hur linjär tilldelning fungerar från och med den 19 juli 2018**

Efter 19 juli korrigerade vi detta beteende i beräknade mått. I stället för att använda de beständiga värden som baseras på senaste beröring eller första beröring använder [!DNL Analytics] nu endast de värden som skickades (den första raden i den övre tabellen). Inställningarna för dimensionsallokering påverkar inte längre det sätt på vilket linjär allokering beräknas (vilket innebär att props och eVars behandlas på samma sätt), och resultaten avspeglar det som ursprungligen skickades i stället för det första eller sista beröringsvärdet som kan ha varit bestående. I alla tre fallen är alltså A = 10 * (2/4) = $5, B = 10 * (1/4) = $2,50 och C = 10 * (1/4) = $2,50.

| Värden | New Last Touch eVar | New First Touch eVar | Nytt utkast |
|---|---|---|---|
| PROMO A | $5.00 | $5.00 | $5.00 |
| PROMO B | $2.50 | $2.50 | $2.50 |
| PROMO C | $2.50 | $2.50 | $2.50 |
| Totalt | $10.00 | $10.00 | $10.00 |

