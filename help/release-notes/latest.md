---
title: Aktuella versionsinformation för Adobe Analytics
description: Visa den aktuella versionsinformationen för Adobe Analytics
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: f258a1150a4bee11f5922d058930dc38b1ddfa14
workflow-type: tm+mt
source-wordcount: '1009'
ht-degree: 0%

---

# Aktuell versionsinformation för Adobe Analytics (juni 2025-utgåvan)

**Senast uppdaterad**: 24 juni 2025

Versionsanteckningarna gäller den 18 juni-15 juli 2025. Adobe Analytics-releaser fungerar på en [kontinuerlig leveransmodell](releases.md), vilket ger en mer skalbar, fasad metod för driftsättning av funktioner. Därför uppdateras versionsinformationen flera gånger i månaden. Kontrollera dem regelbundet.

## Nya funktioner eller förbättringar {#features}

| Funktion | Beskrivning | [Startar](releases.md) | [Allmän tillgänglighet](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Stöd för säkra molnmål i nya Report Builder** | Tillägget Javascript Report Builder har nu stöd för export av rapporter till följande molnlagringsmål:<ul><li>Amazon S3 Role ARN</li><li>Google Cloud Platform</li><li>Azure SAS</li><li>Azure RBAC</li></ul><p>Tidigare var endast FTP- och e-postmål tillgängliga. FTP stöds inte längre på grund av säkerhetsproblem.</p><p>Mer information finns i [Schemalägg arbetsböcker genom att exportera till molnmål](/help/analyze/report-builder/report-builder-export.md).</p><p>När du skapar en plats i Adobe Analytics innehåller fältet Använd med nu även ett alternativ för att använda platsen med Report Builder, vilket beskrivs i [Konfigurera molnimport- och exportplatser](/help/components/locations/configure-import-locations.md).</p> |  | 19 juni 2025 (original 18 juni) |
| **Ny förhandsgranskning** | I förhandsgranskningspanelen, som används när du skapar ett segment eller konfigurerar inställningarna för en datavy, används nu en vågrät fältvisualisering i stället för en donutvisualisering. |  | 18 juni 2025 |
| **Dialogrutan för ändrad attribueringsmodell** | Du kan nu definiera behållaren och tidsperioden separat i dialogrutan för attribueringsmodell. |  | Juni 18,2025 |
| **Navigeringen till användargränssnittet för kundattribut har uppdaterats** | Användargränssnittet för kundattribut är nu tillgängligt direkt från programväljaren i Adobe Experience Cloud. |  | TBD |
| **Direktuppspelande media: Stödschemadata** | Nu kan du överföra schemalagda data från tidigare direktuppspelat mediematerial för att enklare och exaktare spåra tittandet. Nedan följer exempel på live-innehåll som stöds vid schemalagd dataöverföring:<ul><li>FAST-plattformar (Free Ad Supported TV)</li><li>Lokala strömmar</li><li>Livesporter</li></ul>När du överför schemadata kan du spåra visningsdata för enskilda program som kördes under den tid du angav i överföringsfilen. Du kan till och med samla in visningsdata för specifika ämnen eller programsegment. Dessa funktioner är tillgängliga oavsett hur du implementerade Streaming Media Collection.<p>Tidigare var det svårt att knyta en given session till specifika program när man analyserade direktinnehåll, och det var inte möjligt att knyta en given session till enskilda ämnen eller programsegment. Läs mer |  | 15 augusti 2025 (ursprungligen 25 juni 2025) |

## Korrigeringar i Adobe Analytics

**A4T**: AN-379045
**Advertising Analytics**: AN-377338
**Varningar**: AN-377229
**Analysis Workspace**: AN-378891; AN-379589; AN-379604; AN-381270; AN-382264; AN-382414;
**API 1.4**: AN-380188
**API 2.0**: AN-373078; AN-379006; AN-381248
**Klassificeringar**: AN-379209; AN-379315; AN-379567; AN-379573; AN-379749; AN-379764; AN-3 79818; AN-380433; AN-381670; AN-381751; AN-381994; AN-382055; AN-382682; AN-38 3059; AN-383409
**Bidragsanalys**: AN-369822
**Dataflöden**: AN-365552; AN-367158; AN-378288; AN-379754; AN-380433; AN-380855; AN-3 380959; AN-38115; AN-381657; AN-381931
**Data Warehouse**: AN-379244
**Plattform**: AN-375847
**Bearbetningsregler**: AN-375157
**Report Builder**: AN-371395; AN-372174; AN-373815; AN-383194
**Serveranrop**: AN-380930
**Användnings- och åtkomstloggar**: AN-372130; AN-382123
**Virtuella rapportsviter**: AN-382010


## EOL-meddelanden (End-of-life) {#eol}

| EOL-produkt eller -funktion | Datum tillagt eller uppdaterat | Beskrivning |
| --- | --- | --- |
| **Äldre Report Builder** | 18 juni 2025 | Det gamla Report Builder-tillägget upphör i juni 2026. Alla användare bör börja uppgradera sina äldre arbetsböcker till [nya Report Builder](https://experienceleague.adobe.com/sv/docs/analytics/analyze/report-builder/rb-overview). Nya Report Builder är tillgängligt för både Adobe Analytics- och Customer Journey Analytics-kunder. Den har [nästan funktionsparitet](https://experienceleague.adobe.com/sv/docs/analytics/analyze/report-builder/convert-workbooks#unsupported) plus många nya, praktiska funktioner och gränssnittsförbättringar. För att underlätta uppgraderingsprocessen innehåller nya Report Builder en smidig arbetsbokskonverteringsfunktion. Nya Report Builder finns bara som tillägg via Microsoft Store. Många organisationer måste ha en intern process för godkännande innan tillägget kan göras tillgängligt för användarna. Ge lite tid åt den här processen och börja arbeta med organisationen nu för att se till att du hinner uppgradera dina arbetsböcker innan EOL-datumet. |
| **Åtkomst via äldre domäner eller via äldre enkel inloggning** | 10 april 2025 | Adobe planerar att uppdatera hur användare använder Adobe Analytics för att förbättra säkerheten och effektivisera inloggningen. Som en del av denna insats kommer åtkomst via äldre domäner eller via äldre enkel inloggning (SSO), inklusive `my.omniture.com`, att upphöra permanent den **2 januari 2026**. Efter detta datum kommer äldre inloggningsuppgifter och äldre enkel inloggning inte längre att fungera. Alla användare måste logga in via `experience.adobe.com` med sina Adobe Experience Cloud ID:n. Om du behöver hjälp med ditt Experience Cloud ID kontaktar du Adobe Analytics-administratören eller [Adobe kundtjänst](https://helpx.adobe.com/se/contact.html). |
| **Migrering till autentiseringsuppgifter för Adobe I/O OAuth Server-till-Server** | 17 januari 2025 | Adobe Analytics API- och LiveStream-kunder som använder Adobe I/O JWT-autentiseringsuppgifter måste migrera till Adobe I/O OAuth Server-till-Server-autentiseringsuppgifter senast den **30 juni 2025**. Adobe I/O tillåter inte att nya JWT-autentiseringsuppgifter skapas från och med 1 maj 2024. Kunder som använder JWT måste skapa en ny OAuth Server-till-Server-autentiseringsuppgift eller migrera sina befintliga JWT-autentiseringsuppgifter till en OAuth Server-till-Server-autentiseringsuppgift. Kunderna måste även uppdatera sina klientprogram för att kunna använda de nya autentiseringsuppgifterna för OAuth Server-till-Server. <ul><li>[Migrerar från JWT-autentiseringsuppgifter ](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration)</li><li>[Implementeringsguide för nya och gamla program med OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation)<li>[Använder de nya autentiseringsuppgifterna för OAuth Server-till-server](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation)</li><li>[Vanliga frågor](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs)</li></ul> |
| **Adobe Analytics API (version 1.4)** | 17 juli 2024 | Den **12 augusti 2026** kommer följande API-tjänster för Analytics Legacy att ha nått slutet på sin livstid och stängas, och aktuella integreringar som byggts med dessa tjänster kommer att sluta fungera:<ul><li>Adobe Analytics API (version 1.4)</li><li>Adobe Analytics WSSE-autentisering</li></ul><p>Integreringar som använder Adobe Analytics API (version 1.4) måste migrera till [Adobe Analytics 2.0 API](https://developer.adobe.com/analytics-apis/docs/2.0/) medan WSSE-integreringar måste migrera till ett OAuth-baserat autentiseringsprotokoll i [Adobe Developer Console](https://developer.adobe.com/console).</p><p>Se [Vanliga frågor om Adobe Analytics 1.4 API EOL ](/help/admin/c-admin-api/c-admin-14-api-eol.md) för svar på vanliga frågor och ytterligare vägledning.</p> |



## AppMeasurement

De senaste uppdateringarna för AppMeasurement finns i [AppMeasurement versionsinformation](https://github.com/adobe/appmeasurement/releases).


## Relaterade resurser

* [Information om föregående version för 2025](/help/release-notes/2025.md)
* [Versionsinformation för Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=sv-SE)
* [Versionsinformation för direktuppspelad mediainsamling](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=sv-SE)
* Den senaste releaseuppdateringen för [Adobe Experience Cloud-produkter](https://business.adobe.com/products/adobe-experience-cloud-products.html)
