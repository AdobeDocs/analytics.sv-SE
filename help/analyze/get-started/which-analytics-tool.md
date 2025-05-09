---
description: Den här hjälpsidan innehåller rekommenderade användningsexempel för varje Adobe Analytics-verktyg. Verktyg bör beaktas i den ordning de anges. Om ett visst verktyg inte uppfyller behovet går du vidare till nästa verktyg för övervägande.
title: Vilket Adobe Analytics-verktyg ska jag använda?
feature: Analytics Basics
exl-id: d65575df-19c6-4129-89c8-d36de7bb6b2f
source-git-commit: a40f30bbe8fdbf98862c4c9a05341fb63962cdd1
workflow-type: tm+mt
source-wordcount: '1117'
ht-degree: 3%

---

# Vilket Adobe Analytics-verktyg ska jag använda?

Den här hjälpsidan innehåller rekommenderade användningsexempel för varje Adobe Analytics-verktyg. Verktyg bör beaktas i den ordning de anges. Om ett visst verktyg inte uppfyller behovet går du vidare till nästa verktyg för övervägande.

Mer information om Adobe Analytics produktjämförelser finns i [Analytics - produktjämförelse](/help/analyze/get-started/analytics-product-comparison.md).


>[!BEGINSHADEBOX]

Se ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Jämförelse av verktyg](https://video.tv.adobe.com/v/27220?quality=12&learn=on){target="_blank"} för en demonstrationsvideo.

>[!ENDSHADEBOX]


## Adobe Analytics rapporterar användargränssnitt {#user-interfaces}

**[Analysis Workspace](/help/analyze/analysis-workspace/home.md)** bör vara användargränssnittet för alla dina rapporterings- och analysbehov. Adobe fortsätter att investera i och släppa månadsuppdateringar av den här produkten. Om du inte kan göra något i Analysis Workspace bör du överväga de andra gränssnitten nedan.**

**[Adobe Analytics Dashboards](/help/analyze/mobile-app/home.md)** ger användare mobil åtkomst till intuitiva styrkort. Styrkort är en samling viktiga mätvärden och andra komponenter som presenteras i en sida vid sida-layout som du kan trycka på för mer detaljerade uppdelningar och trendrapporter. Mobilappen stöds av både iOS och Android operativsystem.

**[Report Builder](/help/analyze/report-builder/rb-overview.md)** är ett tillägg för Microsoft Excel som kan köras i Mac, Windows och webbläsare. Här kan du skapa anpassade förfrågningar från Adobe Analytics-data, som du kan infoga i dina Excel-kalkylblad. Begäranden kan referera till celler dynamiskt i kalkylbladet, och du kan uppdatera och anpassa hur Report Builder visar data.

**[Äldre Report Builder](/help/analyze/legacy-report-builder/home.md)** är ett tillägg för Microsoft Excel som endast kan köras i Windows. Här kan du skapa anpassade förfrågningar från Adobe Analytics-data, som du kan infoga i dina Excel-kalkylblad. Begäranden kan referera till celler dynamiskt i kalkylbladet, och du kan uppdatera och anpassa hur Report Builder visar data.

**[Activity Map](/help/analyze/activity-map/overview.md)** är en funktion i Adobe Analytics som ger en visuell representation av användarinteraktionen på webbsidor och mobilappar. Det gör det möjligt för marknadsförare och analytiker att spåra och analysera användarinteraktioner som klickningar, hovrar och rullningsbeteende.

## Importera data till Adobe Analytics {#import}

**[Klassificeringar](/help/components/classifications/classifications-overview.md)** bör användas:

* När det finns metadata som du vill koppla till ett samlingsvärde (eVar, prop, marknadsföringskanal). Adobe rekommenderar att du använder [klassificeringsuppsättningar](/help/components/classifications/sets/overview.md). Klassificeringsregelbyggaren och klassificeringsimporteraren är äldre metoder för att överföra klassificeringsdata till Adobe Analytics.

**[Datakällor](/help/import/data-sources/overview.md)** ska användas:

* När det finns offlinedata vill du skriva permanent till Adobe Analytics
* Alternativ:
   * Sammanfattning: enkel dataöverföring per dag eller begränsade dimensioner
   * Transaktions-ID: dataöverföringar som kopplar en online-slutpunkt till offlinedata och kopplar importerade data till en besökarögonblicksbild som tagits online (t.ex. online-beställningar och returneras offline)

**[Adobe Exchange-integreringar](https://www.adobeexchange.com/experiencecloud.html)** ska användas:

* När du kontaktar en tredjepartsleverantör som har skapat en anslutning som stöds av Adobe Analytics. Integreringsappar lägger vanligtvis in data på sammanfattningsnivå i Adobe Analytics permanent och automatiskt, regelbundet.

**[API för datainfogning i grupp](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/bdia.md)**

* API:t för datainfogning i grupp accepterar CSV-formaterade filer som innehåller händelsedata, en händelse per rad. Adobe rekommenderar att du använder API:t för gruppinfogning för alla implementeringar som kräver kod på serversidan eller som på annat sätt inte kan använda AppMeasurement eller Web SDK för datainsamling.

**[API för datainmatning (äldre)](/help/import/c-data-insertion-api/c-data-insertion-api.md)** ska användas:

* När du behöver hämta data till Adobe Analytics och inte kan använda AppMeasurement, Web SDK eller API:t för datainfogning i grupp.

**[Kundattribut](https://experienceleague.adobe.com/docs/core-services/interface/customer-attributes/attributes.html?lang=sv-SE)** ska användas:

* Om du samlar in företagsdata i en CRM-databas (customer relationship management) och vill överföra data till Experience Cloud.
* Om ni vill använda CRM-data för en djupare analys i Analytics, eller som målinriktningskriterier i Adobe Target.

**[Audience Analytics](/help/integrate/c-audience-analytics/mc-audiences-aam.md)** bör användas:

* Om du vill inkludera Adobe Audience Manager målgruppsdata, t.ex. demografisk information (t.ex. kön eller inkomstnivå), psykografisk information (t.ex. intressen och hobbies), CRM-data eller annonsvisningsdata i ett Analytics-arbetsflöde.
* Om du vill att överförda CRM-data ska vara tidsbaserade, eftersom den här integreringen skickar ny information till Analytics som träffats av en träff.

## Exportera data från Adobe Analytics {#export}

**[Report Builder](/help/analyze/report-builder/rb-overview.md)** bör användas:

* Om de anpassade layoutalternativen i Workspace är begränsade (allt är möjligt i Report Builder, inom Excel-gränserna).
* För att smidigt knyta indata från användare eller offlinedatakällor (visningar, kostnader) till Adobe-data. En mer permanent lösning för att binda data är datakällor (se Importera data till analys).
* Att sammanfoga data från olika flerdimensionella rapporter (t.ex. en rapport om kampanjavtryck tillsammans med en kampanjrapport för klick-till-konvertering).
* Om du vill sammanfoga data från olika rapportsviter, antingen genom att summera eller visa dem i samma tabell sida vid sida.
* Om automatisering genom schemaläggning önskas (XLSX, XLSM, CSV, PDF, TXT, XML, MHT).

**[Data Warehouse](/help/export/data-warehouse/data-warehouse.md)** bör användas:

* Om du vill få åtkomst till variabler som annars är dolda i användargränssnittet - IP-adress, Experience Cloud-id, Analytics-besökar-ID, sid-URL)
* Få åtkomst till mer detaljerade data än användargränssnittet (denormaliserad tabellvy)
* Hämta data i ett format som passar för pivottabellindata
* Om klienten vill lägga in Adobe-data i ett datavisualiseringsverktyg från tredje part (något summerat och inte på träffnivå)
* För att få åtkomst till alla unika dimensionsobjekt om du kör i&quot;Låg trafik&quot; i Adobe Analytics

**[Analysdatafeed](/help/export/analytics-data-feed/c-df-contents/datafeeds-contents.md)** ska användas:

* För att kunna använda den mest detaljerade datafeed som vi kan tillhandahålla (besökar-ID, tryck).
* Om kunden vill ha Adobe-data lagrade i en databas på klientsidan, på den mest detaljerade nivå vi kan skicka.
* Om klienten vill utveckla ett Business Intelligence (BI)-verktyg eller lägga in Adobe-data på träffnivå i ett tredjepartsverktyg.

**[Rapporterings-API:er](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/reporting-guide.md)** bör användas när de andra visualiseringsalternativen inte uppfyller dina behov. De tre API-alternativen omfattar:

* **Fullt bearbetad**: när du vill ha funktionsrika data (inklusive besök, besökare och segment). Det här är typiska gränssnittsdata från Analytics, som är tillgängliga inom cirka 30-90 minuter. Kan användas via Report Builder.
* **Realtid**: när du vill visa några mått och dimensioner med fördröjningssekunder. Detta är begränsade, delvis bearbetade, sammanfattade data som är tillgängliga inom cirka 30 sekunder. Innehåller unika algoritmer för de flesta populära, vinnare och förlorare. Kan användas via Report Builder.
* **[!UICONTROL Live Stream]**: när du vill ha en ström med delvis bearbetade analysdata på träffnivå inom några sekunder från insamlingen. Detta är delvis bearbetade data som är tillgängliga inom cirka 30 sekunder. Endast tillgängligt för Analytics Premium. Kräver ett sätt att visualisera data, vanligtvis genom ett engagemang från Engineering Services.

## Anpassade lösningar {#custom-solutions}

Tekniktjänster bör användas när

* De andra Adobe-verktygen uppfyller inte dina behov.
* Ni vill ha en anpassad upplevelse.
* Ni vill ha en helautomatiserad lösning.
* Du vill nå många enheter.
* Du har flera datakällor.
* Du har komplexa krav för ETL (Extract-Transform-Load).
* Du vill ha anpassade varumärken.
* Du vill visa [!UICONTROL Analytics Live Stream].
