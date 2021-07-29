---
description: Det här avsnittet innehåller de viktigaste begreppen för Adobe Analytics, en kort beskrivning av begreppen samt en specifik dokumentationslänk med mer information om ämnet.
title: Adobe Analytics – viktiga begrepp
exl-id: 359c6663-33fd-4491-8ea0-55cd9ae31859
source-git-commit: 9a70d79a83d8274e17407229bab0273abbe80649
workflow-type: tm+mt
source-wordcount: '1815'
ht-degree: 93%

---

# Adobe Analytics – viktiga begrepp

Det här avsnittet innehåller de viktigaste begreppen för Adobe Analytics, en kort beskrivning av begreppen samt en specifik dokumentationslänk med mer information om ämnet.

## Analytics-verktyg {#concept_833EDD4EB056491DA1BC5A3A45FE285B}

| Produkt | Beskrivning | Dokumentationslänk |
| --- | --- | --- |
| Analysis Workspace | Webbläsarlösning för att skapa stabila, anpassade analysprojekt och demokratisera insikter. Ger större rapportflexibilitet än Reports and Analytics | [Analysis Workspace - startsida](/help/analyze/analysis-workspace/home.md) |
| Reports and Analytics (tidigare SiteCatalyst) | Webbläsarlösning för rapportering och analys. Startverktyget i Analytics-paketet. | [Reports and Analytics - startsida](/help/analyze/reports-analytics/getting-started.md) |
| Report Builder | Excel-tillägg som gör att du kan skapa anpassade förfrågningar för Adobe Analytics-data och visualisera dem med Microsoft Excel. | [Report Builder – startsida](/help/analyze/report-builder/home.md) |
| Data Workbench (tidigare Insight) | Utformat för att samla in, bearbeta, analysera och visualisera data från kundinteraktioner både online och offline över flera kanaler. | [Data Workbench-klient](https://experienceleague.adobe.com/docs/data-workbench/using/client/t-open-ins.html) |
| Data Warehouse | Obearbetade rådata för lagring och anpassade rapporter som du kan köra genom att filtrera data. Inte på träffnivå. | [Data Warehouse – startsida](/help/export/data-warehouse/data-warehouse.md) |
| Adobe Mobile Services | Sammanför funktioner för mobil marknadsföring i mobilappar från hela Adobe Experience Cloud så att ni kan förstå och förbättra användarengagemanget i era appar. | [Mobile Services – startsida](https://experienceleague.adobe.com/docs/mobile-services/using/home.html) |
| Adobe Exchange Data Connectors (tidigare Genesis) | Importera spårningsdata från tredjepartsprogram till Analytics för att ge heltäckande insyn i prestanda på en central plats. Från och med den 1 augusti 2021 avser Adobe att avbryta integreringen av dataanslutningar. | [Data Connectors – startsida](/help/import/data-connectors/data-connectors-eol.md) |
| Taggar i Adobe Experience Platform | Nästa generation av funktioner för webbplatstaggar och mobil SDK-hantering från Adobe. | [Översikt över taggar](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html) |

## Viktiga termer {#concept_E473ACBB8E4A42B4AC005538AC12F154}

Klicka [här](/help/technotes/terms.md) om du vill se en utökad ordlista över termer i Adobe Analytics.

| Term | Beskrivning | Dokumentationslänk |
| --- | --- | --- |
| Props (anpassad trafik) | Dimensioner som används för att spåra trafikaktiviteter sida för sida. Props lagras inte mellan sidorna. Viktiga tillämpningar av trafikvariabler: <ul> <li>Enkelt att räkna ut det ”populäraste” av ett specifikt värde</li> <li>Insyn i hur användarna navigerar på webbplatsen</li> </ul> <br>Exempel på trafikvariabler: Sidnamn, webbplatsavsnitt, webbläsare. | [Props](/help/admin/admin/c-traffic-variables/traffic-var.md) |
| eVar (anpassad konvertering) | Dimensioner som kvarstår under en tidsperiod som du anger. Alternativ för förfallotiden är bland annat att händelse, besök eller X dagar och bör styras av den typ av analys som ska utföras på variabeln. <br> Viktiga skillnader mellan eVars och props: <ul> <li>Props används ofta för sökvägsanalys eftersom data inte är beständiga.</li> <li>eVars används ofta för konverteringsanalys.</li> </ul> <br>Exempel på konverteringsvariabler: interna sökord, interna kampanjer, externa kampanjer (s.campaign). | [eVars](/help/admin/admin/conversion-var-admin/conversion-var-admin.md) |
| Händelser/mätvärden (s.events) | Mätvärden som mäter viktiga åtgärder som ni vill att besökarna ska utföra på webbplatsen. Det finns tre typer av händelser: Räknare, numeriska värden och valutor. Händelser är mest användbara när de läggs till i rapporter över konverteringsvariabler (eVar). eVar ger kvalitativ information om vad som hände och Event ger kvantitativ information om vad som hände. <br> Viktiga skillnader mellan eVars och händelser: <ul> <li>eVars berättar vem, vad eller vilket som påverkade konverteringen</li> <li>Händelser mäter hur många konverteringar som har skett</li> </ul> <br> Exempel på konverteringshändelser: beställning, programstart, leads, intäkter. | [Händelser](/help/admin/admin/c-success-events/success-event.md) |
| Komponenter | Dimensioner, mätvärden, segment och tidsdetaljer (datumintervall) som du kan dra och släppa i ett projekt. | [Komponenter](/help/analyze/analysis-workspace/components/analysis-workspace-components.md) |
| Dimensioner | Samling av eVars, props, klassificeringar och insamlade Adobe-standardvärden. | [Dimensioner](/help/components/dimensions/overview.md) |
| Mätvärden | Samling av implementerade händelser och beräknade mätvärden. | [Mätvärden](/help/analyze/analysis-workspace/components/apply-create-metrics.md) |
| Beräknade mätvärden | Förmågan att härleda anpassade mätvärden från befintliga mätvärden som samlats in via implementeringen. | [Beräknade mätvärden](/help/components/c-calcmetrics/cm-overview.md) |
| Segment | Förmågan att skapa, hantera, dela och använda kraftfulla, fokuserade målgruppssegment i Analytics-rapporter. Segment delas mellan olika Analytics-produkter och kan delas över hela Experience Cloud. | [Segmentering](/help/components/segmentation/seg-home.md) |
| Tid (datumintervall) | Förmågan att filtrera datum till valfri tidsperiod och skapa anpassade datumintervall som kan återanvändas i analyser. | [Datumintervall](/help/analyze/analysis-workspace/components/calendar-date-ranges/calendar.md) |
| Visualiseringar | Detaljerade visualiseringar som skapar liv i era projekt. | [Visualiseringar](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md) |
| Insamling | Förmågan att begränsa vilka komponenter som är tillgängliga i ett projekt eller Virtual Report Suite. | [VRS-kurva](/help/components/vrs/vrs-components.md) <br> [Projekturval](/help/analyze/analysis-workspace/curate-share/curate.md) |

## Viktiga rapporter

| Rapport | Beskrivning | Dokumentationslänk |
| --- | --- | --- |
| Fullständig lista över dimensioner/rapporter | Definition av alla dimensioner/rapporter som är tillgängliga i Adobe Analytics. | [Dimensioner](/help/components/dimensions/overview.md) |
| Advertising Analytics | Analysera alla dina betalda Google- och Bing-sökdata sida vid sida i Adobe Analytics. Dimensioner som skapas genom integreringen är annonsplattform, sökord, matchningstyp osv. Mätvärden som skapas är AMO Impressions, AMO Clicks, AMO Cost, Avg. Position och Avg. Quality Score. | [Advertising Analytics](/help/integrate/c-advertising-analytics/overview.md) |
| Audience Analytics | Utöka inkommande Analytics-träffar med användarens målgruppstillhörighet i AAM. Ni kan inkludera AAM-målgruppsdata som demografisk information (t.ex. kön eller inkomstnivå), psykografisk information (t.ex. intressen och hobbies), CRM-data och annonsvisningsdata i alla Analytics-arbetsflöden. Dimensioner som skapas genom den här integreringen är Audience ID och Audience Name. | [Audience Analytics](/help/integrate/c-audience-analytics/mc-audiences-aam.md) |
| Attribution IQ | Gör att ni kan förstå hur betydelsefulla interaktioner skapas under hela kundresan och på ett intelligent sätt identifiera inflexionspunkter som leder kunderna till önskade resultat vilket optimerar marknadsföringsinitiativen på ett effektivt sätt. Modellerna omfattar första, sista, linjära, deltagande, j-formade, omvända j-formade, u-formade, samma gest, anpassad och tidsfördröjning. | [Attribution IQ](/help/analyze/analysis-workspace/c-panels/attribution.md) |
| Avvikelseidentifiering | En statistisk metod för att fastställa hur ett givet mätvärde har ändrats i förhållande till tidigare data. AD är aktiverat som standard för alla trendvisualiseringar i Analysis Workspace. | [Avvikelseidentifiering](/help/analyze/analysis-workspace/virtual-analyst/c-anomaly-detection/anomaly-detection.md) |
| Bidragsanalys | Utforskar anledningen till avvikelser som uppstår genom att köra en automatiserad analys av varje enskilt mätvärde och dimension som du har tillgång till. | [Bidragsanalys](/help/analyze/analysis-workspace/virtual-analyst/contribution-analysis/ca-tokens.md) |
| Kohortanalys | En kohort är en grupp personer som delar gemensamma egenskaper under en angiven period. Kohortanalyser hjälper er att analysera kundlojalitet och bortfall hos era användare. | [Kohortanalys](/help/analyze/analysis-workspace/visualizations/cohort-table/cohort-analysis.md) |
| Customer Journey-rapporter | Visar information om den väg som användarna tar genom webbplatsen eller appen. Prop, eVars och händelser kan användas i den här analysen i Analysis Workspace. | [Analysis Workspace Fallout](/help/analyze/analysis-workspace/visualizations/fallout/fallout-flow.md) <br> [Analysis Workspace Flow](/help/analyze/analysis-workspace/visualizations/c-flow/flow.md) <br> [Reports and Analytics Pathing](/help/analyze/analysis-workspace/visualizations/c-flow/flow.md) |
| Marknadsföringskanaler | Rapporter som visar vilka externa kanaler som driver användare till er webbplats och vilka som är mest effektiva när det gäller konvertering. Vyer för första och sista kontaktpunkt finns. Det här är den rekommenderade rapporten för externa trafikkällor i Adobe Analytics (i stället för Campaigns eller Traffic Sources) eftersom den ger den mest omfattande översikten över både betalda och organiska kanaler. | [Marknadsföringskanaler](/help/components/c-marketing-channels/c-getting-started-mchannel.md) |
| Mobil | Visar information om webbplatser som öppnas via en mobil enhet eller surfplatta. | [Mobilrapport](/help/components/dimensions/mobile-dimensions.md) |
| Mobilapp | Visar grundläggande användningsinformation om mobilappar. Rapporterna är tillgängliga när vår SDK har implementerats och rapportering är aktiverat.  Dessutom har Adobe Mobile Services skapat ett separat mobilappsgränssnitt som ger mer omfattande appdata så att ni kan förstå och förbättra användarengagemanget i era appar. | [Adobe Mobile Services](https://experienceleague.adobe.com/docs/mobile-services/using/home.html) |
| Produkter | Identifierar hur enskilda produkter och grupper av produkter (kategorier) bidrar till olika konverteringsvärden, som intäkter eller utcheckningar. | [Produktrapport](/help/components/dimensions/product.md) |
| Segmentjämförelse | Identifierar de statistiskt mest signifikanta skillnaderna mellan segment genom en automatiserad analys av alla mätvärden och dimensioner du har tillgång till. | [Segmentjämförelse](/help/analyze/analysis-workspace/c-panels/c-segment-comparison/segment-comparison.md) |
| Webbplatsinnehållsrapport | Visar information om vilka sidor och områden på webbplatsen som är mest aktiva och vilka servrar som används mest. | [Webbplatsinnehållsrapport](/help/components/dimensions/page.md) |
| Site Metrics-rapport | Visar kvantitativ information om er webbplats, t.ex. unika besökare, beställningar, intäkter osv. Varje mätvärde kan användas i andra objektbaserade rapporter. | [Site Metrics-rapport](/help/components/metrics/overview.md) |
| Besökarprofil | Rapporter som hjälper dig att se köpmönster för kunder från olika profilkategorier, bland annat länder, delstater, postnummer och domäner. | [Besökarprofil](/help/components/dimensions/language.md) |
| Kvarhållning av besökare | Visar information om kundlojalitet, t.ex. hur många och hur ofta besökare återvänder till er webbplats. | [Kvarhållning av besökare](/help/components/dimensions/customer-loyalty.md) |
| Länka, dela och schemalägga projekt | Metoder för att spara och/eller dela arbete med andra i Analytics-gränssnittet. | [Skicka och schemalägg filer](/help/analyze/analysis-workspace/curate-share/send-schedule-files.md) |

## Nyckeltal {#concept_392819DC275C48688E2CE4ABD4C5EE43}

| Mätvärdets namn | Definition | Dokumentationslänk |
| --- | --- | --- |
| Fullständig lista över mätvärden | Definition av alla mätvärden i Adobe Analytics. | [Översikt över mätvärden](/help/components/metrics/overview.md) |
| Unika besökare | Antalet unika besökare på webbplatsen under en angiven tidsperiod. | [Unika besökare](/help/components/metrics/unique-visitors.md) |
| Besök | En sekvens med sidvisningar under en session. Besöket börjar när en person tittar på en sida på webbplatsen för första gången och slutar efter 30 minuters inaktivitet. | [Besök](/help/components/metrics/visits.md) |
| Sidvisningar | En sidvisning registreras när en besökare visar en sida på webbplatsen. | [Sidvisningar](/help/components/metrics/page-views.md) |
| Instanser | Antalet gånger som en variabel har definierats. Varje gång Adobe Analytics identifierar ett värde i en variabel ökas instanserna med en i respektive rapport. | [Instanser](/help/components/metrics/instances.md) |
| Förekomster | Antalet gånger en variabel definierades eller lagrades. | [Förekomster](/help/components/metrics/occurrences.md) |

## Importalternativ {#concept_7C6DF03B5F9149E2A77F36C739432059}

| Alternativ | Beskrivning | Dokumentationslänk |
| --- | --- | --- |
| Classification Importer | Importera metadata för insamlade dimensioner via webbläsare eller FTP-överföring. Manuell metod jämfört med Rule Builder. | [Classification Importer](/help/components/classifications/importer/c-working-with-saint.md) |
| Rule Builder | Skapa metadataklassificeringar av dimensioner automatiskt baserat på användardefinierade regler. | [Classification Rule Builder](/help/components/classifications/crb/classification-rule-builder.md) |
| Kundattribut | CRM-data överförda till Experience Cloud för användning i Adobe Analytics och Adobe Target. | [Kundattribut](https://experienceleague.adobe.com/docs/core-services/interface/customer-attributes/attributes.html) |
| Datakällor | Importera offlinemätvärden i Analytics efter dimensioner eller helt enkelt efter dag. | [Datakällor](/help/import/c-data-sources/datasrc-home.md) |
| Adobe Exchange Data Connectors | Se [Analytics-verktyg.](/help/import/data-connectors/data-connectors-eol.md) |  |
| Inbyggda integreringar | Audience Analytics och Advertising Analytics. | Se avsnittet Viktiga rapporter. |

## Exportalternativ {#concept_C62B688E259141CF92C048E8110464BE}

| Alternativ | Beskrivning | Dokumentationslänk |
| --- | --- | --- |
| Nedladdning och schemaläggning av användargränssnitt | Exportera data från Analysis Workspace som CSV eller PDF. | [Hämta PDF- eller CSV-filer](/help/analyze/analysis-workspace/curate-share/download-send.md) |
| Report Builder | Se Analytics-verktyg. |  |
| API för Analytics | Skapa egna frågor för Analytics-data. | <ul><li>[API 2.0](https://www.adobe.io/apis/experiencecloud/analytics/docs.html)</li><li>[API 1.4](https://github.com/AdobeDocs/analytics-1.4-apis)</li></ul> |
| data warehouse | Se Analytics-verktyg. |  |
| Datafeed i Analytics | Det mest detaljerade sättet att hämta data från Analytics. Konfigurera en feed på träffnivå med Analytics. | [Analytics-datafeed](/help/export/analytics-data-feed/data-feed-overview.md) |

## Datainsamling och validering {#concept_E07350D4CA5047DAA7D81F762F29606A}

| Metod/resurs | Beskrivning | Dokumentationslänk |
| --- | --- | --- |
| Resurser för utvecklare | Dokumentation som visar vilka bibliotek som är tillgängliga för att samla in Analytics-data på alla tillgängliga plattformar (webb, mobilapp, video, flash osv.) | [Utvecklardokument](https://www.adobe.io/apis/experiencecloud/analytics/docs.html) |
| Implementeringshandbok | En beskrivning av datainsamlingsvariabler och detaljer om hur ni implementerar datainsamlingskod i JavaScript. | [Implementeringshandbok](/help/implement/home.md) |
| Appmätning (s_code) | Global variabelhantering. | [AppMeasurement](/help/implement/js/migrate-from-hcode.md) |
| App-SDK:er | Anpassat paket som innehåller en förifylld version av konfigurationsfilen för appar. | <ul><li>[iOS](https://experienceleague.adobe.com/docs/mobile-services/ios/overview.html)</li><li>[Android](https://experienceleague.adobe.com/docs/mobile-services/android/getting-started-android/requirements.html)</li></ul> |
| Taggar i Adobe Experience Platform | Se Analytics-verktyg. |  |
| VISTA | Gör att ni kan använda logik på serversidan för att ändra eller segmentera data som samlas in. | [VISTA-regler](/help/admin/admin/c-processing-rules/c-processing-rules-configuration/processing-rule-order.md) |
| Bearbetningsregler | Förmågan att ange, ändra och kopiera variabler i Analytics-gränssnittet för att ändra data som samlas in. | [Bearbetningsregler](/help/admin/admin/c-processing-rules/processing-rules.md) |
| Felsökningsalternativ | Det finns flera felsökare och paketutlösare som kan hjälpa dig att validera implementeringen, inklusive Adobe Experience Cloud debugger. | [Adobe Debugger](https://chrome.google.com/webstore/detail/adobe-experience-cloud-de/ocdmogmohccmeicdhlhhgepeaijenapj?hl=sv) |
| API för datainfogning | API:t för datainfogning är en mekanism för datainsamling på serversidan och överföring till Experience Cloud-servrar. I stället för att använda JavaScript-beacons på varje webbsida för att överföra besöksdata till Experience Cloud-servrarna, samlar serversidan in data som enbart baseras på webbläsarfrågor och webbserversvar. | [Steg för att implementera API för infogning av Adobe Analytics-data med POST](https://helpx.adobe.com/se/analytics/kb/data-insertion-api-post-method-adobe-analytics.html) |
