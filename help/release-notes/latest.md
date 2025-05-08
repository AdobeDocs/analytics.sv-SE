---
title: Aktuella versionsinformation för Adobe Analytics
description: Visa den aktuella versionsinformationen för Adobe Analytics
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 0bd4075a15edeeccdd9db8a70a1e871f9fc5af20
workflow-type: tm+mt
source-wordcount: '663'
ht-degree: 2%

---

# Aktuell versionsinformation för Adobe Analytics (aprilversion 2025)

**Senast uppdaterad**: 16 april 2025

Versionsanteckningarna gäller den 26 mars till maj 2025. Adobe Analytics-releaser fungerar på en [kontinuerlig leveransmodell](releases.md), vilket ger en mer skalbar, fasad metod för driftsättning av funktioner. Därför uppdateras versionsinformationen flera gånger i månaden. Kontrollera dem regelbundet.

## Nya funktioner eller förbättringar {#features}

| Funktion | Beskrivning | [Startar](releases.md) | [Allmän tillgänglighet](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Analyslager** | Analytics Inventory ger en omfattande översikt över er Adobe Analytics-miljö, inklusive antalet projekt och komponenter, rapportsviter, användare med mera. Genom att automatisera inventeringsprocessen kan ni snabbt förstå vad ni behöver för att gå över från Adobe Analytics till Customer Journey Analytics. Detta gör övergången enklare och snabbare. [Läs mer](https://experienceleague.adobe.com/sv/docs/analytics/admin/admin-tools/analytics-inventory) |  | 26 mars 2025 |
| **Endast Data Warehouse-dimensioner** | Baserat på kundens feedback har vi beslutat oss för att omvärdera. Vi kommer inte att släppa den automatiska måttfunktionen för endast Data Warehouse som tidigare meddelats. | | TBD |

## Korrigeringar i Adobe Analytics

**A4T**: AN-370625; AN-371279; AN-371351
**Administratörsverktyg**: AN-365072; AN-371303
**Analysis Workspace**: AN-363831; AN-369554
**Klassificeringar**: AN-370519; AN-370727; AN-370827; AN-370941; AN-370995; AN-371377; AN-371 597; AN-371868; AN-371869; AN-372510; AN-372650; AN-373164; AN-373300; AN-3733 08; AN-373592
**Datainsamling**: AN-371877
**Dataflöden**: AN-368676; AN-370225; AN-370514; AN-370521; AN-370687; AN-370761; AN-AN 370911; AN-371047; AN-371542; AN-371627; AN-371746; AN-372708; AN-373068; AN-3 73179
**Data Warehouse**: AN-366649; AN-369817; AN-370705; AN-371127; AN-371995; AN-372596; AN-3 72940
**Marknadskanaler**: AN-372308
**Mobilapp**: AN-370287; AN-371335; AN-371374
**Plattform**: AN-369510; AN-370435; AN-372150
**Report Builder**: AN-369830; AN-371395; AN-372983

## Viktiga meddelanden för Adobe Analytics-administratörer {#admin}

| Meddelande | Datum tillagt eller uppdaterat | Beskrivning |
| ----------- | ---------- | ---------- |
| Ej tillämpligt |  |  |

## EOL-meddelanden (End-of-life) {#eol}

| EOL-produkt eller -funktion | Datum tillagt eller uppdaterat | Beskrivning |
| --- | --- | --- |
| **Åtkomst via äldre domäner eller via äldre enkel inloggning** | 10 april 2025 | Adobe planerar att uppdatera hur användare använder Adobe Analytics för att förbättra säkerheten och effektivisera inloggningen. Som en del av denna insats kommer åtkomst via äldre domäner eller via äldre enkel inloggning (SSO), inklusive `my.omniture.com`, att upphöra permanent den **2 januari 2026**. Efter detta datum kommer äldre inloggningsuppgifter och äldre enkel inloggning inte längre att fungera. Alla användare måste logga in via `experience.adobe.com` med sina Adobe Experience Cloud ID:n. Om du behöver hjälp med ditt Experience Cloud ID kontaktar du Adobe Analytics-administratören eller [Adobe kundtjänst](https://helpx.adobe.com/se/contact.html). |
| **Migrering till autentiseringsuppgifter för Adobe I/O OAuth Server-till-Server** | 17 januari 2025 | Adobe Analytics API- och LiveStream-kunder som använder Adobe I/O JWT-autentiseringsuppgifter måste migrera till Adobe I/O OAuth Server-till-Server-autentiseringsuppgifter senast den **30 juni 2025**. Adobe I/O tillåter inte att nya JWT-autentiseringsuppgifter skapas från och med 1 maj 2024. Kunder som använder JWT måste skapa en ny OAuth Server-till-Server-autentiseringsuppgift eller migrera sina befintliga JWT-autentiseringsuppgifter till en OAuth Server-till-Server-autentiseringsuppgift. Kunderna måste även uppdatera sina klientprogram för att kunna använda de nya autentiseringsuppgifterna för OAuth Server-till-Server. <ul><li>[Migrerar från JWT-autentiseringsuppgifter ](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration)</li><li>[Implementeringsguide för nya och gamla program med OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation)<li>[Använder de nya autentiseringsuppgifterna för OAuth Server-till-server](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation)</li><li>[Vanliga frågor](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs)</li></ul> |
| **EOL för Adobe Analytics API (version 1.4)** | 17 juli 2024 | Den **12 augusti 2026** kommer följande API-tjänster för Analytics Legacy att ha nått slutet på sin livstid och stängas, och aktuella integreringar som byggts med dessa tjänster kommer att sluta fungera:<ul><li>Adobe Analytics API (version 1.4)</li><li>Adobe Analytics WSSE-autentisering</li></ul><p>Integreringar som använder Adobe Analytics API (version 1.4) måste migrera till [Adobe Analytics 2.0 API](https://developer.adobe.com/analytics-apis/docs/2.0/) medan WSSE-integreringar måste migrera till ett OAuth-baserat autentiseringsprotokoll i [Adobe Developer Console](https://developer.adobe.com/console).</p><p>Se [Vanliga frågor om Adobe Analytics 1.4 API EOL ](/help/admin/c-admin-api/c-admin-14-api-eol.md) för svar på vanliga frågor och ytterligare vägledning.</p> |


## AppMeasurement

De senaste uppdateringarna för AppMeasurement finns i [AppMeasurement versionsinformation](https://github.com/adobe/appmeasurement/releases).


## Relaterade resurser

* [Information om föregående version för 2025](/help/release-notes/2025.md)
* [Versionsinformation för Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=sv-SE)
* [Versionsinformation för direktuppspelad mediainsamling](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=sv-SE)
* Den senaste releaseuppdateringen för [Adobe Experience Cloud-produkter](https://business.adobe.com/products/adobe-experience-cloud-products.html)
