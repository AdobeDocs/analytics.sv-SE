---
description: Det här avsnittet innehåller de viktigaste begreppen för Adobe Analytics, en kort beskrivning av konceptet och en specifik dokumentationslänk med ytterligare information om ämnet.
title: Adobe Analytics - viktiga begrepp
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Adobe Analytics - viktiga begrepp

Det här avsnittet innehåller de viktigaste begreppen för Adobe Analytics, en kort beskrivning av konceptet och en specifik dokumentationslänk med ytterligare information om ämnet.

## Analysverktyg {#concept_833EDD4EB056491DA1BC5A3A45FE285B}

| Produkt | Beskrivning | Dokumentationslänk |
|--- |--- |--- |
| Analysis Workspace | Webbläsarlösning för att skapa stabila, anpassade analysprojekt och demokratisera insikter. Ger större rapportflexibilitet än rapporter och analyser | [adobe.ly/aaworkspacedocs](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/analysis-workspace-features.html) |
| Rapporter och analyser (tidigare SiteCatalyst) | Webbläsarlösning för rapportering och analys. Startverktyget i Analytics-paketet. | [Rapporter och analyser - startsida](https://docs.adobe.com/content/help/en/analytics/analyze/reports-analytics/getting-started.html) |
| Report Builder | Excel-tillägg som gör att du kan skapa anpassade förfrågningar från Adobe Analytics-data och visualisera dem med Microsoft Excel. | [Report Builder - startsida](https://docs.adobe.com/content/help/en/analytics/analyze/report-builder/home.html) |
| Ad hoc-analys (tidigare Discover) | Java-baserat verktyg för avancerad digital analys. | [Ad Hoc Analysis - startsida](https://docs.adobe.com/content/help/en/analytics/analyze/ad-hoc-analysis/adhoc-home.html) |
| Data Workbench (tidigare Insight) | Utformad för att samla in, bearbeta, analysera och visualisera data från kundinteraktioner både online och offline över flera kanaler. | [Data Workbench-klient](https://marketing.adobe.com/resources/help/en_US/insight/client/) |
| Datalager | Rådata, obearbetade data för lagring och anpassade rapporter som du kan köra genom att filtrera data. Inte träffnivå. | [Datalagrets startsida](https://docs.adobe.com/content/help/en/analytics/export/data-warehouse/data-warehouse.html) |
| Adobe Mobile Services | Sammanför funktioner för mobilmarknadsföring för mobilappar från hela Adobe Experience Cloud, så att ni kan förstå och förbättra användarengagemanget med era program. | [Mobiltjänster - startsida](https://docs.adobe.com/content/help/en/mobile-services/using/home.html) |
| Adobe Exchange Data Connectors (tidigare Genesis) | Importera spårningsdata från tredjepartsprogram till Analytics för att ge heltäckande insyn i prestanda på en central plats. | [Data Connectors - startsida](https://marketing.adobe.com/developer/documentation/genesis/c-overview-how-it-works) |
| Dynamic Tag Management (DTM) | Hjälper er att hantera era Analytics-, Target- och andra taggar på alla era webbplatser, oavsett hur många domäner ni har. | [DTM - startsida](https://docs.adobe.com/content/help/en/analytics/implementation/implement-analytics-with-dtm/dtm-implementation-overview.html) |
| Adobe Launch | Nästa generation av funktioner för webbplatstagg och mobil SDK-hantering från Adobe. | [Adobe Launch - startsida](https://docs.adobe.com/content/help/en/launch/using/overview.html) |

## Nyckelterminologi {#concept_E473ACBB8E4A42B4AC005538AC12F154}

Klicka [här](https://docs.adobe.com/content/help/en/analytics/technotes/terms.html) om du vill se en utökad ordlista över villkoren i Adobe Analytics.

| Villkor | Beskrivning | Dokumentationslänk |
|--- |--- |--- |
| Props (anpassad trafik) | Dimensioner som används för att spåra trafik sida vid sida. Profilerna finns inte mellan sidorna. Viktiga tillämpningar av trafikvariabler: <ul><li>Enkelt att räkna för att hitta &#39;populäraste&#39; av ett specifikt värde</li><li>Synlighet i hur användarna målar på webbplatsen </li></ul><br>Exempel på trafikvariabler: Sidnamn, webbplatsavsnitt, webbläsare</br> | [Props](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/traffic-variables/traffic-var.html) |
| eVar (anpassad konvertering) | Dimensioner som kvarstår under en tidsperiod som du anpassar. Förfallotiden omfattar bland annat att händelsen förfaller, besök förfaller eller X-dagars förfaller och bör styras av den typ av analys som ska utföras på variabeln.<br>Viktiga skillnader mellan eVars och props:</br><ul><li>Props används ofta för målningsanalys eftersom beständighet tas bort.</li><li>eVars används ofta för konverteringsanalys.</li></ul><br>Exempel på konverteringsvariabler: Interna sökvillkor, interna kampanjer, externa kampanjer (s.campaign)</br> | [eVars](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/conversion-variables/conversion-var-admin.html) |
| Händelser/mått (s.events) | Mätvärden som mäter viktiga åtgärder som vi vill att våra besökare ska utföra på vår webbplats. Det finns tre typer av händelser: Räknare, numeriska värden och valutor. Händelser är mest användbara när de läggs till i konverteringsvariabelrapporter (eVar). eVar ger kvalitativ information om vad som hände och Event ger kvantitativ information om vad som hände. <br>Viktiga skillnader mellan eVars och händelser:</br><ul><li>eVars berättar vilka, vad eller vilka som påverkade konverteringen</li><li>Händelser mäter hur många konverteringar som har gjorts</li></ul><br>Exempel på konverteringshändelser: Order, Application Starts, Leads, Revenue.</br> | [Händelser](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/success-events/success-event.html) |
| Komponenter | Dimensioner, mätvärden, segment och tidsdetaljer (datumintervall) som du kan dra och släppa i ett projekt. | [Komponenter](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/components/analysis-workspace-components.html) |
| Dimensioner | Samling av eVars, props, klassificeringar och insamlade värden från Adobe. | [Dimensioner](https://docs.adobe.com/content/help/en/analytics/components/variables/dimensions-reports/reports-descriptions.html) |
| Mått | Samling av implementerade händelser och beräknade värden. | [Mått](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/components/apply-create-metrics.html) |
| Beräknade mått | Möjlighet att härleda anpassade mätvärden från befintliga mätvärden som samlats in genom er implementering. | [Beräknade mått](https://docs.adobe.com/content/help/en/analytics/components/calculated-metrics/cm-overview.html) |
| Segment | Möjlighet att skapa, hantera, dela och tillämpa kraftfulla, fokuserade målgruppssegment i era Analytics-rapporter. Segment delas mellan olika Analytics-produkter och kan delas över hela Experience Cloud. | [Segmentering](https://docs.adobe.com/content/help/en/analytics/components/segmentation/seg-home.html) |
| Tid (datumintervall) | Möjlighet att filtrera datum till valfri tidsperiod och skapa anpassade datumintervall som kan återanvändas i analysen. | [Datumintervall](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/components/calendar-date-ranges/calendar.html) |
| Visualiseringar | Omfattande bildkvalitet som kan ge liv åt data i dina projekt. | [Visualiseringar](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.html) |
| Kuration | Möjlighet att begränsa vilka komponenter som är tillgängliga i ett projekt eller i Virtual Report Suite. | [VRS-](https://docs.adobe.com/content/help/en/analytics/components/virtual-report-suites/vrs-components.html)<br>[kurationProject](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/curate-share/curate.html)</br><br>[curationComparison](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/curate-share/curate-projects-vrs.html) |

## Viktiga rapporter

| Rapport | Beskrivning | Dokumentationslänk |
|--- |--- |--- |
| Full Dimensions/Reports List | Definition av alla dimensioner/rapporter som är tillgängliga i Adobe Analytics. | [Dimensioner](https://marketing.adobe.com/resources/help/en_US/reference/reports_descriptions.html) |
| Reklamanalys | Analysera alla dina Google- och Bing-betalsökdata sida vid sida, inifrån Adobe Analytics. Dimensioner som skapas genom integreringen är Ad Platform, Keyword, Match Type osv. Mätvärden som skapas är AMO Impressions, AMO Clicks, AMO Cost, Avg. Position och medel. Kvalitetspoäng. | [Reklamanalys](https://docs.adobe.com/help/en/analytics/integration/advertising-analytics/overview.html) |
| Målgruppsanalys | Berika inkommande Analytics-träffar med en användares målgruppsmedlemskap i AAM. kan ni införliva AAM-målgruppsdata som demografisk information (t.ex. kön eller inkomstnivå), psykografisk information (t.ex. intressen och hobbies), CRM-data och annonsvisningsdata i alla Analytics-arbetsflöden. Dimensioner som skapas genom den här integreringen är Audience ID och Audience Name. | [Målgruppsanalys](https://docs.adobe.com/content/help/en/analytics/integration/audience-analytics/mc-audiences-aam.html) |
| Attributions-IQ | Gör det möjligt för er att förstå hur meningsfullt engagemang sker under hela kundresan och på ett intelligent sätt identifiera inflationspunkter som leder kunderna till målresultat och optimera marknadsföringsinitiativen på ett effektivt sätt. Modellerna omfattar första, sista, linjära, deltagande, j-formade, omvänd j-formade, u-form, samma beröring, anpassad och tidsfördröjning. | [Attributions-IQ](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/panels/attribution.html) |
| Analysidentifiering | En statistisk metod för att fastställa hur ett givet mätvärde har ändrats i förhållande till tidigare data. AD är aktiverat som standard för alla visualiseringar som trendas i Analysis Workspace. | [Analysidentifiering](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/virtual-analyst/anomaly-detection/anomaly-detection.html) |
| Bidragsanalys | Utforskar varför-avvikelserna som inträffar genom att köra en automatiserad analys av varje enskilt mått och dimension som du har tillgång till. | [Bidragsanalys](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/virtual-analyst/contribution-analysis/ca-tokens.html) |
| Kohortanalys | En kohort är en grupp personer som delar gemensamma egenskaper under en angiven period. Kohortanalyser hjälper er att analysera kundlojalitet och bortfall hos era användare. | [Kohortanalys](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/visualizations/cohort-table/cohort-analysis.html) |
| Kundreserapporter | Visar information om den sökväg som användarna tar genom webbplatsen eller appen. Prop, eVars och händelser kan användas i den här analysen i Analysis Workspace. | [Analysis Workspace](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/visualizations/fallout/fallout-flow.html)[FalloutAnalysis Workspace](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/visualizations/flow/flow.html)[FlowReports &amp; Analytics-panel](https://docs.adobe.com/content/help/en/analytics/components/variables/dimensions-reports/reports-paths.html) |
| Marknadsföringskanaler | Rapporter som hjälper dig att lära dig vilka externa kanaler som driver användare till er webbplats och vilka som är mest effektiva när det gäller konvertering. Vyer för första och sista beröringsattribuering tillhandahålls. Det här är den föredragna externa trafikkällrapporten i Adobe Analytics (i stället för Campaigns eller Traffic Sources) eftersom den är den mest omfattande looken för både betalda och organiska kanaler. | [Marknadsföringskanaler](https://docs.adobe.com/content/help/en/analytics/components/marketing-channels/c-getting-started-mchannel.html) |
| Mobil | Visar information om webbplatser som du kommer åt från en mobil enhet eller surfplatta. | [Mobilrapport | (https://docs.adobe.com/content/help/en/analytics/components/variables/dimensions-reports/reports-mobile.html) |
| Mobilapp | Visar grundläggande användningsinformation om dina mobilappar. Rapporterna är tillgängliga när SDK har implementerats och rapportering är aktiverat.  Dessutom har Adobe Mobile Services skapat ett separat mobilappsgränssnitt som ger mer omfattande appdata så att ni kan förstå och förbättra användarinteraktionen med era appar.  Gå till gränssnittet [här](https://mobilemarketing.adobe.com). | [Adobe Mobile Services](https://docs.adobe.com/content/help/en/mobile-services/using/home.html) | Produkter | Identifierar hur enskilda produkter och grupper av produkter (kategorier) bidrar till dina olika konverteringsvärden, som Intäkter eller Utcheckningar. | [Produkter - rapport](https://docs.adobe.com/content/help/en/analytics/components/variables/dimensions-reports/reports-products.html) |
| Segmentjämförelse | Identifierar de mest statistiskt signifikanta skillnaderna mellan segment genom en automatiserad analys av alla mätvärden och dimensioner du har tillgång till. | [Segmentjämförelse](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/panels/segment-comparison/segment-comparison.html) |
| Webbplatsinnehållsrapport | Visar information om vilka sidor och områden på platsen som är mest aktiva och vilka servrar som används mest. | [Webbplatsinnehållsrapport](https://docs.adobe.com/content/help/en/analytics/components/variables/dimensions-reports/reports-site-content.html) |
| Site Metrics-rapport | Visa kvantitativ information om din webbplats, t.ex. unika besökare, beställningar, intäkter osv. Varje mätvärde kan placeras i andra objektbaserade rapporter. | [Site Metrics-rapport](https://docs.adobe.com/content/help/en/analytics/components/variables/dimensions-reports/reports-site-metrics.html) |
| Besökarprofil | Rapporter som hjälper dig att se köpmönster för kunder från olika profilkategorier, inklusive länder, delstater, postnummer och domäner. | [Besökarprofil](https://docs.adobe.com/content/help/en/analytics/components/variables/dimensions-reports/reports-visitor-profile.html) |
| Bevarande av besökare | Visar information om er kundlojalitet, t.ex. hur många och hur ofta besökare återvänder till er webbplats. | [Bevarande av besökare](https://docs.adobe.com/content/help/en/analytics/components/variables/dimensions-reports/reports-visitor-retention.html) |
| Project Link, Sharing and Scheduling | Metoder för att spara och/eller dela ditt arbete med andra i Analytics-gränssnittet. | [Skicka och schemalägg filer](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/curate-share/send-schedule-files.html) |

## Nyckeltal {#concept_392819DC275C48688E2CE4ABD4C5EE43}

| Måttnamn | Definition | Dokumentationslänk |
|---|---|---|
| Fullständig måttlista | Definition av alla mätvärden i Adobe Analytics. | [Översikt över mätvärden](https://docs.adobe.com/content/help/en/analytics/components/variables/metrics/metrics-overview.html) |
| Unika besökare | Antalet obeställda besökare på webbplatsen under en angiven tidsperiod. | [Unika besökare](https://docs.adobe.com/content/help/en/analytics/components/variables/dimensions-reports/reports-unique-visitors-v15-dsc.html) |
| Besök | En sekvens med sidvyer i ett möte. Besöken börjar när en person först tittar på en sida på webbplatsen och slutar efter 30 minuters inaktivitet. | [Besök](https://docs.adobe.com/content/help/en/analytics/components/variables/metrics/metrics-visit.html) |
| Sidvyer | En sidvy visas när en besökare visar en sida på webbplatsen. | [Sidvyer](https://docs.adobe.com/content/help/en/analytics/components/variables/metrics/metrics-page-view.html) |
| Instanser | Antalet gånger som en variabel har definierats. Varje gång Adobe Analytics ser ett värde i en variabel ökas instanserna med ett i respektive rapport. | [Instanser](https://docs.adobe.com/content/help/en/analytics/components/variables/metrics/metrics-instance.html) |
| Förekomster | Antalet gånger en variabel definierades eller beständig. | [Förekomster](https://docs.adobe.com/content/help/en/analytics/components/variables/metrics/metrics-occurrences.html) |

## Importalternativ {#concept_7C6DF03B5F9149E2A77F36C739432059}

| Alternativ | Beskrivning | Dokumentationslänk |
|---|---|---|
| Klassificeringsimportör | Importera metadata mot hämtade dimensioner via webbläsare eller FTP-överföring. Manuell metod jämfört med Rule Builder. | [Klassificeringsimportör](https://marketing.adobe.com/resources/help/en_US/reference/c_working_with_saint.html) |
| Regelverktyget | Skapa automatiskt metadataklassificeringar av dimensioner baserat på användardefinierade regler. | [Klassificeringsregelverktyget](https://marketing.adobe.com/resources/help/en_US/reference/classification_rule_builder.html) |
| Kundattribut | CRM-data överförda till Experience Cloud för användning i Adobe Analytics och Adobe Target. | [Kundattribut](https://docs.adobe.com/content/help/en/core-services/interface/customer-attributes/attributes.html) |
| Datakällor | Importera offlinemått i Analytics mot dimensioner eller helt enkelt efter dag. | [Datakällor](https://docs.adobe.com/content/help/en/analytics/import/data-sources/datasrc-home.html) |
| Adobe Exchange Data Connectors | Se [Analysverktyg](/help/landing/an-key-concepts.md) |  |
| Inbyggda integreringar | Målgruppsanalys och annonsanalys. | Se avsnittet&quot;Nyckelrapporter&quot;. |

## Exportalternativ {#concept_C62B688E259141CF92C048E8110464BE}

| Alternativ | Beskrivning | Dokumentationslänk |
|---|---|---|
| Hämtningar och schemaläggning av användargränssnitt | Exportera data från Analysis Workspace som CSV eller PDF | [Hämta PDF- eller CSV-filer](/help/analyze/analysis-workspace/curate-share/download-send.md) |
| Report Builder | Se Analysverktyg. |
| API för analyser | Skapa egna skräddarsydda frågor om Analytics-data. | <ul><li>[API 2.0](https://www.adobe.io/apis/experiencecloud/analytics/docs.html)</li><li>[API 1.4](https://github.com/AdobeDocs/analytics-1.4-apis)</li></ul> |
| Datalager | Se Analysverktyg. |  |
| Analysdatafeed | Det mest detaljerade sättet att få ut data från Analytics. Konfigurera en feed på träffnivå med Analytics. | [Analysdatafeed](https://docs.adobe.com/content/help/en/analytics/export/analytics-data-feed/get-started/data-feed-overview.html) |

## Datainsamling och validering {#concept_E07350D4CA5047DAA7D81F762F29606A}

| Metod/resurs | Beskrivning | Dokumentationslänk |
|--- |--- |--- |
| Resurser för utvecklare | Dokumentation som visar vilka bibliotek som är tillgängliga för att samla in Analytics-data på alla tillgängliga plattformar (webb, mobilapp, video, flash, etc.) | [Utvecklardokument](https://www.adobe.io/apis/experiencecloud/analytics/docs.html) |
| Implementeringshandbok | En beskrivning av datainsamlingsvariabler och detaljer om hur du implementerar datainsamlingskod i JavaScript. | [Implementeringshandbok](https://docs.adobe.com/content/help/en/analytics/implementation/home.html) |
| App Measurement (s_code) | Global variabelhantering | [AppMeasurement](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/appmeasurement-js/appmeasure-mjs.html) |
| Program-SDK | Anpassat paket som innehåller en förifylld version av konfigurationsfilen för appar. | <ul><li>[iOS](https://docs.adobe.com/content/help/en/mobile-services/ios/overview.html)</li><li>[Android](https://docs.adobe.com/content/help/en/mobile-services/android/getting-started-android/requirements.html)</li></ul> |
| DTM och Adobe Launch | Se Analysverktyg. |  |
| VISTA | Gör att du kan använda logik på serversidan för att ändra eller segmentera data när de samlas in. | [VISTA-regler](https://marketing.adobe.com/resources/help/en_US/reference/VISTA.html) |
| Bearbetar regler | Möjlighet att ange, ändra och kopiera variabler i analysgränssnittet för att ändra insamlade data. | [Bearbetar regler](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/processing-rules/processing-rules.html) |
| Felsökningsalternativ | Det finns flera felsökare och paketutlösare som kan hjälpa dig att validera implementeringen, inklusive Adobe Experience Cloud-felsökaren. | [Adobe Debugger](https://chrome.google.com/webstore/detail/adobe-experience-cloud-de/ocdmogmohccmeicdhlhhgepeaijenapj?hl=en) |
| API för datainfogning | API:t för datainfogning är en mekanism för datainsamling på serversidan och överföring till Experience Cloud-servrar. I stället för att använda JavaScript-fyrar på varje webbsida för att överföra besöksdata till Experience Cloud-servrar, samlar serversidesdata in data som enbart baseras på webbläsarbegäranden och webbserversvar. | [Steg för att implementera API:t för infogning av Adobe Analytics-data med POST](https://helpx.adobe.com/analytics/kb/data-insertion-api-post-method-adobe-analytics.html) |
