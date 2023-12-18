---
title: Aktuella versionsinformation för Adobe Analytics
description: Visa den aktuella versionsinformationen för Adobe Analytics
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: d3d4547238bdaedf8a9c8ac9c4a29e9237bbc3d8
workflow-type: tm+mt
source-wordcount: '1155'
ht-degree: 1%

---

# Aktuell versionsinformation för Adobe Analytics (oktober/november 2023)

**Senaste uppdatering**: 13 december 2023

Versionsinformationen omfattar releaseperioden 23 oktober 2023 till slutet av november 2023. Adobe Analytics-releaser fungerar på en [kontinuerlig leveransmodell](releases.md) vilket ger en mer skalbar, stegvis metod för driftsättning av funktioner. Därför uppdateras versionsinformationen flera gånger i månaden. Kontrollera dem regelbundet.

## Nya funktioner eller förbättringar {#features}

| Funktion | Beskrivning | [Startar](releases.md) | [Allmän tillgänglighet](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Förbättringar av Rapporteringsaktivitetshanteraren** | Med Rapporteringsaktivitetshanteraren kan du se rapporteringskapaciteten för varje rapportsvit i organisationen.  Det ger administratörer detaljerad insyn i rapporteringen av förbrukning för att enkelt kunna diagnostisera och åtgärda kapacitetsproblem under perioder med hög rapporteringsnivå. Nedan följer några av förbättringarna som nu finns i Reporting Activity Manager: <ul><li>Begränsa efterföljande begäranden: Förutom att avbryta aktuella begäranden kan administratörer nu begränsa begäranden för en angiven tidsperiod. Administratörer kan begränsa begäranden efter begäran, projekt och användare.</li><li>Utöver användnings- och kapacitetsstatistik innehåller nu Reporting Activity Manager fler data om rapporteringsaktivitet: kolumnen Komplexitet, kolumnen Användare och kolumnen Anslutning.</li><li>Alla avbrott och begränsningar som görs i Rapporteringsaktivitetshanteraren visas nu i granskningsloggen. Administratörer kan använda granskningsloggen för att visa det som för närvarande är avbrutet. Det går inte att återställa annulleringar i Rapporteringsaktivitetshanteraren eller i granskningsloggen.</li></ul><p>Mer information finns i [Översikt över Reporting Activity Manager](/help/admin/admin/reporting-activity-manager/reporting-activity-overview.md)</p> | 17 oktober 2023 | 24 oktober 2023 |
| **Förbättrad Data Warehouse** | När du skapar en begäran om Data Warehouse kan du nu konfigurera ett molnkonto som ska användas som rapportmål. Följande typer av molnkonton är tillgängliga för att skicka data:<ul><li>Amazon S3</li><li>Google Cloud Platform</li><li>Azure SAS</li><li>Azure RBAC</li><li>E-post (det här alternativet var tidigare tillgängligt)</li></ul>FTP, SFTP, Azure Blob och S3 är fortfarande tillgängliga som rapportmål, men rekommenderas inte längre.<p>Användarupplevelsen när begäranden om Data Warehouse skapas och hanteras har också förbättrats. Mer information finns i [Skapa en begäran om Data Warehouse](/help/export/data-warehouse/create-request/t-dw-create-request.md) och [Hantera förfrågningar från Data Warehouse](https://experienceleague.adobe.com/docs/analytics/export/data-warehouse/data-warehouse-requests-manage.html). | 12 september 2023 | 15 december 2023 |

{style="table-layout:auto"}

## Korrigeringar i Adobe Analytics

* De här ändringarna av analysbearbetnings- och rapporteringsmotorn kommer att driftsättas under den sista veckan i oktober: vi kommer att åtgärda ett problem där etiketterna för sid- eller länkdimensionerna felaktigt visades som `Unknown`. Innan korrigeringen `Unknown` etiketter kan ha visats felaktigt när ett sidnamn eller länknamn inte skickades in i en träff, vilket är standard till [!UICONTROL Page URL] och [!UICONTROL Link URL], respektive Dessa dimensioner har konfigurerats så att de inte är skiftlägeskänsliga. Med den här korrigeringen kommer rapporter som går framåt att vara korrekta. Men för rapporter om historiska data kan vissa rapportresultat fortfarande felaktigt märkas som `Unknown`. (AN-328030)

### Andra korrigeringar

AN-315676; AN-323398; AN-326209; AN-328178; AN-328261; AN-328395; AN-328671; AN-AN 329282; AN-329330; AN-329355; AN-329506; AN-329516; AN-329738; AN-329769; AN-3 29771; AN-329816; AN-329877; AN-329928; AN-329957; AN-329962; AN-329966; AN-333 0023; AN-330081; AN-330083; AN-330105; AN-330138; AN-330140; AN-330165; AN-3300 241; AN-330359; AN-330366; AN-330427; AN-330438; AN-330442; AN-330534; AN-3306 16; AN-330654; AN-330783; AN-330879; AN-330881; AN-330883; AN-330887; AN-33088 8; AN-330955; AN-330979; AN-331031; AN-331053; AN-331068; AN-331071; AN-331074; AN-331075; AN-331076; AN-331078; AN-331085; AN-331093; AN-331167; AN-33171; AN-4 331181; AN-331196; AN-331226; AN-331258; AN-331260; AN-331279; AN-331286; AN-3 31290; AN-331365; AN-331375; AN-331376; AN-331454; AN-331519; AN-331570; AN-33 1590; AN-331593; AN-331603; AN-331751; AN-331816; AN-331897; AN-331900; AN-331 906; AN-331926; AN-331929; AN-332031; AN-332067; AN-332101; AN-332114; AN-3321 56; AN-332201; AN-332225; AN-332253; AN-332277; AN-332361; AN-332370; AN-33238 6

## Viktiga meddelanden för Adobe Analytics-administratörer {#admin}

| Meddelande | Datum tillagt eller uppdaterat | Beskrivning |
| ----------- | ---------- | ---------- |
| **Fullständig IP-krånglighet för Adobe Experience Edge-träffar** | 27 september 2023 | IP-infusation för träffar från Experience Edge kommer att uppdateras senare i oktober 2023. I april 2023 lade Experience Edge till möjligheten att dölja IP-adresser. På den tiden stödde Adobe Analytics endast delvis oreda av IP-adresser på grund av hur Analytics-processerna slår igenom från Experience Edge. När kunderna valde fullständig okunskap för Experience Edge fick Analytics bara delvis ofokuserade IP-adresser. När den här ändringen implementeras får Analytics den fullständigt dolda IP-adressen. |
| **Adobe Analytics LiveStream - API:er för Analytics 2.0** | 27 september 2023 | Kunderna har nu tillgång till [Slutpunktshandbok för Adobe Analytics LiveStream](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/livestream/) i Adobe Analytics 2.0 API:er i stället på sin tidigare plats, med 1.4 API:er. Observera att kunder som använder Adobe I/O JWT-inloggningsuppgifter måste migrera till inloggningsuppgifterna för Adobe I/O OAuth Server-till-Server senast 1 januari 2025. (Se informationen i EOL-meddelanden nedan.) |

{style="table-layout:auto"}

## EOL-meddelanden (End-of-life) {#eol}

| EOL-produkt eller -funktion | Datum tillagt eller uppdaterat | Beskrivning |
| --- | --- | --- |
| **EOL för[!DNL Reports & Analytics]** | 13 december 2023 | Effektivt **17 januari 2024** kommer Adobe att upphöra med sin verksamhet [!DNL Reports & Analytics] och tillhörande rapporter och funktioner. Rapporterna, visualiseringar och underliggande teknik som ger kraft åt [!DNL Reports & Analytics] inte längre uppfyller Adobe teknikstandarder. Mest [!DNL Reports & Analytics] funktioner finns i [Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html). Sedan Analysis Workspace släpptes 2015 har [!DNL Reports & Analytics] funktionaliteten och funktionerna har flyttats till Analysis Workspace och ett tröskelvärde för arbetsflödets paritet har uppnåtts. [Detta meddelande](https://spark.adobe.com/page/6WnF8JK6IRDhf/) förklarar processen för att avsluta livscykeln.<p>Den 31 december 2023 kommer många av de tillhörande funktionerna för rapporter och analys att avslutas, inklusive, men inte begränsat till, schemalagda rapporter, dataextrakt och DL-rapporter. Efter den 31 december 2023 skickas inga schemalagda rapporter längre. I **April 2023**, uppdaterades alla rapporter som skulle ha gått ut efter den 31 december 2023 automatiskt och upphörde att gälla den 31 december 2023. Dessutom kan du inte längre schemalägga framtida rapporter efter 31 december 2023. |
| **EOL för [!UICONTROL Publishing Lists] funktion** | 13 december 2023 | Som en del av ledningscentralen för rapporter och analyser [!UICONTROL Publishing Lists] är avsedda att nå livets slut den **17 januari 2024**. Du kan inte skapa nya eller komma åt befintliga [!UICONTROL Publishing Lists] att skicka eller schemalägga [!UICONTROL Analysis Workspace] projekt. |
| **Migrering till autentiseringsuppgifter för Adobe I/O OAuth Server-till-Server** | 11 maj 2023 | Adobe Analytics API- och LiveStream-kunder som använder Adobe I/O JWT-autentiseringsuppgifter måste migrera till Adobe I/O OAuth Server-till-Server-autentiseringsuppgifter genom att **1 januari 2025**. Adobe I/O tillåter inte att nya JWT-autentiseringsuppgifter skapas från och med 1 maj 2024. Kunder som använder JWT måste skapa en ny OAuth Server-till-Server-autentiseringsuppgift eller migrera sina befintliga JWT-autentiseringsuppgifter till en OAuth Server-till-Server-autentiseringsuppgift. Kunderna måste även uppdatera sina klientprogram för att kunna använda de nya autentiseringsuppgifterna för OAuth Server-till-Server. <ul><li>[Migrerar från JWT-autentiseringsuppgifter (Service Account)](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)</li><li>[Implementeringsguide för nya och gamla program med OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)<li>[Använda de nya autentiseringsuppgifterna för OAuth Server-till-Server](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)</li><li>[Vanliga frågor](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)</li></ul> |
| **EOL för Data Workbench** | 14 september 2022 | Adobe har för avsikt att göra Datan Workbench gällande **31 december 2023**. Se [Datans Workbench meddelande om att livscykeln upphör](https://experienceleague.adobe.com/docs/data-workbench/using/eol.html) för mer information. Kontakta din organisations kontoansvarige på Adobe om du har frågor. |

{style="table-layout:auto"}

## AppMeasurement

De senaste uppdateringarna av AppMeasurement (version 2.25.0) finns på [AppMeasurement för versionsinformation för JavaScript](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html).


## Relaterade resurser

* [Information om föregående version för 2022](/help/release-notes/2022.md)
* [Versionsinformation för Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html)
* [Versionsinformation om Media Analytics](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html)
* Den senaste releaseuppdateringen för [Adobe Experience Cloud](https://business.adobe.com/products/adobe-experience-cloud-products.html)
