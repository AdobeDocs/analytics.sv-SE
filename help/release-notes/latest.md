---
title: Aktuella versionsinformation för Adobe Analytics
description: Se versionsinformationen för Adobe Analytics.
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: d4868971596c43721e0d642ae3ad91c316fc6908
workflow-type: tm+mt
source-wordcount: '793'
ht-degree: 3%

---

# Aktuell versionsinformation för Adobe Analytics (september 2023)

**Senaste uppdatering**: 6 september 2023

Versionsinformationen för september omfattar frisläppningsperioden 13 september 2023 till 3 oktober 2023. Adobe Analytics-releaser fungerar på en [kontinuerlig leveransmodell](releases.md) vilket ger en mer skalbar, stegvis metod för driftsättning av funktioner. Därför uppdateras versionsinformationen flera gånger i månaden. Kontrollera dem regelbundet.

## Nya funktioner eller förbättringar {#features}

| Funktion | Beskrivning | [Startar](releases.md) | [Allmän tillgänglighet](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Klassificeringsuppsättningar i API 2.0** | Innehåller Adobe Analytics API 2.0-metoder för att spara, ta bort, hämta, importera och exportera klassificeringsuppsättningsdata. [Läs mer](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/classifications/) | Ej tillämpligt | 13 september 2023 |
| **Stöd för nya `correlationID` fält för A4T-klassificeringar** | The `_experience.decisioning.propositions.scopeDetails.correlationID` -fältet är nu tillgängligt i Adobe Analytics källanslutningsschema. Vi lägger till det här ID:t för enkel koppling av klassificeringsdata för Adobe Target-aktiviteter och upplevelsehändelser. | Ej tillämpligt | 13 september 2023 |
| **Förbättrad Data Warehouse** | När du skapar en begäran om Data Warehouse kan du nu konfigurera ett molnkonto som ska användas som rapportmål. Följande typer av molnkonton är tillgängliga för att skicka data:<ul><li>Amazon S3</li><li>Google Cloud Platform</li><li>Azure SAS</li><li>Azure RBAC</li><li>E-post (det här alternativet var tidigare tillgängligt)</li></ul>FTP, SFTP, Azure Blob och S3 är fortfarande tillgängliga som rapportmål, men rekommenderas inte längre.<p>Användarupplevelsen när begäranden om Data Warehouse skapas och hanteras har också förbättrats. Mer information finns i [Skapa en begäran om Data Warehouse](https://experienceleague.adobe.com/docs/analytics/export/data-warehouse/create-request/t-dw-create-request.html) och [Hantera förfrågningar från Data Warehouse](https://experienceleague.adobe.com/docs/analytics/export/data-warehouse/data-warehouse-requests-manage.html). | 13 september 2023 | 4 oktober 2023 |

{style="table-layout:auto"}

## Korrigeringar i Adobe Analytics

* Ett problem som gjorde att klassificeringsdata inte kunde visas i Workspace har korrigerats. (AN-326827)

## Andra korrigeringar

AN-314882; AN-315591; AN-318165; AN-318559; AN-319031; AN-319244; AN-321657; AN-AN 321759; AN-323099; AN-323596; AN-323640; AN-324442; AN-324921; AN-324953; AN-3 24977; AN-324979; AN-325124; AN-325395; AN-325433; AN-325535; AN-325693; AN-322 5720; AN-325835; AN-325880; AN-325957; AN-325984; AN-326054; AN-326065; AN-326 136; AN-326155; AN-326162; AN-326235; AN-326317; AN-326344; AN-326357; AN-3263 59; AN-326433; AN-326438; AN-326440; AN-326461; AN-326464; AN-326523; AN-32655 3; AN-326606; AN-326635; AN-326642; AN-326652; AN-326678; AN-326769; AN-32677; AN-326830; AN-326938; AN-326949; AN-327081; AN-327082; AN-327085; AN-327103; AN-4 327198; AN-327225; AN-327275; AN-327358; AN-327423; AN-327561; AN-327755; AN-3 27896; AN-327922; AN-328128; AN-328300; AN-328428; AN-328518; AN-328554

## Viktiga meddelanden för Adobe Analytics-administratörer {#admin}

| Meddelande | Datum tillagt eller uppdaterat | Beskrivning |
| ----------- | ---------- | ---------- |
| Ej tillämpligt | Ej tillämpligt | Ej tillämpligt |

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

De senaste uppdateringarna av AppMeasurement (version 2.24.0) finns på [AppMeasurement för versionsinformation för JavaScript](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html).


## Relaterade resurser

* [Information om föregående version för 2022](/help/release-notes/2022.md)
* [Versionsinformation för Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html)
* [Versionsinformation om Media Analytics](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html)
* Den senaste releaseuppdateringen för [Adobe Experience Cloud](https://business.adobe.com/products/adobe-experience-cloud-products.html)
