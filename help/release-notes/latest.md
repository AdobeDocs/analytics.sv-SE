---
title: Aktuella versionsinformation för Adobe Analytics
description: Visa den aktuella versionsinformationen för Adobe Analytics
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 043f2c2b2e3e50570e2f0367680274a1f2670492
workflow-type: tm+mt
source-wordcount: '1185'
ht-degree: 1%

---

# Aktuell versionsinformation för Adobe Analytics (mars 2024)

**Senaste uppdatering**: 19 mars 2024

Versionsinformationen gäller den 12 mars 2024 till april 2024. Adobe Analytics-releaser fungerar på en [kontinuerlig leveransmodell](releases.md) vilket ger en mer skalbar, stegvis metod för driftsättning av funktioner. Därför uppdateras versionsinformationen flera gånger i månaden. Kontrollera dem regelbundet.

## Nya funktioner eller förbättringar {#features}

| Funktion | Beskrivning | [Startar](releases.md) | [Allmän tillgänglighet](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **AppMeasurement** | [AppMeasurement version v2.26.0](/help/implement/appmeasurement-updates.md) är tillgängligt. | | 4 mars 2024 |
| **Ny kolumn som är tillgänglig på startsidan för projekt** | The **[!UICONTROL Last used]** -kolumnen är nu tillgänglig när du visar fliken Projekt på fliken [Adobe Analytics landningssida](https://experienceleague.adobe.com/docs/analytics/analyze/landing.html). <p>Den här informationen kan hjälpa dig att avgöra om ett projekt är värdefullt för användare i organisationen genom att visa datum och tid när projektet senast öppnades.</p> <p>Tidigare **[!UICONTROL Last used]** kolumnen var bara tillgänglig i Beräknat mått-hanteraren, Segment-hanteraren och Alerts-hanteraren.</p> |  | 13 mars 2024 |
| **Analysstöd för godkännandeflaggor som krävs av Google för DMA** | På grund av nya europeiska sekretessbestämmelser kräver Google att uppgifter som samlats in i Europa och som skickats till dem måste ange om två olika typer av samtycke har beviljats. **Från 6 mars**, kommer Google inte längre att godkänna händelsedata som inte tyder på att relevant samtycke beviljats. Adobe Analytics har släppt stöd för att hämta in dessa data via en ny variabel, adConsent. Du kan se den nya variabeln i listan i [Sekretessrapporteringsgränssnitt](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/privacy-reporting.md). Om du vill aktivera detta och redan har sekretess aktiverat för föregående medgivandevariabler måste du aktivera sekretess igen.<p>The [Dimensionen för godkännande av annonsplattform](/help/components/dimensions/ad-consent.md) visar om samtycke samlas in för att skicka data till tredjepartsleverantörer av annonser, som Google, Meta och andra. |  | 13 mars 2024 |
| **Användning av Report Builder ingår i kolumnen&quot;Används i&quot; i Beräknat mått-hanteraren och segmenthanteraren** | När du visar **Används i** -kolumnen i Calculated Metrics Manager eller Segments Manager är nu användningsdata tillgängliga för Report Builder.<p>Tidigare var användningsdata i segmenthanteraren bara tillgängliga för aviseringar, projekt, schemalagda projekt och beräknade mätvärden, medan användningsdata i hanteraren för beräknade mätvärden endast var tillgängliga för aviseringar, projekt och schemalagda projekt.</p> |  | Sent mars eller tidig april |
| **Använd samma molnkonton för datafeeds, Data Warehouse och klassificeringsuppsättningar** | Molnkonton och platser som du skapar kan nu användas för att exportera data (med datafeeds och Data Warehouse) och importera data (med klassificeringsgrupper).<p> **Ändringar när konton konfigureras:** Användare kan konfigurera molnimport- och exportkonton och konfigurera platser för molnimport och -export som kan användas i något av följande syften:<ul><li>Importera data med klassificeringsuppsättningar</li><li>Exportera data med dataflöden</li><li>Exportera data med Data Warehouse.</li></ul><p>**Ändringar när konton hanteras**: Användare kan använda sidan Platser (under Komponenter > Platser) för att visa och hantera alla konton och platser som de skapar, oavsett var de skapades. <p>Tidigare tillämpades sidan Platser bara på konton som skapades för import av data med klassificeringsuppsättningar.</p> | | April 2024 |
| **Administratörer kan hantera alla platser i sin organisation** | Med ett nytt alternativ på sidan Platser kan administratörer visa och hantera alla platser i organisationen. <p>Tidigare kunde administratörer bara visa och hantera de platser som de skapade.</p> |  | April 2024 |
| **Activity Map använder färre serveranrop till Web SDK** | För närvarande räknas länkarhändelser i Activity Map som sina egna händelser och medför extra kostnader. <p>Den här förbättringen tar några länkhändelser och paketerar dem i nästa träff, ungefär som hur händelser hanteras av AppMeasurementet.</p> |  | 3 april 2024 |
| **Ökning av standardtröskelvärden för låg trafik** | I **mitten av april 2024** kommer Adobe att börja öka standardrapporteringsprogrammets lågtrafiktrösklar enligt följande: ![lågtrafiktrösklar](assets/thresholds.png) Detta påverkar endast variabler som för närvarande ligger under de nya tröskelvärdena. Dessa ändringar kommer att göras stegvis, och vi förväntar oss att arbetet ska vara slutfört av **slutet av maj**. När dessa ökningar introduceras kan du märka förändringar för variabler med hög kardinalitet:<ul><li>Fler dimensionsvärden kan vara tillgängliga för rapportering.</li><li>Segment och beräknade värden kan innehålla mer data.</li><li>Virtuella rapportsviter baserade på segment kan innehålla mer data.</li><li>Export av klassificeringar kan innehålla mer data.</li></ul> | | Mid April, 2024 |

{style="table-layout:auto"}

## Korrigeringar i Adobe Analytics

* Åtgärdade följande klassificeringsproblem: AN-335632; AN-337559; AN-340164; AN-340370; AN-341089; AN-341211; AN-341 284; AN-341469; AN-341481; AN-341760; AN-341778; AN-342144; AN-342258; AN-3423 38, AN-342400
* Åtgärdade följande fel i klassificeringsregelbyggaren: AN-340921; AN-341269; AN-341292; AN-341467; AN-341666; AN-342145; AN-34 2329
* Åtgärdade följande problem med intelligenta aviseringar: AN-340736
* Åtgärdade följande segmenteringsproblem: AN-336242
* Följande problem med Datan Warehouse har korrigerats: AN-335354; AN-339446; AN-339774; AN-340221; AN-340599; AN-341277; AN-342 009; AN-342088; AN-342592
* Åtgärdade följande dataflödesproblem: AN-335508; AN-340887; AN-341050; AN-341208; AN-341403; AN-341479; AN-341 524; AN-341661; AN-342000; AN-342125; AN-342256; AN-342301; AN-342410; AN-3425 02; AN-342525
* Åtgärdade följande problem med Report Builder: AN-340540
* Följande Analysis Workspace-problem har korrigerats: AN-295889; AN-330981; AN-338818; AN-339730; AN-341114; AN-341520;

### Korrigeringar för andra analyser

AN-312198; AN-338009; AN-339549; AN-333970; AN-334790; AN-336461; AN-336572; AN-4 339549; AN-34119; AN-341246; AN-341268; AN-341272; AN-341475; AN-341547; AN-34 41558; AN-341680; AN-342017;

## Viktiga meddelanden för Adobe Analytics-administratörer {#admin}

| Meddelande | Datum tillagt eller uppdaterat | Beskrivning |
| ----------- | ---------- | ---------- |
| **Tillägg för Adobe API-objektmedlemmar** | 17 januari 2024 | Adobe kan när som helst och utan föregående meddelande eller ändringar i versionshanteringen lägga till medlemmar för begäran och svar (namn/värde-par) i befintliga API-objekt. Adobe rekommenderar att du läser API-dokumentationen för alla tredjepartsverktyg som du integrerar med våra API:er så att sådana tillägg ignoreras vid bearbetningen, om de inte tolkas. Om de implementeras på rätt sätt är sådana tillägg fasta ändringar för implementeringen. Adobe tar inte bort parametrar eller lägger till obligatoriska parametrar utan att först skicka standardmeddelanden via versionsinformation. |
| **`getPageLoadTime`insticksprogrammet är inaktuellt** | 10 januari 2024 | Detta plugin-program stöds inte längre. I koden används metoden performance.timing som (enligt MDN) har [inaktuell](https://developer.mozilla.org/en-US/docs/Web/API/PerformanceTiming). Arbetet med ett uppdaterat plugin-program har startats. |

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
