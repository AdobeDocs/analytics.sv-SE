---
description: Det här avsnittet innehåller de viktigaste begreppen för Adobe Analytics, en kort beskrivning av begreppen samt en specifik dokumentationslänk med mer information om ämnet.
title: Adobe Analytics – viktiga begrepp
translation-type: tm+mt
source-git-commit: 4b6107fe57787e639fb06ef957d6230d1bc45bd1
workflow-type: tm+mt
source-wordcount: '2385'
ht-degree: 99%

---


# Adobe Analytics – viktiga begrepp

Det här avsnittet innehåller de viktigaste begreppen för Adobe Analytics, en kort beskrivning av begreppen samt en specifik dokumentationslänk med mer information om ämnet.

## Analytics-verktyg {#concept_833EDD4EB056491DA1BC5A3A45FE285B}

| Produkt | Beskrivning | Dokumentationslänk |
|--- |--- |--- |
| Analysis Workspace | Webbläsarlösning för att skapa stabila, anpassade analysprojekt och demokratisera insikter. Ger större rapportflexibilitet än Reports &amp; Analytics. | [adobe.ly/aaworkspacedocs](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/home.html) |
| Reports &amp; Analytics (tidigare SiteCatalyst) | Webbläsarlösning för rapportering och analys. Startverktyget i Analytics-paketet. | [Reports &amp; Analytics – startsida](https://docs.adobe.com/content/help/en/analytics/analyze/reports-analytics/getting-started.html) |
| Report Builder | Excel-tillägg som gör att du kan skapa anpassade förfrågningar för Adobe Analytics-data och visualisera dem med Microsoft Excel. | [Report Builder – startsida](https://docs.adobe.com/content/help/en/analytics/analyze/report-builder/home.html) |
| Ad Hoc Analysis (tidigare Discover) | Java-baserat verktyg för avancerad digital analys. | [Ad Hoc Analysis – startsida](https://docs.adobe.com/content/help/en/analytics/analyze/ad-hoc-analysis/adhoc-home.html) |
| Data Workbench (tidigare Insight) | Utformat för att samla in, bearbeta, analysera och visualisera data från kundinteraktioner både online och offline över flera kanaler. | [Data Workbench-klient](https://docs.adobe.com/content/help/en/data-workbench/using/client/t-open-ins.html) |
| Data Warehouse | Obearbetade rådata för lagring och anpassade rapporter som du kan köra genom att filtrera data. Inte på träffnivå. | [Data Warehouse – startsida](https://docs.adobe.com/content/help/en/analytics/export/data-warehouse/data-warehouse.html) |
| Adobe Mobile Services | Sammanför funktioner för mobil marknadsföring i mobilappar från hela Adobe Experience Cloud så att ni kan förstå och förbättra användarengagemanget i era appar. | [Mobile Services – startsida](https://docs.adobe.com/content/help/en/mobile-services/using/home.html) |
| Adobe Exchange Data Connectors (tidigare Genesis) | Importera spårningsdata från tredjepartsprogram till Analytics för att ge heltäckande insyn i prestanda på en central plats. | [Data Connectors – startsida](https://marketing.adobe.com/developer/documentation/genesis/c-overview-how-it-works) |
| Dynamic Tag Management (DTM) | Hjälper er att hantera Analytics-, Target- och andra taggar på alla era webbplatser, oavsett hur många domäner ni har. | [DTM – startsida](https://docs.adobe.com/content/help/en/analytics/implementation/implement-analytics-with-dtm/dtm-implementation-overview.html) |
| Adobe Launch | Nästa generation av funktioner för webbplatstaggar och mobil SDK-hantering från Adobe. | [Adobe Launch – startsida](https://docs.adobe.com/content/help/en/launch/using/overview.html) |

## Viktiga termer {#concept_E473ACBB8E4A42B4AC005538AC12F154}

Klicka [här](https://docs.adobe.com/content/help/en/analytics/technotes/terms.html) om du vill se en utökad ordlista över termer i Adobe Analytics.

| Term | Beskrivning | Dokumentationslänk |
|--- |--- |--- |
| Props (anpassad trafik) | Dimensioner som används för att spåra trafikaktiviteter sida för sida. Props lagras inte mellan sidorna. Viktiga tillämpningar av trafikvariabler: <ul><li>Enkelt att räkna ut det ”populäraste” av ett specifikt värde</li><li>Insyn i hur användarna navigerar på webbplatsen </li></ul><br>Exempel på trafikvariabler: Sidnamn, webbplatsavsnitt, webbläsare.</br> | [Props](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/traffic-variables/traffic-var.html) |
| eVar (anpassad konvertering) | Dimensioner som kvarstår under en tidsperiod som du anger. Alternativ för förfallotiden är bland annat att händelse, besök eller X dagar och bör styras av den typ av analys som ska utföras på variabeln.<br>Viktiga skillnader mellan eVars och props:</br><ul><li>Props används ofta för sökvägsanalys eftersom data inte är beständiga.</li><li>eVars används ofta för konverteringsanalys.</li></ul><br>Exempel på konverteringsvariabler: interna sökord, interna kampanjer, externa kampanjer (s.campaign).</br> | [eVars](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/conversion-variables/conversion-var-admin.html) |
| Händelser/mätvärden (s.events) | Mätvärden som mäter viktiga åtgärder som ni vill att besökarna ska utföra på webbplatsen. Det finns tre typer av händelser: Räknare, numeriska värden och valutor. Händelser är mest användbara när de läggs till i rapporter över konverteringsvariabler (eVar). eVar ger kvalitativ information om vad som hände och Event ger kvantitativ information om vad som hände. <br>Viktiga skillnader mellan eVars och händelser:</br><ul><li>eVars berättar vem, vad eller vilket som påverkade konverteringen</li><li>Händelser mäter hur många konverteringar som har skett</li></ul><br>Exempel på konverteringshändelser: beställning, programstart, leads, intäkter.</br> | [Händelser](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/success-events/success-event.html) |
| Komponenter | Dimensioner, mätvärden, segment och tidsdetaljer (datumintervall) som du kan dra och släppa i ett projekt. | [Komponenter](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/components/analysis-workspace-components.html) |
| Dimensioner | Samling av eVars, props, klassificeringar och insamlade Adobe-standardvärden. | [Dimensioner](https://docs.adobe.com/content/help/en/analytics/components/variables/dimensions-reports/reports-descriptions.html) |
| Mätvärden | Samling av implementerade händelser och beräknade mätvärden. | [Mätvärden](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/components/apply-create-metrics.html) |
| Beräknade mätvärden | Förmågan att härleda anpassade mätvärden från befintliga mätvärden som samlats in via implementeringen. | [Beräknade mätvärden](https://docs.adobe.com/content/help/en/analytics/components/calculated-metrics/cm-overview.html) |
| Segment | Förmågan att skapa, hantera, dela och använda kraftfulla, fokuserade målgruppssegment i Analytics-rapporter. Segment delas mellan olika Analytics-produkter och kan delas över hela Experience Cloud. | [Segmentering](https://docs.adobe.com/content/help/en/analytics/components/segmentation/seg-home.html) |
| Tid (datumintervall) | Förmågan att filtrera datum till valfri tidsperiod och skapa anpassade datumintervall som kan återanvändas i analyser. | [Datumintervall](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/components/calendar-date-ranges/calendar.html) |
| Visualiseringar | Detaljerade visualiseringar som skapar liv i era projekt. | [Visualiseringar](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.html) |
| Insamling | Förmågan att begränsa vilka komponenter som är tillgängliga i ett projekt eller Virtual Report Suite. | [VRS-insamling](https://docs.adobe.com/content/help/en/analytics/components/virtual-report-suites/vrs-components.html)<br>[Projektinsamling](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/curate-share/curate.html)</br><br>[jämförelse](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/curate-share/curate-projects-vrs.html) |

## Viktiga rapporter

| Rapport | Beskrivning | Dokumentationslänk |
|--- |--- |--- |
| Fullständig lista över dimensioner/rapporter | Definition av alla dimensioner/rapporter som är tillgängliga i Adobe Analytics. | [Dimensioner](https://docs.adobe.com/content/help/en/analytics/components/variables/c-variables.html) |
| Advertising Analytics | Analysera alla dina betalda Google- och Bing-sökdata sida vid sida i Adobe Analytics. Dimensioner som skapas genom integreringen är annonsplattform, sökord, matchningstyp osv. Mätvärden som skapas är AMO Impressions, AMO Clicks, AMO Cost, Avg. Position och Avg. Quality Score. | [Advertising Analytics](https://docs.adobe.com/help/en/analytics/integration/advertising-analytics/overview.html) |
| Audience Analytics | Utöka inkommande Analytics-träffar med användarens målgruppstillhörighet i AAM. Ni kan inkludera AAM-målgruppsdata som demografisk information (t.ex. kön eller inkomstnivå), psykografisk information (t.ex. intressen och hobbies), CRM-data och annonsvisningsdata i alla Analytics-arbetsflöden. Dimensioner som skapas genom den här integreringen är Audience ID och Audience Name. | [Audience Analytics](https://docs.adobe.com/content/help/en/analytics/integration/audience-analytics/mc-audiences-aam.html) |
| Attribution IQ | Gör att ni kan förstå hur betydelsefulla interaktioner skapas under hela kundresan och på ett intelligent sätt identifiera inflexionspunkter som leder kunderna till önskade resultat vilket optimerar marknadsföringsinitiativen på ett effektivt sätt. Modellerna omfattar första, sista, linjära, deltagande, j-formade, omvända j-formade, u-formade, samma gest, anpassad och tidsfördröjning. | [Attribution IQ](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/panels/attribution.html) |
| Avvikelseidentifiering | En statistisk metod för att fastställa hur ett givet mätvärde har ändrats i förhållande till tidigare data. AD är aktiverat som standard för alla trendvisualiseringar i Analysis Workspace. | [Avvikelseidentifiering](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/virtual-analyst/anomaly-detection/anomaly-detection.html) |
| Bidragsanalys | Utforskar anledningen till avvikelser som uppstår genom att köra en automatiserad analys av varje enskilt mätvärde och dimension som du har tillgång till. | [Bidragsanalys](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/virtual-analyst/contribution-analysis/ca-tokens.html) |
| Kohortanalys | En kohort är en grupp personer som delar gemensamma egenskaper under en angiven period. Kohortanalyser hjälper er att analysera kundlojalitet och bortfall hos era användare. | [Kohortanalys](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/visualizations/cohort-table/cohort-analysis.html) |
| Customer Journey-rapporter | Visar information om den väg som användarna tar genom webbplatsen eller appen. Prop, eVars och händelser kan användas i den här analysen i Analysis Workspace. | [Analysis Workspace utfall](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/visualizations/fallout/fallout-flow.html)[Analysis Workspace-flöde](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/visualizations/flow/flow.html)[Reports &amp; Analytics-vägar](https://docs.adobe.com/content/help/en/analytics/components/variables/dimensions-reports/reports-paths.html) |
| Marknadsföringskanaler | Rapporter som visar vilka externa kanaler som driver användare till er webbplats och vilka som är mest effektiva när det gäller konvertering. Vyer för första och sista kontaktpunkt finns. Det här är den rekommenderade rapporten för externa trafikkällor i Adobe Analytics (i stället för Campaigns eller Traffic Sources) eftersom den ger den mest omfattande översikten över både betalda och organiska kanaler. | [Marknadsföringskanaler](https://docs.adobe.com/content/help/en/analytics/components/marketing-channels/c-getting-started-mchannel.html) |
| Mobil | Visar information om webbplatser som öppnas via en mobil enhet eller surfplatta. | [Mobilrapport](https://docs.adobe.com/content/help/en/analytics/components/variables/dimensions-reports/reports-mobile.html) |
| Mobilapp | Visar grundläggande användningsinformation om mobilappar. Rapporterna är tillgängliga när vår SDK har implementerats och rapportering är aktiverat.  Dessutom har Adobe Mobile Services skapat ett separat mobilappsgränssnitt som ger mer omfattande appdata så att ni kan förstå och förbättra användarengagemanget i era appar.  Gå till gränssnittet [här](https://mobilemarketing.adobe.com). | [Adobe Mobile Services](https://docs.adobe.com/content/help/en/mobile-services/using/home.html) | Produkter | Identifierar hur enskilda produkter och grupper av produkter (kategorier) bidrar till olika konverteringsvärden, som intäkter eller utcheckningar. | [Produktrapport](https://docs.adobe.com/content/help/en/analytics/components/variables/dimensions-reports/reports-products.html) |
| Segmentjämförelse | Identifierar de statistiskt mest signifikanta skillnaderna mellan segment genom en automatiserad analys av alla mätvärden och dimensioner du har tillgång till. | [Segmentjämförelse](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/panels/segment-comparison/segment-comparison.html) |
| Webbplatsinnehållsrapport | Visar information om vilka sidor och områden på webbplatsen som är mest aktiva och vilka servrar som används mest. | [Webbplatsinnehållsrapport](https://docs.adobe.com/content/help/en/analytics/components/variables/dimensions-reports/reports-site-content.html) |
| Site Metrics-rapport | Visar kvantitativ information om er webbplats, t.ex. unika besökare, beställningar, intäkter osv. Varje mätvärde kan användas i andra objektbaserade rapporter. | [Site Metrics-rapport](https://docs.adobe.com/content/help/en/analytics/components/variables/dimensions-reports/reports-site-metrics.html) |
| Besökarprofil | Rapporter som hjälper dig att se köpmönster för kunder från olika profilkategorier, bland annat länder, delstater, postnummer och domäner. | [Besökarprofil](https://docs.adobe.com/content/help/en/analytics/components/variables/dimensions-reports/reports-visitor-profile.html) |
| Kvarhållning av besökare | Visar information om kundlojalitet, t.ex. hur många och hur ofta besökare återvänder till er webbplats. | [Kvarhållning av besökare](https://docs.adobe.com/content/help/en/analytics/components/variables/dimensions-reports/reports-visitor-retention.html) |
| Länka, dela och schemalägga projekt | Metoder för att spara och/eller dela arbete med andra i Analytics-gränssnittet. | [Skicka och schemalägg filer](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/curate-share/send-schedule-files.html) |

## Nyckeltal {#concept_392819DC275C48688E2CE4ABD4C5EE43}

| Mätvärdets namn | Definition | Dokumentationslänk |
|---|---|---|
| Fullständig lista över mätvärden | Definition av alla mätvärden i Adobe Analytics. | [Översikt över mätvärden](https://docs.adobe.com/content/help/en/analytics/components/variables/metrics/metrics-overview.html) |
| Unika besökare | Antalet unika besökare på webbplatsen under en angiven tidsperiod. | [Unika besökare](https://docs.adobe.com/content/help/en/analytics/components/variables/dimensions-reports/reports-unique-visitors-v15-dsc.html) |
| Besök | En sekvens med sidvisningar under en session. Besöket börjar när en person tittar på en sida på webbplatsen för första gången och slutar efter 30 minuters inaktivitet. | [Besök](https://docs.adobe.com/content/help/en/analytics/components/variables/metrics/metrics-visit.html) |
| Sidvisningar | En sidvisning registreras när en besökare visar en sida på webbplatsen. | [Sidvisningar](https://docs.adobe.com/content/help/en/analytics/components/variables/metrics/metrics-page-view.html) |
| Instanser | Antalet gånger som en variabel har definierats. Varje gång Adobe Analytics identifierar ett värde i en variabel ökas instanserna med en i respektive rapport. | [Instanser](https://docs.adobe.com/content/help/en/analytics/components/variables/metrics/metrics-instance.html) |
| Förekomster | Antalet gånger en variabel definierades eller lagrades. | [Förekomster](https://docs.adobe.com/content/help/en/analytics/components/variables/metrics/metrics-occurrences.html) |

## Importalternativ {#concept_7C6DF03B5F9149E2A77F36C739432059}

| Alternativ | Beskrivning | Dokumentationslänk |
|---|---|---|
| Classification Importer | Importera metadata för insamlade dimensioner via webbläsare eller FTP-överföring. Manuell metod jämfört med Rule Builder. | [Classification Importer](https://docs.adobe.com/content/help/en/analytics/components/classifications/classifications-importer/c-working-with-saint.html) |
| Rule Builder | Skapa metadataklassificeringar av dimensioner automatiskt baserat på användardefinierade regler. | [Classification Rule Builder](https://docs.adobe.com/content/help/en/analytics/components/classifications/classifications-rulebuilder/classification-rule-builder.html) |
| Kundattribut | CRM-data överförda till Experience Cloud för användning i Adobe Analytics och Adobe Target. | [Kundattribut](https://docs.adobe.com/content/help/en/core-services/interface/customer-attributes/attributes.html) |
| Datakällor | Importera offlinemätvärden i Analytics efter dimensioner eller helt enkelt efter dag. | [Datakällor](https://docs.adobe.com/content/help/en/analytics/import/data-sources/datasrc-home.html) |
| Adobe Exchange Data Connectors | Se [Analytics-verktyg.](/help/landing/an-key-concepts.md) |  |
| Inbyggda integreringar | Audience Analytics och Advertising Analytics. | Se avsnittet Viktiga rapporter. |

## Exportalternativ {#concept_C62B688E259141CF92C048E8110464BE}

| Alternativ | Beskrivning | Dokumentationslänk |
|---|---|---|
| Nedladdning och schemaläggning av användargränssnitt | Exportera data från Analysis Workspace som CSV eller PDF. | [Hämta PDF- eller CSV-filer](/help/analyze/analysis-workspace/curate-share/download-send.md) |
| Report Builder | Se Analytics-verktyg. |
| API för Analytics | Skapa egna frågor för Analytics-data. | <ul><li>[API 2.0](https://www.adobe.io/apis/experiencecloud/analytics/docs.html)</li><li>[API 1.4](https://github.com/AdobeDocs/analytics-1.4-apis)</li></ul> |
| Data Warehouse | Se Analytics-verktyg. |  |
| Datafeed i Analytics | Det mest detaljerade sättet att hämta data från Analytics. Konfigurera en feed på träffnivå med Analytics. | [Analytics-datafeed](https://docs.adobe.com/content/help/en/analytics/export/analytics-data-feed/data-feed-overview.html) |

## Datainsamling och validering {#concept_E07350D4CA5047DAA7D81F762F29606A}

| Metod/resurs | Beskrivning | Dokumentationslänk |
|--- |--- |--- |
| Resurser för utvecklare | Dokumentation som visar vilka bibliotek som är tillgängliga för att samla in Analytics-data på alla tillgängliga plattformar (webb, mobilapp, video, flash osv.) | [Utvecklardokument](https://www.adobe.io/apis/experiencecloud/analytics/docs.html) |
| Implementeringshandbok | En beskrivning av datainsamlingsvariabler och detaljer om hur ni implementerar datainsamlingskod i JavaScript. | [Implementeringshandbok](https://docs.adobe.com/content/help/en/analytics/implementation/home.html) |
| Appmätning (s_code) | Global variabelhantering. | [AppMeasurement](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/appmeasurement-js/appmeasure-mjs.html) |
| App-SDK:er | Anpassat paket som innehåller en förifylld version av konfigurationsfilen för appar. | <ul><li>[iOS](https://docs.adobe.com/content/help/en/mobile-services/ios/overview.html)</li><li>[Android](https://docs.adobe.com/content/help/en/mobile-services/android/getting-started-android/requirements.html)</li></ul> |
| DTM och Adobe Launch | Se Analytics-verktyg. |  |
| VISTA | Gör att ni kan använda logik på serversidan för att ändra eller segmentera data som samlas in. | [VISTA-regler](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/processing-rules/processing-rules-configuration/processing-rule-order.html) |
| Bearbetningsregler | Förmågan att ange, ändra och kopiera variabler i Analytics-gränssnittet för att ändra data som samlas in. | [Bearbetningsregler](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/processing-rules/processing-rules.html) |
| Felsökningsalternativ | Det finns flera felsökare och paketanalysatorer som kan hjälpa er att validera implementeringen, inklusive Adobe Experience Cloud-felsökaren. | [Adobe Debugger](https://chrome.google.com/webstore/detail/adobe-experience-cloud-de/ocdmogmohccmeicdhlhhgepeaijenapj?hl=sv) |
| API för datainfogning | API:t för datainfogning är en mekanism för datainsamling på serversidan och överföring till Experience Cloud-servrar. I stället för att använda JavaScript-beacons på varje webbsida för att överföra besöksdata till Experience Cloud-servrarna, samlar serversidan in data som enbart baseras på webbläsarfrågor och webbserversvar. | [Steg för att implementera API för infogning av Adobe Analytics-data med POST](https://helpx.adobe.com/se/analytics/kb/data-insertion-api-post-method-adobe-analytics.html) |
