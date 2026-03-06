---
title: Uppdateringar av teknisk dokumentation för Adobe Analytics
description: Viktiga uppdateringar av dokumentationsuppsättningen för Adobe Analytics.
short-title: Analytics documentation updates
feature: Release Notes
exl-id: fe8e3c4c-6782-46f7-8e28-4f8f54807788
mini-toc-levels: 3
source-git-commit: 761ee1993296cab3c29f706d6e1c79bb08b46303
workflow-type: tm+mt
source-wordcount: '6585'
ht-degree: 17%

---

# Uppdateringar av teknisk dokumentation för Adobe Analytics

Innehållsuppdateringar för Adobe Analytics-dokumentation sedan januari 2019.

* Mer information om [!UICONTROL Customer Journey Analytics] finns i [Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-landing.html?lang=sv-SE).
* Mer information om Adobe direktuppspelade medietjänster finns i [Mäta ljud och video i Analytics](https://experienceleague.adobe.com/docs/media-analytics/using/media-overview.html?lang=sv-SE).

## Information om större dokumentationsuppdateringar

### 2026 {#year2026}

| Funktion | Beskrivning |
| --- | --- |
| **Mars 2026** | |
| Identifierade standardalternativet för IP-förfalskning för nya rapportsviter | Tillagd information om att **Ta bort IP-adress** är standardalternativet [IP-förfalskning för nya rapportsviter](/help/admin/tools/manage-rs/edit-settings/general/general-acct-settings-admin.md). |
| **Februari 2026** |  |
| Lagt till information om hur du använder geo- och teknikrapporter | Lagt till information om skillnader när du använder geo- och teknikrapporter [för olika Analytics-produkter](/help/analyze/get-started/analytics-product-comparison.md)-artikel. |
| **Januari 2026** | |
| Regelverktyget för klassificeringsuppsättningar | Dokumentation för den nya funktionen [Regelbyggaren i funktionen för klassificeringsuppsättningar](/help/components/classifications/sets/manage/rules.md). |
| Enhetsdiagram | Referenser till funktionen [för enhetsdiagram har tagits bort](https://experienceleague.adobe.com/sv/docs/discontinued/using/device-graph). |

### 2025 {#year2025}

| Funktion | Beskrivning |
| --- | --- |
| **November 2025** | |
| Viktiga överväganden om VISTA-regler | Viktiga överväganden gällande [Vista-regler](/help/technotes/vista.md) har uppdaterats. |
| Datakolumn-ID har lagts till för konversationsbaserade AI-verktyg | [kolumnreferens-ID &#x200B;](/help/export/analytics-data-feed/c-df-contents/datafeeds-reference.md) för konversationsbaserade AI-verktyg har lagts till i kolumnen ref_type. |
| **Oktober 2025** | |
| Klassificeringsuppsättningar | Uppdateringar av dokumentationen för [klassificeringsuppsättningar](/help/components/classifications/sets/overview.md). |
| Attributionskonfiguration | Ytterligare uppdateringar som återspeglar de nya attributkonfigurationsalternativen för modell-, container- och lookback-fönster. |
| Ytterligare förbättringar av besöksidentifiering | Avsnittet [Besökaridentifiering](/help/implement/id/overview.md) har lagts till, och det rekommenderade sättet att identifiera besökare för alla implementeringstyper beskrivs. |
| **September 2025** | |
| Förbättrad identifiering av besökare | Tydligare rutiner för besökaridentifiering, med fokus på syftet med variablerna [`trackingServer`](/help/implement/vars/config-vars/trackingserver.md) och [`trackingServerSecure`](/help/implement/vars/config-vars/trackingserversecure.md) i AppMeasurement. |
| **Augusti 2025** | |
| Dataflödenamn måste vara unika | Tydligare varför [dataflödets namn måste vara unika](/help/export/analytics-data-feed/df-faq.md#must-feed-names-be-unique). |
| Varningar vid borttagning | Lagt till borttagningsvarningar för artiklar i avsnitten [Klassificeringsregelbyggaren](/help/components/classifications/crb/classification-rule-builder.md) och [Klassificeringsimporteraren](/help/components/classifications/importer/c-working-with-saint.md). |
| **Juli 2025** | |
| Bearbetar regler | Dokumentationen för bearbetningsregler har gjorts om helt och hållet och innehåller mer information om gränssnittet och aktuella användningsfall. |
| Debugger | Ny artikel om hur du aktiverar, använder och inaktiverar felsökningsfunktionen för projekt i Analysis Workspace. |
| Prestandarekommendation för visualisering av flöde | Tillagd information om att mer än 10 noder utökas i en enda flödesvisualisering kan påverka rapporttiden. |
| Granska och uppdatera | Granska och uppdatera Analysis Workspace-dokumentationen. Dokumentationen är nu synkroniserad med Customer Journey Analytics-dokumentationen för Analysis Workspace. |
| **Juni 2025** | |
| Nya kortkommandofunktioner | Med nya kortkommandon i Analysis Workspace kan du nu [flytta Workspace-paneler](/help/analyze/analysis-workspace/build-workspace-project/fa-shortcut-keys.md#move-panel-actions) uppåt och nedåt i ett projekt. |
| **Mars 2025** |  |
| Analyslager | [Analysinventering](/help/admin/tools/analytics-inventory.md) ger en omfattande översikt över din Adobe Analytics-miljö, inklusive antalet projekt och komponenter, rapportsviter, användare och mer. |
| Customer Journey Analytics uppgraderingsguide | Gör att du kan generera en [steg-för-steg-guide](https://experienceleague.adobe.com/sv/docs/analytics-platform/using/compare-aa-cja/upgrade-to-cja/cja-upgrade-recommendations?lang=en#recommended-upgrade-steps-for-most-organizations) för uppgradering från Adobe Analytics till Customer Journey Analytics. |
| Tydligare datumformat i Data Warehouse-exporter | Tidsbaserade dimensionsvärden i Data Warehouse-exporter har en annan datumformatering än standard. Tillagd information som förklarar hur datumvärden från Data Warehouse-exporter kan tolkas. <p>Se [Dimensioner stöds på ett annat sätt (datumformatering som inte är standard)](/help/export/data-warehouse/component-support.md#dimensions-supported-in-a-different-way-non-standard-date-formatting) i [Komponentstöd i Data Warehouse](/help/export/data-warehouse/component-support.md).</p> |
| Uppdaterad information om IP-undantag | Tillagd information som förklarar att [IP-undantag](/help/admin/tools/exclude-ip.md) kan ta upp till 5 minuter innan de träder i kraft och att ändringarna bara gäller för nya träffar (data som fångats in innan undantaget ställdes in påverkas inte). <p>Innehållets layout har också uppdaterats för att förbättra läsbarheten.</p> |
| **Februari 2025** |  |
| Uppdaterad information om att pausa och återaktivera en datafeed | När [pausar och återaktiverar en datafeed](/help/export/analytics-data-feed/df-manage-feeds.md#activate-a-data-feed) klargjordes beteendet för livefeeds. Databearbetningen sker inte från den tidpunkt då flödet pausas till den tidpunkt då det återaktiveras. |
| Lagringsperiod för ändrat transaktions-ID | Kvarhållningsperioden för transaktions-ID på 90 dagar förlängdes till 25 månader. Variabeln transactionID identifierar en transaktion unikt så att träffen kan koppla till data som överförs via datakällor. Se [sidvariabler](/help/implement/vars/page-vars/transactionid.md) och [datakällor](/help/import/data-sources/transactionid.md). |
| Livesream API - klientimplementering | Använd [Livesream-klientimplementeringen](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/livestream/clientcode/) för att förbruka data från Livesream. |
| Uppdatera till klassificerings-API | Du kan nu [ta bort enskilda klassificeringsfält eller -nycklar från servern](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/classifications/remove-values/). Detta är ett alternativ till att ta bort en hel klassificeringsdatamängd med metoden DELETE. |
| **Januari 2025** |  |
| API-referens för dataflöden | Referensen [för API:t för datafeeds &#x200B;](https://adobedocs.github.io/analytics-2.0-apis/?urls.primaryName=Data%20Feeds%20APIs) är nu tillgänglig. |
| Ny dokumentation om schemaläggning i nya Report Builder | [Schemaläggning](/help/analyze/report-builder/schedule-reportbuilder.md) tillåter inte bara att du schemalägger nya Report Builder-arbetsböcker. Dessutom kan du hämta metadata för gamla schemalagda aktiviteter när du konverterar äldre arbetsböcker. |
| Förbättringar av rapporter (kallas även mallar) i Analysis Workspace | Det finns nu olika förbättringar för rapporter (kallas även [mallar](/help/analyze/analysis-workspace/templates/use-templates.md)) |


### 2024 {#year2024}

| Funktion | Beskrivning |
| --- | --- |
| **Oktober 2024** |  |
| Ny information om begärandefaktorer i Analysis Workspace prestanda | En ny [Request factor](/help/analyze/analysis-workspace/workspace-faq/optimizing-performance.md#request-factors)-sektion i artikeln [Optimize Analysis Workspace performance](/help/analyze/analysis-workspace/workspace-faq/optimizing-performance.md) förklarar hur begäranden behandlas och de olika faktorer som påverkar bearbetningstiderna. |
| Nya Report Builder | [Ny dokumentation](/help/analyze/report-builder/rb-overview.md) för det strömlinjeformade Report Builder-tillägget som stöds i Mac, Windows och webbläsare. |
| **Augusti 2024** | |
| Varningshanteraren | Effektiv dokumentation om [Varningshanteraren](/help/components/alerts/alert-manager.md). Uppdaterat för tydlighet och precision. |
| **Juli 2024** | |
| Slutförda händelser | Effektiv dokumentation om [success events](/help/admin/tools/manage-rs/edit-settings/conversion-var-admin/c-success-events/success-event.md). Uppdaterat för tydlighet och precision. |
| Minst en kontotyp måste väljas vid hantering av platser | Tydligare är att när administratörer [begränsar de kontotyper som används för export och import](/help/components/locations/locations-manager.md#limit-the-account-types-that-are-available-to-users) måste minst en kontotyp väljas. |
| Lagt till information om snabba beräknade mätvärden | Uppdaterad information i [Metrisk](/help/analyze/analysis-workspace/components/apply-create-metrics.md) för att förtydliga skillnaden mellan [beräknade mått som skapas i beräkningsverktyget](/help/analyze/analysis-workspace/components/apply-create-metrics.md#create-calculated-metrics-for-all-projects) och [de som skapas som snabbberäknade mätvärden i ett enskilt projekt](/help/analyze/analysis-workspace/components/apply-create-metrics.md#create-calculated-metrics-for-a-single-project). Ytterligare information om slangarna för att skapa snabba beräknade mätvärden.<p>Beräknade mätvärden som har skapats i verktyget för beräknade mätvärden är tillgängliga i komponentlistan och kan tillämpas på projekt i hela organisationen, medan beräknade mätvärden som har skapats som snabba beräknade mätvärden endast är tillgängliga i det projekt där de skapades.</p><p>Uppdaterad information i [Build metrics](/help/components/calculated-metrics/workflow/c-build-metrics/cm-build-metrics.md) för att göra liknande förtydliganden.</p> |
| Lagt till threads.net i dimensionen &#39;Refererartyp&#39; | threads.net har lagts till i listan över sociala nätverk som används i dimensionen [&#x200B; för &#x200B;](/help/components/dimensions/referrer-type.md)-referenstypen. |
| Uppdaterad dokumentation för hantering av dataflöden | Uppdaterad information i [Hantera dataflöden](/help/export/analytics-data-feed/df-manage-feeds.md) för att förbättra tydligheten. <p>Bland uppdateringarna finns:</p><ul><li>Skapade separata avsnitt för olika uppgifter för att göra informationen enklare att skanna och använda.</li><li>Lagt till information om förändringar i beteendet för liveflöden som återaktiveras. Dessa ändringar är för närvarande begränsade och är ännu inte tillgängliga för alla kunder.</li><li>Tillagd information som anger att dataflöden måste ha statusen Aktiv innan de kan tas bort.</li> |
| Uppdaterade vanliga felmeddelanden | Mindre uppdateringar av de [vanliga felmeddelandena](/help/analyze/analysis-workspace/workspace-faq/error-messages.md) har gjorts. |
| **Juni 2024** | |
| Uppdaterat produktnamn som hänvisar till funktioner för direktuppspelande medietjänster | Ersatte instanser av&quot;Media Analytics&quot; och&quot;Streaming Media&quot; med namnet&quot;Streaming Media Collection Add-on&quot; och&quot;Streaming Media Collection&quot; när de refererar till en uppsättning funktioner för direktuppspelande media som samlar in direktuppspelningsdata och visar dessa i Analysis Workspace. <p>Dessa uppdateringar är tillgängliga i hela Adobe Analytics-dokumentationen samt i [dokumentationen för direktuppspelad mediesamling](https://experienceleague.adobe.com/sv/docs/media-analytics/using/media-overview).</p> |
| Förbättrad varningsdokumentation | Uppdaterad och förbättrad dokumentation om varningar. Uppdateringarna innehåller information om [att skapa aviseringar](/help/components/alerts/alert-builder.md), [hantera aviseringar](/help/components/alerts/alert-manager.md) och [översiktsinformation](/help/components/alerts/alerts-overview.md). |
| `cookieDomainPeriods` har tagits bort | Nu när AppMeasurement automatiskt identifierar rätt domän att ange cookies för, är variabeln [`cookieDomainPeriods`](/help/implement/vars/config-vars/cookiedomainperiods.md) föråldrad. |
| Dokumentation för Data Connectors | Flyttade Data Connectors-sidan för förfallodatum till [Avbrutna produkter](https://experienceleague.adobe.com/sv/docs/discontinued/using/data-connectors). |
| **Maj 2024** | |
| Nödvändig information vid användning av organisationsprincipbegränsningar med Google Cloud Platform i Data Feeds och Data Warehouse | Det Adobe-ägda organisation-ID:t för Google Cloud-plattformen har lagts till i dokumentationen för [datafeeds](/help/export/analytics-data-feed/create-feed.md) och [Data Warehouse](/help/export/data-warehouse/create-request/dw-request-report-destinations.md). <p>Den här informationen krävs bara för organisationer som använder [begränsningar för organisationsprinciper](https://cloud.google.com/storage/docs/org-policy-constraints) i Google Cloud Platform.</p> |
| Dokumentation om hur du lägger till komponenter i projekt | Allmän information om hur du [lägger till olika typer av komponenter i projekt i Analysis Workspace](/help/analyze/analysis-workspace/components/use-components-in-workspace.md) har lagts till. |
| Uppdaterad Advertising Analytics-dokumentation | Dokumentationen har uppdaterats i enlighet med uppdateringarna i användargränssnittet för [Advertising Analytics](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-workflow.md). |
| Explicit mappa XDM-objektvariabler till kontextdatavariabler | Dokumenterade möjligheten att [explicit ange kontextdatavariabler med XDM-objektvariabelmappning](/help/implement/aep-edge/xdm-var-mapping.md#explicit-mapping). |
| Ny dokumentation för uppgradering från Adobe Analytics till Customer Journey Analytics | För organisationer som uppgraderar från Adobe Analytics till Customer Journey Analytics finns det flera uppgraderingsalternativ och många överväganden att tänka på baserat på organisationens nuvarande Adobe Analytics-implementering och långsiktiga mål.<p>Nu finns det nya dokumentationsresurser som hjälper dig att förstå:</p><ul><li>De olika uppgraderingssökvägarna som finns</li><li>Vilka uppgraderingsalternativ som finns tillgängliga baserat på en organisations aktuella implementering av Adobe Analytics</li><li>Fördelar och nackdelar med varje uppgraderingsväg</li><li>Stegvisa anvisningar för varje uppgraderingsväg</li><li>Att tänka på vid hantering av historiska data</li><li>Och mycket mer!</li></ul><p>[Kom igång med uppgraderingen till Customer Journey Analytics](https://experienceleague.adobe.com/sv/docs/analytics-platform/using/compare-aa-cja/upgrade-to-cja/cja-upgrade-getstarted).</p> |
| Uppdaterad dokumentation om anpassade datumintervall | Skärmbilder och procedurer som rör [att skapa anpassade datumintervall](/help/analyze/analysis-workspace/components/calendar-date-ranges/custom-date-ranges.md) har uppdaterats för att matcha de aktuella produktfunktionerna och designen. |
| **April 2024** | |
| Borttagen dokumentation för &quot;ägare&quot; i klassificeringsuppsättningar | Filtret och kolumnen Ägare togs bort från [Klassificeringsuppsättningshanteraren](/help/components/classifications/sets/manage-sets.md) och fältet Ägare togs bort från [klassificeringsuppsättningsinställningarna](/help/components/classifications/sets/manage/settings.md). <p>Dokumentationen uppdaterades för att ta bort filtret, kolumnen och fältet.</p> |
| Komprimerbara avsnitt har tagits bort i dokumentationen om hur du konfigurerar platser för molnimport och -export | Borttagna komprimerbara avsnitt i [Konfigurera molnimport och exportplatser](/help/components/locations/configure-import-locations.md) för information om molnkontotyper. |
| **Mars 2024** | |
| AppMeasurement Update | [Versionsinformation](/help/implement/appmeasurement-updates.md) om AppMeasurement Update v2.26.0.<br/>Innehåller referens till och uppdatering av [`cookieDomainPeriods`](/help/implement/vars/config-vars/cookiedomainperiods.md) config-variabeldokumentation. |
| Användningsinformation om kolumnen Används i är tillgänglig först från och med september 2023. | Tydligare är att användningsinformationen för kolumnen **Används i** på [projektstartsidan](/help/analyze/landing.md) endast går tillbaka till september 2023. |
| **Februari 2024** | |
| Uppdateringar av information om hantering av Data Warehouse-förfrågningar | Tydligare är att användare som standard bara kan visa de förfrågningar de skapar när de [hanterar Data Warehouse-förfrågningar](/help/export/data-warehouse/data-warehouse-requests-manage.md). |
| Uppdateringar av projektdelningsdokumentation | Lagt till information om hur du [visar delade projekt](/help/analyze/analysis-workspace/curate-share/share-projects.md#view-projects-shared-with-you).<p>Effektivare information om att [dela enskilda eller flera projekt](/help/analyze/analysis-workspace/curate-share/share-projects.md#share-a-specific-project-role).</p> |
| Lagt till behörighetskrav för överföring av filer till Azure SAS och Azure RBAC i Data Warehouse och dataflöden | Exakta behörighetskrav för överföring av filer till Azure SAS och Azure RBAC lades till när [mål konfigurerades för Data Warehouse](/help/export/data-warehouse/create-request/dw-request-report-destinations.md) och [när mål konfigurerades för datafeeds](/help/export/analytics-data-feed/create-feed.md). |
| Lagt till behörighetskrav för att överföra filer till Amazon S3- och GCP-bucket i Data Warehouse och dataflöden | Exakta behörighetskrav för överföring av filer till Amazon S3- och Google Cloud Platform-bucket lades till när [mål för Data Warehouse](/help/export/data-warehouse/create-request/dw-request-report-destinations.md) och [konfigurerades för datafeeds](/help/export/analytics-data-feed/create-feed.md). |
| **Januari 2024** | |
| Komponentmigrering gäller för enskilda IMS-organ | Det klargjordes att [komponentmigrering](/help/admin/tools/component-migration/component-migration.md) inte stöder migrering mellan IMS-grupper. |
| Klarade att viss information endast är tillgänglig för administratörer | Tillagd information om att kolumnerna &quot;Senast använd&quot; och &quot;Används i&quot; som beskrivs i [Beräknad mätstatistik-hanterare](/help/components/calculated-metrics/workflow/cm-manager.md) och [Segmenthanterare](/help/components/segmentation/segmentation-workflow/seg-manage.md) endast är tillgängliga för systemadministratörer. |
| Uppdateringar av medieminarium - dokumentation om den genomsnittliga minuten-målgruppen | Uppdaterad information i [Medel - genomsnittlig minutmålspanel](/help/analyze/analysis-workspace/c-panels/average-minute-audience-panel.md) för att förbättra tydligheten.<p>Bland förbättringarna finns:</p> <ul><li>Förbättrad organisation av information</li><li>Tillagda steg för att ange uppgiftsbaserad information</li></ul> |

### 2023 {#year2023}

| Funktion | Beskrivning |
| --- | --- |
| **December 2023** | |
| Förbättrad dokumentation av robotregler | Uppdaterad information i [Förstå och konfigurera båda reglerna](/help/admin/tools/manage-rs/edit-settings/general/bot-removal/bot-rules.md) för att förbättra klarheten.<p>Bland förbättringarna finns:</p> <ul><li>Artikeltiteln har uppdaterats för att bli mer beskrivande</li><li>Förbättrad organisation av information</li><li>Tillagda steg för att ange uppgiftsbaserad information</li><li>Mer information om kraven för CSV-filer har lagts till vid överföring av robotregler</li></ul> |
| Avsnittet Nya rapporter | Ett nytt rapportavsnitt har lagts till som innehåller information om [Använd mallar](/help/analyze/analysis-workspace/templates/use-templates.md) och [skapa företagsmallar](/help/analyze/analysis-workspace/templates/create-templates.md). |
| Uppdateringar av dokumentationen för avvikelseidentifiering och bidragsanalys | Dokumentationen för avvikelseidentifiering och bidragsanalys fanns tidigare i ett avsnitt om Virtual Analyst. Följande ändringar har gjorts: <ul><li>Termen Virtual Analyst har tagits bort från dokumentationen.</li><li>Avsnittet om [avvikelseidentifiering](/help/analyze/analysis-workspace/c-anomaly-detection/anomaly-detection.md) flyttades direkt under Analysis Workspace-avsnittet.</li><li>Bidragsanalysdokumentationen slogs samman i dokumentationen för avvikelseidentifiering.</li></ul> |
| &quot;Attribution IQ&quot; ändrad till &quot;Attribution&quot; | Alla instanser av Attribution IQ har ändrats till [Attribution](/help/analyze/analysis-workspace/attribution/overview.md) i dokumentationen. |
| **November 2023** | |
| Uppdateringar av Activity Map aktiverings-/aktiveringsämne | [Webbinnehåll för SDK](/help/analyze/activity-map/getting-started.md) (både manuellt och via Adobe Experience Platform-taggtillägg) har lagts till. |
| **Oktober 2023** | |
| Logginformation har lagts till i Rapporteringsaktivitetshanteraren | Lagt till information om att alla [avbrott och efterföljande begränsningar för rapporteringsaktivitet](/help/admin/tools/reporting-activity-manager/reporting-activity-cancel-requests.md) i Rapporteringsaktivitetshanteraren fångas in i [loggarna](/help/admin/tools/logs.md). |
| Uppdateringar av stödet för Data Warehouse-komponenter | Lagt till tillgänglighet för vissa komponenter och tagit bort tillgänglighet för andra för Data Warehouse. Ändringarna återspeglas i [Komponentstödet i Data Warehouse](/help/export/data-warehouse/component-support.md). <ul><li>Stöd för dimensionen Besöksdjup har lagts till (borttaget Besöksdjup i listan över dimensioner stöds inte)</li><li>Borttaget stöd för deltagandemått (extra deltagandemått i listan över mätvärden som inte stöds)</li><li>Stöd för följande tidsbaserade dimensioner har lagts till: År, Kvartal, Månad, Vecka, Dag, Timme och Minut (de här dimensionerna har tagits bort från listan över dimensioner som inte stöds) <p>Tidigare hade Data Warehouse bara stöd för dessa mått i den första kolumnen i en friformstabell när Kornighet valdes. Nu stöds alltid dessa dimensioner.</p><p>Datumutdata är dock inte standard när de här måtten används. Året är 1900 och månaderna är nollbaserade.</li></ul> |
| **September 2023** | |
| Uppdaterad struktur för artiklar för panelen Medieuppspelningstid för spenderad tid | Mappen Media Playback Time Spent har tagits bort och innehållet i mappen har kombinerats till en enda artikel: [Media Playback Time Spent panel](/help/analyze/analysis-workspace/c-panels/media-playback-time-spent.md). <p>Den här ändringen är mer i linje med dokumentationen för andra paneler.</p> |
| Komma igång med innehållsförbättringar | Lagt till information som beskriver viktiga uppgifter och resurser för att komma igång för administratörer, analytiker, slutanvändare och utvecklare. Följande nya artiklar är nu tillgängliga: <ul><li>[Kom igång (efter roll)](/help/analyze/get-started/get-started-by-role.md)</li><li>[Förstå analysgränssnittet](/help/analyze/get-started/analytics-interface.md)<li>[Användningsexempel](/help/analyze/get-started/use-cases.md)</li></ul> |
| Förbättringar av rapportdokumentationen för Streaming Media Collection | Omorganiserat en del av innehållet i avsnittet Rapportering i guiden Direktuppspelning av media Collection, bland annat genom att konsolidera API-dokumentationen i ett eget avsnitt och justera ordningen för vissa artiklar. <p>Namnet på Media Workspace Templates-artikeln ändrades till [Medierapporter i Workspace](https://experienceleague.adobe.com/docs/media-analytics/using/media-reports/media-workspace-templates.html?lang=sv-SE) för att bättre överensstämma med namngivningen i produkten. </p> |
| **Augusti 2023** | |
| Förtydligande av dataflöde | [Definitionen av start- och slutdatum](/help/export/analytics-data-feed/create-feed.md) har uppdaterats för att förtydliga att du kan ange startdatumet till vilket datum som helst tidigare när data samlas in när du bearbetar dataflöden för historiska data. |
| Adobe Experience Platform Edge Network datahantering | Innehåll har lagts till om hur Adobe Analytics [hanterar data från Edge Network](../implement/aep-edge/overview.md). |
| Medieuppspelningstid spenderad panel | Uppdaterat innehåll för [Media Playback Time Spent Panel](/help/analyze/analysis-workspace/c-panels/media-playback-time-spent.md) för att förbättra läsbarheten. |
| Flyttat innehåll om hantering av schemalagda projekt | Skapade en ny artikel i Analytics Components Guide med namnet [Schemalagda projekt](/help/components/scheduled-projects-manager.md). Det här innehållet fanns tidigare i artikeln [Schemalägg projekt](/help/analyze/analysis-workspace/curate-share/t-schedule-report.md) i verktygshandboken för analyser. |
| Jämför implementeringsmetoder | Uppdaterad dokumentation som jämför olika implementeringsmetoder. [Läs mer](../implement/prepare/comparison.md) |
| Adobe kundtjänst krävs inte för att konfigurera SFTP för dataflöden | Tydligare i [Skicka Adobe-data till ett externt FTP-konto hos SFTP](/help/export/ftp-and-sftp/c-sftp/ftp-sftp-transfer.md) som kunder inte behöver kontakta Adobe kundtjänst för att konfigurera SFTP för datafeeds. <p>Dessutom lades ett meddelande till om att SFTP inte längre rekommenderas och att kunder bör använda ett molnmål när de konfigurerar datafeeds.</p> |
| Dokumentationsförbättringar för Streaming Media Collection | Följande dokumentationsförbättringar har gjorts för Streaming Media Collection: <ul><li>Uppdaterade den [allmänna översikten](https://experienceleague.adobe.com/docs/media-analytics/using/media-overview.html?lang=sv-SE) för att förbättra klarheten och inkludera information om Customer Journey Analytics.</li><li>Uppdaterade [implementeringsöversikten](https://experienceleague.adobe.com/docs/media-analytics/using/implementation/overview.html?lang=sv-SE) för att tydligt skilja mellan Edge-implementeringar och enbart Analytics-implementeringar. Dessutom ingår diagram som illustrerar de olika implementeringsmetoderna.</li><li>Lagt till krav som är specifika för [Edge-implementeringar](https://experienceleague.adobe.com/docs/media-analytics/using/implementation/edge-recommended/prerequisites-edge.html?lang=sv-SE) och [Endast analyser](https://experienceleague.adobe.com/docs/media-analytics/using/implementation/analytics-only/prerequisites-analytics.html?lang=sv-SE). Uppdaterade även de [allmänna kraven](https://experienceleague.adobe.com/docs/media-analytics/using/getting-started/prereqs.html?lang=sv-SE).</li><li>Uppdaterade tabeller i artikeln [Get Media SDKs, Extensions using Tags och OTT SDKs](https://experienceleague.adobe.com/docs/media-analytics/using/getting-started/download-sdks.html?lang=sv-SE) för att inkludera nya kolumner för *Supported solutions* och *Implementation method*.</li><li>Effektivt innehåll och enklare organisering av artiklar under [Implementering](https://experienceleague.adobe.com/docs/media-analytics/using/implementation/overview.html?lang=sv-SE) i dokumentationen. Detta inkluderade kategorisering av implementeringar med Edge och implementeringar med enbart analys.</li><li>En extra hierarkinivå som inte behövdes under [Spärra/knip](https://experienceleague.adobe.com/docs/media-analytics/using/tracking/track-core-overview.html?lang=sv-SE) har tagits bort och omdirigeringar för ändrade URL:er har lagts till i det här avsnittet.</li><ul> |
| **Juli 2023** | |
| ADOBE EXPERIENCE PLATFORM EDGE NETWORK API | Mer omfattande dokumentation om när och hur datainsamling ska implementeras med Adobe Analytics med [Adobe Experience Platform Edge Network API](../implement/aep-edge/api/overview.md). Om du till exempel implementerar datainsamling med Adobe Analytics i datorprogram, IoT-enheter, anger du de övre rutorna. |
| Globalt företag-ID | Dokumenterade [hur du hittar det globala företags-ID:t](../admin/tools/company/web-services-admin.md) för det Analytics-företag som du är inloggad på. Detta ID krävs för API:er i Analytics 2.0. |
| Uppdaterad storleksgräns för FTP | Ändrade standarddatalagringsgränsen [för FTP](/help/export/ftp-and-sftp/ftp-limits.md) till 100 GB. |
| Ny AppMeasurement-variabel | Variabeln `decodeLinkParameters` innehåller kantfall där implementeringar kodar flerbytetecken i länkspårningsvariabler. [Läs mer](../implement/vars/config-vars/decodelinkparameters.md) |
| Konfigurera lagringsplatser för molnkonton för inhämtning av klassificeringsdata | Nu kan du hantera lagringsplatser för molnkonton som används för automatisering av klassificeringsuppsättningar. [Läs mer](/help/components/locations/configure-import-accounts.md) |
| Förbättrat datareparationsfilter | Tre filtreringsförbättringar har lagts till i Datareparation. [Läs mer](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/data-repair/) |
| **Juni 2023** | |
| Nya funktioner för klassificeringsuppsättningar | [Klassificeringsuppsättningar](/help/components/classifications/sets/overview.md) har uppdaterats med flera nya funktioner:<ul><li>**Konsolideringar**: Kombinera klassificeringsuppsättningar till en enda konsoliderad klassificeringsuppsättning. Den konsoliderade klassificeringsuppsättningen kan användas som andra klassificeringsuppsättningar eller som en uppslagsuppsättning i Customer Journey Analytics. [Läs mer](../components/classifications/sets/consolidations/manage.md)</li><li>**Regler**: Klassificera värden automatiskt baserat på reglerna i klassificeringsuppsättningen. [Läs mer](../components/classifications/sets/manage/rules.md)</li><li>**Automatisk import**: Importera klassificeringsdata automatiskt från molnlagringsmål. [Läs mer](../components/classifications/sets/manage/schema.md)</li></ul> |
| Uppdateringar av beräknade mätvärden | Uppdateringar gjordes för olika artiklar om beräknade mätvärden, inklusive uppdatering av skärmdumpar och steg i procedurer. Dessa ändringar har gjorts för att få dokumentationen att överensstämma med den aktuella Adobe Analytics-funktionen. |
| Säkra destinationer för datafeed-export | Datamatningar kan nu skickas till följande molnlagringsmål:<ul><li>Amazon S3</li><li>Azure RBAC</li><li>Azure SAS</li><li>Google Cloud Platform</li></ul>Destinationer som tidigare var tillgängliga (FTP, SFTP, S3 och Azure Blob) rekommenderas inte längre. [Läs mer](/help/export/analytics-data-feed/create-feed.md) |
| Bot-rapportering i Workspace | Bot-rapportering finns nu i Analysis Workspace. Den här funktionen innehåller flera tillägg:<ul><li>En ny dimension: [Punktnamn](/help/components/dimensions/bot-name.md)</li><li>Två nya mätvärden: [Bot-sidvyer](/help/components/metrics/bot-page-views.md) och [Bot-förekomster](/help/components/metrics/bot-occurrences.md).</li><li>En ny mall för beräknade mätvärden: [Vyförhållande för punktsidor](/help/components/calculated-metrics/cm-reference/default-calcmetrics.md)</li><li>En ny Workspace-rapport: Bot-rapportering</li></ul>Den nya dimensionen och mätvärdena innehåller data som är förifyllda från mars 2023. |
| **Maj 2023** | |
| Deep Linking-dokumentation (mobilapp) | Tillåter användare att skicka länkar till styrkort som leder dem direkt till styrkortsprojektet i appen. [Läs mer](/help/analyze/mobile-app/create-scorecard.md#shareable-link) |
| Dokumentation för den uppdaterade startskärmen för kontrollpanelsappen för Analytics (mobilapp) | På den nya uppdaterade startskärmen kan du visa alla dina styrkort i en konsoliderad styrkortslista. [Läs mer](/help/analyze/mobile-app/executive.md#use-dashboards) |
| Spektrum-ikoner | Skärmbilder av användargränssnittsikoner i dokumentationen har ersatts, där så är lämpligt, med referenser till motsvarande ikoner i [Adobe Spectrum Design System](https://spectrum.adobe.com/page/icons/). |
| Rapporteringsaktivitetshanteraren | Den här betadokumentationen har uppdaterats, särskilt avsnittet [Visa rapporteringsaktivitet för enskilda rapportsviter](/help/admin/tools/reporting-activity-manager/reporting-activity-overview.md). |
| Översikt över Analysis Workspace | [Analysis Workspace-översikt](/help/analyze/analysis-workspace/home.md) har uppdaterats med mer allmän översiktsinformation och länkar till relevant innehåll. |
| Skapa projekt | Skapade en ny artikel som förklarar i detalj hur du [skapar projekt](/help/analyze/analysis-workspace/build-workspace-project/create-projects.md) i Analysis Workspace. |
| Sortera komponenter i den vänstra listen | Lagt till information om hur du sorterar komponentlistan i den vänstra listen. Se avsnittet Sök, filtrera och sortera komponentlistan i [Komponentöversikt](/help/analyze/analysis-workspace/components/analysis-workspace-components.md). |
| Ta bort rader som innehåller dynamiska dimensioner från en frihandstabell | Lagt till information om hur du snabbt tar bort specifika rader som innehåller dynamiska dimensioner med hjälp av x-ikonen. Se avsnittet&quot;Snabb uteslutning av specifika rader från en tabell&quot; i [Filtrera och sortera tabeller](/help/analyze/analysis-workspace/visualizations/freeform-table/filter-and-sort.md). |
| Knapp för att lägga till en visualisering på en panel | Lagt till information om en ny knapp längst ned på varje panel i Analysis Workspace som gör att du snabbt kan lägga till en visualisering. Se avsnittet&quot;Lägg till visualiseringar i en panel&quot; i [Översikt över visualiseringar](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md). |
| **April 2023** | |
| Överför användarresurser och ange förfallodatum för konton | Lagt till information om hur du [överför användarresurser och anger kontots förfallodatum](/help/admin/tools/user-management/users-assets.md). |
| 2 nya slutpunktsguider för Adobe Analytics 2.0 API | <ul><li>[API för analysdimensioner](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/dimensions/)</li><li>[API för analysmått](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/metrics/)</li></ul> |
| Projektsegment (ad hoc- och snabbsegment) | Effektiv dokumentation om projektsegment och borttagen dubblettinformation. Stegen för att skapa ad hoc-segment kombineras nu med stegen för att [skapa snabbsegment](/help/analyze/analysis-workspace/components/segments/quick-segments.md). |
| Dynamiska sökningar | Ytterligare information om [Dynamiska sökningar](/help/export/analytics-data-feed/c-df-contents/dynamic-lookups.md) har lagts till. Tidigare fanns bara information för mobilattribut, som är en av flera dynamiska sökningar. |
| **Mars 2023** | |
| Stöd för SDK på Activity Map | Uppdaterade [Implementera Adobe Analytics](/help/implement/home.md). |
| Översikt över trafikvariabler (props) | Lagt till avsnitt och stegvisa procedurer för att förtydliga och förbättra artikelinnehållet. Sammanfogat innehåll från en artikel med rubriken&quot;Aktivera trafikvariabelrapporter&quot; och tog bort artikeln. Se [Översikt över trafikvariabler (props)](/help/admin/tools/manage-rs/edit-settings/c-traffic-variables/traffic-var.md). |
| Interna URL-filter | Lagt till avsnitt och stegvisa procedurer för att förtydliga och förbättra artikelinnehållet. Se [Interna URL-filter](/help/admin/tools/manage-rs/edit-settings/general/internal-url-filter-admin.md). |
| Skapa dataartiklar i mobilstyrkort | En [dataartikel](/help/analyze/mobile-app/create-scorecard.md#create-data-stories) är en samling med stöddatapunkter, företagskontext och relaterade mått som bygger på ett centralt tema eller mätvärden. |
| Standardberäknade värden | Innehåll har lagts till som förklarar de [beräknade standardmåtten från Adobe](/help/components/calculated-metrics/cm-reference/default-calcmetrics.md). |
| Dataordlista | <p>Lagt till ny dokumentation för datamordlistan, inklusive en [översikt](/help/analyze/analysis-workspace/components/data-dictionary/data-dictionary-overview.md), [visning](/help/analyze/analysis-workspace/components/data-dictionary/view-data-dictionary.md), [redigering](/help/analyze/analysis-workspace/components/data-dictionary/edit-entries-data-dictionary.md) och [övervakning](/help/analyze/analysis-workspace/components/data-dictionary/monitor-data-dictionary-health.md) i datamappningslistan.</p><p>Information i [Att lägga till komponentbeskrivningar](/help/analyze/analysis-workspace/components/add-component-descriptions.md) har uppdaterats för att ta hänsyn till funktionen för dataordlista.</p> |
| Länkdelning för projekt (ingen inloggning krävs) | <p>Befintlig dokumentation som förklarar hur man delar en skrivskyddad länk till ett projekt med personer som inte har tillgång till Analysis Workspace har uppdaterats.</p> <p>Den uppdaterade användardokumentationen innehåller [Dela projekt](/help/analyze/analysis-workspace/curate-share/share-projects.md) och [Skapa delningsbara länkar](/help/analyze/analysis-workspace/curate-share/shareable-links.md).</p> <p>Alternativ för administratörer lades till i [Inställningar](/help/analyze/analysis-workspace/user-preferences.md).</p> |
| **Februari 2023** | |
| Implementering | Uppdaterat innehåll om hur du [implementerar Adobe Analytics för webb och mobiler](../implement/home.md). |
| Workspace-kalendrar och datumintervall | Uppdaterat innehåll som beskriver relativa datumintervall, uppdateringar av formelberäkning och ändringar i kalendergränssnittet. Se [Om relativa paneldatumintervall](/help/analyze/analysis-workspace/components/calendar-date-ranges/calendar.md). |
| Mobil styrkort | Nytt dokumentationsavsnitt som beskriver hur du visar och döljer datumintervall för jämförelse. Se [Visa datumintervall för jämförelse](/help/analyze/mobile-app/create-scorecard.md) i Customer Journey Analytics. |
| 1.4 API | API:t [&#x200B; för &#x200B;](https://developer.adobe.com/analytics-apis/docs/1.4/)Adobe Analytics 1.4 har fått en fullständig omskrivning och har nu publicerats på Adobe Developer. |
| Spåra olika implementeringstyper | Användningsexemplet [Spåra olika implementeringstyper](../implement/id/cross-type-implementation.md) har uppdaterats för att passa Experience Cloud ID-tjänsten. |
| **Januari 2023** | |
| Filtrera och ordna tabeller | Uppdaterat innehåll (inklusive att lägga till procedurer och förklara tillgängliga alternativ) i artikeln [Filtrera och sortera tabeller](/help/analyze/analysis-workspace/visualizations/freeform-table/filter-and-sort.md). Artikelns namn ändrades från&quot;Sidnumrering, filtrering och sortering&quot;. |
| Mappar | Dedikerade sidor för [mapphantering](/help/analyze/analysis-workspace/build-workspace-project/workspace-folders/about-folders.md). |
| Användarinställningar | Många ytterligare användarinställningar finns nu tillgängliga i [Inställningar](/help/analyze/analysis-workspace/user-preferences.md). |
| Spara automatiskt för projekt | Innehållet har uppdaterats för att inkludera funktioner för att spara automatiskt i [Spara projekt](/help/analyze/analysis-workspace/build-workspace-project/save-projects.md). |
| Landningssida | Nya [uppdateringar av landningssidan](/help/analyze/landing.md) |

### 2022 {#year22}

| Funktion | Beskrivning |
| --- | --- |
| **November 2022** | |
| Variabler för hantering av samtycke | Dedikerade sidor för [Medgivandehanteringsanmälan](/help/components/dimensions/cm-opt-in.md) och [Medgivandehanteringsavanmälan](/help/components/dimensions/cm-opt-out.md). |
| Uppdatering i flera valutor | Sidorna runt [Stöd för flera valutor](/help/implement/vars/config-vars/currencycode.md) uppdateras. |
| **Oktober 2022** |  |
| Data Workbench | [Meddelande om upphörande av livscykel](https://experienceleague.adobe.com/docs/data-workbench/using/eol.html?lang=sv-SE) |
| Klienttips | Ny [översikt och vanliga frågor &#x200B;](/help/technotes/client-hints.md). |
| Sammanfattning av nyckelmått | Nytt avsnitt om visualiseringen av [Översikt över nyckeltal](/help/analyze/analysis-workspace/visualizations/key-metric.md). |
| Klassificeringsuppsättningar | Den nya användarupplevelsen [Klassificeringsuppsättningar](/help/components/classifications/sets/overview.md) ger ett enda gränssnitt för att hantera klassificeringar och regler och förbättrar synligheten för kundägda klassificeringsdata. |
| Mobilapp: Anpassade detaljvyer | Nytt avsnitt om [anpassade detaljvyer](/help/analyze/mobile-app/create-scorecard.md). |
| VISTA | Ny sida som förklarar grunderna i [VISTA-regler](/help/technotes/vista.md). |
| **September 2022** | |
| Kombinationsdiagram | Nytt ämne i [kombinationsdiagramvisningen](/help/analyze/analysis-workspace/visualizations/combo-charts.md). |
| Uppdaterat plugin-program | Uppdaterad version av implementerings-plugin-programmet [getvalonce](/help/implement/vars/plugins/getvalonce.md). |
| Ny konfigurationsvariabel | Dokumentation om [collectHighEntropyUserAgentHints](/help/implement/vars/config-vars/collecthighentropyuseragenthints.md) |
| Kundtips med hög entropi | Nytt avsnitt om hur Adobe använder [klienttips](/help/technotes/client-hints.md) förutom användaragenten för att fastställa enhetsinformation. |
| Bearbetningsorder | Olika hjälpsidor har sammanställts för att ge ett enda hjälpavsnitt om [Bearbetningsordning](/help/technotes/processing-order.md). |
| **Augusti 2022** | |
| Stöd för listvariabler i XDM för Edge Collection | Gör det möjligt för kunder att samla in data med Web SDK att använda XDM för att ange innehåll i listvariabler. [Läs mer](../implement/vars/page-vars/list.md#list-variables-using-the-web-sdk) |
| Användning av SKU-fält i XDM för Edge Collection vid inställning av produktsträngsvariabler | Gör det möjligt för kunder att samla in data med Web SDK att använda SKU-värdet för att ange produktfältet i variabeln products. [Läs mer](../implement/vars/page-vars/products.md#products-using-the-web-sdk) |
| **Juni 2022** |  |
| Marknadsföringsvariabler i XDM för Edge Collection | Dokumentation om [stöd för Merchandising-variabler i XDM för Edge Collection](/help/components/dimensions/evar-merchandising.md) |
| Dokumentation för Experience Platform Edge | Nya artiklar om Adobe Analytics-implementering via [Web SDK](/help/implement/aep-edge/web-sdk/overview.md), [Mobile SDK](/help/implement/aep-edge/mobile-sdk/overview.md) och [Edge API](/help/implement/aep-edge/api/overview.md). |
| Uppdaterad dokumentation om visualisering av flöde | Baserat på det [nya användargränssnittet](/help/analyze/analysis-workspace/visualizations/c-flow/create-flow.md) |
| Dokumentation om att dela anteckningar i mobilstyrkort | Du kan visa [anteckningar som har skapats i Workspace i Mobile Scorecards](/help/analyze/analysis-workspace/components/annotations/mobile-annotations.md). |
| **Maj 2022** | |
| Fylla i livscykeldimensioner och mätvärden via Edge Network | Mobila livscykeldata som skickas till Edge Network visas nu i Analytics-rapporter. Mer information om vilka XDM-fält som mappar till befintliga mobila Livscykelrapporter finns i [Variabelmappning för analys](/help/implement/aep-edge/xdm-var-mapping.md). |
| **April 2022** | |
| Uppdateringar av Adobe Analytics landningssida | Uppdateringar till den gemensamma [startsidan för Workspace/Reports &amp; Analytics](/help/analyze/landing.md) som förbättrar användbarheten och underlättar navigeringen. |
| Nytt ämne på panelen [!UICONTROL Page Summary] | [Panelen Sidsammanfattning](/help/analyze/analysis-workspace/c-panels/page-summary.md) |
| Nytt ämne på panelen [!UICONTROL Next/Previous item] | [Panelen Nästa/föregående dimensionsobjekt](/help/analyze/analysis-workspace/c-panels/next-previous.md) |
| **Mars 2022** | |
| Nytt avsnitt om vilka HTTPS-krypteringsalgoritmer som stöds | HTTPS-krypteringsalgoritmer som stöds för kunder med krypteringssäkerhetsnivån &quot;Hög&quot;. |
| Ny dokumentation om anteckningar i Workspace | Med [Anteckningar i Workspace](/help/analyze/analysis-workspace/components/annotations/overview.md) kan du effektivt kommunicera kontextuella datanunkter och insikter till din organisation. |
| Uppdateringar av Adobe Analytics landningssida | [Uppdateringar](/help/analyze/landing.md) till den gemensamma startsidan för Workspace/Reports &amp; Analytics som förbättrar användbarheten och gör det enklare att navigera. |
| [!UICONTROL Next item] eller [!UICONTROL Previous item] Workspace-panel | På den här panelen kan du utforska objekt som följer eller föregår ett av de önskade dimensionsobjekten. |
| [!UICONTROL Page Summary] Workspace-panel | Panelen innehåller en djupgående analys av en sida som du väljer. |
| Nytt avsnitt om att pausa äldre schemalagda rapporter | Från och med **15 april 2022** har Adobe för avsikt att pausa alla schemalagda rapporter som har ett skapandedatum som är senare än två år |
| **Februari 2022** | |
| Förhandsgranskningsläge för mobilstyrda projekt | I [förhandsgranskningsläget](/help/analyze/mobile-app/create-scorecard.md#preview) kan du förhandsgranska upplevelsen innan du sparar och delar ett styrkort. |
| Slutpunkt för API-projekt | Lägg till, redigera eller ta bort Analysis Workspace-projekt med API:t. [Läs mer](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/projects/) |
| Uppdaterat ämne om att pausa äldre schemalagda Report Builder-aktiviteter | **Från och med 15 april 2022** har Adobe för avsikt att [pausa alla schemalagda Report Builder-aktiviteter som skapades för mer än två år sedan](/help/analyze/legacy-report-builder/r-arb-scheduled-reports.md). |

### 2021 {#year2021}

| Funktion | Beskrivning |
| --- | --- |
| **Oktober 2021** |  |
| 21 oktober 2021 | Ny dokumentation om [snabbsegment](/help/analyze/analysis-workspace/components/segments/quick-segments.md) i Analysis Workspace |
| 21 oktober 2021 | Ny dokumentation om panelen [Medieuppspelningstid spenderad](/help/analyze/analysis-workspace/c-panels/media-playback-time-spent.md) i Analysis Workspace. |
| 7 oktober 2021 | Ny dokumentation om [visualiseringar för mobila styrkort](/help/analyze/mobile-app/create-scorecard.md#apply-visualizations) |
| **Augusti 2021** |  |
| 18 augusti 2021 | Reviderad struktur på översta nivån och konsoliderad till en enda [landningssida](https://experienceleague.adobe.com/docs/analytics.html?lang=sv-SE) |
| 18 augusti 2021 | Nytt avsnitt om [A4T och virtuella rapportsviter](/help/components/vrs/vrs-a4t.md) |
| 18 augusti 2021 | Nytt ämne om [Bästa praxis för attribuering](/help/analyze/analysis-workspace/attribution/best-practices.md) |
| 5 augusti 2021 | Nytt avsnitt om [Antal upprepade förekomster](/help/components/metrics/count-repeat-instances.md) |
| 5 augusti 2021 | Klassificeringsdokumentationen för [mallar](/help/components/classifications/importer/c-download-saint-data.md), [webbläsarimport](/help/components/classifications/importer/browser-import.md) och [webbläsarexport](/help/components/classifications/importer/browser-export.md) har uppdaterats för att visa alternativ som inte är tillgängliga för rapportsviter som har aktiverats för den nya klassificeringsarkitekturen. |
| 2 augusti 2021 | Flera sidor har uppdaterats för att återspegla omprofileringen av [Adobe Experience Platform Launch](/help/implement/launch/overview.md) |
| **Juli 2021** |  |
| 23 juli 2021 | Ny fördjupad diskussion om [Merchandising eVars](/help/admin/tools/manage-rs/edit-settings/conversion-var-admin/merchandising-evars.md) |
| 15 juli 2021 | Lagt till ny dokumentation på den nya [Adobe Analytics-landningssidan](/help/analyze/landing.md) |
| **Juni 2021** |  |
| 15 juni 2021 | [Bästa praxis för marknadsföringskanaler har uppdaterats](/help/components/c-marketing-channels/mchannel-best-practices.md) |
| 3 juni 2021 | Dokumentationen har uppdaterats för att bättre förklara [Dataflödesimplementering](/help/export/analytics-data-feed/create-feed.md) och [BucketOwnerFullControl](/help/export/analytics-data-feed/df-faq.md#BucketOwnerFullControl). |
| 25 maj 2021 | Dokumentationen om [eVar skiftlägeskänslighet i rapportering](/help/components/dimensions/evar.md) har uppdaterats. |
| 13 maj 2021 | Uppdateringar av [Data Warehouse API-begäranden](https://developer.adobe.com/analytics-apis/docs/1.4/guides/reporting/data-warehouse/). De har nu stöd för&quot;Timmar&quot;. |
| **Mars 2021** | |
| Mars, april 2021 | Uppdateringar av Adobe Analytics-kontrollpaneler [Executive Guide](/help/analyze/mobile-app/executive.md) och [Curator Guide](/help/analyze/mobile-app/curator.md) |
| 25 mars 2021 | Ny dokumentation på sidan [!UICONTROL Components] > [!UICONTROL User preferences]. Med den kan du hantera [!UICONTROL Analysis Workspace]-inställningar och relaterade komponenter för din användare. [!UICONTROL User preferences] gäller för alla nya projekt och paneler. <br>**Obs!** Följande inställningar har flyttats till sidan [!UICONTROL User preferences]:<ul><li>Rapportinställningar: Tusentalsavgränsare (kallas nu _nummerformat_)</li><li>Rapportinställningar: CSV-avgränsare</li><li>Workspace-projekt: Hjälp > Aktivera tips</li><li>Workspace-projekt: Tom panel _Starta nya projekt med den här panelen_</li></ul> |
| 25 mars 2021 | [!UICONTROL Histogram Smart Bucket Prediction] hjälper till med histogram med höga kardinalitetsmått genom att automatiskt identifiera rätt bredd och antal bucklar för ditt datauppslag. För lågkardinalitetsmått fungerar visualiseringen på samma sätt som tidigare. |
| 25 mars 2021 | [API:t för datareparation](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/data-repair/) uppdateringar (filtrera efter URL:er, frågesträngar, vid tecken med mera) |
| 25 mars 2021 | Ny dokumentation för [användningslogg-API](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/usage-logs.md) |
| **Februari 2021** | |
| 4 februari 2021 | Komponentval: Den nedrullningsbara listruta/släppzonkomponent som hittades i [!UICONTROL Quick Insights] lades till i alla släppzoner i [!UICONTROL Workspace]. Den här förbättringen gör att du kan välja från en listruta med kompatibla komponenter eller fortsätta att använda utrymmet som en släppzon. |
| **Januari 2021** | |
| 14 januari 2021 | Språkval har lagts till i dokumentationen för kontrollpanelerna i Analytics. |
| 14 januari 2021 | Lagt till dokumentation om hur du kan lägga till bilder i Workspace-projekt genom att referera till en offentlig bild-URL. |
| 14 januari 2021 | Kombinerad käll- och inställningshanterare för Workspace-visualiseringar: [!UICONTROL Data Source]-hanteraren (punkt) och inställningshanteraren (kugghjulet) för visualiseringar har kombinerats till en enda leverantör, så att du enkelt kan hantera källan och inställningarna från samma plats. |

### 2020 {#year2020}

| Funktion | Beskrivning |
| --- | --- |
| **December 2020** | |
| 7 december 2020 | Ändrade alla relevanta sidor så att slutpunkten &quot;adobedc.net&quot; skulle inkluderas eller ersättas. |
| 8 december 2020 | Uppdateringar av sidan [Skapa nytt projekt](/help/analyze/analysis-workspace/build-workspace-project/freeform-overview.md) i Workspace. |
| **November 2020** | |
| 24 november 2020 | Uppdaterar till sidan [Panelöversikt](/help/analyze/analysis-workspace/c-panels/panels.md) i Workspace. |
| 24 november 2020 | Nya granskningsdokument för implementering: <ul><li>[Fullständig implementeringsgranskning](/help/implement/review/full-review.md)</li><li>[Fokuserad implementeringsgranskning](/help/implement/review/focused-review.md)</li></ul> |
| 24 november 2020 | Analysis Workspace [Visualiseringar - översikt](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md) har uppdaterats. |
| 12 november 2020 | Ny sida på [Ärvd Adobe Analytics-implementering](/help/implement/prepare/existing-implementation.md). |
| 2 november 2020 | Uppdaterat dokument på [FTP för klassificeringar](/help/export/ftp-and-sftp/c-set-up-ftp-accounts/ftp-saint.md). |
| **Oktober 2020** | |
| 23 oktober 2020 | Workspace Line-visualisering: [Glidande medeltrendlinjealternativ](/help/analyze/analysis-workspace/visualizations/line.md): Den här inställningen lades till i [!UICONTROL Line] visualiseringstrendlinjeinställningar. Ett glidande medelvärde kallas även för ett rullande medelvärde och använder ett visst antal datapunkter (som bestäms av en **[!UICONTROL Periods]**-markering), jämför dem och använder medelvärdet som en punkt på raden. |
| 23 oktober 2020 | På hjälpsidan för [prestanda](/help/analyze/analysis-workspace/workspace-faq/optimizing-performance.md) i Workspace visas olika faktorer som påverkar projektets prestanda och länkar till tips för optimering. |
| 23 oktober 2020 | Förbättringar har lagts till i dokumentationen för Adobe Analytics kontrollpaneler. I mobilstyrkortet i Workspace matchar styrkortets format nu appen. |
| **September 2020** | |
| 17 september 2020 | [Hämta 50 000 objekt för en dimension](/help/analyze/analysis-workspace/curate-share/download-send.md#download-items): Du kan nu hämta 50 000 objekt för en dimension i en frihandstabell, med segment och filter. Det ger dig åtkomst till mer än de 400 dataraderna utanför Analysis Workspace. |
| 17 september 2020 | [Förbättringar av linjevisualisering](/help/analyze/analysis-workspace/visualizations/line.md): <ul><li>Du kan visa eller dölja X-axeln och Y-axeln för [!UICONTROL Line]-visualisering. Detta kan vara praktiskt när dina [!UICONTROL Line]-visualiseringar är mer kompakta.</li><li>Du kan lägga över en etikett för minsta och högsta värde på alla linjevisualiseringar för att snabbt markera toppar och dalar i ett mätresultat.</li><li>Du kan täcka över olika regressionstrendlinjer på alla linjevisualiseringar för att lättare se trenden i data. Alternativen är [!UICONTROL Linear], [!UICONTROL Logarithmic], [!UICONTROL Exponential], [!UICONTROL Power] och [!UICONTROL Quadratic].</li></ul> |
| 17 september 2020 | Nya datumintervall i Workspace: Vi har lagt till fem nya datumintervall så att du kan välja mellan datumintervall som inte innehåller data för delar av dagen från idag: Senaste 7 fullständiga dagarna, Senaste 14 fullständiga dagarna, Senaste 30 fullständiga dagarna, Senaste 60 fullständiga dagarna, Senaste 90 fullständiga dagarna |
| 17 september 2020 | Ny dokumentation om [Media Concurrent Viewer-panelen i Workspace](/help/analyze/analysis-workspace/c-panels/media-concurrent-viewers.md) |
| **Augusti 2020** | |
| 31 augusti 2020 | Förbättringar har lagts till i [fältbaserad sammanslagningsdokumentation](/help/components/cda/field-based-stitching.md) i enhetsövergripande analys. |
| **Juli 2020** | |
| 21 juli 2020 | Stora uppdateringar och revideringar av [Enhetsövergripande analys](/help/components/cda/overview.md). [Fältbaserad sammanfogning har lagts till](/help/components/cda/field-based-stitching.md). |
| 16 juli 2020 | Nya förinställningar för datumintervall i Workspace. Fyra nya datumintervall har lagts till: ([!UICONTROL This week/month/quarter/year (excluding today)]). På så sätt kan du välja från datumintervall som inte innehåller data för delar av dagen från och med idag. |
| **Juni 2020** | |
| 25 juni 2020 | Ny dokumentation för [panelen Snabbinformation](/help/analyze/analysis-workspace/c-panels/quickinsight.md) i Workspace. Där finns vägledning för icke-analytiker och nya användare av Analysis Workspace som snabbt och enkelt kan besvara affärsfrågor. |
| 25 juni 2020 | Ny dokumentation för [Analytics för målpanelen](/help/analyze/analysis-workspace/c-panels/a4t-panel.md) i Workspace. Ni kan analysera Adobe Target aktiviteter och upplevelser med lyft och självförtroende. |
| 18 juni 2020 | Ny dokumentation om [Attribution: Algoritmisk attribuering](/help/analyze/analysis-workspace/attribution/algorithmic.md) |
| 18 juni 2020 | Ny dokumentation för [Attribution: Anpassade fönster för sökning](/help/analyze/analysis-workspace/attribution/models.md#lookback-windows) |
| 18 juni 2020 | Ny dokumentation för [projektroller](/help/analyze/analysis-workspace/curate-share/share-projects.md) för delade Workspace-projekt. När du delar ett Workspace-projekt kan du nu placera mottagare i en av tre projektroller, beroende på vilken projektupplevelse du vill att de ska ha: Redigera, Duplicera och Visa. |
| 18 juni 2020 | Ny dokumentation om [&quot;Visa endast&quot; Workspace-projekt](/help/analyze/analysis-workspace/curate-share/view-only-projects.md). Projekt kan delas med användare som&quot;Kan visa&quot;. När en Visa-mottagare öppnar det delade projektet får de en mer restriktiv projekterfarenhet, utan någon vänster spårsträcka och begränsad interaktion. |
| 18 juni 2020 | Ny dokumentation om [projektroller](/help/analyze/analysis-workspace/curate-share/share-projects.md) för delade Workspace-projekt. När du delar ett Workspace-projekt kan du nu placera mottagare i en av tre projektroller, beroende på vilken projektupplevelse du vill att de ska ha: Redigera, Duplicera och Visa. |
| 18 juni 2020 | Ny dokumentation om [Samredigering av Workspace-projekt](/help/analyze/analysis-workspace/curate-share/share-projects.md). Mottagare som läggs till i rollen Kan redigera kan spara över ett projekt som har delats med dem. Detta gäller både administratörer och icke-administratörer. |
| **Maj 2020** |  |
| 31 maj 2020 | Ny dokumentation om [API för datainfogning i grupp](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/bdia.md) |
| 21 maj 2020 | Ny dokumentation för [Adobe Analytics-instrumentpaneler](/help/analyze/mobile-app/home.md) |
| 21 maj 2020 | Ny dokumentation om [tillgänglighetsförbättringar](/help/analyze/analysis-workspace/workspace-faq/aw-accessibility.md) för Analysis Workspace, inklusive förbättrad tangentbordsnavigering, färgkontrast och stöd för skärmläsare. |
| **April 2020** |  |
| 28 april 2020 | Dokumentation för mätvärdet [Content Velocity](/help/components/metrics/content-velocity.md) har lagts till. |
| 16 april 2020 | Dokumentation om hur [!UICONTROL Freeform Tables] byggs automatiskt från ett tomt tillstånd. Tidigare gick det inte att släppa komponenter direkt i ett tomt projekt eller på en tom panel, utan du var tvungen att lägga till en friformstabell först. Nu kan du släppa komponenter direkt i ett tomt projekt eller på en tom panel, så skapas en friformstabell automatiskt i det format som rekommenderas. Dessutom har vi förbättrat hur blandade komponenttyper (som mått och mätvärden) hanteras när de släpps tillsammans i en tom [!UICONTROL Freeform Table]. |
| **Mars 2020** |  |
| 12 mars 2020 | [Publicera segment i Experience Cloud](/help/components/segmentation/segmentation-workflow/seg-publish.md) har uppdaterats. |
| 12 mars 2020 | Uppdateringar av svarstider för CDA-sammanfogning. |
| 12 mars 2020 | Stöd för flera rapportsviter i Workspace. Nu kan du samla in data från flera rapportsviter i ett enda projekt och visa dem sida vid sida. [Läs mer …](/help/analyze/analysis-workspace/build-workspace-project/multiple-report-suites.md) |
| 12 mars 2020 | Utbildningsmall i Workspace. Den här nya standardmallen vägleder dig bland vanliga termer och steg när du skapar din första analys i Workspace. Den finns som en standardmall i det modala fönstret Nytt projekt och ersätter det exempelprojekt som finns idag för nya användare, som inte har andra projekt i sin lista. [Läs mer …](/help/analyze/analysis-workspace/build-workspace-project/starter-projects.md) |
| **Februari 2020** |  |
| 27 februari 2020 | Dokumentation för [Adobe Analytics Labs](/help/analyze/labs.md) har lagts till. |
| 25 februari 2020 | [`useLinkTrackSessionStorage`](/help/implement/vars/config-vars/uselinktracksessionstorage.md)-variabel har lagts till. |
| 20 februari 2020 | Ny Workspace-mall för organisationer som använder korsanalys. Den här mallen visar hur effektivt funktionen för analys över olika enheter sammanfogar besök och utbildar dig om mått och mätvärden som är specifika för just den här analysen. En rapportsvit som har analys över olika enheter krävs. Mer information finns i [Konfigurera enhetsanalys](/help/components/cda/setup.md). |
| 20 februari 2020 | Nya snabbtangenter i Workspace:<ul><li>Visa/dölj alla paneler: `alt + m`</li><li>Visa/dölj aktiv panel: `alt + ctrl + m`</li><li>Sök i vänster list: `ctrl + /`</li><li>Gå till nästa panel: `alt + Right Key`</li><li>Gå till föregående panel: `alt + Left Key`</li></ul>[Läs mer …](/help/analyze/analysis-workspace/build-workspace-project/fa-shortcut-keys.md) |
| 20 februari 2020 | Workspace-förbättringar: <ul><li>När en panel eller visualisering släpps i Workspace växlar den vänstra listen nu automatiskt till komponenter för ett smidigare arbetsflöde.</li><li>Mallkomponenter kan nu användas direkt (till exempel taggas, anges som favoriter eller godkännas).</li><li>Filtrerade mätvärdes- och segmentlistor har en plusknapp för att lägga till en ny komponent om du inte hittar det du behöver.</li></ul> |
| 20 februari 2020 | Workspace debugger lades till på Hjälp-menyn, vilket ger ett smidigare sätt att aktivera den för felsökning av Workspace-begäranden. [Läs mer …](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/reporting-tricks.md) |
| 18 februari 2020 | [`writeSecureCookies`](/help/implement/vars/config-vars/writesecurecookies.md)-variabel har lagts till. |
| 12 februari 2020 | Uppdateringar och omorganisering av dokumentationen för [marknadsföringskanaler](/help/components/c-marketing-channels/c-getting-started-mchannel.md). |
| 12 februari 2020 | Nya snabbtangenter har lagts till på [den här Workspace-sidan](/help/analyze/analysis-workspace/build-workspace-project/fa-shortcut-keys.md) |
| 7 februari 2020 | Uppdateringar av [Konfigurera Analytics över enheter](/help/components/cda/setup.md) och [Vanliga frågor och svar](/help/components/cda/faq.md). |
| 4 februari 2020 | Fullständig omarbetning av [användarhandboken för implementering](/help/implement/home.md). |
| 22 januari 2020 | Sidan om frihandstabeller har uppdaterats med information om nya [Freeform Table Builder](/help/analyze/analysis-workspace/visualizations/freeform-table/freeform-table.md). |
| **Januari 2020** | |
| 24 januari 2020 | Uppdateringar av sidan [Radinställningar](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/visualizations/freeform-table/column-row-settings/table-settings.html?lang=sv-SE#cja-workspace) i Workspace. |
| 16 januari 2020 | Ny dokumentation om [Frihandsritabellbyggaren](/help/analyze/analysis-workspace/visualizations/freeform-table/freeform-table.md). Med tabellverktyget aktiverat kan du dra och släppa i många mått, uppdelningar, mätvärden och segment för att skapa tabeller som besvarar mer komplexa affärsfrågor. Data uppdateras inte omedelbart. I stället uppdateras de när du klickar på **[!UICONTROL Build]**, vilket sparar tid när du väl vet vilken tabell du vill skapa. Dessutom har den här funktionen följande:<ul><li>**Förhandsgranskning**: Du kan förhandsgranska tabellformatet innan du lägger tid på att återge verkliga data.</li><li>**Inställningar för flexibla rader och uppdelning**: Du kan ange rad- och uppdelningsnivåer för alla måttrader. Tidigare användes standardvärden som inte gick att ändra förrän data returnerades.</li><li>**Uppdelning efter position**: Du kan ange att måttrader alltid ska _delas upp efter position_ i stället för _efter ett visst objekt_ (standard).</li><li>**Ordna statiska rader manuellt**: Du kan ordna statiska rader manuellt så att tabellraderna visas exakt som du vill ha dem. Tidigare kunde statiska rader bara sorteras efter en mätvärdeskolumn eller i bokstavsordning.</li></ul> |
| 13 januari 2020 | [Adobe Analytics och webbläsarcookies](/help/technotes/cookies/cookies.md) har lagts till. |
| 13 januari 2020 | Ändrade sidan [Vilken Adobe Analytics-verktyg jag ska använda](/help/analyze/get-started/which-analytics-tool.md). |

### 2019 {#year2019}

| Funktion | Beskrivning |
| --- | --- |
| 19 december 2020 | Ändrade standarddatalagringsgränsen [för FTP](/help/export/ftp-and-sftp/ftp-limits.md) till 10 GB. |
| 29 november 2019 | Dokumentationen för [dataflöden](/help/export/analytics-data-feed/data-feed-overview.md) har setts över. |
| 25 november 2019 | Nytt avsnitt om Slutet av livscykeln för Tvinga begränsningar för IP-inloggning. |
| 21 november 2019 | Ny dokumentation för [Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-landing.html?lang=sv-SE). |
| 21 november 2019 | [Vanliga frågor om Audience Analytics-arbetsflöde](/help/integrate/c-audience-analytics/mc-audiences-faqs.md) har uppdaterats för att indikera tillgänglighet i LiveStream. |
| 25 oktober 2019 | Uppdaterade sidan [Adobe Analytics Key Concepts](/help/technotes/terms.md). |
| 10 oktober 2019 | Uppdatera till Frihand-tabellsummor: de innehåller nu två summor, en **[!UICONTROL Table total]** och en **[!UICONTROL Grand total]**. Raden med tabellsumman avser de [rapportfilter](/help/analyze/analysis-workspace/visualizations/freeform-table/filter-and-sort.md) som används. Tidigare påverkades summorna bara av segmentering. [Läs mer](/help/analyze/analysis-workspace/visualizations/freeform-table/workspace-totals.md)<br/>Dessutom har alternativen **[!UICONTROL Show Totals]** och **[!UICONTROL Show Grand Total]** lagts till i **[!UICONTROL Column Settings]**.<br/>Med den här förändringen av totalsummor för friformstabeller uppdateras beroende visualiseringar (som länkade **[!UICONTROL Summary Number]**-visualiseringar) samt exporterade CSV- och PDF-data. |
| Oktober 10,2019 | I Workspace lades möjligheten att enkelt ta bort &#39;Ospecificerad (ingen)&#39; till som ett alternativ för att rapportera filter. |
| Oktober 10,2019 | I Workspace har de lila granularitetskomponenterna (Minute, Hour, Day, Week, Month, Quarter, Year) tagits bort. Du **behöver inte göra något** om du tidigare har använt någon av de lila tidskomponenterna.<br/>Den här ändringen innebär även att det lila avsnittet **[!UICONTROL Time]** har bytt namn till **[!UICONTROL Date Ranges]**. |
| 1 oktober 2019 | Ny artikel om [Workspace-summor](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/visualizations/freeform-table/workspace-totals.html?lang=sv-SE#cja-workspace). |
| 28 september 2019 | Nya artiklar om [konfigurationsvariabler för JavaScript-implementering](/help/implement/vars/config-vars/configuration-variables.md). |
| 19 september 2019 | Reviderad segmenteringsdokumentation som förklarar [logikgruppsbehållare](/help/components/segmentation/segmentation-workflow/seg-sequential-build.md#logic-group-containers). |
| 12 september 2019 | Ny dokumentation för [Enhetsövergripande analys](/help/components/cda/overview.md) |
| 12 september 2019 | Uppdatera dokumentet [Beräknade måttsummor](/help/components/calculated-metrics/cm-totals.md). |
| 28 augusti 2019 | Ny artikel om [progressiva webbappar (PWA) för Analytics](/help/technotes/pwa.md). |
| 8 augusti 2019 | Ny artikel om [summor för beräknade mätvärden](/help/components/calculated-metrics/cm-totals.md). |
| 8 augusti 2019 | Förtydligande av [sessionsdata med aktiverade tidsstämplar](/help/admin/tools/manage-rs/edit-settings/general/timestamp-configuration.md). |
| 8 augusti 2019 | I Workspace har Adobe ökat gränsen för objekt som kan placeras i ett statiskt nedrullningsbart filter från 50 till 200. Den här förbättringen kommer till nytta i flera olika sammanhang, till exempel kan du nu lägga till alla länder (195) eller alla delstater och provinser i USA (52) i ett filter. |
| 2 augusti 2019 | Större uppdatering av [Analytics-ordlistan](/help/technotes/terms.md). |
| 22 juli 2019 | Tillägg för Magento: Mall för marknadsföring och handel i [dokumentationen om Analysis Workspace-mallarna](/help/analyze/analysis-workspace/build-workspace-project/starter-projects.md). |
| 18 juli 2019 | Uppdaterade [inställningar för kohorttabeller](/help/analyze/analysis-workspace/visualizations/cohort-table/t-cohort.md). |
| 18 juli 2019 | I den vänstra listen i Workspace kan användare nu välja att _visa objekt från de senaste 18 månaderna_. Tidigare var den perioden högst 6 månader. Detta gör det enklare att jämföra med sidor eller kampanjer från föregående år, upp till för 18 månader sedan. |
| 18 juli 2019 | Dokumentation om en ny Workspace-mall med namnet [&quot;Magento: Marketing &amp; Commerce&quot;](/help/analyze/analysis-workspace/build-workspace-project/starter-projects.md) till Analysis Workspace. Den är särskilt utformad för Magentos e-handelskunder, men alla återförsäljare kan använda den för att få unika insikter i e-handelsverksamheten. |
| 13 juni 2019 | Nya färdiga filter har lagts till i sökningen till vänster i Workspace. Utöver det som redan finns (mått, mätvärden, godkända med mera) har vi lagt till nya filter, som beräknade värden, kundattribut, evariabler, egenskaper och video, för att det ska vara enklare att hitta de komponenter du behöver. |
| 4 juni 2019 | Ny handbok har skrivits med namnet [Migrera från en analysplattform från tredje part till Adobe Analytics](/help/technotes/ga-to-aa/home.md). |
| 30 maj 2019 | [Referensen för datafeed-kolumner](/help/export/analytics-data-feed/c-df-contents/datafeeds-reference.md) har setts över. |
| 9 maj 2019 | En ny inställning har lagts till i inställningarna för Flödesvisualisering: Inkludera upprepningsinstanser. Se [Flödesinställningar](/help/analyze/analysis-workspace/visualizations/c-flow/create-flow.md) |
| 11 apr 2019 | Förbättringar av Workspace bästa praxis för optimering: Optimera prestanda |
| 11 apr 2019 | Uppdateringar av [Optimera Workspace-prestanda](/help/analyze/analysis-workspace/workspace-faq/optimizing-performance.md). |
| 14 mars 2019 | Större uppdatering av regional datainsamling. |
| 7 februari 2019 | Mindre uppdatering av inställningarna Ersätt den sista oktetten i IP-adresser med 0 och Dölj IP i [Allmänna kontoinställningar](/help/admin/tools/manage-rs/edit-settings/general/general-acct-settings-admin.md). |
| 1 februari 2019 | Större uppdatering av implementeringsplugin-programmet [getPercentPageViewed](../implement/vars/plugins/getpercentpageviewed.md). |
| 17 januari 2019 | [Kohortanalys](/help/analyze/analysis-workspace/visualizations/cohort-table/cohort-analysis.md) - Med större förbättringar av kohortanalys kan du:<ul><li>Använda segmentinkludering och returnera mätvärden separat. </li><li>Visa bortfall i stället för lojalitet.</li><li>Visa latenstabeller (förfluten tid före och efter en inkluderingshändelse).</li><li>Anpassa kohortmått (för att gruppera besökare baserat på en evariabel, inte bara tid).</li><li>Utföra en rullande kohortberäkning: beräkna lojalitet/bortfall baserat på tidigare tidsperiod, inte ursprunglig kohort. </li><li>Lägga till flera mätvärden i inkluderings- och returfält samt använda segment. (Beräknade värden stöds inte.)</li></ul> |
| 17 januari 2019 | [Visa densitet](/help/analyze/analysis-workspace/build-workspace-project/view-density.md). Med den här nya inställningen kan du visa mer data på en enda skärm genom att minska den lodräta utfyllnaden i den vänstra listen, friformstabeller och kohorttabeller. Tillgängligt via Projekt > Projektinformation och inställningar. |
| 17 januari 2019 | [Stöd för flervärdesvariabler i Attribution](/help/analyze/analysis-workspace/attribution/overview.md). Vissa mått i Analytics kan innehålla flera värden för en enda träff, till exempel listvariabler, produktvariabler, listegenskaper eller evariabler för försäljning. Med Analysis Workspace kan du använda Attribution på någon av dessa typer av variabler på träffnivå. |
