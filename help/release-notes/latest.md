---
title: Aktuella versionsinformation för Adobe Analytics
description: Visa den aktuella versionsinformationen för Adobe Analytics
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: df9470f1870879ac91f00a021ed890bc6fb10cda
workflow-type: tm+mt
source-wordcount: '987'
ht-degree: 1%

---

# Aktuell versionsinformation för Adobe Analytics (juni 2024)

**Senaste uppdatering**: 13 juni 2024

Versionsanteckningarna gäller frisläppningsperioden 12 juni 2024 till juli. Adobe Analytics-releaser fungerar på en [kontinuerlig leveransmodell](releases.md) vilket ger en mer skalbar, stegvis metod för driftsättning av funktioner. Därför uppdateras versionsinformationen flera gånger i månaden. Kontrollera dem regelbundet.

## Nya funktioner eller förbättringar {#features}

| Funktion | Beskrivning | [Startar](releases.md) | [Allmän tillgänglighet](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Markera flera fält i ett nedrullningsbart filter** | När flera fält har lagts till i ett nedrullningsbart filter kan användare nu markera mer än ett fält i taget. Panelen filtreras så att den innehåller något av de markerade fälten. <p>Tidigare kunde användaren bara markera ett fält i taget i ett droppfilter.</p><p>Mer information finns i [Statiska rullgardinssegment](/help/analyze/analysis-workspace/c-panels/panels.md#static-drop-down-segments) in [Paneler - översikt](/help/analyze/analysis-workspace/c-panels/panels.md).</p> |  | 19 juni 2024 |
| **Innehållsförteckning för arbetsyteprojekt** | En ny innehållsförteckning är nu tillgänglig för projekt. Innehållsförteckningen innehåller länkar som gör att användare snabbt kan gå till paneler och visualiseringar i projektet. Innehållsförteckningen kan aktiveras för enskilda projekt eller för alla projekt för en viss användare.<p>Mer information finns i [Innehållsförteckning för projekt](/help/analyze/analysis-workspace/build-workspace-project/project-table-of-contents.md).</p> |  | 19 juni 2024 |
| **Skapa hyperlänkar för dimensionsobjekt i en frihandstabell** | Du kan skapa hyperlänkar för ett eller flera dimensionsobjekt för att göra dem klickbara i en frihandstabell i Analysis Workspace. <p>Du kan skapa hyperlänkar för dimensionsobjekt som har URL-värden, eller så kan du skapa anpassade URL:er för dimensionsobjekt som inte har URL-värden.</p><p>Du kan skapa dynamiska anpassade URL:er för flera dimensionsobjekt med hjälp av variabler. Variabler kan referera till värdet för en dimensionsartikel eller referera till uppdelningsdimensionen.</p><p>Mer information finns i [Skapa hyperlänkar för dimensioner i en frihandstabell](/help/analyze/analysis-workspace/visualizations/freeform-table/freeform-table-hyperlinks.md).</p> |  | 19 juni 2024 |
| **Administratörsinställningar för att styra konton och platser som används för export och import** | En ny [fliken Administratörsinställningar i Platshanteraren](/help/components/locations/locations-manager.md#configure-company-wide-settings-administrators-only) ger administratörer kontroll över om användare kan skapa och redigera konton och platser. De här inställningarna gäller när användare [konfigurera molnimport- och exportkonton](/help/components/locations/configure-import-accounts.md) och [konfigurera platser för molnimport och -export](/help/components/locations/configure-import-locations.md). <p>Administratörer kan också begränsa vilka typer av konton (Google Cloud Platform, Azure RBAC, Amazon S3 och så vidare) som användare kan skapa och använda.</p><p>Tidigare kunde alla användare skapa, redigera och använda konton och platser för alla typer av konton.</p> | 12 juni 2024 | 20 juni 2024 |
| **Dela konton och platser som används för export och import** | Användarna kan nu göra de konton och platser de skapar tillgängliga för alla användare i organisationen. Endast konto- och platsägare och systemadministratörer kan redigera och ta bort konton och platser.<p>Tidigare kunde konton och platser bara användas av den användare som skapade dem.</p><p>Dessa inställningar är tillgängliga när användare [konfigurera molnimport- och exportkonton](https://experienceleague.adobe.com/en/docs/analytics/components/locations/configure-import-accounts) och [konfigurera platser för molnimport och -export](https://experienceleague.adobe.com/en/docs/analytics/components/locations/configure-import-locations). </p> | 12 juni 2024 | 20 juni 2024 |
| **Activity Map för att använda färre serveranrop för Web SDK** | För närvarande räknas länkarhändelser i Activity Map som sina egna händelser och medför extra kostnader. Den här förbättringen tar några länkhändelser och paketerar dem i nästa träff, ungefär som hur händelser hanteras av AppMeasurementet. <p>(Länk till uppdaterad dokumentation följer)</p> | Open Beta börjar 19 juni 2024 | TBD |

{style="table-layout:auto"}

## Korrigeringar i Adobe Analytics

* Åtgärdade följande klassificeringsproblem: AN-347682; AN-348396; AN-348625; AN-348668; AN-348926; AN-348936; AN-349 040; AN-349191; AN-349195; AN-349443; AN-349697; AN-349758; AN-349862; AN-3500 51; AN-350054; AN-350208; AN-350497; AN-350525; AN-351067
* Följande problem med Datan Warehouse har korrigerats: AN-346862; AN-349409; AN-349926; AN-350629; AN-350996
* Åtgärdade följande dataflödesproblem: AN-346727; AN-348282; AN-348334; AN-348725; AN-348726; AN-348823; AN-349 081; AN-349207; AN-349307; AN-349539; AN-349710; AN-349729; AN-349742; AN-3498 78; AN-349943; AN-350527;
* Åtgärdade följande problem med datakällor: AN-350038
* Följande Analysis Workspace-problem har korrigerats: AN-342953; AN-346346; AN-349590; AN-349717; AN-350057; AN-350697; AN-3509 04
* Åtgärdade följande problem med Report Builder: AN-348903; AN-350691
* Åtgärdade följande A4T-problem: AN-347690; AN-350853

### Korrigeringar för andra analyser

AN-346470; AN-346850; AN-347227; AN-348145; AN-348564; AN-349001; AN-349008; AN-349211; AN-349719; AN-350523;

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

* [Information om föregående version för 2024](/help/release-notes/2024.md)
* [Versionsinformation för Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html)
* [Versionsinformation om Media Analytics](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html)
* Den senaste releaseuppdateringen för [Adobe Experience Cloud](https://business.adobe.com/products/adobe-experience-cloud-products.html)
