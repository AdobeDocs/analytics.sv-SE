---
title: Aktuella versionsinformation för Adobe Analytics
description: Visa den aktuella versionsinformationen för Adobe Analytics
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: e9abbc03cf01abecab4ea0627624b5272b503d5c
workflow-type: tm+mt
source-wordcount: '722'
ht-degree: 1%

---

# Aktuell versionsinformation för Adobe Analytics (februari 2024)

**Senaste uppdatering**: 16 februari 2024

Versionsanteckningarna gäller frisläppningsperioden 14 februari 2024 till 11 mars 2024. Adobe Analytics-releaser fungerar på en [kontinuerlig leveransmodell](releases.md) vilket ger en mer skalbar, stegvis metod för driftsättning av funktioner. Därför uppdateras versionsinformationen flera gånger i månaden. Kontrollera dem regelbundet.

## Nya funktioner eller förbättringar {#features}

| Funktion | Beskrivning | [Startar](releases.md) | [Allmän tillgänglighet](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Activity Map för Web SDK utan extra kostnad** | För närvarande räknas länkarhändelser i Activity Map som sina egna händelser och medför extra kostnader. Den här förbättringen tar några länkhändelser och paketerar dem i nästa träff, ungefär som hur händelser hanteras av AppMeasurementet. |  | 6 mars 2024 |
| **Ökning av standardtröskelvärden för låg trafik** | I **mitten av april 2024** kommer Adobe att börja öka standardrapporteringsprogrammets lågtrafiktrösklar enligt följande: ![lågtrafiktrösklar](assets/thresholds.png) Detta påverkar endast variabler som för närvarande ligger under de nya tröskelvärdena. Dessa ändringar kommer att göras stegvis, och vi förväntar oss att arbetet ska vara slutfört av **slutet av maj**. När dessa ökningar introduceras kan du märka förändringar för variabler med hög kardinalitet:<ul><li>Fler dimensionsvärden kan vara tillgängliga för rapportering.</li><li>Segment och beräknade värden kan innehålla mer data.</li><li>Virtuella rapportsviter baserade på segment kan innehålla mer data.</li><li>Export av klassificeringar kan innehålla mer data.</li></ul> | Mid April, 2024 | I slutet av maj 2024 |

{style="table-layout:auto"}

## Korrigeringar i Adobe Analytics

* Åtgärdade följande klassificeringsproblem: AN-319515; AN-337559; AN-338149; AN-338702; AN-338769; AN-338891; AN-339 327; AN-339649; AN-339668; AN-339669; AN-339776; AN-339822; AN-340017; AN-3402 02; AN-340476;
* Åtgärdade följande fel i klassificeringsregelbyggaren: AN-338385; AN-338399; AN-338592; AN-338810; AN-338893; AN-339431; AN-33 9894; AN-339933; AN-340201; AN-340309;
* Åtgärdade följande A4T-problem: AN-334830; AN-336194; AN-338309; AN-338650;
* Åtgärdade följande datainsamlingsproblem: AN-339323
* Åtgärdade följande problem med Datan Warehouse: AN-335542; AN-331425; AN-337215; AN-338445; AN-338643; AN-338651; AN-399 461; AN-340066; AN-340207; AN-340460
* Åtgärdade följande dataflödesproblem: AN-335952; AN-338653; AN-339508; AN-339681; AN-340418
* Åtgärdade följande problem med datakällor: AN-338648
* Följande Analysis Workspace-problem har korrigerats: AN-326509; AN-336186; AN-336190; AN-336309; AN-337922; AN-338094; AN-383; AN-338556; AN-339600; AN-340445

### Korrigeringar för andra analyser

AN-328239; AN-332908; AN-335449; AN-335517; AN-336075; AN-336100; AN-336128; AN-4 338088; AN-338270; AN-338393; AN-338494; AN-339326; AN-339742; AN-339883; AN-3 40419,

## Viktiga meddelanden för Adobe Analytics-administratörer {#admin}

| Meddelande | Datum tillagt eller uppdaterat | Beskrivning |
| ----------- | ---------- | ---------- |
| Tillägg för Adobe API-objektmedlemmar | 17 januari 2024 | Adobe kan när som helst och utan föregående meddelande eller ändringar i versionshanteringen lägga till medlemmar för begäran och svar (namn/värde-par) i befintliga API-objekt. Adobe rekommenderar att du läser API-dokumentationen för alla tredjepartsverktyg som du integrerar med våra API:er så att sådana tillägg ignoreras vid bearbetningen, om de inte tolkas. Om de implementeras på rätt sätt är sådana tillägg fasta ändringar för implementeringen. Adobe tar inte bort parametrar eller lägger till obligatoriska parametrar utan att först skicka standardmeddelanden via versionsinformation. |
| `getPageLoadTime` insticksprogrammet är inaktuellt | 10 januari 2024 | Detta plugin-program stöds inte längre. I koden används metoden performance.timing som (enligt MDN) har [inaktuell](https://developer.mozilla.org/en-US/docs/Web/API/PerformanceTiming). Arbetet med ett uppdaterat plugin-program har startats. |

{style="table-layout:auto"}

## EOL-meddelanden (End-of-life) {#eol}

| EOL-produkt eller -funktion | Datum tillagt eller uppdaterat | Beskrivning |
| --- | --- | --- |
| **Migrering till autentiseringsuppgifter för Adobe I/O OAuth Server-till-Server** | 11 maj 2023 | Adobe Analytics API- och LiveStream-kunder som använder Adobe I/O JWT-autentiseringsuppgifter måste migrera till Adobe I/O OAuth Server-till-Server-autentiseringsuppgifter genom att **1 januari 2025**. Adobe I/O tillåter inte att nya JWT-autentiseringsuppgifter skapas från och med 1 maj 2024. Kunder som använder JWT måste skapa en ny OAuth Server-till-Server-autentiseringsuppgift eller migrera sina befintliga JWT-autentiseringsuppgifter till en OAuth Server-till-Server-autentiseringsuppgift. Kunderna måste även uppdatera sina klientprogram för att kunna använda de nya autentiseringsuppgifterna för OAuth Server-till-Server. <ul><li>[Migrerar från JWT-autentiseringsuppgifter (Service Account)](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)</li><li>[Implementeringsguide för nya och gamla program med OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)<li>[Använda de nya autentiseringsuppgifterna för OAuth Server-till-Server](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)</li><li>[Vanliga frågor](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)</li></ul> |

{style="table-layout:auto"}

## AppMeasurement

De senaste uppdateringarna av AppMeasurement (version 2.25.0) finns på [AppMeasurement för versionsinformation för JavaScript](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html).


## Relaterade resurser

* [Information om föregående version för 2023](/help/release-notes/2023.md)
* [Versionsinformation för Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html)
* [Versionsinformation om Media Analytics](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html)
* Den senaste releaseuppdateringen för [Adobe Experience Cloud](https://business.adobe.com/products/adobe-experience-cloud-products.html)
