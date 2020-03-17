---
description: Den här hjälpsidan innehåller rekommenderade användningsexempel för varje Adobe Analytics-verktyg. Verktyg bör beaktas i den ordning de anges. Om ett visst verktyg inte uppfyller behovet går du vidare till nästa verktyg för övervägande.
title: Vilket Adobe Analytics-verktyg ska jag använda?
uuid: 1179e49d-3cfc-4abd-a8eb-35c5ae380c16
translation-type: tm+mt
source-git-commit: b4e17f7aad73af250c89cb8117f741f7eed89b7e

---


# Vilket Adobe Analytics-verktyg ska jag använda?

Den här hjälpsidan innehåller rekommenderade användningsexempel för varje Adobe Analytics-verktyg. Verktyg bör beaktas i den ordning de anges. Om ett visst verktyg inte uppfyller behovet går du vidare till nästa verktyg för övervägande.

Mer information om produktjämförelser i Adobe Analytics finns [här](/help/admin/c-analytics-product-comparison/analytics-product-comparison.md).

## Användargränssnitt för Adobe Analytics Reporting {#section_8265460EBB47405AB19A3B2B0729C8A4}

**[Analysis Workspace](/help/analyze/analysis-workspace/analysis-workspace-features.md)**ska vara användargränssnittet för alla dina rapporterings- och analysbehov. Adobe fortsätter att investera i och släppa månadsuppdateringar av den här produkten. Om det finns en uppgift som du inte kan utföra i Analysis Workspace bör du överväga de andra gränssnitten nedan.**

**[Rapporter och analyser](/help/analyze/reports-analytics/overview/report-overview.md)**ska användas:

* Av nybörjare som behöver tillgång till fördefinierade rapporter som är enklare att navigera i.
* För att förstå Target-aktivitet (Analytics for Target/A4T) och öka förtroendet.
* Få åtkomst till realtidsdata i användargränssnittet.
* Så här ställer du in kalenderhändelser.
* Så här ställer du in mål.
* Så här visar du Bot-rapportering.
* Om du vill titta på flera rapportsviter på en enda kontrollpanel för användargränssnittet.
* För att få tillgång till unika videovisualiseringar av Concurrent Viewer, Video Daypart och Viewer Drop-off.
* För att utnyttja publiceringslistor i schemalagda rapporter.

**[Användargränssnittet](https://docs.adobe.com/content/help/en/mobile-services/using/home.html)**för mobiltjänster ska användas:

* Om du vill ha en vy över data i mobilappen separat.
* Så här hanterar du implementeringen av din SDK för mobilappar.
* För att konfigurera mobilannonsering, till exempel meddelanden i appen, push-meddelanden och positionering.
* Om mer interaktiva visualiseringar önskas för appdata (Sunburst).
* Så här visualiserar du intressepunkter på en karta.
* För livstidsvärden.

**[Ad hoc-analys](/help/analyze/ad-hoc-analysis/adhoc-home.md)**ska användas:

* Exportera 50 000 datarader
* Om du vill ha en tabbordning för projektarbete.
* Så här använder du platsanalysrapporten (rapport om 3D-målning).

**[Data Workbench](https://docs.adobe.com/content/help/en/data-workbench/using/home.html)**ska användas:

* Det mest flexibla analysverktyget (ned till besökarnivå, träffnivåanalys).
* Skapa en flerkanalig datauppsättning med online- och offlineinteraktioner från CRM till POS till Web.
* För avancerad attribuering (regelbaserade och algoritmiska modeller).
* För prediktiv, statistisk modellering (benägenhetsbedömning, klustring, korrelation osv.).
* För fördröjningsanalys (tid före/sedan en händelse).
* För identifiering och export av komplexa segment i hela Adobe Experience Cloud.

## Importera data till Adobe Analytics {#section_B42B998D6E3E4357B024AEFA4EC69A23}

**[Klassificeringar](/help/components/c-classifications2/c-classifications.md)**bör användas:

* När det finns metadata som du vill koppla till ett samlingsvärde (eVar, prop, marknadsföringskanal)
* Alternativ:

   * Regelverktyget: används när du har förutsägbara formaterade värden som samlas in för en variabel, t.ex. avgränsade värden. Med den här metoden kan ni lägga upp regler en gång och i stort sett&quot;skapa och glömma&quot;.
   * Webbläsarimporterare: används när du inte har några förutsägbara värden eller när du har en begränsad lista med värden som kräver en engångsuppdatering. På så sätt måste du kontinuerligt övervaka klassificeringarna för nya värden.

**[Datakällor](/help/import/c-data-sources/datasrc-home.md)**ska användas:

* När det finns offlinedata vill du ha permanent inskriven i Adobe Analytics
* Alternativ:

   * Sammanfattning: enkel dataöverföring per dag eller begränsade dimensioner
   * Transaktions-ID: överföring av data som kopplar en online-slutpunkt till offlinedata och kopplar importerade data till en besökarögonblicksbild som tagits online (t.ex. online-beställningar och returneras offline)
   * Fullständig bearbetning: tidstämplade datakällor, bearbetade som om de vore en träff som samlats in av Adobes servrar. Dvs. data infogas direkt i besökarresan.

**[Dataanslutningar](https://www.adobeexchange.com/experiencecloud.html)(tidigare Genesis)**ska användas:

* När ni kontaktar en tredjepartsleverantör som har skapat en anslutning som stöds med Adobe Analytics. Data Connectors lägger vanligtvis in data på sammanfattningsnivå i Adobe Analytics permanent och automatiskt, regelbundet.

**[API](https://marketing.adobe.com/developer/documentation/data-insertion/c-data-insertion-api)**för datainmatning ska användas:

* När du behöver överföra data till Adobe Analytics, och inte kan använda Adobe AppMeasurement eller mobil SDK-kod.

**[Kundattribut](/help/components/c-variables/dimensionslist/reports-customer-attributes.md)**ska användas:

* Om du samlar in företagsdata i en CRM-databas (customer relationship management) och vill överföra data till Experience Cloud.
* Om ni vill använda CRM-data för en djupare analys i Analytics, eller som målinriktningskriterier i Adobe Target.

**[Målgruppsanalys](/help/integrate/c-audience-analytics/mc-audiences-aam.md)**ska användas:

* Om du vill inkludera målgruppsdata från Adobe Audience Manager (AAM), t.ex. demografisk information (t.ex. kön eller inkomstnivå), psykografisk information (t.ex. intressen och hobbies), CRM-data eller annonsvisningsdata i ett Analytics-arbetsflöde.
* Om du vill att överförda CRM-data ska vara tidsbaserade, eftersom den här integreringen skickar ny information till Analytics som träffats av en träff.

## Exportera data från Adobe Analytics {#section_901C06ABF2014E92B2952906723DF235}

**[Report Builder](/help/analyze/report-builder/home.md)**ska användas:

* Om de anpassade layoutalternativen för arbetsytan är begränsade (allt är möjligt i Report Builder, inom Excel-gränserna).
* Lättare att knyta indata från användare eller offlinedatakällor (visningar, kostnader) till Adobe-data. En mer permanent lösning för att binda data är datakällor (se Importera data till analys).
* Att sammanfoga data från olika flerdimensionella rapporter (t.ex. en rapport om kampanjavtryck tillsammans med en kampanjrapport för klick-till-konvertering).
* Om du vill visa flera rapporter samtidigt.
* Om automatisering genom schemaläggning önskas (XLSX, XLSM, CSV, PDF, TXT, XML, MHT).

**[Datalagret](/help/export/data-warehouse/data-warehouse.md)**ska användas:

* Om du vill få åtkomst till variabler som annars är dolda i användargränssnittet - IP-adress, Experience Cloud-ID, Analytics-besökar-ID, sid-URL)
* Få åtkomst till mer detaljerade data än användargränssnittet (denormaliserad tabellvy)
* Hämta data i ett format som passar för pivottabellindata
* Om kunden vill lägga in Adobe-data i ett datavisualiseringsverktyg från tredje part (något sammanfattande, inte på träffnivå)
* Få åtkomst till alla unika dimensionsvärden om du kör i&quot;Låg trafik&quot; i Adobe Analytics

**[Analysdatafeed](/help/export/analytics-data-feed/c-df-contents/datafeeds-contents.md)**ska användas:

* För att kunna använda den mest detaljerade datafeed som vi kan tillhandahålla (besökar-ID, tryck).
* Om kunden vill ha Adobe-data lagrade i en databas på klientsidan, på den mest detaljerade nivå vi kan skicka.
* Om kunden vill utveckla ett Business Intelligence-verktyg (BI) eller lägga in data på hög nivå i ett tredjepartsverktyg.

**[Rapporterings-API](https://marketing.adobe.com/developer/get-started/introduction/c-introduction)**bör användas när de andra visualiseringsalternativen inte uppfyller dina behov. De tre API-alternativen omfattar:

* **Fullt bearbetad**: när ni vill ha funktionsrika data (inklusive besök, besökare och segment). Det här är typiska gränssnittsdata från Analytics, som är tillgängliga inom cirka 30-90 minuter. Kan användas med Report Builder.
* **Realtid**: när du vill visa ett par mätvärden och dimensioner med några sekunders fördröjning. Detta är begränsade, delvis bearbetade, sammanfattade data som är tillgängliga inom cirka 30 sekunder. Innehåller unika algoritmer för de flesta populära, vinnare och förlorare. Kan användas med Report Builder.
* **[!UICONTROL Live Stream]**: när ni vill ha en ström av delvis bearbetade analysdata på träffnivå inom sekunder från insamlingen. Detta är delvis bearbetade data som är tillgängliga inom cirka 30 sekunder. Endast tillgängligt för Analytics Premium. Kräver ett sätt att visualisera data, vanligtvis genom ett engagemang från Engineering Services.

## Anpassade lösningar {#section_4A212F26A15947599DFB0399A0440CB6}

Tekniktjänster bör användas när

* De andra Adobe-verktygen uppfyller inte dina behov.
* Ni vill ha en anpassad upplevelse.
* Ni vill ha en helautomatiserad lösning.
* Du vill nå många enheter.
* Du har flera datakällor.
* Du har komplexa krav för ETL (Extract-Transform-Load).
* Du vill ha anpassade varumärken.
* Du vill visualisera [!UICONTROL Analytics Live Stream].
