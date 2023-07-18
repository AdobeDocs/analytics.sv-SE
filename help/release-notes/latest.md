---
title: Versionsinformation om den senaste analysen
description: Se versionsinformationen för Adobe Analytics.
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: f996448224ffebd57023c8d8e4eeeccb4d6e2a47
workflow-type: tm+mt
source-wordcount: '912'
ht-degree: 2%

---

# Aktuell versionsinformation för Adobe Analytics (juli 2023)

**Senaste uppdatering**: 10 juli 2023

Adobe Analytics-releaser fungerar på en [kontinuerlig leveransmodell](releases.md) vilket ger en mer skalbar, stegvis metod för driftsättning av funktioner. Därför uppdateras versionsinformationen flera gånger i månaden. Kontrollera dem regelbundet.

## Nya funktioner eller förbättringar {#features}

| Funktion | Beskrivning | [Startar](releases.md) | [Allmän tillgänglighet](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Konfigurera lagringsplatser för molnkonton för inhämtning av klassificeringsdata** | Nu kan du hantera lagringsplatser för molnkonton som används för automatisering av klassificeringsuppsättningar. [Läs mer](/help/components/locations/configure-import-accounts.md)<p> | Ej tillämpligt | 10 juli 2023 |
| **Förbättrat datareparationsfilter** | Tre filtreringsförbättringar har lagts till i Datareparation:<ul><li>Filtrera efter en variabel för att ändra en andra variabel. Om `eVar2` innehåller&quot;@&quot; och sedan ta bort `eVar3`.</li><li>Filter för numeriska eller icke-numeriska värden</li><li>Använd flera filter med AND. Där `eVar2="a"` OCH `eVar3="b"`</li></ul>[Läs mer](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/data-repair/) | 21 juni 2023 | 12 juli 2023 |
| **Säkra destinationer för datafeed-export** | Datamatningar kan nu skickas till följande molnlagringsmål:<ul><li>Amazon S3</li><li>Azure RBAC</li><li>Azure SAS</li><li>Google Cloud Platform</li></ul>Destinationer som tidigare var tillgängliga (FTP, SFTP, S3 och Azure Blob) rekommenderas inte längre. [Läs mer](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/create-feed.html) | 12 juni 2023 | 13 juli 2023 |
| **Ny AppMeasurement-variabel** | Variabeln `decodeLinkParameters` används för kantfall där implementeringar kodar flerbytetecken i länkspårningsvariabler. De flesta implementeringar behöver inte definiera den här variabeln. [Läs mer](../implement/vars/config-vars/decodelinkparameters.md) |  | 17 juli 2023 |

{style="table-layout:auto"}

## Korrigeringar i Adobe Analytics

AN-307816; AN-318111; AN-318584; AN-318828; AN-320440; AN-320568; AN-320616; AN-321013; AN-321513; AN-321520; AN-321757; AN-321820; AN-321917; AN-322034; AN-322135; AN-322140; AN-322142; AN-322251; AN-322353; AN-322378; AN-322383; AN-322427; AN-322458; AN-322543; AN-322630; AN-322637; AN-322638; AN-322647; AN-322728; AN-322732; AN-322777; AN-322817; AN-322957; AN-322958; AN-323035; AN-323074; AN-323150; AN-323196; AN-323197; AN-323205; AN-323206; AN-323217; AN-323224; AN-323225; AN-323244; AN-323257; AN-323277; AN-323280; AN-323293; AN-323309; AN-323318; AN-323468; AN-323476; AN-323514; AN-323572; AN-323592; AN-323782; AN-323835

## Viktiga meddelanden för Adobe Analytics-administratörer {#admin}

| Meddelande | Datum tillagt eller uppdaterat | Beskrivning |
| ----------- | ---------- | ---------- |
| **37-månaders förfallodatum för inköps-ID och händelse-ID (händelseserialisering)** | Juli 10,2023 | En kommande version av motorn för bearbetning av träff i Analytics, avsedd för lansering den **13 juli 2023**, kommer att börja genomdriva en 37-månaders förfallotid för inköps-ID och händelse-ID (händelseserialisering). För närvarande går köp-ID och händelse-ID aldrig ut i Adobe Analytics. När ett inköps-ID eller händelse-ID visas/används kommer eventuella framtida träffar, oavsett när, att markeras som dubbletter. Med den nya versionen av bearbetningsmotorn:<ul><li>Inköps-ID och händelse-ID:n går alltid ut efter 37 månader.</li><li>Om det har gått 37 månader sedan inköps-ID:t eller händelse-ID:t sågs, betraktas det inte längre som ett dubblettköp eller -händelse.</li><li> Om du återanvänder inköps-ID:n eller händelse-ID:n för mer än 37 månader sedan betraktas de inte längre som dubbletter.</li></ul> |
| **Migrering till autentiseringsuppgifter för Adobe I/O OAuth Server-till-Server** | 11 maj 2023 | Adobe Analytics API- och LiveStream-kunder som använder Adobe I/O JWT-autentiseringsuppgifter måste migrera till Adobe I/O OAuth Server-till-Server-autentiseringsuppgifter genom att **1 januari 2025**. Mer information och tidslinjer finns i meddelandet om att produkten upphör att gälla i tabellen nedan. |

{style="table-layout:auto"}

## EOL-meddelanden (End-of-life) {#eol}

| EOL-produkt eller -funktion | Datum tillagt eller uppdaterat | Beskrivning |
| --- | --- | --- |
| **Migrering till autentiseringsuppgifter för Adobe I/O OAuth Server-till-Server** | 11 maj 2023 | Adobe Analytics API- och LiveStream-kunder som använder Adobe I/O JWT-autentiseringsuppgifter måste migrera till Adobe I/O OAuth Server-till-Server-autentiseringsuppgifter genom att **1 januari 2025**. Adobe I/O tillåter inte att nya JWT-autentiseringsuppgifter skapas från och med 1 maj 2024. Kunder som använder JWT måste skapa en ny OAuth Server-till-Server-autentiseringsuppgift eller migrera sina befintliga JWT-autentiseringsuppgifter till en OAuth Server-till-Server-autentiseringsuppgift. Kunderna måste även uppdatera sina klientprogram för att kunna använda de nya autentiseringsuppgifterna för OAuth Server-till-Server. <ul><li>[Migrerar från JWT-autentiseringsuppgifter (Service Account)](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)</li><li>[Implementeringsguide för nya och gamla program med OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)<li>[Använda de nya autentiseringsuppgifterna för OAuth Server-till-Server](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)</li><li>[Vanliga frågor](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)</li></ul> |
| **EOL för[!DNL Reports & Analytics]** | 7 mars 2023 | Effektivt **31 december 2023** kommer Adobe att upphöra med sin verksamhet [!DNL Reports & Analytics] och tillhörande rapporter och funktioner. Rapporterna, visualiseringarna och den underliggande tekniken som ligger till grund för [!DNL Reports & Analytics] inte längre uppfyller Adobe teknikstandarder. Mest [!DNL Reports & Analytics] funktioner finns i [Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html). Sedan Analysis Workspace släpptes 2015 har [!DNL Reports & Analytics] funktionaliteten och funktionerna har flyttats till Analysis Workspace och ett tröskelvärde för arbetsflödets paritet har uppnåtts. [Detta meddelande](https://spark.adobe.com/page/6WnF8JK6IRDhf/) förklarar processen för att avsluta livscykeln.<p>Den 31 december 2023 kommer vi att avsluta många av de tillhörande funktionerna i Rapporter och analyser, bland annat, men inte begränsat till: Schemalagda rapporter, dataextrakt och DL-rapporter. Efter den 31 december 2023 skickas inga schemalagda rapporter längre. I **April 2023**, kommer alla rapporter som skulle ha gått ut efter den 31 december 2023 automatiskt att uppdateras och återställas till att upphöra den 31 december 2023. Dessutom kan du inte längre schemalägga framtida rapporter efter 31 december 2023. |
| **EOL för [!UICONTROL Publishing Lists] funktion** | 29 september 2022 | Som en del av ledningscentralen för rapporter och analyser [!UICONTROL Publishing Lists] kommer att nå slutet av livscykeln i **December 2023**. Du kommer inte att kunna skapa nya eller komma åt befintliga [!UICONTROL Publishing Lists] att skicka eller schemalägga [!UICONTROL Analysis Workspace] projekt. |
| **EOL för Data Workbench** | 14 september 2022 | Adobe har för avsikt att göra Datan Workbench gällande **31 december 2023**. Se [Datans Workbench meddelande om att livscykeln upphör](https://experienceleague.adobe.com/docs/data-workbench/using/eol.html) för mer information. Kontakta din organisations kontoansvarige på Adobe om du har frågor. |

{style="table-layout:auto"}

## AppMeasurement

De senaste uppdateringarna av AppMeasurement (version 2.24.0) finns på [Versionsinformation om AppMeasurement for JavaScript](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html).


## Relaterade resurser

* [Information om föregående version för 2022](/help/release-notes/2022.md)
* [Versionsinformation för Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html)
* [Versionsinformation om Media Analytics](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html)
* Den senaste releaseuppdateringen för [Adobe Experience Cloud-produkter](https://business.adobe.com/products/adobe-experience-cloud-products.html)
