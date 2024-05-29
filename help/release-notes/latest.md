---
title: Aktuella versionsinformation för Adobe Analytics
description: Visa den aktuella versionsinformationen för Adobe Analytics
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 47893ea714f0a0baaccce66578c9f9175c59511f
workflow-type: tm+mt
source-wordcount: '1144'
ht-degree: 1%

---

# Aktuell versionsinformation för Adobe Analytics (maj 2024)

**Senaste uppdatering**: 22 maj 2024

Versionsanteckningarna gäller releaseserien 15 maj 2024 till juni. Adobe Analytics-releaser fungerar på en [kontinuerlig leveransmodell](releases.md) vilket ger en mer skalbar, stegvis metod för driftsättning av funktioner. Därför uppdateras versionsinformationen flera gånger i månaden. Kontrollera dem regelbundet.

## Nya funktioner eller förbättringar {#features}

| Funktion | Beskrivning | [Startar](releases.md) | [Allmän tillgänglighet](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Ny dokumentation för uppgradering från Adobe Analytics till Customer Journey Analytics** | För organisationer som uppgraderar från Adobe Analytics till Customer Journey Analytics finns det flera uppgraderingsalternativ och många överväganden att tänka på baserat på organisationens nuvarande Adobe Analytics-implementering och långsiktiga mål. Nu finns det nya dokumentationsresurser som hjälper dig att förstå:<ul><li>De olika uppgraderingssökvägarna som finns</li><li>Vilka uppgraderingsalternativ som finns tillgängliga baserat på en organisations aktuella implementering av Adobe Analytics</li><li>Fördelar och nackdelar med varje uppgraderingsväg</li><li>Stegvisa anvisningar för varje uppgraderingsväg</li><li>Att tänka på vid hantering av historiska data</li></ul>[Kom igång med uppgraderingen till Customer Journey Analytics](https://experienceleague.adobe.com/en/docs/analytics-platform/using/compare-aa-cja/upgrade-to-cja/cja-upgrade-getstarted) | | Ute nu |
| **Ange `contextData` fält via XML** | Kunder som skickar data till Adobe Analytics via Experience Edge Network kan [ange kontextdatavärden](https://experienceleague.adobe.com/en/docs/analytics/implementation/vars/page-vars/contextdata) direkt antingen i XDM eller i nyttolastens datadel. |  | Ute nu |
| **API för realtidsrapportering för Analytics 2.0** | Det nya API:t för realtidsrapportering i Adobe Analytics 2.0 förbättrar kundintegreringen och ger snabba rapportresultat. Dessa resultat kan användas programmatiskt för att arbeta med enkla, trendmässiga och uppdelade rapporter. [Läs mer](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/reports/real-time/) | | 30 maj 2024 |
| **Direktuppspelningsmedia: Skicka webbdata till Adobe Experience Platform Edge Network med Web SDK** | Nu kan du använda Adobe Experience Platform Web SDK för att skicka Streaming Media-webbdata till Adobe Experience Platform Edge Network. Den här förbättringen gör att ni kan skapa mer personaliserade kampanjer och leverera mer personaliserat innehåll, vilket resulterar i mer spårningsdata att rapportera om.<p>Den här ändringen ger en enhetlig insamlingsmetod för webbimplementeringar i alla plattformslösningar, till exempel Customer Journey Analytics, Adobe CDP, Adobe Journey Optimizer och händelsevidarebefordring i realtid. Tidigare var det enda sättet att skicka Streaming Media-webbdata till Edge Network att använda Media Edge API. <p>[Läs mer](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/edge-recommended/media-edge-sdk/edge-web-sdk)</p> | | 29 maj 2024 |
| **Ökning av standardtröskelvärden för låg trafik** | I **mitten av april 2024** kommer Adobe att börja öka standardrapporteringsprogrammets lågtrafiktrösklar enligt följande: ![lågtrafiktrösklar](assets/thresholds.png) Detta påverkar endast variabler som för närvarande ligger under de nya tröskelvärdena. Dessa ändringar kommer att göras stegvis, och vi förväntar oss att arbetet ska vara slutfört av **slutet av maj**. När dessa ökningar introduceras kan du märka förändringar för variabler med hög kardinalitet:<ul><li>Fler dimensionsvärden kan vara tillgängliga för rapportering.</li><li>Segment och beräknade värden kan innehålla mer data.</li><li>Virtuella rapportsviter baserade på segment kan innehålla mer data.</li><li>Export av klassificeringar kan innehålla mer data.</li></ul> | Mid April, 2024 | 31 maj 2024 |
| **Administratörsinställningar för att styra konton och platser som används för export och import** | Den nya fliken Administratörsinställningar i Platshanteraren ger administratörer kontroll över om användare kan skapa och redigera konton och platser. De här inställningarna gäller när användare konfigurerar molnimport- och exportkonton och konfigurerar platser för molnimport och -export. <p>Administratörer kan också begränsa vilka typer av konton (Google Cloud Platform, Azure RBAC, Amazon S3 och så vidare) som användare kan skapa och använda.</p><p>Tidigare kunde alla användare skapa, redigera och använda konton och platser för alla typer av konton.</p><p>(Länk till uppdaterad dokumentation följer)</p> | 12 juni 2024 | 30 juni 2024 |
| **Dela konton och platser som används för export och import** | Användarna kan nu göra de konton och platser de skapar tillgängliga för alla användare i organisationen. Endast konto- och platsägare och systemadministratörer kan redigera och ta bort konton och platser.<p>Tidigare kunde konton och platser bara användas av den användare som skapade dem.</p><p>De här inställningarna är tillgängliga när användare konfigurerar molnimport- och exportkonton och konfigurerar platser för molnimport och -export. </p> <p>(Länk till uppdaterad dokumentation följer)</p> | 12 juni 2024 | 30 juni 2024 |
| **Activity Map för att använda färre serveranrop för Web SDK** | För närvarande räknas länkarhändelser i Activity Map som sina egna händelser och medför extra kostnader. Den här förbättringen tar några länkhändelser och paketerar dem i nästa träff, ungefär som hur händelser hanteras av AppMeasurementet. <p>(Länk till uppdaterad dokumentation följer)</p> | Beta börjar 31 maj 2024 | TBD |

{style="table-layout:auto"}

## Korrigeringar i Adobe Analytics

* Åtgärdade följande klassificeringsproblem: AN-343186; AN-344711; AN-344856; AN-345094; AN-345179; AN-346265; AN-345 288; AN-346339; AN-346560; AN-347572; AN-347681; AN-347768; AN-348024
* Följande problem med Datan Warehouse har korrigerats: AN-346789, AN-347031, AN-347568,
* Åtgärdade följande dataflödesproblem: AN-343616; AN-345831; AN-345988; AN-346124; AN-346232; AN-346972; AN-347 680; AN-347755; AN-347954
* Åtgärdade följande problem med datakällor: AN-347890;
* Följande Analysis Workspace-problem har korrigerats: AN-321503; AN-343103; AN-343471; AN-345171; AN-345223; AN-345912; AN-3460 26; AN-346330; AN-346839; AN-347679
* Åtgärdade följande A4T-problem: AN-345118;

### Korrigeringar för andra analyser

AN-327749; AN-332949; AN-342881; AN-343171; AN-343708; AN-344034; AN-34559; AN-3 346023; AN-346230; AN-346330; AN-346469; AN-346606; AN-346750; AN-346973; AN-3 47026; AN-347110; AN-347439;

## Viktiga meddelanden för Adobe Analytics-administratörer {#admin}

| Meddelande | Datum tillagt eller uppdaterat | Beskrivning |
| ----------- | ---------- | ---------- |
| **13 månaders förfallodatum för sparat`cust_visids`** | 22 maj 2024 | En kommande version av Analytics Träffbehandlarmotorn, **riktad mot juli 2024**, börjar tillämpa 13-månaders förfallodatum för sparade `cust_visids`. Om rapportsviten har Aktivera besökarinställning aktiverat, används den här inställningen för att hitta `cust_visid` för `visid_high/visid_low value` med nej `cust_visid` på träffen. Mappningen av en `cust_visid` för `visid_high/visid_low`. I den här versionen, om minst 13 månader har gått sedan `visid_high/visid_low` har haft en `cust_visid` vid en träff upphör mappningen. |
| **Uppdateringar av ISO-område** | 10 maj 2024 | Adobe kommer att genomföra 2024 ISO-regionsuppdateringar den 7 juni 2024. Efter den här versionen förväntas mindre uppdateringar av geoinformation (region) visas. |

{style="table-layout:auto"}

## EOL-meddelanden (End-of-life) {#eol}

| EOL-produkt eller -funktion | Datum tillagt eller uppdaterat | Beskrivning |
| --- | --- | --- |
| **Migrering till autentiseringsuppgifter för Adobe I/O OAuth Server-till-Server** | 11 maj 2023 | Adobe Analytics API- och LiveStream-kunder som använder Adobe I/O JWT-autentiseringsuppgifter måste migrera till Adobe I/O OAuth Server-till-Server-autentiseringsuppgifter genom att **1 januari 2025**. Adobe I/O tillåter inte att nya JWT-autentiseringsuppgifter skapas från och med 1 maj 2024. Kunder som använder JWT måste skapa en ny OAuth Server-till-Server-autentiseringsuppgift eller migrera sina befintliga JWT-autentiseringsuppgifter till en OAuth Server-till-Server-autentiseringsuppgift. Kunderna måste även uppdatera sina klientprogram för att kunna använda de nya autentiseringsuppgifterna för OAuth Server-till-Server. <ul><li>[Migrerar från JWT-autentiseringsuppgifter (Service Account)](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)</li><li>[Implementeringsguide för nya och gamla program med OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)<li>[Använda de nya autentiseringsuppgifterna för OAuth Server-till-Server](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)</li><li>[Vanliga frågor](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)</li></ul> |

{style="table-layout:auto"}

## AppMeasurement

De senaste uppdateringarna av AppMeasurement (version 2.26.0) finns på [AppMeasurement för versionsinformation för JavaScript](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html).


## Relaterade resurser

* [Information om föregående version för 2023](/help/release-notes/2023.md)
* [Versionsinformation för Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html)
* [Versionsinformation om Media Analytics](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html)
* Den senaste releaseuppdateringen för [Adobe Experience Cloud](https://business.adobe.com/products/adobe-experience-cloud-products.html)
