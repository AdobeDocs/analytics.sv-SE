---
title: Uppdateringar av teknisk dokumentation för Adobe Analytics
description: Viktiga uppdateringar av dokumentationsuppsättningen för Adobe Analytics.
short-title: Analytics documentation updates
feature: Release Notes
exl-id: fe8e3c4c-6782-46f7-8e28-4f8f54807788
mini-toc-levels: 3
source-git-commit: 556f2131de980362094c691e8de61c6b077b5c15
workflow-type: tm+mt
source-wordcount: '5419'
ht-degree: 21%

---

# Uppdateringar av teknisk dokumentation för Adobe Analytics

Innehållsuppdateringar för Adobe Analytics-dokumentation sedan januari 2019.

* Mer information om [!UICONTROL Customer Journey Analytics] finns [här](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-landing.html).
* Mer information om Adobe Media Analytics finns i [Mäta ljud och video i Analytics](https://experienceleague.adobe.com/docs/media-analytics/using/media-overview.html).

## Information om större dokumentationsuppdateringar

### 2024 {#year2024}

| Funktion | Beskrivning |
| --- | --- |
| **Maj 2024** | |
| Uppdaterad Advertising Analytics-dokumentation | Uppdaterad dokumentation i linje med uppdateringar av [Advertising Analytics](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-workflow.md) användargränssnitt. |
| Explicit mappa XDM-objektvariabler till kontextdatavariabler | Dokumenterad möjlighet att [explicit ange kontextdatavariabler med hjälp av XDM-objektvariabelmappning](/help/implement/aep-edge/xdm-var-mapping.md#explicit-mapping). |
| Ny dokumentation för uppgradering från Adobe Analytics till Customer Journey Analytics | För organisationer som uppgraderar från Adobe Analytics till Customer Journey Analytics finns det flera uppgraderingsalternativ och många överväganden att tänka på baserat på organisationens nuvarande Adobe Analytics-implementering och långsiktiga mål.<p>Nu finns det nya dokumentationsresurser som hjälper dig att förstå:</p><ul><li>De olika uppgraderingssökvägarna som finns</li><li>Vilka uppgraderingsalternativ som finns tillgängliga baserat på en organisations aktuella implementering av Adobe Analytics</li><li>Fördelar och nackdelar med varje uppgraderingsväg</li><li>Stegvisa anvisningar för varje uppgraderingsväg</li><li>Att tänka på vid hantering av historiska data</li><li>Och mycket mer!</li></ul><p>[Kom igång med uppgraderingen till Customer Journey Analytics](https://experienceleague.adobe.com/en/docs/analytics-platform/using/compare-aa-cja/upgrade-to-cja/cja-upgrade-getstarted).</p> |
| Uppdaterad dokumentation om anpassade datumintervall | Uppdaterade skärmdumpar och procedurer för [skapa anpassade datumintervall](/help/analyze/analysis-workspace/components/calendar-date-ranges/custom-date-ranges.md) för att matcha de nuvarande produktfunktionerna och designen. |
| **April 2024** | |
| Borttagen dokumentation för &quot;ägare&quot; i klassificeringsuppsättningar | Filtret och kolumnen Ägare har tagits bort från [Klassificeringsuppsättningshanterare](/help/components/classifications/sets/manage/set-manager.md) och fältet Ägare har tagits bort från [Inställningar för klassificeringsuppsättning](/help/components/classifications/sets/manage/settings.md). <p>Dokumentationen uppdaterades för att ta bort filtret, kolumnen och fältet.</p> |
| Komprimerbara avsnitt har tagits bort i dokumentationen om hur du konfigurerar platser för molnimport och -export | Borttagna komprimerbara avsnitt i [Konfigurera platser för molnimport och -export](/help/components/locations/configure-import-locations.md) för information om olika typer av molnkonton. |
| **Mars 2024** | |
| AppMeasurement | [Versionsinformation](/help/implement/appmeasurement-updates.md) på AppMeasurementet update v2.26.0.<br/>Innehåller referens till och uppdatering av [`cookieDomainPeriods`](/help/implement/vars/config-vars/cookiedomainperiods.md) dokumentation för config variable. |
| Användningsinformation om kolumnen Används i är tillgänglig först från och med september 2023. | Tydligare användningsinformation om **Används i** kolumn på [landningssida för projekt](/help/analyze/landing.md) går tillbaka endast till september 2023. |
| **Februari 2024** | |
| Uppdateringar av information om hantering av Data Warehouse | Tydligare är att användare som standard bara kan visa de förfrågningar de skapar när [hantera förfrågningar från Data Warehouse](/help/export/data-warehouse/data-warehouse-requests-manage.md). |
| Uppdateringar av projektdelningsdokumentation | Lagt till information om hur [visa delade projekt](/help/analyze/analysis-workspace/curate-share/share-projects.md#view-projects-shared-with-you).<p>Effektivare information om [dela enskilda eller flera projekt](/help/analyze/analysis-workspace/curate-share/share-projects.md#share-a-specific-project-role).</p> |
| Lagt till behörighetskrav för att överföra filer till Azure SAS och Azure RBAC i Data Warehouse och dataflöden | Exakta behörighetskrav för överföring av filer till Azure SAS och Azure RBAC har lagts till när [konfigurera mål för Data Warehouse](/help/export/data-warehouse/create-request/dw-request-report-destinations.md) och [när mål för datafeeds konfigureras](/help/export/analytics-data-feed/create-feed.md). |
| Lagt till behörighetskrav för att överföra filer till Amazon S3- och GCP-kretsar i Data Warehouse- och dataflöden | Exakta behörighetskrav för överföring av filer till Amazon S3 och Google Cloud Platform har lagts till när [konfigurera mål för Data Warehouse](/help/export/data-warehouse/create-request/dw-request-report-destinations.md) och [när mål för datafeeds konfigureras](/help/export/analytics-data-feed/create-feed.md). |
| **Januari 2024** | |
| Komponentmigrering gäller för enskilda IMS-organ | Klarade att [komponentmigrering](/help/admin/admin/component-migration/component-migration.md) stöder inte migrering mellan IMS-plattformar. |
| Klarade att viss information endast är tillgänglig för administratörer | Tillagd information om att kolumnerna &quot;Senast använd&quot; och &quot;Används i&quot; beskrivs i [Beräknat måttansvarig](/help/components/c-calcmetrics/c-workflow/cm-workflow/cm-manager.md) och [Segmenthanterare](/help/components/segmentation/segmentation-workflow/seg-manage.md) är bara tillgängliga för systemadministratörer. |
| Uppdateringar av medieminarium - dokumentation om den genomsnittliga minuten-målgruppen | Uppdaterad information i [Mediemedelets minutmålspanel](/help/analyze/analysis-workspace/c-panels/average-minute-audience-panel.md) för att förbättra klarheten.<p>Bland förbättringarna finns:</p> <ul><li>Förbättrad organisation av information</li><li>Tillagda steg för att ange uppgiftsbaserad information</li></ul> |

### 2023 {#year2023}

| Funktion | Beskrivning |
| --- | --- |
| **December 2023** | |
| Förbättrad dokumentation av robotregler | Uppdaterad information i [Förstå och konfigurera robotregler](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/bot-rules.md) för att förbättra klarheten.<p>Bland förbättringarna finns:</p> <ul><li>Artikeltiteln har uppdaterats för att bli mer beskrivande</li><li>Förbättrad organisation av information</li><li>Tillagda steg för att ange uppgiftsbaserad information</li><li>Mer information om kraven för CSV-filer har lagts till vid överföring av robotregler</li></ul> |
| Avsnittet Nya rapporter | Ett nytt rapportavsnitt har lagts till som innehåller information om [med färdiga rapporter](/help/analyze/analysis-workspace/reports/use-reports.md) och [skapa och hantera företagsrapporter](/help/analyze/analysis-workspace/reports/create-company-reports.md). |
| Uppdateringar av dokumentationen för avvikelseidentifiering och bidragsanalys | Dokumentationen för avvikelseidentifiering och bidragsanalys fanns tidigare i ett avsnitt om Virtual Analyst. Följande ändringar har gjorts: <ul><li>Termen Virtual Analyst har tagits bort från dokumentationen.</li><li>Avsnittet om [Analysidentifiering](/help/analyze/analysis-workspace/c-anomaly-detection/anomaly-detection.md) har flyttats direkt under Analysis Workspace.</li><li>Bidragsanalysdokumentationen slogs samman i dokumentationen för avvikelseidentifiering.</li></ul> |
| &quot;Attribution IQ &quot; ändrad till &quot;Attribution&quot; | Ändrade alla instanser av &quot;Attribution IQ&quot; till &quot;[Attribut](/help/analyze/analysis-workspace/attribution/overview.md)&quot; i hela dokumentationen. |
| **November 2023** | |
| Uppdateringar av Activity Map aktiverings-/aktiveringsämne | Tillagd [Web SDK](https://experienceleague.adobe.com/docs/analytics/analyze/activity-map/getting-started/activitymap-enable.html) (både manuellt och via Adobe Experience Platform-taggtillägg). |
| **Oktober 2023** | |
| Logginformation har lagts till i Rapporteringsaktivitetshanteraren | Lagt till information som [annulleringar och efterföljande begränsningar av rapporteringsaktivitet](/help/admin/admin/reporting-activity-manager/reporting-activity-cancel-requests.md) i Rapporteringsaktivitetshanteraren hämtas i [Loggar](/help/admin/admin/logs.md). |
| Uppdateringar av Datans Warehouse komponentstöd | Lagt till tillgänglighet för vissa komponenter och tagit bort tillgänglighet för andra för Data Warehouse. Dessa ändringar återspeglas i [Komponentstöd i Data Warehouse](/help/export/data-warehouse/component-support.md). <ul><li>Stöd för dimensionen Besöksdjup har lagts till (borttaget Besöksdjup i listan över dimensioner stöds inte)</li><li>Borttaget stöd för deltagandemått (extra deltagandemått i listan över mätvärden som inte stöds)</li><li>Stöd för följande tidsbaserade dimensioner har lagts till: År, Kvartal, Månad, Vecka, Dag, Timme och Minut (de här dimensionerna har tagits bort från listan över dimensioner som inte stöds) <p>Tidigare hade Datan Warehouse bara stöd för dessa mått i den första kolumnen i en friformstabell när Kornighet markerades. Nu stöds alltid dessa dimensioner.</p><p>Datumutdata är dock inte standard när de här måtten används. Året är 1900 och månaderna är nollbaserade.</li></ul> |
| **September 2023** | |
| Uppdaterad struktur för artiklar för panelen Medieuppspelningstid för spenderad tid | Mappen Media Playback Time Spent har tagits bort och innehållet i mappen har kombinerats till en enda artikel: [Medieuppspelningstid spenderad panel](/help/analyze/analysis-workspace/c-panels/media-playback-time-spent.md). <p>Den här ändringen är mer i linje med dokumentationen för andra paneler.</p> |
| Komma igång med innehållsförbättringar | Lagt till information som beskriver viktiga uppgifter och resurser för att komma igång för administratörer, analytiker, slutanvändare och utvecklare. Följande nya artiklar är nu tillgängliga: <ul><li>[Kom igång (efter roll)](/help/analyze/get-started/get-started-by-role.md)</li><li>[Förstå analysgränssnittet](/help/analyze/get-started/analytics-interface.md)<li>[Användningsexempel](/help/analyze/get-started/use-cases.md)</li></ul> |
| Förbättringar av dokumentationen för Media Analytics-rapportering | Omorganiserat en del av innehållet i avsnittet Rapportering i guiden Direktuppspelande media, bland annat genom att konsolidera API-dokumentationen i ett eget avsnitt och justera ordningen för vissa artiklar. <p>Namnet på artikeln Mallar för arbetsytor för media har ändrats till [Medierapporter i arbetsytan](https://experienceleague.adobe.com/docs/media-analytics/using/media-reports/media-workspace-templates.html) för att bättre anpassa till namngivningen i produkten. </p> |
| **Augusti 2023** | |
| Förtydligande av dataflöde | Uppdaterat [definitionen av start- och slutdatum](/help/export/analytics-data-feed/create-feed.md) för att förtydliga att när du bearbetar dataflöden för historiska data kan du ange startdatumet till vilket datum som helst tidigare när data samlas in. |
| Adobe Experience Platform Edge Network datahantering | Lagt till innehåll om hur Adobe Analytics [hanterar data från Edge Network](../implement/aep-edge/overview.md). |
| Medieuppspelningstid spenderad panel | Uppdaterat innehåll för  [Medieuppspelningstid spenderad panel](/help/analyze/analysis-workspace/c-panels/media-playback-time-spent.md) för att förbättra läsbarheten. |
| Flyttat innehåll om hantering av schemalagda projekt | Skapade en ny artikel i Analytics Components Guide med namnet [Schemalagda projekt](/help/components/scheduled-projects-manager.md). Innehållet fanns tidigare i [Schemalägg projekt](/help/analyze/analysis-workspace/curate-share/t-schedule-report.md) artikel i Analytics Tools Guide. |
| Jämför implementeringsmetoder | Uppdaterad dokumentation som jämför olika implementeringsmetoder. [Läs mer](../implement/prepare/comparison.md) |
| Adobe kundtjänst krävs inte för att konfigurera SFTP för dataflöden | Tydligare i [Skicka Adobe-data till ett externt FTP-konto med SFTP](/help/export/ftp-and-sftp/c-sftp/ftp-sftp-transfer.md) som kunderna inte behöver kontakta Adobe kundtjänst för att konfigurera SFTP för dataflöden. <p>Dessutom lades ett meddelande till om att SFTP inte längre rekommenderas och att kunder bör använda ett molnmål när de konfigurerar datafeeds.</p> |
| Dokumentationsförbättringar för direktuppspelningsmedia | Följande dokumentationsförbättringar har gjorts för Streaming Media: <ul><li>Uppdaterade [allmän översikt](https://experienceleague.adobe.com/docs/media-analytics/using/media-overview.html) för att förbättra klarheten och inkludera information om Customer Journey Analytics.</li><li>Uppdaterade [implementeringsöversikt](https://experienceleague.adobe.com/docs/media-analytics/using/implementation/overview.html) för att tydligt skilja mellan Edge-implementeringar och implementeringar som enbart innehåller analyser. Dessutom ingår diagram som illustrerar de olika implementeringsmetoderna.</li><li>Lagt till krav som är specifika för [Edge-implementeringar](https://experienceleague.adobe.com/docs/media-analytics/using/implementation/edge-recommended/prerequisites-edge.html) och [Implementeringar med enbart analys](https://experienceleague.adobe.com/docs/media-analytics/using/implementation/analytics-only/prerequisites-analytics.html). Uppdaterade även [allmänna krav](https://experienceleague.adobe.com/docs/media-analytics/using/getting-started/prereqs.html).</li><li>Uppdaterade tabeller i [Hämta SDK:er för media, tillägg med taggar och OTT SDK:er](https://experienceleague.adobe.com/docs/media-analytics/using/getting-started/download-sdks.html) artikel som innehåller nya kolumner för *Lösningar* och *Implementeringsmetod*.</li><li>Effektivt innehåll och smidigare organisering av artiklar i [Implementering](https://experienceleague.adobe.com/docs/media-analytics/using/implementation/overview.html) dokumentationsdelen. Detta inkluderade kategorisering av implementeringar med Edge och implementeringar med enbart analys.</li><li>En extra hierarkinivå som inte behövdes under har tagits bort [Spårning](https://experienceleague.adobe.com/docs/media-analytics/using/tracking/track-core-overview.html) och lade till omdirigeringar för ändrade URL:er i det här avsnittet.</li><ul> |
| **Juli 2023** | |
| API för Adobe Experience Platform Edge Network Server | Mer omfattande dokumentation om när och hur datainsamlingen ska genomföras med Adobe Analytics med [API för Adobe Experience Platform Edge Network Server](../implement/aep-edge/server-api/overview.md). Om du till exempel implementerar datainsamling med Adobe Analytics i datorprogram, IoT-enheter, anger du de övre rutorna. |
| Globalt företag-ID | Dokumenterad [hur du hittar det globala företags-ID:t](../admin/admin/company/web-services-admin.md) för det Analytics-företag du är inloggad på. Detta ID krävs för API:er i Analytics 2.0. |
| Uppdaterad storleksgräns för FTP | Ändrad som standard [Lagringsgräns för FTP-data](/help/export/ftp-and-sftp/ftp-limits.md) till 100 GB. |
| Variabeln Nytt AppMeasurement | Variabeln `decodeLinkParameters` används för kantfall där implementeringar kodar flerbytetecken i länkspårningsvariabler. [Läs mer](../implement/vars/config-vars/decodelinkparameters.md) |
| Konfigurera lagringsplatser för molnkonton för inhämtning av klassificeringsdata | Nu kan du hantera lagringsplatser för molnkonton som används för automatisering av klassificeringsuppsättningar. [Läs mer](/help/components/locations/configure-import-accounts.md) |
| Förbättrat datareparationsfilter | Tre filtreringsförbättringar har lagts till i Datareparation. [Läs mer](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/data-repair/) |
| **Juni 2023** | |
| Nya funktioner för klassificeringsuppsättningar | [Klassificeringsuppsättningar](/help/components/classifications/sets/overview.md) har uppdaterats med flera nya funktioner:<ul><li>**Konsolideringar**: Kombinera klassificeringsuppsättningar i en enda konsoliderad klassificeringsuppsättning. Den konsoliderade klassificeringsuppsättningen kan användas som andra klassificeringsuppsättningar eller som en uppslagsuppsättning i Customer Journey Analytics. [Läs mer](../components/classifications/sets/consolidations/manage.md)</li><li>**Regler**: Klassificera värden automatiskt baserat på reglerna i klassificeringsuppsättningen. [Läs mer](../components/classifications/sets/manage/rules.md)</li><li>**Automatiserad import**: Importera klassificeringsdata automatiskt från molnlagringsmål. [Läs mer](../components/classifications/sets/manage/schema.md)</li></ul> |
| Uppdateringar av beräknade mätvärden | Uppdateringar gjordes för olika artiklar om beräknade mätvärden, inklusive uppdatering av skärmdumpar och steg i procedurer. Dessa ändringar har gjorts för att få dokumentationen att överensstämma med den aktuella Adobe Analytics-funktionen. |
| Säkra destinationer för datafeed-export | Datamatningar kan nu skickas till följande molnlagringsmål:<ul><li>Amazon S3</li><li>Azure RBAC</li><li>Azure SAS</li><li>Google Cloud Platform</li></ul>Destinationer som tidigare var tillgängliga (FTP, SFTP, S3 och Azure Blob) rekommenderas inte längre. [Läs mer](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/create-feed.html) |
| Punktrapportering på arbetsytan | Bot-rapportering finns nu i Analysis Workspace. Den här funktionen innehåller flera tillägg:<ul><li>En ny dimension: [Punktnamn](/help/components/dimensions/bot-name.md)</li><li>Två nya mätvärden: [Bot page views](/help/components/metrics/bot-page-views.md) och [Punkter](/help/components/metrics/bot-occurrences.md).</li><li>En ny mall för beräknade mått: [Vyförhållande för startsida](/help/components/c-calcmetrics/cm-reference/default-calcmetrics.md)</li><li>En ny arbetsytrapport: Bot-rapportering</li></ul>Den nya dimensionen och mätvärdena innehåller data som är förifyllda från mars 2023. |
| **Maj 2023** | |
| Deep Linking-dokumentation (mobilapp) | Tillåter användare att skicka länkar till styrkort som leder dem direkt till styrkortsprojektet i appen. [Läs mer](/help/analyze/mobile-app/create-scorecard.md#shareable-link) |
| Dokumentation för den uppdaterade startskärmen för kontrollpanelsappen för Analytics (mobilapp) | På den nya uppdaterade startskärmen kan du visa alla dina styrkort i en konsoliderad styrkortslista. [Läs mer](/help/analyze/mobile-app/executive.md#use-dashboards) |
| Spektrum-ikoner | Ersatt, där så är lämpligt, skärmdumpar av användargränssnittsikoner i dokumentationen med referenser till motsvarande ikoner i [Adobe Spectrum Design System](https://spectrum.adobe.com/page/icons/). |
| Rapporteringsaktivitetshanteraren | Den här betatestningsdokumentationen har uppdaterats, särskilt avsnittet om [Visa rapporteringsaktivitet för enskilda rapportsviter](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/reporting-activity.html#view-reporting-activity-for-individual-report-suites). |
| Översikt över Analysis Workspace | Uppdaterat [Analysis Workspace - översikt](/help/analyze/analysis-workspace/home.md) för att inkludera mer allmän översiktsinformation och länkar till relevant innehåll. |
| Skapa projekt | Skapade en ny artikel som förklarar i detalj hur du [Skapa projekt](/help/analyze/analysis-workspace/build-workspace-project/create-projects.md) i Analysis Workspace. |
| Sortera komponenter i den vänstra listen | Lagt till information om hur du sorterar komponentlistan i den vänstra listen. Se avsnittet&quot;Sök, filtrera och sortera komponentlistan&quot; i [Komponenter - översikt](/help/analyze/analysis-workspace/components/analysis-workspace-components.md). |
| Ta bort rader som innehåller dynamiska dimensioner från en frihandstabell | Lagt till information om hur du snabbt tar bort specifika rader som innehåller dynamiska dimensioner med hjälp av x-ikonen. Se avsnittet&quot;Snabb uteslutning av specifika rader från en tabell&quot; i [Filtrera och ordna tabeller](/help/analyze/analysis-workspace/visualizations/freeform-table/filter-and-sort.md). |
| Knapp för att lägga till en visualisering på en panel | Lagt till information om en ny knapp längst ned på varje panel i Analysis Workspace som gör att du snabbt kan lägga till en visualisering. Se avsnittet&quot;Lägga till visualiseringar i en panel&quot; i [Visualiseringar - översikt](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md). |
| **April 2023** | |
| Överför användarresurser och ange förfallodatum för konton | Lagt till information om hur [överföra användarresurser och ange förfallodatum för konton](/help/admin/admin/user-management2/users-assets.md). |
| 2 nya slutpunktsguider för Adobe Analytics 2.0 API | <ul><li>[API för Analytics-Dimensioner](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/dimensions/)</li><li>[API för analysmått](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/metrics/)</li></ul> |
| Projektsegment (ad hoc- och snabbsegment) | Effektiv dokumentation om projektsegment och borttagen dubblettinformation. Stegen för att skapa ad hoc-segment kombineras nu med stegen för [skapa snabbsegment](/help/analyze/analysis-workspace/components/segments/quick-segments.md). |
| Dynamiska sökningar | Ytterligare information om [Dynamiska sökningar](/help/export/analytics-data-feed/c-df-contents/dynamic-lookups.md) läggs till. Tidigare fanns bara information för mobilattribut, som är en av flera dynamiska sökningar. |
| **Mars 2023** | |
| Stöd för Web SDK i Activity Map | Uppdaterat [Implementera Adobe Analytics](/help/implement/home.md) och [Aktivera Activity Map](/help/analyze/activity-map/activitymap-getting-started/activitymap-enable.md). |
| Översikt över trafikvariabler (props) | Lagt till avsnitt och stegvisa procedurer för att förtydliga och förbättra artikelinnehållet. Sammanfogat innehåll från en artikel med rubriken&quot;Aktivera trafikvariabelrapporter&quot; och tog bort artikeln. Se [Översikt över trafikvariabler (props)](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/c-traffic-variables/traffic-var.md). |
| Interna URL-filter | Lagt till avsnitt och stegvisa procedurer för att förtydliga och förbättra artikelinnehållet. Se [Interna URL-filter](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/internal-url-filter-admin.md). |
| Skapa dataartiklar i mobilstyrkort | A [dataartikel](/help/analyze/mobile-app/create-scorecard.md#create-data-stories) är en samling datapunkter, företagskontext och relaterade mätvärden som bygger på ett centralt tema eller mätvärden. |
| Standardberäknade värden | Innehåll som förklarar [standardberäknade värden från Adobe](/help/components/c-calcmetrics/cm-reference/default-calcmetrics.md). |
| Dataordlista | <p>Lagt till ny dokumentation för Data Dictionary, inklusive en [Ökning](/help/analyze/analysis-workspace/components/data-dictionary/data-dictionary-overview.md), [Visning](/help/analyze/analysis-workspace/components/data-dictionary/view-data-dictionary.md), [Redigering](/help/analyze/analysis-workspace/components/data-dictionary/edit-entries-data-dictionary.md)och [Övervakning](/help/analyze/analysis-workspace/components/data-dictionary/monitor-data-dictionary-health.md) Data Dictionary.</p><p>Information i [Lägga till komponentbeskrivningar](/help/analyze/analysis-workspace/components/add-component-descriptions.md) har uppdaterats för att ta hänsyn till funktionen för datamordlista.</p> |
| Länkdelning för projekt (ingen inloggning krävs) | <p>Befintlig dokumentation som förklarar hur man delar en skrivskyddad länk till ett projekt med personer som inte har tillgång till Analysis Workspace har uppdaterats.</p> <p>Uppdaterad användardokumentation innehåller [Dela projekt](/help/analyze/analysis-workspace/curate-share/share-projects.md) och [Skapa delningsbara länkar](/help/analyze/analysis-workspace/curate-share/shareable-links.md).</p> <p>Alternativ för administratörer lades till i [Inställningar](/help/analyze/analysis-workspace/user-preferences.md).</p> |
| **Februari 2023** | |
| Implementering | Uppdaterat innehåll om hur man [implementera Adobe Analytics för webb och mobiler](../implement/home.md). |
| Arbetsytekalendrar och datumintervall | Uppdaterat innehåll som beskriver relativa datumintervall, uppdateringar av formelberäkning och ändringar i kalendergränssnittet. Se [Om relativa paneldatumintervall](/help/analyze/analysis-workspace/components/calendar-date-ranges/calendar.md). |
| Mobil styrkort | Nytt dokumentationsavsnitt som beskriver hur du visar och döljer datumintervall för jämförelse. Se [Visa datumintervall för jämförelse](/help/analyze/mobile-app/create-scorecard.md) i Customer Journey Analytics. |
| 1.4 API | The [Adobe Analytics 1.4 API](https://developer.adobe.com/analytics-apis/docs/1.4/) har fått en fullständig omskrivning och har nu publicerats på Adobe Developer. |
| Spåra olika implementeringstyper | Användningsexemplet har uppdaterats [Spåra olika implementeringstyper](../implement/use-cases/cross-type-implementation.md) för att få plats med Experience Cloud ID-tjänsten. |
| **Januari 2023** | |
| Filtrera och ordna tabeller | Uppdaterat innehåll (inklusive att lägga till procedurer och förklara tillgängliga alternativ) i [Filtrera och ordna tabeller](/help/analyze/analysis-workspace/visualizations/freeform-table/filter-and-sort.md) artikel. Artikelns namn ändrades från&quot;Sidnumrering, filtrering och sortering&quot;. |
| Mappar | Särskilda sidor för [Mapphantering](/help/analyze/analysis-workspace/build-workspace-project/workspace-folders/about-folders.md). |
| Användarinställningar | Många andra användarinställningar finns nu tillgängliga i [Inställningar](/help/analyze/analysis-workspace/user-preferences.md). |
| Spara automatiskt för projekt | Uppdaterat innehåll som inkluderar autosparfunktion i [Spara projekt](/help/analyze/analysis-workspace/build-workspace-project/save-projects.md). |
| Landningssida | Nytt [uppdatering av landningssida](/help/analyze/landing.md) |

### 2022 {#year22}

| Funktion | Beskrivning |
| --- | --- |
| **November 2022** | |
| Variabler för hantering av samtycke | Särskilda sidor för [Medgivandehanteringsanmälan](/help/components/dimensions/cm-opt-in.md) och [Avanmäl dig till hantering av samtycke](/help/components/dimensions/cm-opt-out.md). |
| Uppdatering i flera valutor | Sidor runt [Stöd för flera valutor](/help/implement/vars/config-vars/currencycode.md) uppdateras. |
| **Oktober 2022** |  |
| Data Workbench | [Meddelande om att produkten är slut](https://experienceleague.adobe.com/docs/data-workbench/using/eol.html) |
| Klienttips | Nytt [översikt och frågor och svar](https://experienceleague.adobe.com/docs/analytics/technotes/client-hints.html). |
| Sammanfattning av nyckelmått | Nytt ämne på [Sammanfattning av nyckelmått](/help/analyze/analysis-workspace/visualizations/key-metric.md) visualisering. |
| Klassificeringsuppsättningar | Den nya användaren [Klassificeringsuppsättningar](https://experienceleague.adobe.com/docs/analytics/components/classifications/sets/overview.html) upplevelsen ger ett enda gränssnitt för att hantera klassificeringar och regler och ger en bättre överblick över kundägda klassificeringsdata. |
| Mobilapp: Anpassade detaljvyer | Nytt ämne [anpassade detaljvyer](https://experienceleague.adobe.com/docs/analytics/analyze/mobapp/create-scorecard.html). |
| VISTA | Ny sida som förklarar grunderna i [VISTA-regler](/help/technotes/vista.md). |
| **September 2022** | |
| Kombinationsdiagram | Nytt ämne på [kombinationsdiagram](/help/analyze/analysis-workspace/visualizations/combo-charts.md) visualisering. |
| Uppdaterat plugin-program | Uppdaterad version av [getvalonce](/help/implement/vars/plugins/getvalonce.md) implementerings-plugin. |
| Ny konfigurationsvariabel | Dokumentation på [collectHighEntropyUserAgentHints](/help/implement/vars/config-vars/collecthighentropyuseragenthints.md) |
| Kundtips med hög entropi | Nytt avsnitt om hur Adobe använder [klienttips](/help/technotes/client-hints.md) utöver User-Agent för att fastställa enhetsinformation. |
| Bearbetningsorder | Olika hjälpsidor har sammanställts för att ge ett enda hjälpavsnitt om [Bearbetningsorder](/help/technotes/processing-order.md). |
| **Augusti 2022** | |
| Stöd för listvariabler i XDM för Edge Collection | Gör det möjligt för kunder att samla in data med Web SDK att använda XDM för att ange innehåll i listvariabler. [Läs mer](../implement/vars/page-vars/list.md#list-variables-using-the-web-sdk) |
| Användning av SKU-fält i XDM för Edge Collection när produktsträngsvariabler anges | Gör det möjligt för kunder att samla in data med hjälp av Web SDK att använda SKU-värdet för att ställa in produktfältet i variabeln products. [Läs mer](../implement/vars/page-vars/products.md#products-using-the-web-sdk) |
| **Juni 2022** |  |
| Marknadsföringsvariabler i XDM för Edge Collection | Dokumentation på [stöd för Merchandising-variabler i XDM för Edge Collection](/help/components/dimensions/evar-merchandising.md) |
| Experience Platform Edge-dokumentation | Nya artiklar om Adobe Analytics implementering via [Web SDK](/help/implement/aep-edge/web-sdk/overview.md), [Mobile SDK](/help/implement/aep-edge/mobile-sdk/overview.md)och [Edge API](/help/implement/aep-edge/server-api/overview.md). |
| Uppdaterad dokumentation om visualisering av flöde | Baserat på [nytt användargränssnitt](/help/analyze/analysis-workspace/visualizations/c-flow/create-flow.md) |
| Dokumentation om att dela anteckningar i mobilstyrkort | Du kan visa [anteckningar som har skapats i Workspace i Mobile Scorecards](/help/analyze/analysis-workspace/components/annotations/mobile-annotations.md). |
| **Maj 2022** | |
| Fylla i livscykeldimensioner och mätvärden via Edge Network | Mobila livscykeldata som skickas till Edge Network visas nu i Analytics-rapporter. Se [Variabelmappning för analyser](/help/implement/aep-edge/xdm-var-mapping.md) för information om vilka XDM-fält som mappar till befintliga mobila livscykelrapporter. |
| **April 2022** | |
| Uppdateringar av Adobe Analytics landningssida | Uppdateringar av leden [Startsida för arbetsyta/rapporter och analyser](/help/analyze/landing.md) som förbättrar användbarheten och underlättar navigeringen. |
| Nytt ämne [!UICONTROL Page Summary] panel | [Panelen Sidsammanfattning](/help/analyze/analysis-workspace/c-panels/page-summary.md) |
| Nytt ämne [!UICONTROL Next/Previous item] panel | [Panelen Nästa/föregående dimensionsobjekt](/help/analyze/analysis-workspace/c-panels/next-previous.md) |
| **Mars 2022** | |
| Nytt avsnitt om vilka HTTPS-krypteringsalgoritmer som stöds | HTTPS-krypteringsalgoritmer som stöds för kunder med krypteringssäkerhetsnivån &quot;Hög&quot;. |
| Ny dokumentation om anteckningar i arbetsytan | [Anteckningar i arbetsytan](/help/analyze/analysis-workspace/components/annotations/overview.md) kan ni effektivt kommunicera kontextuella datanunkter och insikter till er organisation. |
| Uppdateringar av Adobe Analytics landningssida | [Uppdateringar](/help/analyze/landing.md) till landningssidan för gemensam arbetsyta/rapporter och analyser som förbättrar användbarheten och underlättar navigeringen. |
| [!UICONTROL Next item] eller [!UICONTROL Previous item] Panelen Arbetsyta | På den här panelen kan du utforska objekt som följer eller föregår ett av de önskade dimensionsobjekten. |
| [!UICONTROL Page Summary] Panelen Arbetsyta | Panelen innehåller en djupgående analys av en sida som du väljer. |
| Nytt avsnitt om att pausa äldre schemalagda rapporter | Effektivt **15 april 2022** kommer Adobe att pausa alla schemalagda rapporter som har ett skapandedatum som är längre än två år |
| **Februari 2022** | |
| Förhandsgranskningsläge för mobilstyrda projekt | The [förhandsgranskningsläge](https://experienceleague.adobe.com/docs/analytics/analyze/mobapp/create-scorecard.html#preview) I kan du förhandsgranska upplevelsen innan du sparar och delar ett styrkort. |
| Slutpunkt för API-projekt | Lägg till, redigera eller ta bort Analysis Workspace-projekt med API:t. [Läs mer](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/projects/) |
| Uppdaterat ämne om att pausa äldre schemalagda Report Builder-aktiviteter | **Gäller från 15 april 2022**, Adobe tänker [pausa alla schemalagda aktiviteter i Report Builder som skapades för mer än två år sedan](/help/analyze/report-builder/r-arb-scheduled-reports.md). |

### 2021 {#year2021}

| Funktion | Beskrivning |
| --- | --- |
| **Oktober 2021** |  |
| 21 oktober 2021 | Ny dokumentation om [Snabbsegment](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/components/segments/quick-segments.html) i ANALYSIS WORKSPACE |
| 21 oktober 2021 | Ny dokumentation på [Medieuppspelningstid spenderad](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/media-playback-timespent/media-playback-time-spent.html) i Analysis Workspace. |
| 7 oktober 2021 | Ny dokumentation om [visualiseringar för mobilstyrkort](https://experienceleague.adobe.com/docs/analytics/analyze/mobapp/create-scorecard.html#apply-visualizations) |
| **Augusti 2021** |  |
| 18 augusti 2021 | Reviderad toppnivåstruktur och konsoliderad till en enda [Landningssida](https://experienceleague.adobe.com/docs/analytics.html) |
| 18 augusti 2021 | Nytt ämne [A4T och virtuella rapportsviter](/help/components/vrs/vrs-a4t.md) |
| 18 augusti 2021 | Nytt ämne [Bästa praxis för attribuering](/help/analyze/analysis-workspace/attribution/best-practices.md) |
| 5 augusti 2021 | Nytt ämne [Antal upprepande instanser](https://experienceleague.adobe.com/docs/analytics/components/metrics/count-repeat-instances.html) |
| 5 augusti 2021 | Uppdaterad klassificeringsdokumentation om [mallar](https://experienceleague.adobe.com/docs/analytics/components/classifications/classifications-importer/c-download-saint-data.html), [webbläsarimport](https://experienceleague.adobe.com/docs/analytics/components/classifications/classifications-importer/browser-import.html)och [webbläsarexport](https://experienceleague.adobe.com/docs/analytics/components/classifications/classifications-importer/browser-export.html) för att ange alternativ som inte är tillgängliga för rapportsviter som är aktiverade för den nya klassificeringsarkitekturen. |
| 2 augusti 2021 | Flera sidor har uppdaterats för att återspegla omprofileringen av [Adobe Experience Platform Launch](https://experienceleague.adobe.com/docs/analytics/implementation/launch/overview.html) |
| **Juli 2021** |  |
| 23 juli 2021 | Ny fördjupad diskussion om [Merchandising eVars](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/conversion-variables/merchandising-evars.html) |
| 15 juli 2021 | Lagt till ny dokumentation om den nya [Adobe Analytics landningssida](/help/analyze/landing.md) |
| **Juni 2021** |  |
| 15 juni 2021 | Uppdaterat [Bästa praxis för marknadsföringskanaler](https://experienceleague.adobe.com/docs/analytics/components/marketing-channels/mchannel-best-practices.html) |
| 3 juni 2021 | Dokumentationen har uppdaterats för att förklara bättre [Implementering av datafeed](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/create-feed.html) och [här](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/df-faq.html#BucketOwnerFullControl). |
| 25 maj 2021 | Dokumentationen uppdaterades den [eVar - skiftlägeskänslighet vid rapportering](https://experienceleague.adobe.com/docs/analytics/components/dimensions/evar.html). |
| 13 maj 2021 | Uppdateringar till [Datas Warehouse-API-begäranden](https://github.com/AdobeDocs/analytics-1.4-apis/blob/master/docs/reporting-api/data_warehouse.md). De har nu stöd för&quot;Timmar&quot;. |
| **Mars 2021** | |
| Mars, april 2021 | Uppdateringar av Adobe Analytics kontrollpaneler [Executive Guide](https://experienceleague.adobe.com/docs/analytics/analyze/mobapp/executive.html) och [Kurvguide](https://experienceleague.adobe.com/docs/analytics/analyze/mobapp/curator.html) |
| 25 mars 2021 | Ny dokumentation på [!UICONTROL Components] > [!UICONTROL User preferences] sida. Det gör att du kan hantera [!UICONTROL Analysis Workspace] inställningar och relaterade komponenter för användaren. [!UICONTROL User preferences] gäller för alla nya projekt och paneler. <br>**Obs!** följande inställningar har flyttats till [!UICONTROL User preferences] sida:<ul><li>Rapportinställningar: Tusentalsavgränsare (kallas nu _Nummerformat_)</li><li>Rapportinställningar: CSV-avgränsare</li><li>Arbetsyteprojekt: Hjälp > Aktivera tips</li><li>Arbetsyteprojekt: Tom panel _Starta nya projekt med den här panelen_ option</li></ul> |
| 25 mars 2021 | [!UICONTROL Histogram Smart Bucket Prediction] hjälper till med histogram med höga kardinalitetsmått genom att automatiskt identifiera rätt bredd och antal buckar för ert datauppslag. För lågkardinalitetsmått fungerar visualiseringen på samma sätt som tidigare. |
| 25 mars 2021 | [API för datareparation](https://github.com/AdobeDocs/analytics-2.0-apis/blob/master/data-repair.md) uppdateringar (filtrera efter URL:er, frågesträngar, vid tecken med mera) |
| 25 mars 2021 | Nytt [API för användningslogg](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/usage-logs.md) dokumentation |
| **Februari 2021** | |
| 4 februari 2021 | Komponentval: Komponenten för rullgardinsmeny/släppzon finns i [!UICONTROL Quick Insights] lades till i alla släppzoner i [!UICONTROL Workspace]. Den här förbättringen gör att du kan välja från en listruta med kompatibla komponenter eller fortsätta att använda utrymmet som en släppzon. |
| **Januari 2021** | |
| 14 januari 2021 | Språkval har lagts till i dokumentationen för kontrollpanelerna i Analytics. |
| 14 januari 2021 | Lagt till dokumentation om hur du kan lägga till bilder i Workspace-projekt genom att referera till en offentlig bild-URL. |
| 14 januari 2021 | Kombinerad käll- och inställningshanterare för arbetsytevisualiseringar: [!UICONTROL Data Source] hanteraren (punkt) och inställningshanteraren (kugghjulet) för visualiseringar har kombinerats till en enda leverantör, så att du enkelt kan hantera källan och inställningarna från samma plats. |

### 2020 {#year2020}

| Funktion | Beskrivning |
| --- | --- |
| **December 2020** | |
| 7 december 2020 | Ändrade alla relevanta sidor så att slutpunkten &quot;adobedc.net&quot; skulle inkluderas eller ersättas. |
| 8 december 2020 | Uppdateringar av [Skapa nytt projekt](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/freeform-overview.html) i Workspace. |
| **November 2020** | |
| 24 november 2020 | Uppdateringar till [Panelöversikt](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/panels.html) i Workspace. |
| 24 november 2020 | Nya granskningsdokument för implementering: <ul><li>[Fullständig implementeringsgranskning](https://experienceleague.adobe.com/docs/analytics/implementation/review/full-review.html)</li><li>[Fokuserad implementeringsgranskning](https://experienceleague.adobe.com/docs/analytics/implementation/review/focused-review.html)</li></ul> |
| 24 november 2020 | Uppdaterad Analysis Workspace [Visualiseringar - översikt](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.html) sida. |
| 12 november 2020 | Ny sida på [Ärvd Adobe Analytics-implementering](https://experienceleague.adobe.com/docs/analytics/implementation/prepare/existing-implementation.html). |
| 2 november 2020 | Uppdaterat dokument den [FTP för klassificeringar](https://experienceleague.adobe.com/docs/analytics/export/ftp-and-sftp/set-up-ftp-accounts/ftp-saint.html). |
| **Oktober 2020** | |
| 23 oktober 2020 | Arbetsytans radvisualisering: [Alternativ för glidande medeltrendlinje](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/line.html): Den här inställningen har lagts till i [!UICONTROL Line] trendlinjeinställningar för visualisering. Ett glidande medelvärde kallas även för ett rullande medelvärde och använder ett visst antal datapunkter (som bestäms av en **[!UICONTROL Periods]** ), beräknar ett medelvärde för dem och använder medelvärdet som en punkt på raden. |
| 23 oktober 2020 | Arbetsytan [Hjälpsida för prestanda](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/workspace-faq/optimizing-performance.html) visar de olika faktorer som påverkar projektets prestanda och länkar till tips för optimering. |
| 23 oktober 2020 | Förbättringar har lagts till i dokumentationen för Adobe Analytics kontrollpaneler. I det mobila styrkortet i Workspace matchar nu styrkortets format appen. |
| **September 2020** | |
| 17 september 2020 | [Ladda ned 50 000 artiklar för en enda dimension](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/download-send.html#download-items): Du kan nu ladda ned 50 000 objekt för en enda dimension i en friformstabell med segment och filter. Det ger dig åtkomst till mer än de 400 dataraderna utanför Analysis Workspace. |
| 17 september 2020 | [Förbättringar av linjevisualisering](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/line.html): <ul><li>Du kan visa eller dölja X-axeln och Y-axeln för alla [!UICONTROL Line] visualisering. Detta kan vara praktiskt när du [!UICONTROL Line] visualiseringar är mer kompakta.</li><li>Du kan lägga över en etikett för minsta och högsta värde på alla linjevisualiseringar för att snabbt markera toppar och dalar i ett mätresultat.</li><li>Du kan täcka över olika regressionstrendlinjer på alla linjevisualiseringar för att lättare se trenden i data. Alternativen inkluderar [!UICONTROL Linear], [!UICONTROL Logarithmic], [!UICONTROL Exponential], [!UICONTROL Power] och [!UICONTROL Quadratic].</li></ul> |
| 17 september 2020 | Nya datumintervall i Workspace: Vi har lagt till fem nya datumintervall så att du kan välja mellan datumintervall som inte innehåller data för delar av dagen från och med idag: Senaste 7 fullständiga dagarna, Senaste 14 fullständiga dagarna, Senaste 30 fullständiga dagarna, Senaste 60 fullständiga dagarna, Senaste 90 fullständiga dagarna |
| 17 september 2020 | Ny dokumentation om [Media Concurrent Viewer panel i Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/media-concurrent-viewers.html) |
| **Augusti 2020** | |
| 31 augusti 2020 | Förbättringar har lagts till i [fältbaserad sammanfogningsdokumentation](https://experienceleague.adobe.com/docs/analytics/components/cda/field-based-stitching.html) i Enhetsövergripande analys. |
| **Juli 2020** | |
| 21 juli 2020 | Viktiga uppdateringar och revideringar av [Enhetsövergripande analys](/help/components/cda/overview.md). Tillagd [Fältbaserad stygn](/help/components/cda/field-based-stitching.md). |
| 16 juli 2020 | Nya förinställningar för datumintervall i Arbetsyta. Fyra nya datumintervall har lagts till: ([!UICONTROL This week/month/quarter/year (excluding today)]). På så sätt kan du välja från datumintervall som inte innehåller data för delar av dagen från och med idag. |
| **Juni 2020** | |
| 25 juni 2020 | Ny dokumentation för [Panelen Snabbinsikter](/help/analyze/analysis-workspace/c-panels/quickinsight.md) i Workspace. Där finns vägledning för icke-analytiker och nya användare av Analysis Workspace som snabbt och enkelt kan besvara affärsfrågor. |
| 25 juni 2020 | Ny dokumentation för [Analyser för målpanelen](/help/analyze/analysis-workspace/c-panels/a4t-panel.md) i Workspace. Ni kan analysera Adobe Target aktiviteter och upplevelser med lyft och självförtroende. |
| 18 juni 2020 | Ny dokumentation om [Attribution: Algoritmisk attribuering](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/attribution/algorithmic.html) |
| 18 juni 2020 | Ny dokumentation om [Attribut: Anpassade fönster för sökning](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/attribution/models.html#lookback-windows) |
| 18 juni 2020 | Ny dokumentation för [Projektroller](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/share-projects.html) för delade arbetsyteprojekt. När du delar ett Workspace-projekt kan du nu placera mottagare i en av tre projektroller, beroende på vilken projektupplevelse du vill att de ska ha: Redigera, Duplicera och Visa. |
| 18 juni 2020 | Ny dokumentation om [Visa endast arbetsyteprojekt](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/view-only-projects.html). Projekt kan delas med användare som&quot;Kan visa&quot;. När en Visa-mottagare öppnar det delade projektet får de en mer restriktiv projekterfarenhet, utan någon vänster spårsträcka och begränsad interaktion. |
| 18 juni 2020 | Ny dokumentation om [Projektroller](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/share-projects.html) för delade arbetsyteprojekt. När du delar ett Workspace-projekt kan du nu placera mottagare i en av tre projektroller, beroende på vilken projektupplevelse du vill att de ska ha: Redigera, Duplicera och Visa. |
| 18 juni 2020 | Ny dokumentation om [Samredigera projekt på arbetsytan](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/share-projects.html). Mottagare som läggs till i rollen Kan redigera kan spara över ett projekt som har delats med dem. Detta gäller både administratörer och icke-administratörer. |
| **Maj 2020** |  |
| 31 maj 2020 | Ny dokumentation om [API för massdatainmatning](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/bdia.md) |
| 21 maj 2020 | Ny dokumentation för [Adobe Analytics dashboards](https://experienceleague.adobe.com/docs/analytics/analyze/mobapp/home.html) |
| 21 maj 2020 | Ny dokumentation om [tillgänglighetsförbättringar](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/workspace-faq/aw-accessibility.html) till Analysis Workspace, inklusive förbättrad tangentbordsnavigering, färgkontrast och skärmläsarstöd. |
| **April 2020** |  |
| 28 april 2020 | Dokumentation för mätvärdet [Content Velocity](/help/components/metrics/content-velocity.md) har lagts till. |
| 16 april 2020 | Dokumentation om hur man skapar automatiskt [!UICONTROL Freeform Tables] från ett tomt läge. Tidigare gick det inte att släppa komponenter direkt i ett tomt projekt eller på en tom panel, utan du var tvungen att lägga till en friformstabell först. Nu kan du släppa komponenter direkt i ett tomt projekt eller på en tom panel, så skapas en friformstabell automatiskt i det format som rekommenderas. Dessutom har vi förbättrat hur blandade komponenttyper (som mått och mätvärden) hanteras när de släpps tillsammans i en tom [!UICONTROL Freeform Table]. |
| **Mars 2020** |  |
| 12 mars 2020 | [Publicera segment i Experience Cloud](/help/components/segmentation/segmentation-workflow/seg-publish.md) har uppdaterats. |
| 12 mars 2020 | Uppdateringar av svarstider för CDA-sammanfogning. |
| 12 mars 2020 | Stöd för flera rapportsviter i Workspace. Nu kan du samla in data från flera rapportsviter i ett enda projekt och visa dem sida vid sida. [Läs mer …](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/multiple-report-suites.html) |
| 12 mars 2020 | Utbildningsmall i Workspace. Den här nya standardmallen vägleder dig bland vanliga termer och steg när du skapar din första analys i Workspace. Den finns som en standardmall i det modala fönstret Nytt projekt och ersätter det exempelprojekt som finns idag för nya användare, som inte har andra projekt i sin lista. [Läs mer …](/help/analyze/analysis-workspace/build-workspace-project/starter-projects.md) |
| **Februari 2020** |  |
| 27 februari 2020 | Dokumentation för [Adobe Analytics Labs](/help/analyze/labs.md) har lagts till. |
| 25 februari 2020 | [`useLinkTrackSessionStorage`](/help/implement/vars/config-vars/uselinktracksessionstorage.md)-variabel har lagts till. |
| 20 februari 2020 | Ny arbetsytemall för organisationer som använder analyser på olika enheter. Den här mallen visar hur effektivt funktionen för analys över olika enheter sammanfogar besök och utbildar dig om mått och mätvärden som är specifika för just den här analysen. En rapportsvit som har analys över olika enheter krävs. Se [Ställ in enhetsövergripande analys](/help/components/cda/setup.md) för mer information. |
| 20 februari 2020 | Nya snabbtangenter i Workspace:<ul><li>Visa/dölj alla paneler: `alt + m`</li><li>Visa/dölj aktiv panel: `alt + ctrl + m`</li><li>Sök i vänster list: `ctrl + /`</li><li>Gå till nästa panel: `alt + Right Key`</li><li>Gå till föregående panel: `alt + Left Key`</li></ul>[Läs mer …](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/fa-shortcut-keys.html) |
| 20 februari 2020 | Förbättringar av arbetsytan: <ul><li>När en panel eller visualisering släpps i Workspace växlar den vänstra listen nu automatiskt till komponenter för ett smidigare arbetsflöde.</li><li>Mallkomponenter kan nu användas direkt (till exempel taggas, anges som favoriter eller godkännas).</li><li>Filtrerade mätvärdes- och segmentlistor har en plusknapp för att lägga till en ny komponent om du inte hittar det du behöver.</li></ul> |
| 20 februari 2020 | Arbetsytefelsökaren lades till på Hjälp-menyn, vilket ger ett smidigare sätt att aktivera den för felsökning av arbetsytebegäranden. [Läs mer …](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/reporting-tricks.md) |
| 18 februari 2020 | [`writeSecureCookies`](/help/implement/vars/config-vars/writesecurecookies.md)-variabel har lagts till. |
| 12 februari 2020 | Uppdateringar och omorganisering av dokumentationen för [marknadsföringskanaler](/help/components/c-marketing-channels/c-getting-started-mchannel.md). |
| 12 februari 2020 | Nya snabbtangenter har lagts till i [den här arbetsytesidan](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/fa-shortcut-keys.html) |
| 7 februari 2020 | Uppdateringar av [Konfigurera Analytics över enheter](/help/components/cda/setup.md) och [Vanliga frågor och svar](/help/components/cda/faq.md). |
| 4 februari 2020 | Fullständig omarbetning av [användarhandboken för implementering](/help/implement/home.md). |
| 22 januari 2020 | Sidan om frihandstabeller har uppdaterats med information om nya [Freeform Table Builder](/help/analyze/analysis-workspace/visualizations/freeform-table/freeform-table.md). |
| **Januari 2020** | |
| 24 januari 2020 | Uppdateringar av [Radinställningar](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/visualizations/freeform-table/column-row-settings/table-settings.html#cja-workspace) i Workspace. |
| 16 januari 2020 | Ny dokumentation om [Frihandsformstabellverktyget](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/freeform-table/freeform-table.html). Med tabellverktyget aktiverat kan du dra och släppa i många mått, uppdelningar, mätvärden och segment för att skapa tabeller som besvarar mer komplexa affärsfrågor. Data uppdateras inte omedelbart. I stället uppdateras de när du klickar på **[!UICONTROL Build]**, vilket sparar tid när du väl vet vilken tabell du vill skapa. Dessutom har den här funktionen följande:<ul><li>**Förhandsgranskning**: Du kan förhandsgranska tabellformatet innan du lägger tid på att återge verkliga data.</li><li>**Inställningar för flexibla rader och uppdelning**: Du kan ange rad- och uppdelningsnivåer för alla måttrader. Tidigare användes standardvärden som inte gick att ändra förrän data returnerades.</li><li>**Uppdelning efter position**: Du kan ange att måttrader alltid ska _delas upp efter position_ i stället för _efter ett visst objekt_ (standard).</li><li>**Ordna statiska rader manuellt**: Du kan ordna statiska rader manuellt så att tabellraderna visas exakt som du vill ha dem. Tidigare kunde statiska rader bara sorteras efter en mätvärdeskolumn eller i bokstavsordning.</li></ul> |
| 13 januari 2020 | [Adobe Analytics och webbläsarcookies](/help/technotes/cookies/cookies.md) har lagts till. |
| 13 januari 2020 | Ändrad [Vilket Adobe Analytics-verktyg ska jag använda](/help/analyze/get-started/which-analytics-tool.md) sida. |

### 2019 {#year2019}

| Funktion | Beskrivning |
| --- | --- |
| 19 december 2020 | Ändrad som standard [Lagringsgräns för FTP-data](https://experienceleague.adobe.com/docs/analytics/export/ftp-and-sftp/ftp-limits.html) till 10 GB. |
| 29 november 2019 | Dokumentationen för [dataflöden](/help/export/analytics-data-feed/data-feed-overview.md) har setts över. |
| 25 november 2019 | Nytt avsnitt om Slutet av livscykeln för Tvinga begränsningar för IP-inloggning. |
| 21 november 2019 | Ny dokumentation för [Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-landing.html). |
| 21 november 2019 | Uppdaterat [Vanliga frågor om arbetsflödet i Audience Analytics](https://experienceleague.adobe.com/docs/analytics/integration/audience-analytics/audience-analytics-workflow/mc-audiences-faqs.html) för att ange tillgänglighet i LiveStream. |
| 25 oktober 2019 | Uppdaterat [Adobe Analytics Key Concepts](/help/technotes/terms.md) sida. |
| 10 oktober 2019 | Uppdatera till tabellsummor i frihand: de innehåller nu två summor, en **[!UICONTROL Table total]** och **[!UICONTROL Grand total]**. Raden med tabellsumman avser de [rapportfilter](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/freeform-table/pagination-filtering-sorting.html) som används. Tidigare påverkades summorna bara av segmentering. [Läs mer](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/freeform-table/workspace-totals.html)<br/>Dessutom har alternativen **[!UICONTROL Show Totals]** och **[!UICONTROL Show Grand Total]** lagts till i **[!UICONTROL Column Settings]**.<br/>Med den här förändringen av totalsummor för friformstabeller uppdateras beroende visualiseringar (som länkade **[!UICONTROL Summary Number]**-visualiseringar) samt exporterade CSV- och PDF-data. |
| Oktober 10,2019 | I arbetsytan lades möjligheten att enkelt ta bort &#39;Ospecificerad (ingen)&#39; till som ett alternativ för att rapportera filter. |
| Oktober 10,2019 | I Workspace har de lila granularitetskomponenterna (Minute, Hour, Day, Week, Month, Quarter, Year) tagits bort. Du **behöver inte göra något** om du tidigare har använt någon av de lila tidskomponenterna.<br/>Den här ändringen innebär även att det lila avsnittet **[!UICONTROL Time]** har bytt namn till **[!UICONTROL Date Ranges]**. |
| 1 oktober 2019 | Ny artikel på [Summor för arbetsyta](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/visualizations/freeform-table/workspace-totals.html#cja-workspace). |
| 28 september 2019 | Nya artiklar om [konfigurationsvariabler för JavaScript-implementering](/help/implement/vars/config-vars/configuration-variables.md). |
| 19 september 2019 | Reviderad segmenteringsdokumentation som förklarar [Behållare för logikgrupp](https://experienceleague.adobe.com/docs/analytics/components/segmentation/segmentation-workflow/seg-sequential-build.html#logic-group-containers). |
| 12 september 2019 | Ny dokumentation för [Journey IQ: Enhetsövergripande analyser](/help/components/cda/overview.md). |
| 12 september 2019 | Uppdatera [Beräknade mätsummor](https://experienceleague.adobe.com/docs/analytics/components/calculated-metrics/calcmetrics-reference/cm-totals.html) -dokument. |
| 28 augusti 2019 | Ny artikel om [progressiva webbappar (PWA) för Analytics](/help/technotes/pwa.md). |
| 8 augusti 2019 | Ny artikel om [summor för beräknade mätvärden](/help/components/c-calcmetrics/cm-totals.md). |
| 8 augusti 2019 | Förtydligande av [sessionsdata med aktiverade tidsstämplar](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/timestamp-optional.md). |
| 8 augusti 2019 | I Workspace har Adobe ökat gränsen för objekt som kan placeras i ett statiskt nedrullningsbart filter från 50 till 200. Den här förbättringen kommer till nytta i flera olika sammanhang, till exempel kan du nu lägga till alla länder (195) eller alla delstater och provinser i USA (52) i ett filter. |
| 2 augusti 2019 | Större uppdatering av [Analytics-ordlistan](/help/technotes/terms.md). |
| 22 juli 2019 | Tillägg för Magento: Mall för marknadsföring och handel i [dokumentationen om Analysis Workspace-mallarna](/help/analyze/analysis-workspace/build-workspace-project/starter-projects.md). |
| 18 juli 2019 | Uppdaterade [inställningar för kohorttabeller](/help/analyze/analysis-workspace/visualizations/cohort-table/t-cohort.md). |
| 18 juli 2019 | I den vänstra listen i Workspace kan användarna nu välja att _Visa objekt från de senaste 18 månaderna_. Tidigare var den perioden högst 6 månader. Detta gör det enklare att jämföra med sidor eller kampanjer från föregående år, upp till för 18 månader sedan. |
| 18 juli 2019 | Dokumentation om en ny arbetsytemall som kallas [&quot;Magento: Marketing &amp; Commerce&quot;](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/starter-projects.html) till Analysis Workspace. Den är särskilt utformad för Magentos e-handelskunder, men alla återförsäljare kan använda den för att få unika insikter i e-handelsverksamheten. |
| 13 juni 2019 | Nya färdiga filter har lagts till i den vänstra fältsökningen i Workspace. Utöver det som redan finns (mått, mätvärden, godkända med mera) har vi lagt till nya filter, som beräknade värden, kundattribut, evariabler, egenskaper och video, för att det ska vara enklare att hitta de komponenter du behöver. |
| 4 juni 2019 | Ny handbok har skrivits med namnet [Migrera från en analysplattform från tredje part till Adobe Analytics](/help/technotes/ga-to-aa/home.md). |
| 30 maj 2019 | [Referensen för datafeed-kolumner](/help/export/analytics-data-feed/c-df-contents/datafeeds-reference.md) har setts över. |
| 9 maj 2019 | En ny inställning har lagts till i inställningarna för Flödesvisualisering: Inkludera upprepningsinstanser. Se [Flödesinställningar](/help/analyze/analysis-workspace/visualizations/c-flow/create-flow.md) |
| 11 apr 2019 | Förbättringar av de bästa sätten att optimera arbetsytan: [Optimera prestanda](/help/analyze/analysis-workspace/new-features-in-analysis-workspace.md) |
| 11 apr 2019 | Uppdateringar av [Optimera Workspace-prestanda](/help/analyze/analysis-workspace/workspace-faq/optimizing-performance.md). |
| 14 mars 2019 | Större uppdatering av regional datainsamling. |
| 7 februari 2019 | Mindre uppdatering av inställningarna Ersätt den sista oktetten i IP-adresser med 0 och Dölj IP i [Allmänna kontoinställningar](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/general-acct-settings-admin.md). |
| 1 februari 2019 | Större uppdatering av implementeringsplugin-programmet [getPercentPageViewed](../implement/vars/plugins/getpercentpageviewed.md). |
| 17 januari 2019 | [Kohortanalys](/help/analyze/analysis-workspace/visualizations/cohort-table/cohort-analysis.md) - Större förbättringar av kohortanalysen gör att du kan:<ul><li>Använda segmentinkludering och returnera mätvärden separat. </li><li>Visa bortfall i stället för lojalitet.</li><li>Visa latenstabeller (förfluten tid före och efter en inkluderingshändelse).</li><li>Anpassa kohortmått (för att gruppera besökare baserat på en evariabel, inte bara tid).</li><li>Utföra en rullande kohortberäkning: beräkna lojalitet/bortfall baserat på tidigare tidsperiod, inte ursprunglig kohort. </li><li>Lägga till flera mätvärden i inkluderings- och returfält samt använda segment. (Beräknade värden stöds inte.)</li></ul> |
| 17 januari 2019 | [Visa densitet](/help/analyze/analysis-workspace/build-workspace-project/view-density.md). Med den här nya inställningen kan du visa mer data på en enda skärm genom att minska den lodräta utfyllnaden i den vänstra listen, friformstabeller och kohorttabeller. Tillgängligt via Projekt > Projektinformation och inställningar. |
| 17 januari 2019 | [Stöd för flervärdesvariabler i Attribution](/help/analyze/analysis-workspace/attribution/overview.md). Vissa mått i Analytics kan innehålla flera värden för en enda träff, till exempel listvariabler, produktvariabler, listegenskaper eller evariabler för försäljning. Med Analysis Workspace kan du använda Attribution på någon av dessa typer av variabler på träffnivå. |
