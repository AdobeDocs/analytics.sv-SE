---
title: Aktuella versionsinformation för Adobe Analytics
description: Visa den aktuella versionsinformationen för Adobe Analytics
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 4134eed3cb97c478304988123196b0c906c86560
workflow-type: tm+mt
source-wordcount: '1225'
ht-degree: 1%

---

# Aktuell versionsinformation för Adobe Analytics (oktober 2023)

**Senaste uppdatering**: 4 oktober 2023

Versionsinformationen för oktober omfattar frisläppningsperioden 4 oktober 2023 till 25 oktober 2023. Adobe Analytics-releaser fungerar på en [kontinuerlig leveransmodell](releases.md) vilket ger en mer skalbar, stegvis metod för driftsättning av funktioner. Därför uppdateras versionsinformationen flera gånger i månaden. Kontrollera dem regelbundet.

## Nya funktioner eller förbättringar {#features}

| Funktion | Beskrivning | [Startar](releases.md) | [Allmän tillgänglighet](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Nya kolumner är tillgängliga när komponenter hanteras** | Följande nya kolumner är nu tillgängliga när du hanterar komponenter:<ul><li>Används i<p>Den här kolumnen är tillgänglig i [Beräknat måttansvarig](/help/components/c-calcmetrics/c-workflow/cm-workflow/cm-manager.md) och [Segmenthanterare](/help/components/segmentation/segmentation-workflow/seg-manage.md).</p></li><li>Senast använd<p>Den här kolumnen är tillgänglig i [Beräknat måttansvarig](/help/components/c-calcmetrics/c-workflow/cm-workflow/cm-manager.md), [Segmenthanterare](/help/components/segmentation/segmentation-workflow/seg-manage.md)och [Varningshanteraren](/help/components/c-alerts/alert-manager.md).</p></li></ul><p>Den här informationen kan hjälpa dig att avgöra om en komponent är värdefull för användare i organisationen, var den används och om den behöver tas bort eller ändras. Du kan använda ordlistan tillsammans med den här informationen för att hålla reda på och förstå hur komponenter används i organisationen bättre.</p> | 20 september 2023 | 4 oktober 2023 |
| **Förbättringar av Rapporteringsaktivitetshanteraren** | Med Rapporteringsaktivitetshanteraren kan du se rapporteringskapaciteten för varje rapportsvit i organisationen.  Det ger administratörer detaljerad insyn i rapporteringen av förbrukning för att enkelt kunna diagnostisera och åtgärda kapacitetsproblem under perioder med hög rapporteringsnivå. Nedan följer några av förbättringarna som nu finns i Reporting Activity Manager: <ul><li>Begränsa efterföljande begäranden: Förutom att avbryta aktuella begäranden kan administratörer nu begränsa begäranden för en angiven tidsperiod. Administratörer kan begränsa begäranden efter begäran, projekt och användare.</li><li>Utöver användnings- och kapacitetsstatistik innehåller nu Reporting Activity Manager fler data om rapporteringsaktivitet: kolumnen Komplexitet, kolumnen Användare och kolumnen Anslutning.</li><li>Alla avbrott och begränsningar som görs i Rapporteringsaktivitetshanteraren visas nu i granskningsloggen. Administratörer kan använda granskningsloggen för att visa det som för närvarande är avbrutet. Det går inte att återställa annulleringar i Rapporteringsaktivitetshanteraren eller i granskningsloggen.</li></ul><p>Mer information finns i [Översikt över Reporting Activity Manager](/help/admin/admin/reporting-activity-manager/reporting-activity-overview.md)</p> | 17 oktober 2023 | 23 oktober 2023 |
| **Förbättrad Data Warehouse** | När du skapar en begäran om Data Warehouse kan du nu konfigurera ett molnkonto som ska användas som rapportmål. Följande typer av molnkonton är tillgängliga för att skicka data:<ul><li>Amazon S3</li><li>Google Cloud Platform</li><li>Azure SAS</li><li>Azure RBAC</li><li>E-post (det här alternativet var tidigare tillgängligt)</li></ul>FTP, SFTP, Azure Blob och S3 är fortfarande tillgängliga som rapportmål, men rekommenderas inte längre.<p>Användarupplevelsen när begäranden om Data Warehouse skapas och hanteras har också förbättrats. Mer information finns i [Skapa en begäran om Data Warehouse](/help/export/data-warehouse/create-request/t-dw-create-request.md) och [Hantera förfrågningar från Data Warehouse](https://experienceleague.adobe.com/docs/analytics/export/data-warehouse/data-warehouse-requests-manage.html). | 12 september 2023 | 25 oktober 2023 |
| **Migrera Adobe Analytics-projekt och alla komponenter som ingår till Customer Journey Analytics** | Nu kan du migrera dina Adobe Analytics-projekt till Customer Journey Analytics. Den här processen förenklar övergången från Adobe Analytics till Customer Journey Analytics. <p>När du migrerar projekt till Customer Journey Analytics mappas resurserna från en Adobe Analytics-rapportsvit till en datavy i Customer Journey Analytics.</p> <p>Du migrerar projekt till Customer Journey Analytics från Adobe Analytics gränssnitt. [Läs mer](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/component-migration/prepare-component-migration.html)</p> | Ej tillämpligt | 9 oktober 2023 |

{style="table-layout:auto"}

## Korrigeringar i Adobe Analytics

* Korrigerade problem där A4T-rapporter inte visades i gränssnittet för mål/analys. (AN-329375, AN-329745, AN-330026)

AN-313983; AN-324189; AN-325095; AN-325677; AN-325886; AN-326068; AN-326360; AN 326458; AN-327290; AN-327315; AN-327353; AN-327505; AN-327589; AN-327609; AN-3 27922; AN-328110; AN-328222; AN-328261; AN-328496; AN-328577; AN-328629; AN-32 8736; AN-328888; AN-328899; AN-328902; AN-328921; AN-328958; AN-329208; AN-329 277; AN-329332; AN-329334; AN-329335; AN-329336; AN-329357; AN-329385; AN-3293 87; AN-329397; AN-329463; AN-329501; AN-329504; AN-329505; AN-329515; AN-32952 4; AN-329526; AN-329534; AN-329539; AN-329541; AN-329543; AN-329545; AN-329564; AN-329570; AN-329623; AN-329624; AN-329636; AN-329646; AN-329647; AN-32968; AN-329701; AN-329737; AN-329741; AN-329751; AN-329812; AN-329813; AN-329821; AN-3 29824; AN-329833; AN-329848; AN-329852; AN-329861; AN-329863; AN-329874; AN-32 9882; AN-329911; AN-329917; AN-329942; AN-329954; AN-329968; AN-329971; AN-329 982; AN-330044; AN-330052; AN-330131; AN-330132; AN-330230; AN-330352; AN-3303 67; AN-330541; AN-330599

## Viktiga meddelanden för Adobe Analytics-administratörer {#admin}

| Meddelande | Datum tillagt eller uppdaterat | Beskrivning |
| ----------- | ---------- | ---------- |
| **Fullständig IP-krånglighet för Adobe Experience Edge-träffar** | 27 september 2023 | IP-infusation för träffar från Experience Edge kommer att uppdateras senare i oktober 2023. I april lade Experience Edge till möjligheten att dölja IP-adresser. På den tiden stödde Adobe Analytics endast delvis oreda av IP-adresser på grund av hur Analytics-processerna slår igenom från Experience Edge. När kunderna valde fullständig okunskap för Experience Edge fick Analytics bara delvis ofokuserade IP-adresser. När den här ändringen implementeras får Analytics den fullständigt dolda IP-adressen. |
| **Adobe Analytics LiveStream - API:er för Analytics 2.0** | 27 september 2023 | Kunderna har nu tillgång till [Slutpunktshandbok för Adobe Analytics LiveStream](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/livestream/) i Adobe Analytics 2.0 API:er i stället på sin tidigare plats, med 1.4 API:er. Observera att kunder som använder Adobe I/O JWT-inloggningsuppgifter måste migrera till inloggningsuppgifterna för Adobe I/O OAuth Server-till-Server senast 1 januari 2025. (Se informationen i EOL-meddelanden nedan.) |

{style="table-layout:auto"}

## EOL-meddelanden (End-of-life) {#eol}

| EOL-produkt eller -funktion | Datum tillagt eller uppdaterat | Beskrivning |
| --- | --- | --- |
| **Migrering till autentiseringsuppgifter för Adobe I/O OAuth Server-till-Server** | 11 maj 2023 | Adobe Analytics API- och LiveStream-kunder som använder Adobe I/O JWT-autentiseringsuppgifter måste migrera till Adobe I/O OAuth Server-till-Server-autentiseringsuppgifter genom att **1 januari 2025**. Adobe I/O tillåter inte att nya JWT-autentiseringsuppgifter skapas från och med 1 maj 2024. Kunder som använder JWT måste skapa en ny OAuth Server-till-Server-autentiseringsuppgift eller migrera sina befintliga JWT-autentiseringsuppgifter till en OAuth Server-till-Server-autentiseringsuppgift. Kunderna måste även uppdatera sina klientprogram för att kunna använda de nya autentiseringsuppgifterna för OAuth Server-till-Server. <ul><li>[Migrerar från JWT-autentiseringsuppgifter (Service Account)](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)</li><li>[Implementeringsguide för nya och gamla program med OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)<li>[Använda de nya autentiseringsuppgifterna för OAuth Server-till-Server](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)</li><li>[Vanliga frågor](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)</li></ul> |
| **EOL för[!DNL Reports & Analytics]** | 7 mars 2023 | Effektivt **31 december 2023** kommer Adobe att upphöra med sin verksamhet [!DNL Reports & Analytics] och tillhörande rapporter och funktioner. Rapporterna, visualiseringar och underliggande teknik som ger kraft åt [!DNL Reports & Analytics] inte längre uppfyller Adobe teknikstandarder. Mest [!DNL Reports & Analytics] funktioner finns i [Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html). Sedan Analysis Workspace släpptes 2015 har [!DNL Reports & Analytics] funktionaliteten och funktionerna har flyttats till Analysis Workspace och ett tröskelvärde för arbetsflödets paritet har uppnåtts. [Detta meddelande](https://spark.adobe.com/page/6WnF8JK6IRDhf/) förklarar processen för att avsluta livscykeln.<p>Den 31 december 2023 kommer många av de tillhörande funktionerna för rapporter och analys att avslutas, inklusive, men inte begränsat till, schemalagda rapporter, dataextrakt och DL-rapporter. Efter den 31 december 2023 skickas inga schemalagda rapporter längre. I **April 2023**, uppdaterades alla rapporter som skulle ha gått ut efter den 31 december 2023 automatiskt och upphörde att gälla den 31 december 2023. Dessutom kan du inte längre schemalägga framtida rapporter efter 31 december 2023. |
| **EOL för [!UICONTROL Publishing Lists] funktion** | 29 september 2022 | Som en del av ledningscentralen för rapporter och analyser [!UICONTROL Publishing Lists] kommer att nå slutet av livscykeln i **December 2023**. Du kan inte skapa nya eller komma åt befintliga [!UICONTROL Publishing Lists] att skicka eller schemalägga [!UICONTROL Analysis Workspace] projekt. |
| **EOL för Data Workbench** | 14 september 2022 | Adobe har för avsikt att göra Datan Workbench gällande **31 december 2023**. Se [Datans Workbench meddelande om att livscykeln upphör](https://experienceleague.adobe.com/docs/data-workbench/using/eol.html) för mer information. Kontakta din organisations kontoansvarige på Adobe om du har frågor. |

{style="table-layout:auto"}

## AppMeasurement

De senaste uppdateringarna av AppMeasurement (version 2.25.0) finns på [AppMeasurement för versionsinformation för JavaScript](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html).


## Relaterade resurser

* [Information om föregående version för 2022](/help/release-notes/2022.md)
* [Versionsinformation för Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html)
* [Versionsinformation om Media Analytics](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html)
* Den senaste releaseuppdateringen för [Adobe Experience Cloud](https://business.adobe.com/products/adobe-experience-cloud-products.html)
