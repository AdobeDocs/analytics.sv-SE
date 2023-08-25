---
description: Allmän översiktsinformation om Adobe Analytics, inklusive information om Analytics-gränssnittet samt komma igång-information för administratörer, analytiker, användare och utvecklare.
title: Kom igång för administratörer, analytiker, slutanvändare och utvecklare
feature: Analytics Basics
hide: true
hidefromtoc: true
source-git-commit: 5bf266628506bc2f664e4382f819615c5a082763
workflow-type: tm+mt
source-wordcount: '1901'
ht-degree: 4%

---

# Kom igång för administratörer, analytiker, slutanvändare och utvecklare

Det finns fyra typer av Adobe Analytics-användare i en typisk organisation:

* **Administratörer:** Implementera och konfigurera Adobe Analytics.

* **Analytiker:** Konfigurera projekt och skapa analyser med Analysis Workspace

* **Slutanvändare:** Få användbara insikter om sina kunder, antingen genom att skapa egna analyser eller genom att samarbeta med analytiker för att skapa dem

* **Utvecklare:** Använd API:erna i Adobe Analytics 2.0 för att direkt anropa Adobe för att utföra nästan alla åtgärder som kan utföras i användargränssnittet, som att skapa rapporter för att utforska, få insikter eller besvara viktiga frågor om data.

Informationen nedan visar hur dessa användare kan komma igång med Adobe Analytics.

## Kom igång för administratörer

Analysadministratörer ansvarar för att välja den implementeringsmetod som passar bäst för deras organisation.

När Adobe Analytics har implementerats måste administratörer utföra olika konfigurationsuppgifter för att säkerställa att analytiker och slutanvändare får ut det fulla värdet från Adobe Analytics. Administratörer bör också regelbundet övervaka sin Analytics-miljö för att säkerställa att systemet körs effektivt.

### Bestäm vilka typer av data som ska samlas in

Med Adobe Analytics kan ni samla in data från flera olika typer av kanaler och samla ihop dem för att leverera meningsfulla kundinsikter i realtid.

Här följer några av de kanaler som stöds där data kan samlas in:

* Mobiltelefoner

* Sakernas internet

* TV

* Röstassistenter

* Anslutna bilar

* Och mer (nya kanaler som stöds läggs till regelbundet)

The [implementeringsmetod](https://experienceleague.adobe.com/docs/analytics/implementation/home.html) du väljer avgör vilken typ av data som kan samlas in.

### Implementera Adobe Analytics

Det finns olika implementeringsmetoder för att implementera Adobe Analytics på din webbplats eller i din mobilapp.

Mer information om de olika metoderna finns i [Implementera Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/implementation/home.html).

| | Implementeringsmetoder |
|---------|---------|
| **Webbplatser** | <ul><li>Web SDK-tillägg (rekommenderas)</li><li>Webb-SDK</li><li>Analystillägg</li><li>Äldre JavaScript</li></ul> |
| **Mobilappar** | <ul><li>Mobile SDK-tillägg (rekommenderas)</li><li>Analystillägg</li></ul> |

{style="table-layout:auto"}

### Konfigurera Adobe Analytics

Analysadministratörer bör utföra följande uppgifter innan de gör Adobe Analytics tillgängligt för användare i organisationen:

| Uppgift | Avsedd användning | Mer information |
|---------|----------|---------|
| Definiera administratörsroller | Adobe Analytics stöder olika typer av administratörer | [Administratörsroller i Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/admin/admin-console/admin-roles-in-analytics.html?lang=en) |
| Definiera behörigheter | Analysadministratörer måste tilldela produktprofiler i Admin Console för Adobe Analytics, Report Suite Tools och Analytics Tools. | [Analysbehörigheter i Admin Console](https://experienceleague.adobe.com/docs/analytics/admin/admin-console/permissions/summary-tables.html?lang=en) |
| Ställ in rapportsviter och definiera inställningar för ditt företag | En rapportsvit är en silo data som Adobe Analytics använder för att generera rapporter.<p>Administratörer kan också konfigurera [virtuella rapportsviter](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-about.html?lang=en) för ytterligare segmentdata.</p> | <ul><li>[Skapa en rapportsvit](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/manage-report-suites/c-new-report-suite/t-create-a-report-suite.html?lang=en)</li><li>[Översikt över företagsinställningar](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/company-settings/c-company-settings.html?lang=en)</li></ul> |
| Importera data | Med Adobe Analytics datakällor kan du importera ytterligare online- eller offlinedata för rapportering. | [Översikt över datakällor](https://experienceleague.adobe.com/docs/analytics/import/data-sources/overview.html?lang=en) |
| Klassificera data med klassificeringar | Med hjälp av klassificeringar kan du klassificera data så att du bättre kan använda variabler, så att du kan ta med mer innehåll i en enda variabel. | [Klassificeringsöversikt](https://experienceleague.adobe.com/docs/analytics/components/classifications/c-classifications.html?lang=en) |
| Hantera komponenter | Använd Data Dictionary och hanteringsområdena för varje komponenttyp för att definiera vilka komponenter som är tillgängliga i din Analytics-implementering, samt vilka som är godkända för din organisation.<p>Detta bör vara en pågående aktivitet för att säkerställa att komponenterna används effektivt i organisationen. </p> | <ul><li>[Översikt över dataordlistan](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/components/data-dictionary/data-dictionary-overview.html?lang=en)</li><li>[Beräknat måttansvarig](https://experienceleague.adobe.com/docs/analytics/components/calculated-metrics/calcmetric-workflow/cm-manager.html?lang=en)</li><li>[Hantera segment](https://experienceleague.adobe.com/docs/analytics/components/segmentation/segmentation-workflow/seg-manage.html?lang=en)</li><li>[Skapa anpassade datumintervall](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/components/calendar-date-ranges/custom-date-ranges.html?lang=en)</li></ul> |
| Analysidentifiering | Analysidentifiering är en statistisk metod för att fastställa hur ett givet mätresultat har ändrats i förhållande till tidigare data. | [Översikt över avvikelseidentifiering](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/virtual-analyst/anomaly-detection/anomaly-detection.html?lang=en) |
| Bidragsanalys | Contribute Analysis avslöjar dolda mönster i era data för att förklara statistiska avvikelser och identifiera korrelationer bakom oväntade kundaktiviteter, obundna värden och plötsliga toppar eller dalar för valda mätvärden över konvergerande målgruppssegment. | [Översikt över bidragsanalys](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/virtual-analyst/contribution-analysis/ca-tokens.html?lang=en) |
| Analytics-segmentering | Gör att ni kan skapa, hantera, dela och tillämpa kraftfulla, fokuserade målgruppssegment i era rapporter med hjälp av Analytics-funktionerna, Adobe Experience Cloud, Adobe Target och andra integrerade Adobe-produkter. | [Analytics-segmentering](https://experienceleague.adobe.com/docs/analytics/components/segmentation/seg-home.html?lang=en) |
| Publicera målgrupper i Audience Manager | Adobe Audience Manager är en kraftfull datahanteringsplattform som hjälper er att skapa unika målgruppsprofiler från dataintegreringar från första part, andra part (partner) och tredje part. | [Audience Analytics - översikt](https://experienceleague.adobe.com/docs/analytics/integration/audience-analytics/mc-audiences-aam.html?lang=en) |
| Integreringar | Du kan visa information från andra program i Adobe Analytics. <p>Nedan följer några vanliga integreringar:</p><ul><li><a href="https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/a4t-panel.html?lang=en">Analyser för Target</a></li><li><a href="https://experienceleague.adobe.com/docs/media-analytics/using/media-overview.html?lang=en">Media Analytics</a></li> | [Analytics-integrering](https://experienceleague.adobe.com/docs/analytics/integration/home.html?lang=en) |

{style="table-layout:auto"}

### Övervaka Adobe Analytics

Det finns olika funktioner som hjälper dig att övervaka din Adobe Analytics-miljö.

Analysadministratörer bör vara medvetna om följande funktioner som är tillgängliga för att övervaka viktiga aspekter av din Analytics-miljö:

| Uppgift | Avsedd användning | Mer information |
|---------|----------|---------|
| Rapporteringsaktivitetshanteraren | Med Rapporteringsaktivitetshanteraren kan du se rapporteringskapaciteten för varje rapportsvit i organisationen. Den ger detaljerad insyn i hur man rapporterar förbrukning och hjälper er att enkelt diagnostisera och åtgärda kapacitetsproblem under perioder med hög rapporteringsnivå. | [Rapporteringsaktivitetshanteraren](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/reporting-activity.html?lang=en) |
| Serversamtalsanvändning | Ett serveranrop, även kallat &quot;träff&quot; eller &quot;bildbegäran&quot;, är en instans där data skickas till Adobe-servrar för bearbetning. Det finns en kontrollpanel för användning av serversamtal som spårar dina förbrukningsdata för serversamtal och jämför dem med din avtalsgräns. Du kan ställa in varningsmeddelanden för att förhindra övertäckning. | [Översikt över användningen av serversamtal](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/server-call-usage/overage-overview.html?lang=en) |
| Loggfiler | Logga filer som hjälper dig att se när användare loggar in, deras användning, åtkomst, rapportsviter och administratörsändringar. | [Loggar](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/logs.html?lang=en) |

{style="table-layout:auto"}

## Kom igång med analytiker

Medan vem som helst i en organisation kan använda Adobe Analytics för att få åtgärdbara insikter om kundbeteenden på olika webbplatser och i olika appar har Adobe Analytics utformats med dataanalytiker i åtanke.

Här följer några viktiga uppgifter och funktioner som analytikerna bör känna till för att kunna utnyttja Adobe Analytics och Analysis Workspace fullt ut.

| Funktion | Avsedd användning | Mer information |
|---------|----------|---------|
| Bygg och dela projekt i Analysis Workspace | Analysis Workspace är ett flexibelt webbläsarverktyg som gör att du snabbt kan skapa analyser och dela insikter. Med dra-och-släpp-gränssnittet kan ni utforma analyser, lägga till visualiseringar för att ge liv åt data, strukturera en datauppsättning, dela och schemalägga projekt med vem som helst i organisationen.<p>Dataanalytiker ansvarar ofta för att skapa projekt i Analysis Workspace för användare inom organisationen.</p><p>När projekten har skapats delar analytikerna dessa projekt med [slutanvändare](#end-users)(icke-analytiker) i sina organisationer som begärt data och hjälper dem att förstå hur de ska tolka dem.</p> | <ul><li>[Skapa projekt](/help/analyze/analysis-workspace/build-workspace-project/create-projects.md)</li><li>[Dela projekt](/help/analyze/analysis-workspace/curate-share/share-projects.md)</li></ul> |
| Attribuering | Analytikerna kan anpassa hur dimensionsposter får kredit för lyckade händelser genom att använda olika attribueringsmodeller och lookback-fönster i Analysis Workspace.<p>Linjära attribueringsmodeller ger samma betyg till alla kontaktytor som leder till konvertering, medan First Touch ger full uppskattning till den första kontaktytan. Många andra attribueringsmodeller finns tillgängliga, bland annat algoritmisk modell, som använder statistiska tekniker för att dynamiskt avgöra den optimala kreditfördelningen. </p> | [Attributmodeller och uppslagsfönster](/help/analyze/analysis-workspace/attribution/models.md) |
| Analysidentifiering | Statistisk modellering i Analysis Workspace hittar automatiskt oväntade trender i dina data genom att analysera mätvärden och fastställa en nedre gräns, övre gräns och förväntat värdeintervall. När en oväntad krökning eller släppning inträffar visas en varning i rapporten. | [Översikt över avvikelseidentifiering](/help/analyze/analysis-workspace/virtual-analyst/c-anomaly-detection/anomaly-detection.md) |
| Bidragsanalys | Använd Analysis Workspace för att identifiera dolda mönster i era data för att förklara statistiska avvikelser och identifiera samband bakom oväntade kundaktiviteter, utombundna värden och plötsliga toppar eller dalar för mätvärden mellan målgruppssegment. | [Översikt över bidragsanalys](/help/analyze/analysis-workspace/virtual-analyst/contribution-analysis/ca-tokens.md) |
| Intelligenta aviseringar | Skapa och hantera aviseringar baserat på dataavvikelser och&quot;staplade&quot; aviseringar som fångar in flera mätvärden i en enda avisering. | [Översikt över intelligenta aviseringar](/help/analyze/analysis-workspace/c-intelligent-alerts/intellligent-alerts.md) |
| Dataexport | Med Data Warehouse- och datafeeds kan du exportera data till olika molnmål, till exempel Google Cloud Platform, Azure RBAC, Azure SAS och Amazon S3. | [Exporthandbok för Analytics](https://experienceleague.adobe.com/docs/analytics/export/home.html) |
| Aktivitetskarta | Activity Map är ett Adobe Analytics-program som är utformat för att rangordna länkaktivitet med visuella överlägg och tillhandahålla en instrumentpanel med realtidsanalyser för att övervaka målgruppens engagemang på era webbsidor.<p>Med Activity Map kan ni skapa olika vyer för att visuellt identifiera kundaktivitetens acceleration, kvantifiera marknadsföringssatsningar och agera utifrån målgruppens behov och beteenden.</p> | [Activity Map](https://experienceleague.adobe.com/docs/analytics/analyze/activity-map/activity-map.html) |
| Report Builder | Report Builder är ett tillägg för Microsoft Excel. Med Report Builder kan du skapa anpassade förfrågningar från Adobe Analytics-data som infogas i dina Excel-kalkylblad. Begäranden kan referera till celler dynamiskt i kalkylbladet, och du kan uppdatera och anpassa hur Report Builder visar data. | [Report Builder](https://experienceleague.adobe.com/docs/analytics/analyze/report-builder/home.html) |

{style="table-layout:auto"}

<!-- * Realtime reporting? -->

## Kom igång för slutanvändare

Slutanvändare som inte är professionella analytiker kan antingen samarbeta med analytiker i organisationen för att utnyttja Adobe Analytics och Analysis Workspace fullt ut, eller också kan de lära sig grunderna i Analysis Workspace för att få åtgärdbara insikter om sina kunder.

### Arbeta med analytiker

Vanligtvis är användare i en organisation som är intresserade av att lära sig mer om kundbeteenden på olika webbplatser inte professionella analytiker.

Helst bör dessa användare arbeta med [analytiker](#analysts) inom en organisation för att

1. Definiera krav för analyserna genom att förklara för analytikerna vad de hoppas få veta om kunderna.

1. Granska analyserna för att säkerställa att de uppfyller målen.

1. Diskutera de data som erhållits från analyserna.

1. Ändra analyserna efter behov med tiden.

### Skapa analyser i Analysis Workspace

Du behöver inte vara dataanalytiker för att få användbara insikter från Adobe Analytics.

En del användare kan tycka att det är praktiskt att arbeta med en dataanalytiker för att konfigurera ett projekt i Analysis Workspace och förklara hur data ska tolkas enligt beskrivningen i [Arbeta med analytiker](#work-with-analysts); andra användare kan vara bekväma med att bygga projektet och tolka själva data.

Med Analysis Workspace kan ni snabbt skapa analyser för att samla in insikter och sedan dela dessa insikter med andra. Med dra-och-släpp-gränssnittet i webbläsaren kan du utforma analyser, lägga till visualiseringar för att ge liv åt data, strukturera en datauppsättning samt dela och schemalägga projekt med vem du vill.

Mer information om hur du skapar analyser i Analysis Workspace finns i [Analysis Workspace - översikt](/help/analyze/analysis-workspace/home.md).

## Kom igång för utvecklare

[API:er för analys](https://developer.adobe.com/analytics-apis/docs/2.0/) gör att du kan anropa Adobe-servrar direkt för att utföra nästan alla åtgärder som du kan utföra i användargränssnittet.

Du kan skapa rapporter för att utforska, få insikter eller besvara viktiga frågor om dina data. Du kan också hantera komponenter i Adobe Analytics, till exempel när du skapar segment eller beräknade värden.