---
description: Den här hjälpsidan innehåller rekommenderade användningsexempel för varje Adobe Analytics-verktyg. Verktyg bör beaktas i den ordning de anges. Om ett visst verktyg inte uppfyller behovet går du vidare till nästa verktyg för övervägande.
title: Vilket Adobe Analytics-verktyg ska jag använda?
feature: Analytics Basics
exl-id: d65575df-19c6-4129-89c8-d36de7bb6b2f
source-git-commit: 52f7ff8a357cfe80e1f92b4162057da807f44e9d
workflow-type: tm+mt
source-wordcount: '1222'
ht-degree: 2%

---

# Vilket Adobe Analytics-verktyg ska jag använda?

Den här hjälpsidan innehåller rekommenderade användningsexempel för varje Adobe Analytics-verktyg. Verktyg bör beaktas i den ordning de anges. Om ett visst verktyg inte uppfyller behovet går du vidare till nästa verktyg för övervägande.

Mer information om Adobe Analytics produktjämförelser finns på [Analysproduktjämförelse](/help/analyze/get-started/analytics-product-comparison.md).

Här är en video som jämför olika Adobe Analytics-verktyg:

>[!VIDEO](https://video.tv.adobe.com/v/27220/?quality=12)

## Adobe Analytics Reporting-användargränssnitt {#user-interfaces}

**[Analysis Workspace](/help/analyze/analysis-workspace/home.md)** bör vara användargränssnittet för alla dina rapporterings- och analysbehov. Adobe fortsätter att investera i och släppa månadsuppdateringar av den här produkten. Om du inte kan göra något i Analysis Workspace bör du överväga de andra gränssnitten nedan.**

**[Rapporter och analyser](/help/analyze/reports-analytics/overview/report-overview.md)** ska användas:

* Av nybörjare som behöver tillgång till fördefinierade rapporter som är enklare att navigera i.
* Få åtkomst till realtidsdata i användargränssnittet.
* Så här ställer du in kalenderhändelser.
* Så här ställer du in mål.
* Få tillgång till unika videovisualiseringar av Video Daypart och Viewer Drop-off.

>[!IMPORTANT]
>
>Effektivt **31 december 2023** kommer Adobe att upphöra med rapporter och analyser och tillhörande rapporter och funktioner. Då slutar rapporter och analyser och alla rapporter och scheman att fungera. Rapporterna, visualiseringarna och den underliggande tekniken som används i Rapporter och analyser uppfyller inte längre Adobe teknikstandarder. De flesta funktionerna Rapporter och Analytics är tillgängliga i Analysis Workspace. Sedan Analysis Workspace lanserades 2015 har funktionerna och funktionerna i Rapporter och analyser flyttats till Analysis Workspace och en tröskel på arbetsflödets paritet har uppnåtts. Det här meddelandet förklarar processen vid slutet av livscykeln.

**[Data Workbench](https://experienceleague.adobe.com/docs/data-workbench/using/home.html)** ska användas:

* För prediktiv, statistisk modellering (benägenhetsbedömning, klustring, korrelation osv.).
* För fördröjningsanalys (tid före/sedan en händelse).
* För identifiering och export av komplexa segment i hela Adobe Experience Cloud.

>[!IMPORTANT]
>
>Läs mer om Datans Workbench [Meddelande om att produkten är slut](https://experienceleague.adobe.com/docs/data-workbench/using/eol.html?lang=en).


## Importera data till Adobe Analytics {#import}

**[Klassificeringar](/help/components/classifications/c-classifications.md)** ska användas:

* När det finns metadata som du vill koppla till ett samlingsvärde (eVar, prop, marknadsföringskanal)
* Alternativ:

   * Regelbyggaren: använd när du har förutsägbara formaterade värden som samlas in för en variabel, t.ex. avgränsade värden. Med den här metoden kan ni lägga upp regler en gång och i stort sett&quot;skapa och glömma&quot;.
   * Webbläsarimporterare: använd när du inte har några förutsägbara värden eller när du har en begränsad lista med värden som kräver en engångsuppdatering. På så sätt måste du kontinuerligt övervaka klassificeringarna för nya värden.

**[Datakällor](/help/import/data-sources/overview.md)** ska användas:

* När det finns offlinedata vill du skriva permanent till Adobe Analytics
* Alternativ:

   * Sammanfattning: enkel dataöverföring per dag eller begränsade dimensioner
   * Transaktions-ID: dataöverföringar som kopplar en online-slutpunkt till offlinedata och kopplar importerade data till en besökarögonblicksbild som tagits online (t.ex. online-beställningar och returneras offline)
   * Fullständig bearbetning: tidstämplade datakällor, bearbetade som om de hade träffats av Adobe-servrar. Dvs. data infogas direkt i besökarresan.

**[Integreringar med Adobe Exchange](https://www.adobeexchange.com/experiencecloud.html)** ska användas:

* När du kontaktar en tredjepartsleverantör som har skapat en anslutning som stöds av Adobe Analytics. Integreringsappar lägger vanligtvis in data på sammanfattningsnivå i Adobe Analytics permanent och automatiskt, regelbundet.

**[API för datainfogning](/help/import/c-data-insertion-api/c-data-insertion-api.md)** ska användas:

* När du behöver överföra data till Adobe Analytics och inte kan använda Adobe AppMeasurement eller mobil SDK-kod.

**[API för insättning av data i bulk](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/bdia.md)**

* API:t för datainfogning och API:t för datainfogning i grupp är båda metoder för att skicka samlingsdata på serversidan till Adobe Analytics. API-anrop för datainfogning görs en händelse i taget. API för datainfogning i grupp accepterar CSV-formaterade filer som innehåller händelsedata, en händelse per rad. Om du arbetar med en ny implementering av en serversidessamling rekommenderar vi att du använder API:t för datainfogning i grupp.

**[Kundattribut](https://experienceleague.adobe.com/docs/core-services/interface/customer-attributes/attributes.html)** ska användas:

* Om du samlar in företagsdata i en CRM-databas (customer relationship management) och vill överföra data till Experience Cloud.
* Om ni vill använda CRM-data för en djupare analys i Analytics, eller som målinriktningskriterier i Adobe Target.

**[Audience Analytics](/help/integrate/c-audience-analytics/mc-audiences-aam.md)** ska användas:

* Om du vill inkludera Adobe Audience Manager målgruppsdata, t.ex. demografisk information (t.ex. kön eller inkomstnivå), psykografisk information (t.ex. intressen och hobbies), CRM-data eller annonsvisningsdata i ett Analytics-arbetsflöde.
* Om du vill att överförda CRM-data ska vara tidsbaserade, eftersom den här integreringen skickar ny information till Analytics som träffats av en träff.

## Exportera data från Adobe Analytics {#export}

**[Report Builder](/help/analyze/report-builder/home.md)** ska användas:

* Om de anpassade layoutalternativen för arbetsytan är begränsade (allt är möjligt i Report Builder, inom Excel-gränserna).
* För att smidigt knyta indata från användare eller offlinedatakällor (visningar, kostnader) till data från Adobe. En mer permanent lösning för att binda data är datakällor (se Importera data till analys).
* Att sammanfoga data från olika flerdimensionella rapporter (t.ex. en rapport om kampanjavtryck tillsammans med en kampanjrapport för klick-till-konvertering).
* Om du vill sammanfoga data från olika rapportsviter, antingen genom att summera eller visa dem i samma tabell sida vid sida.
* Om automatisering genom schemaläggning önskas (XLSX, XLSM, CSV, PDF, TXT, XML, MHT).

**[Data Warehouse](/help/export/data-warehouse/data-warehouse.md)** ska användas:

* Om du vill få åtkomst till variabler som annars är dolda i användargränssnittet - IP-adress, Experience Cloud-ID, Analytics-besökar-ID, sid-URL)
* Få åtkomst till mer detaljerade data än användargränssnittet (denormaliserad tabellvy)
* Hämta data i ett format som passar för pivottabellindata
* Om klienten vill mata in data från Adobe i ett datavisualiseringsverktyg från tredje part (något summerat och inte på träffnivå)
* För att få åtkomst till alla unika dimensionsobjekt om du kör i&quot;Låg trafik&quot; i Adobe Analytics

**[Analysdatafeed](/help/export/analytics-data-feed/c-df-contents/datafeeds-contents.md)** ska användas:

* För att kunna använda den mest detaljerade datafeed som vi kan tillhandahålla (besökar-ID, tryck).
* Om klienten vill ha Adobe-data lagrade i en klientdatabas, på den mest detaljerade nivå vi kan skicka.
* Om klienten vill utveckla ett verktyg för Business Intelligence (BI) eller mata in data på träffnivå i ett verktyg från tredje part.

**[Rapporterings-API:er](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/reporting-guide.md)** bör användas när de andra visualiseringsalternativen inte uppfyller dina behov. De tre API-alternativen omfattar:

* **Fullt bearbetad**: när du vill ha funktionsrika data (inklusive besök, besökare och segment). Det här är typiska gränssnittsdata från Analytics, som är tillgängliga inom cirka 30-90 minuter. Kan användas via Report Builder.
* **Realtid**: när du vill visa ett par mätvärden och dimensioner med några sekunders fördröjning. Detta är begränsade, delvis bearbetade, sammanfattade data som är tillgängliga inom cirka 30 sekunder. Innehåller unika algoritmer för de flesta populära, vinnare och förlorare. Kan användas via Report Builder.
* **[!UICONTROL Live Stream]**: när ni vill ha en ström av delvis bearbetade analysdata på träffnivå inom sekunder från insamlingen. Detta är delvis bearbetade data som är tillgängliga inom cirka 30 sekunder. Endast tillgängligt för Analytics Premium. Kräver ett sätt att visualisera data, vanligtvis genom ett engagemang från Engineering Services.

## Anpassade lösningar {#custom-solutions}

Tekniktjänster bör användas när

* De andra Adobe-verktygen uppfyller inte dina behov.
* Ni vill ha en anpassad upplevelse.
* Ni vill ha en helautomatiserad lösning.
* Du vill nå många enheter.
* Du har flera datakällor.
* Du har komplexa krav för ETL (Extract-Transform-Load).
* Du vill ha anpassade varumärken.
* Du vill visualisera [!UICONTROL Analytics Live Stream].
