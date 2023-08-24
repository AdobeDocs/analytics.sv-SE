---
title: Aktuella versionsinformation för Adobe Analytics
description: Se versionsinformationen för Adobe Analytics.
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 5d0133495613c89deca4dc070d38389ef89853b3
workflow-type: tm+mt
source-wordcount: '883'
ht-degree: 2%

---

# Aktuell versionsinformation för Adobe Analytics (augusti 2023)

**Senaste uppdatering**: 24 augusti 2023

Versionsanteckningarna gäller den 9 augusti-13 september 2023. Adobe Analytics-releaser fungerar på en [kontinuerlig leveransmodell](releases.md) vilket ger en mer skalbar, stegvis metod för driftsättning av funktioner. Därför uppdateras versionsinformationen flera gånger i månaden. Kontrollera dem regelbundet.

## Nya funktioner eller förbättringar {#features}

| Funktion | Beskrivning | [Startar](releases.md) | [Allmän tillgänglighet](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Klassificeringsuppsättningar i API 2.0** | Innehåller Adobe Analytics API 2.0-metoder för att spara, ta bort, hämta, importera och exportera klassificeringsuppsättningsdata. | Ej tillämpligt | 30 augusti 2023 |
| **Rapporteringsaktivitetshanteraren** | Rapporteringsaktivitetshanteraren ger administratörer detaljerad insyn i rapporteringsförbrukningen för varje rapportsvit, så att administratörer enkelt kan diagnostisera och sedan åtgärda kapacitetsproblem under högbelastade rapporteringstider. [Läs mer](/help/admin/admin/reporting-activity.md) | Ej tillämpligt | 12 september 2023 |

{style="table-layout:auto"}

## Korrigeringar i Adobe Analytics

* Korrigerade ett problem med anpassade händelser som inte lästes in. (AN-324163)
* Korrigerade ett problem med att det inte gick att redigera etiketter för teckenförklaringen i en visualisering. (AN-323246)

AN-315605; AN-316306; AN-317494; AN-317844; AN-320424; AN-320597; AN-320680; AN 320869; AN-321624; AN-321693; AN-322009; AN-322244; AN-322380; AN-322432; AN-33 22466; AN-322556; AN-322669; AN-322735; AN-323151; AN-323220; AN-323380; AN-322 3492; AN-323595; AN-323755; AN-323854; AN-323916; AN-324044; AN-324200; AN-324 213; AN-324238; AN-324347; AN-323598; AN-323625; AN-323631; AN-323638; AN-3236 41; AN-323755; AN-323767; AN-323777; AN-323825; AN-323846; AN-323972; AN-32411 3; AN-324170; AN-324197; AN-324273; AN-324275; AN-324345; AN-324384; AN-324433; AN-324511; AN-324513; AN-324521; AN-324524; AN-324531; AN-324532; AN-324534; AN 324537; AN-324569; AN-324618; AN-324635; AN-324688; AN-324704; AN-324712; AN-3 24721; AN-324745; AN-324792; AN-324793; AN-324794; AN-324795; AN-324824; AN-32 4905; AN-324918; AN-324932; AN-324934; AN-324947; AN-325003; AN-325073; AN-325 143; AN-325148; AN-325153; AN-325177; AN-325187; AN-325252; AN-325305; AN-3253 63; AN-325401; AN-325439; AN-325431; AN-325491; AN-325495; AN-325508; AN-32559 4; AN-325601; AN-325660; AN-325779; AN-325857; AN-325883; AN-325885; AN-32586


## Viktiga meddelanden för Adobe Analytics-administratörer {#admin}

| Meddelande | Datum tillagt eller uppdaterat | Beskrivning |
| ----------- | ---------- | ---------- |
| **37-månaders förfallodatum för inköps-ID och händelse-ID (händelseserialisering)** | Juli 10,2023 | Den senaste releasen av motorn för bearbetning av träffar i Analytics, släppt den **13 juli 2023**, började genomdriva en 37-månaders förfallotid för inköps-ID och händelse-ID (händelseserialisering). Tidigare upphörde aldrig Inköp-ID och Händelse-ID i Adobe Analytics. När ett inköps-ID eller ett händelse-ID visades/användes, hade eventuella framtida träffar, oavsett när, markerats som en dubblett. Med den nya versionen av bearbetningsmotorn:<ul><li>Inköps-ID och händelse-ID:n går alltid ut efter 37 månader.</li><li>Om det har gått 37 månader sedan inköps-ID:t eller händelse-ID:t sågs, betraktas det inte längre som ett dubblettköp eller -händelse.</li><li> Om du återanvänder inköps-ID:n eller händelse-ID:n för mer än 37 månader sedan betraktas de inte längre som dubbletter.</li></ul> |
| **Migrering till autentiseringsuppgifter för Adobe I/O OAuth Server-till-Server** | 11 maj 2023 | Adobe Analytics API- och LiveStream-kunder som använder Adobe I/O JWT-autentiseringsuppgifter måste migrera till Adobe I/O OAuth Server-till-Server-autentiseringsuppgifter genom att **1 januari 2025**. Mer information och tidslinjer finns i meddelandet om att produkten upphör att gälla i tabellen nedan. |

{style="table-layout:auto"}

## EOL-meddelanden (End-of-life) {#eol}

| EOL-produkt eller -funktion | Datum tillagt eller uppdaterat | Beskrivning |
| --- | --- | --- |
| **Migrering till autentiseringsuppgifter för Adobe I/O OAuth Server-till-Server** | 11 maj 2023 | Adobe Analytics API- och LiveStream-kunder som använder Adobe I/O JWT-autentiseringsuppgifter måste migrera till Adobe I/O OAuth Server-till-Server-autentiseringsuppgifter genom att **1 januari 2025**. Adobe I/O tillåter inte att nya JWT-autentiseringsuppgifter skapas från och med 1 maj 2024. Kunder som använder JWT måste skapa en ny OAuth Server-till-Server-autentiseringsuppgift eller migrera sina befintliga JWT-autentiseringsuppgifter till en OAuth Server-till-Server-autentiseringsuppgift. Kunderna måste även uppdatera sina klientprogram för att kunna använda de nya autentiseringsuppgifterna för OAuth Server-till-Server. <ul><li>[Migrerar från JWT-autentiseringsuppgifter (Service Account)](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)</li><li>[Implementeringsguide för nya och gamla program med OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)<li>[Använda de nya autentiseringsuppgifterna för OAuth Server-till-Server](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)</li><li>[Vanliga frågor](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)</li></ul> |
| **EOL för[!DNL Reports & Analytics]** | 7 mars 2023 | Effektivt **31 december 2023** kommer Adobe att upphöra med sin verksamhet [!DNL Reports & Analytics] och tillhörande rapporter och funktioner. Rapporterna, visualiseringar och underliggande teknik som ger kraft åt [!DNL Reports & Analytics] inte längre uppfyller Adobe teknikstandarder. Mest [!DNL Reports & Analytics] funktioner finns i [Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html). Sedan Analysis Workspace släpptes 2015 har [!DNL Reports & Analytics] funktionaliteten och funktionerna har flyttats till Analysis Workspace och ett tröskelvärde för arbetsflödets paritet har uppnåtts. [Detta meddelande](https://spark.adobe.com/page/6WnF8JK6IRDhf/) förklarar processen för att avsluta livscykeln.<p>Den 31 december 2023 kommer många av de tillhörande funktionerna för rapporter och analys att avslutas, inklusive, men inte begränsat till, schemalagda rapporter, dataextrakt och DL-rapporter. Efter den 31 december 2023 skickas inga schemalagda rapporter längre. I **April 2023**, kommer alla rapporter som skulle ha gått ut efter den 31 december 2023 automatiskt att uppdateras och återställas till att upphöra den 31 december 2023. Dessutom kan du inte längre schemalägga framtida rapporter efter 31 december 2023. |
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
