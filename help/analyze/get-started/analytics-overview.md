---
description: Allmän information om Adobe Analytics
title: Adobe Analytics - översikt
feature: Analytics Basics
hide: true
hidefromtoc: true
source-git-commit: 1c6cc23c9cb6b4b007d2f296ea23e697cc135bd4
workflow-type: tm+mt
source-wordcount: '3098'
ht-degree: 3%

---

# Adobe Analytics - översikt

Med Adobe Analytics kan organisationer samla in data och få åtgärdbara insikter från alla digitala kundinteraktioner. Med djupgående analyser, flexibel rapportering och prediktiv analys får organisationer den insiktsfulla grund de behöver för att skapa bättre upplevelser för sina kunder.

## Viktiga fördelar

Nedan följer några av de viktigaste sätten som Adobe Analytics kan hjälpa företag att få viktiga insikter för att bättre kunna betjäna sina kunder.

Mer information om fördelarna med Adobe Analytics finns i [Adobe Analytics produktsida](https://business.adobe.com/products/analytics/adobe-analytics.html).

### Webbanalys

Adobe Analytics tillhandahåller följande komplexa segmenterings- och prediktiva verktyg för analys av webbplatstrafik:

* [Ad hoc-analys i Analysis Workspace](/help/analyze/analysis-workspace/home.md)

* [Flödesanalys](/help/analyze/analysis-workspace/visualizations/c-flow/flow.md)

* [avancerad segmentering](/https://experienceleague.adobe.com/docs/analytics/components/segmentation/seg-home.html)

### Marknadsföringsanalys

Adobe Analytics hjälper organisationer att förstå var kunderna interagerar med sina varumärken, vilka kanaler kunderna föredrar och vilka upplevelser som passar dem.

Följande viktiga funktioner i Adobe Analytics:

* Samling av flerkanalsdata

* [Integrering av offlinedata](https://experienceleague.adobe.com/docs/analytics/import/data-sources/overview.html?lang=en)

* [Ad hoc-analys i Analysis Workspace](/help/analyze/analysis-workspace/home.md)

### Attribuering

Med attribuering kan organisationer se hur olika interaktioner under kundresan påverkar konverteringen. Förutom att tillhandahålla fler traditionella attribueringsalternativ, som Linear- eller First Touch-modeller, använder Attribution i Adobe Analytics även maskininlärning och avancerade statistiska modeller för att förstå den exakta effekten av varje beröring.

Mer information finns i [Attributmodeller och uppslagsfönster](/help/analyze/analysis-workspace/attribution/models.md).


### Prediktiv analys

Prediktiv analys använder maskininlärning och avancerad statistisk modellering för att analysera kunddata, hitta mönster och förutse framtida beteenden som förändring eller sannolikhet för konvertering. Det gör det möjligt för dataanalytiker att utnyttja enorma datauppsättningar som annars skulle kunna slösas bort.

Följande viktiga funktioner i Adobe Analytics har dessa prediktiva funktioner:

* [Analysidentifiering](#anomaly-detection)

* [Bidragsanalys](#contribution-analysis)

* [Intelligenta aviseringar](#intelligent-alerts)

## Krav för att använda Adobe Analytics

Innan du kan använda Adobe Analytics måste du ha

* En giltig Adobe Analytics-licens

  Adobe Analytics kräver en licens. Kontakta din kontorepresentant för Adobe om du vill ha mer information. <!--is this phrased correctly? Is this important? -->

* En webbläsare som stöds

  Alla användare som använder Adobe Analytics måste använda en webbläsare som stöds. Mer information finns i [Systemkrav för Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/analyze/admin-overview/sys-reqs.html?lang=en).

<!-- are there more? -->

## Förstå analysgränssnittet

Adobe Analytics gränssnitt består av följande huvudområden:

### Fliken Arbetsyta

The [!UICONTROL Workspace] visas en lista med Analysis Workspace-projekt.

1. I Adobe Analytics väljer du [!UICONTROL **Arbetsyta**] -fliken.

   ![Fliken Arbetsyta](assets/landing-all2.png)

Mer information om funktioner finns på [!UICONTROL Workspace] flik, se [Adobe Analytics landningssida](/help/analyze/landing.md).

### Fliken Rapport

Från och med den 31 december 2023 avser Adobe att upphöra med rapporter och analyser och tillhörande rapporter och funktioner.

Använd i stället [!UICONTROL **Rapporter**] området i den vänstra listen på vänster sida [!UICONTROL **Arbetsyta**] -fliken. Mer information finns i *Navigera på fliken Rapporter* in [Adobe Analytics landningssida](/help/analyze/landing.md).

### Fliken Komponenter

The [!UICONTROL Components] -fliken innehåller funktioner som hjälper dig att finjustera och underlätta dataanalysen.

1. I Adobe Analytics väljer du [!UICONTROL **Komponenter**] tabbtangenten och sedan välja [!UICONTROL **Alla komponenter**].

   ![Fliken Arbetsyta](assets/components-tab.png)

2. Välj någon av följande produktfunktioner för att konfigurera den:


   | Funktioner |  -funktion | Mer information |
   |---------|----------|----------|
   | Segment | Med Adobe Analytics kan ni skapa, hantera, dela och tillämpa kraftfulla, fokuserade målgruppssegment i era rapporter med hjälp av Analytics-funktionerna, Adobe Experience Cloud, Adobe Target och andra integrerade Adobe-produkter. | [Analytics-segmentering](https://experienceleague.adobe.com/docs/analytics/components/segmentation/seg-home.html?lang=en) |
   | Beräknade värden | Beräknade och avancerade beräknade (eller härledda) mått är anpassade mått som du kan skapa utifrån befintliga mätvärden.  Med dem kan marknadsförare, produktchefer och analytiker ställa frågor om data utan att behöva ändra implementeringen av Analytics. | [Beräknade och avancerade beräknade (härledda) mätvärden](https://experienceleague.adobe.com/docs/analytics/components/calculated-metrics/cm-overview.html?lang=en) |
   | Datumintervall | Analysis Workspace innehåller en lista med standarddatumintervall som användare kan använda när de skapar analyser. Dessutom kan du skapa anpassade datumintervall och göra dem tillgängliga för användare i Analysis Workspace. | [Skapa anpassade datumintervall](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/components/calendar-date-ranges/custom-date-ranges.html?lang=en) <!-- should create an article in the Components Guide for managing/creating date ranges. This article in the Tools Guide needs updating. --> |
   | Virtuella rapportsviter |  |  |
   | Larm | Intelligenta aviseringar ger mer exakt kontroll över aviseringar och integrerar avvikelseidentifiering med varningssystemet. | [Intelligenta aviseringar](https://experienceleague.adobe.com/docs/analytics/components/alerts/intellligent-alerts.html?lang=en) |
   | Målgrupper | Med målgrupperna kan ni mäta webbplatsens resultat och följa utvecklingen mot målmålen. När du skapar mål väljer du vilka attributvärden eller eVars som du vill mäta, eller så kan du välja att mäta hela webbplatsen mot det valda måttet. <p>Målen ingår i Rapporter och analyser. Läs mer om rapporter och analyser [Meddelande om att produkten är slut](https://express.adobe.com/page/6WnF8JK6IRDhf/).</p> | [Målgrupper](https://experienceleague.adobe.com/docs/analytics/analyze/reports-analytics/targets.html?lang=en) |
   | Kalenderhändelser | För rapporter som utvecklats över tid kan du med kalenderhändelser visa händelser grafiskt och se om kampanjer eller andra händelser har påverkat webbplatsens trafik, intäkter eller andra mätvärden. | [Kalenderhändelser](https://experienceleague.adobe.com/docs/analytics/components/t-calendar-event.html?lang=en) |
   | Anteckningar | Anteckningar i Workspace gör att du effektivt kan kommunicera kontextuella datanunkter och insikter till din organisation. De gör att du kan koppla kalenderhändelser till specifika dimensioner och mätvärden. | [Hantera anteckningar](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/components/annotations/manage-annotations.html?lang=en) |
   | Klassificeringsuppsättningar | Klassificeringsuppsättningar har ett enda gränssnitt för att hantera klassificeringar och regler. <p>En klassificering är ett sätt att kategorisera Analytics-variabeldata och sedan visa data på olika sätt när du genererar rapporter. Du upprättar en relation mellan ett variabelvärde och metadata som är relaterade till det värdet. Klassificeringar kan användas för de flesta anpassade dimensioner, som spårningskod, props och eVars.</p> | [Översikt över klassificeringsuppsättningar](https://experienceleague.adobe.com/docs/analytics/components/classifications/sets/overview.html?lang=en) |
   | Platser | För att kunna importera Adobe Analytics-klassificeringsdata från ett molnmål måste du först lägga till och konfigurera platsen där du vill att klassificeringsdata ska samlas in. Du kan skapa, redigera och ta bort platser. | [Platshanteraren](https://experienceleague.adobe.com/docs/analytics/components/locations/locations-manager.html?lang=en) |
   | Schemalagda projekt | När du hanterar schemalagda projekt kan du redigera och ta bort återkommande projektscheman, söka efter ett schema i sökfältet eller med filteralternativen i den vänstra listen och filtrera efter tagg, godkända scheman, ägare med mera. | [Schemalagda projekt](/help/components/scheduled-projects-manager.md) |
   | Bokmärken | Bokmärken ger dig tillgång till de rapporter du använder mest. Bokmärkena som du skapar läggs till i Experience Cloud och finns i integrerade funktioner som dataanslutningar. <p>Bokmärken ingår i Rapporter och analyser. Läs mer om rapporter och analyser [Meddelande om att produkten är slut](https://express.adobe.com/page/6WnF8JK6IRDhf/). | [Bokmärkeshanteraren](https://experienceleague.adobe.com/docs/analytics/analyze/reports-analytics/bookmarks.html?lang=en) |
   | Kontrollpaneler | Kontrollpaneler skapas för att visualisera mätvärden och tillhandahålla interaktiv analysfunktion med data. Genom att klicka på objekt i en kontrollpanel kan du snabbt och enkelt segmentera data för att hämta information från din analys. <p>Instrumentpaneler ingår i Datan Workbench. Läs mer om Datan Workbench [Meddelande om att produkten är slut](https://experienceleague.adobe.com/docs/data-workbench/using/eol.html?lang=en). | [Instrumentpanelshanteraren](https://experienceleague.adobe.com/docs/analytics/analyze/reports-analytics/dashboard-manage.html?lang=en) |
   | Schemalagda rapporter | Administratörsnivåanvändare kan se och hantera schemalagda rapporter i hela organisationen. | [Schemalagd rapportkö](https://experienceleague.adobe.com/docs/analytics/components/scheduled-reports-admin.html?lang=en) |
   | Rapportinställningar | Dessa inställningar avser äldre Adobe Analytics-produkter, som inte innehåller Analysis Workspace och dess tillhörande komponenter. Gå till Komponenter > Inställningar om du vill göra ändringar i Analysis Workspace-inställningarna. |  |
   | Inställningar | Hantera inställningar för Analysis Workspace och dess tillhörande komponenter för alla nya projekt eller paneler som du skapar. Befintliga projekt och paneler påverkas inte. | [Inställningar](/help/analyze/analysis-workspace/user-preferences.md) |

   {style="table-layout:auto"}

### Fliken Verktyg

Fliken Verktyg ...

1. I Adobe Analytics väljer du [!UICONTROL **verktyg**] tabbtangenten och sedan välja [!UICONTROL **Alla verktyg**].

   ![Fliken Arbetsyta](assets/tools-tab.png)

2. Välj någon av följande produktfunktioner för att konfigurera den:

   | Funktioner |  -funktion | Mer information |
   |---------|----------|----------|
   | Data Warehouse | Data Warehouse avser kopian av Analytics-data för lagring och anpassade rapporter, som du kan köra genom att filtrera data. <p>Med Hanteraren för begäran kan du visa, duplicera och prioritera om begäranden.</p> | [Hantera Data Warehouse-förfrågningar](https://experienceleague.adobe.com/docs/analytics/export/data-warehouse/data-warehouse-requests-manage.html?lang=en) |
   | Activity Map | Activity Map är utformat för att rangordna länkaktivitet med hjälp av visuella överlägg och tillhandahålla en instrumentpanel med realtidsanalyser för att övervaka målgruppernas engagemang på era webbsidor. Ni kan skapa olika vyer för att visuellt identifiera kundaktivitetens acceleration, kvantifiera marknadsföringssatsningar och agera utifrån målgruppens behov och beteenden. | [Översikt över Activity Map](https://experienceleague.adobe.com/docs/analytics/analyze/activity-map/activity-map.html?lang=en) |
   | Recommendations Classic |  |  |
   | Sök och marknadsför |  |  |
   | Mobiltjänster |  |  |
   | Kontrollpaneler för analyser (mobilapp) |  |  |
   | Report Builder |  |  |

   {style="table-layout:auto"}

### Fliken Admin

Fliken Admin ...

1. I Adobe Analytics väljer du [!UICONTROL **Administratör**] tabbtangenten och sedan välja [!UICONTROL **Alla administratörer**].

   ![Fliken Arbetsyta](assets/admin-tab.png)

## Kom igång för administratörer, analytiker och slutanvändare

Det finns tre typer av Adobe Analytics-användare i en typisk organisation: administratörer, analytiker och slutanvändare.

Administratörer implementerar och konfigurerar Adobe Analytics, analytiker konfigurerar projekt och skapar analyser med Analysis Workspace, och slutanvändarna får åtgärdbara insikter om sina kunder, antingen genom att skapa egna analyser eller genom att arbeta med analytiker för att skapa dem.

Expandera avsnitten nedan för att lära dig hur dessa användare kan komma igång med Adobe Analytics.

### Kom igång för administratörer

Analysadministratörer ansvarar för att välja den implementeringsmetod som passar bäst för deras organisation.

När Adobe Analytics har implementerats måste administratörer utföra olika konfigurationsuppgifter för att säkerställa att analytiker och slutanvändare får ut det fulla värdet från Adobe Analytics.

#### Bestäm vilka typer av data som ska samlas in

Med Adobe Analytics kan ni samla in data från flera olika typer av kanaler och samla ihop dem för att leverera meningsfulla kundinsikter i realtid.

Här följer några av de kanaler som stöds där data kan samlas in:

* Mobiltelefoner

* Sakernas internet

* TV

* Röstassistenter

* Anslutna bilar

* Och mer (nya kanaler som stöds läggs till regelbundet)

The [implementeringsmetod](https://experienceleague.adobe.com/docs/analytics/implementation/home.html) du väljer avgör vilken typ av data som kan samlas in.

#### Implementera Adobe Analytics

Det finns olika implementeringsmetoder för att implementera Adobe Analytics på din webbplats eller i din mobilapp.

Mer information om de olika metoderna finns i [Implementera Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/implementation/home.html).

| | Implementeringsmetoder |
|---------|---------|
| **Webbplatser** | <ul><li>Web SDK-tillägg (rekommenderas)</li><li>Webb-SDK</li><li>Analystillägg</li><li>Äldre JavaScript</li></ul> |
| **Mobilappar** | <ul><li>Mobile SDK-tillägg (rekommenderas)</li><li>Analystillägg</li></ul> |

{style="table-layout:auto"}

#### Konfigurera Adobe Analytics

Analysadministratörer bör utföra följande uppgifter innan de gör Adobe Analytics tillgängligt för användare i organisationen:

| Uppgift | Avsedd användning | Mer information |
|---------|----------|---------|
| Definiera administratörsroller | Adobe Analytics stöder olika typer av administratörer | [Administratörsroller i Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/admin/admin-console/admin-roles-in-analytics.html?lang=en) |
| Definiera behörigheter | Analysadministratörer måste tilldela produktprofiler i Admin Console för Adobe Analytics, Report Suite Tools och Analytics Tools. | [Analysbehörigheter i Admin Console](https://experienceleague.adobe.com/docs/analytics/admin/admin-console/permissions/summary-tables.html?lang=en) |
| Ställ in rapportsviter och definiera inställningar för ditt företag | En rapportsvit är en silo data som Adobe Analytics använder för att generera rapporter.<p>Administratörer kan också konfigurera [virtuella rapportsviter](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-about.html?lang=en) för ytterligare segmentdata.</p> | <ul><li>[Skapa en rapportsvit](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/manage-report-suites/c-new-report-suite/t-create-a-report-suite.html?lang=en)</li><li>[Översikt över företagsinställningar](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/company-settings/c-company-settings.html?lang=en)</li></ul> |
| Importera data | Med Adobe Analytics datakällor kan du importera ytterligare online- eller offlinedata för rapportering. | [Översikt över datakällor](https://experienceleague.adobe.com/docs/analytics/import/data-sources/overview.html?lang=en) |
| Klassificera data med klassificeringar | Med hjälp av klassificeringar kan du klassificera data så att du bättre kan använda variabler, så att du kan ta med mer innehåll i en enda variabel. | |
| Hantera komponenter | Använd Data Dictionary och hanteringsområdena för varje komponenttyp för att definiera vilka komponenter som är tillgängliga i din Analytics-implementering, samt vilka som är godkända för din organisation.<p>Detta bör vara en pågående aktivitet för att säkerställa att komponenterna används effektivt i organisationen. </p> | <ul><li>[Översikt över dataordlistan](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/components/data-dictionary/data-dictionary-overview.html?lang=en)</li><li>[Beräknat måttansvarig](https://experienceleague.adobe.com/docs/analytics/components/calculated-metrics/calcmetric-workflow/cm-manager.html?lang=en)</li><li>[Hantera segment](https://experienceleague.adobe.com/docs/analytics/components/segmentation/segmentation-workflow/seg-manage.html?lang=en)</li><li>[Skapa anpassade datumintervall](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/components/calendar-date-ranges/custom-date-ranges.html?lang=en)</li></ul> |
| Analys av avvikelseidentifiering och bidrag | | |
| avancerad segmentering | | |
| Publicera målgrupper i Audience Manager | | |
| Attribuering | | |
| Rapporteringsaktivitetshanteraren | | |
| Integreringar | Du kan visa information från andra program i Adobe Analytics. <p>Nedan följer några vanliga integreringar:</p><ul><li><a href="https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/a4t-panel.html?lang=en">Analyser för Target</a></li><li><a href="https://experienceleague.adobe.com/docs/media-analytics/using/media-overview.html?lang=en">Media Analytics</a></li> | |

{style="table-layout:auto"}

### Kom igång med analytiker

Medan vem som helst i en organisation kan använda Adobe Analytics för att få åtgärdbara insikter om kundbeteenden på olika webbplatser och i olika appar har Adobe Analytics utformats med dataanalytiker i åtanke.

Här följer några viktiga uppgifter och funktioner som analytikerna bör känna till för att kunna utnyttja Adobe Analytics och Analysis Workspace fullt ut.

| Funktion | Avsedd användning | Mer information |
|---------|----------|---------|
| Bygg och dela projekt i Analysis Workspace | Analysis Workspace är ett flexibelt webbläsarverktyg som gör att du snabbt kan skapa analyser och dela insikter. Med dra-och-släpp-gränssnittet kan ni utforma analyser, lägga till visualiseringar för att ge liv åt data, strukturera en datauppsättning, dela och schemalägga projekt med vem som helst i organisationen.<p>Dataanalytiker ansvarar ofta för att skapa projekt i Analysis Workspace för användare inom organisationen.</p><p>När projekten har skapats delar analytikerna dessa projekt med [slutanvändare](#end-users)(icke-analytiker) i sina organisationer som begärt data och hjälper dem att förstå hur de ska tolka dem.</p> | <ul><li>[Skapa projekt](/help/analyze/analysis-workspace/build-workspace-project/create-projects.md)</li><li>[Dela projekt](/help/analyze/analysis-workspace/curate-share/share-projects.md)</li></ul> |
| Attribuering | Analytikerna kan anpassa hur dimensionsposter får kredit för lyckade händelser genom att använda olika attribueringsmodeller och lookback-fönster i Analysis Workspace.<p>Linjära attribueringsmodeller ger samma betyg till alla kontaktytor som leder till konvertering, medan First Touch ger full uppskattning till den första kontaktytan. Många andra attribueringsmodeller finns tillgängliga, bland annat algoritmisk modell, som använder statistiska tekniker för att dynamiskt avgöra den optimala kreditfördelningen. </p> | [Attributmodeller och uppslagsfönster](/help/analyze/analysis-workspace/attribution/models.md) |
| Analysidentifiering | Statistisk modellering i Analysis Workspace hittar automatiskt oväntade trender i dina data genom att analysera mätvärden och fastställa en nedre gräns, övre gräns och förväntat värdeintervall. När en oväntad krökning eller släppning inträffar visas en varning i rapporten. | [Översikt över avvikelseidentifiering](/help/analyze/analysis-workspace/virtual-analyst/c-anomaly-detection/anomaly-detection.md) |
| Bidragsanalys | Använd Analysis Workspace för att identifiera dolda mönster i era data för att förklara statistiska avvikelser och identifiera samband bakom oväntade kundaktiviteter, utombundna värden och plötsliga toppar eller dalar för mätvärden mellan målgruppssegment. | [Översikt över bidragsanalys](/help/analyze/analysis-workspace/virtual-analyst/contribution-analysis/ca-tokens.md) |
| Intelligenta aviseringar | Skapa och hantera aviseringar baserat på dataavvikelser och&quot;staplade&quot; aviseringar som fångar in flera mätvärden i en enda avisering. | [Översikt över intelligenta aviseringar](help/analyze/analysis-workspace/c-intelligent-alerts/intellligent-alerts.md) |
| Dataexport | Med Data Warehouse- och datafeeds kan du exportera data till olika molnmål, till exempel Google Cloud Platform, Azure RBAC, Azure SAS och Amazon S3. | [Exporthandbok för Analytics](https://experienceleague.adobe.com/docs/analytics/export/home.html) |
| Aktivitetskarta | Activity Map är ett Adobe Analytics-program som är utformat för att rangordna länkaktivitet med visuella överlägg och tillhandahålla en instrumentpanel med realtidsanalyser för att övervaka målgruppens engagemang på era webbsidor.<p>Med Activity Map kan ni skapa olika vyer för att visuellt identifiera kundaktivitetens acceleration, kvantifiera marknadsföringssatsningar och agera utifrån målgruppens behov och beteenden.</p> | [Activity Map](https://experienceleague.adobe.com/docs/analytics/analyze/activity-map/activity-map.html) |
| Report Builder | Report Builder är ett tillägg för Microsoft Excel. Med Report Builder kan du skapa anpassade förfrågningar från Adobe Analytics-data som infogas i dina Excel-kalkylblad. Begäranden kan referera till celler dynamiskt i kalkylbladet, och du kan uppdatera och anpassa hur Report Builder visar data. | [Report Builder](https://experienceleague.adobe.com/docs/analytics/analyze/report-builder/home.html) |

{style="table-layout:auto"}

<!-- * Realtime reporting? -->

### Kom igång för slutanvändare

Slutanvändare som inte är professionella analytiker kan antingen samarbeta med analytiker i organisationen för att utnyttja Adobe Analytics och Analysis Workspace fullt ut, eller också kan de lära sig grunderna i Analysis Workspace för att få åtgärdbara insikter om sina kunder.

#### Arbeta med analytiker

Vanligtvis är användare i en organisation som är intresserade av att lära sig mer om kundbeteenden på olika webbplatser inte professionella analytiker.

Helst bör dessa användare arbeta med [analytiker](#analysts) inom en organisation för att

1. Definiera krav för analyserna genom att förklara för analytikerna vad de hoppas få veta om kunderna.

1. Granska analyserna för att säkerställa att de uppfyller målen.

1. Diskutera de data som erhållits från analyserna.

1. Ändra analyserna efter behov med tiden.

#### Skapa analyser i Analysis Workspace

Du behöver inte vara dataanalytiker för att få användbara insikter från Adobe Analytics.

En del användare kan tycka att det är praktiskt att arbeta med en dataanalytiker för att konfigurera ett projekt i Analysis Workspace och förklara hur data ska tolkas enligt beskrivningen i [Arbeta med analytiker](#work-with-analysts); andra användare kan vara bekväma med att bygga projektet och tolka själva data.

Med Analysis Workspace kan ni snabbt skapa analyser för att samla in insikter och sedan dela dessa insikter med andra. Med dra-och-släpp-gränssnittet i webbläsaren kan du utforma analyser, lägga till visualiseringar för att ge liv åt data, strukturera en datauppsättning samt dela och schemalägga projekt med vem du vill.

Mer information om hur du skapar analyser i Analysis Workspace finns i [Analysis Workspace - översikt](/help/analyze/analysis-workspace/home.md).

### Kom igång för utvecklare

[API:er för analys](https://developer.adobe.com/analytics-apis/docs/2.0/) gör att du kan anropa Adobe-servrar direkt för att utföra nästan alla åtgärder som du kan utföra i användargränssnittet.

Du kan skapa rapporter för att utforska, få insikter eller besvara viktiga frågor om dina data. Du kan också hantera komponenter i Adobe Analytics, till exempel när du skapar segment eller beräknade värden.

## Videoöversikt

Läs mer om grunderna i Adobe Analytics *Introduktion till Adobe Analytics - Webbseminarium om kunskapsbyggaren* video. Videon visar grunderna för hur data hämtas, hur data skickas till Adobe Analytics och vilka visualiseringsfunktioner du kan använda i Adobe Analytics. Videon ger er en grund för att bygga, driftsätta, samla in och tolka data, så att ni kan ge er åtgärdbara insikter och rekommendationer baserat på insamlade data.

>[!VIDEO](https://video.tv.adobe.com/v/27429/?quality=12)

Mer information om vilket verktyg som ska användas finns i [Vilket Adobe Analytics-verktyg ska jag använda?](https://experienceleague.adobe.com/docs/analytics/analyze/admin-overview/which-analytics-tool.html).

## Gå längre med Customer Journey Analytics

Customer Journey Analytics är Adobe nästa generation av Analytics-lösning som gör att ni kan använda kraften i Analysis Workspace med data från Adobe Experience Platform. Den kan bryta ned, filtrera, ställa frågor och visualisera årens datavärde och kombineras med plattformens möjlighet att lagra alla typer av datamappningar och datatyper.

Nedan följer några av fördelarna med Customer Journey Analytics framför Adobe Analytics:

* **Obegränsade variabler och händelser**: Begreppen eVars, props och händelser finns inte längre. Data fokuseras främst på dimensioner och mätvärden. Datauppsättningar kan ha ett obegränsat antal unika mått och mätvärden.

* **Obegränsade unika värden**: Adobe Experience Platform begränsas inte till några unika begränsningar.

* **Ändra historiska data**: Med Adobe Experience Platform kan data tas bort eller korrigeras.

* **Data för flera rapporter**: Befintliga implementeringar från flera datauppsättningar kan kombineras i Platform.

Mer information finns i [Customer Journey Analytics - översikt](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-overview.html?lang=en).

