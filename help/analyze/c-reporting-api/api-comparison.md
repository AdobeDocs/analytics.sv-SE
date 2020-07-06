---
description: En jämförelsetabell för Analytics API:er för rapportering. Det finns länkar till styrkande dokumentation.
title: API för Analytics-rapportering – jämförelse
uuid: fa533a8e-33c0-42f4-a294-cabee0258c8f
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '290'
ht-degree: 16%

---


# API för Analytics-rapportering – jämförelse

En jämförelsetabell för Analytics API:er för rapportering. Det finns länkar till styrkande dokumentation.

>[!NOTE]
>
>När det gäller fördröjning kombinerar Analytics för Target (A4T) Analytics- och Target-data på samma träff för integrerad rapportering. Eftersom Analytics- och Target-anrop sker vid olika tidpunkter, lagras träffar innan någon behandling utförs för att samla in data från båda lösningarna. Den här processen lägger till **ytterligare 7-10 minuters** fördröjning till alla kontrollpunkter.

<table id="table_7AF4FD678D494063ADF459B3CBC3EF3F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> API-typ </th> 
   <th colname="col2" class="entry"> Fullt bearbetad </th> 
   <th colname="col3" class="entry"> Realtid </th> 
   <th colname="col4" class="entry"> Livesream </th> 
   <th colname="col5" class="entry"> Data Warehouse </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>Beskrivning</b> </td> 
   <td colname="col2"> Fullständigt bearbetade, slutförda data som är tillgängliga i alla Analytics-gränssnitt. </td> 
   <td colname="col3"> Delvis bearbetade, begränsade mätvärden är tillgängliga inom några sekunder efter insamlingen. </td> 
   <td colname="col4"> Delvis bearbetade träffdata är tillgängliga inom några sekunder efter insamlingen. </td> 
   <td colname="col5"> Fullständigt bearbetade, slutförda data som används för att dra igång stora dataexporter. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><a href="https://docs.adobe.com/content/help/sv-SE/analytics/technotes/latency.html"  > Latens</a> </p> </td> 
   <td colname="col2"> 30-90 minuter </td> 
   <td colname="col3"> * Sekunder -10 minuter </td> 
   <td colname="col4"> Sekunder -10 minuter </td> 
   <td colname="col5"> 90 minuter + </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Slutförd bearbetning</b> </td> 
   <td colname="col2"> Fullständig </td> 
   <td colname="col3"> Delvis </td> 
   <td colname="col4"> Delvis </td> 
   <td colname="col5"> Fullständig </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <a href="https://docs.adobe.com/content/help/sv-SE/analytics/landing/home.html"  > Rapporteringsgränssnitt</a> </td> 
   <td colname="col2"> Reports &amp; Analytics, Report Builder, API </td> 
   <td colname="col3"> Realtidsrapport i Rapporter &amp; Analytics, Report Builder, API </td> 
   <td colname="col4"> Endast API </td> 
   <td colname="col5"> Data warehouse &amp; API </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Datakorprecision</b> </td> 
   <td colname="col2"> Sammanfattad </td> 
   <td colname="col3"> Sammanfattad </td> 
   <td colname="col4"> Träffnivå </td> 
   <td colname="col5"> Sammanfattad </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Bearbetning av besökarprofiler</b> </td> 
   <td colname="col2"> Ja </td> 
   <td colname="col3"> Nej </td> 
   <td colname="col4"> Nej </td> 
   <td colname="col5"> Ja </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Stöder segment</b> </td> 
   <td colname="col2"> Ja </td> 
   <td colname="col3"> Nej </td> 
   <td colname="col4"> Nej </td> 
   <td colname="col5"> Ja (men endast Data warehouse-kompatibla segment) </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Analytics SKU</b> </td> 
   <td colname="col2"> Standard+ </td> 
   <td colname="col3"> Standard+ </td> 
   <td colname="col4"> Premium Complete eller Predictive Intelligence </td> 
   <td colname="col5"> Standard+ </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Dokumentation</b> </td> 
   <td colname="col2"> <p> <a href="https://marketing.adobe.com/developer/documentation/analytics-reporting-1-4/get-started%E2%80%8B"  > Webbtjänster</a> </p> </td> 
   <td colname="col3"> <p> <a href="https://marketing.adobe.com/developer/documentation/analytics-reporting-1-4/real-time"  > Realtidsrapporter</a> </p> </td> 
   <td colname="col4"> <p> <a href="https://marketing.adobe.com/developer/documentation/analytics-live-stream/overview-1%E2%80%8B"  > Livesream Overview</a> </p> </td> 
   <td colname="col5"> <p><a href="https://docs.adobe.com/content/help/en/analytics/export/data-warehouse/data-warehouse.html"  > Data Warehouse</a> </p> </td> 
  </tr> 
 </tbody> 
</table>

**Relaterad hjälp**

* [Adobe/IO](https://www.adobe.io/) - En omfattande källa för den tekniska dokumentation och de verktyg som behövs för att integrera Adobe-tekniker i era program.
* [Data Workbench Query API](https://marketing.adobe.com/developer/documentation/data-workbench-query-api/c-ins-qry-api)

