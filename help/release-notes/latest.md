---
title: Aktuella versionsinformation för Adobe Analytics
description: Visa den aktuella versionsinformationen för Adobe Analytics
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 5dde5298f522d6045f8872c878f6796dcfa0f710
workflow-type: tm+mt
source-wordcount: '1086'
ht-degree: 1%

---

# Aktuell versionsinformation för Adobe Analytics (april 2026)

**Senast uppdaterad**: 9 april 2026

Versionskommentarerna gäller versionsperioden april 2026. Adobe Analytics-releaser fungerar på en [kontinuerlig leveransmodell](releases.md), vilket ger en mer skalbar, fasad metod för driftsättning av funktioner. Versionsinformationen uppdateras därför flera gånger i månaden. Kontrollera dem regelbundet.

## Nya funktioner eller förbättringar {#features}

| Funktion och beskrivning | [Startar](releases.md) | [Allmän tillgänglighet](releases.md) |
| ----------- | ---------- | ---- |
| **Activity Map-förbättringar**<br/> Activity Map innehåller följande förbättringar:</p><ul><li>Stöd för Activity Map Overlay-tillägget med Web SDK-implementeringar av Adobe Analytics.</li><li>Stöd för WebSDK-spårning (när spårningen går till Analytics).</li><li>Formateringen har uppdaterats i hela användargränssnittet.</li></ul><p>(Dokumentationslänk som ska följas.)</p> | | April 2026 |
| **MCP-servrar för Adobe Analytics** <br/>Nu kan du koppla Adobe Analytics till dina befintliga autentiska arbetsflöden med MCP (Model Context Protocol). Du kan begära rapporter och insikter med det naturliga språket.<p>(Dokumentationslänk som ska följas.)</p> | | I slutet av april 2026 |
| **Direktuppspelande medietjänster: Stöd för schemadata** <br/>Du kan nu överföra schemalagda data från tidigare direktuppspelningsmediainnehåll för att enklare och mer korrekt spåra tittarskap.<p>Nedan följer exempel på live-innehåll som stöds vid schemalagd dataöverföring:</p><ul><li>FAST-plattformar (Free Ad Supported TV)</li><li>Lokala strömmar</li><li>Livesporter</li></ul><p>När du överför schemadata kan du spåra visningsdata för enskilda program som kördes under den tid du angav i överföringsfilen. Du kan till och med samla in visningsdata för specifika ämnen eller programsegment.</p><p>Dessa funktioner är tillgängliga oavsett hur du implementerade Streaming Media Collection.</p><p>Tidigare var det svårt att knyta en given session till specifika program när man analyserade direktinnehåll, och det var inte möjligt att knyta en given session till enskilda ämnen eller programsegment.</p><p>Mer information finns i [Överför schemadata för att spåra livematerial](https://experienceleague.adobe.com/en/docs/media-analytics/using/media-use-cases/track-schedule-data)</p> | 29 oktober 2025 | Första halvåret 2026<p>(Ursprungligen planerat att släppas den 29 oktober 2025)</p> |
| **Ytterligare API-formatering för datumintervall**<br/> Två nya format stöds nu för att ange datumintervall i API-rapportbegäranden för Analytics 2.0. Detta inkluderar en datumformel och ett blandat format. [Läs mer](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/reports/#date-range-field--supported-formats) | | Mars 2026 |
| **Valfri dimension i API-rapportbegäranden**<br/> Ett dimensionsobjekt krävs inte i rapport-API-begäranden. Om ingen dimension anges visar svaret data för en summeringsrapport. [Läs mer](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/reports/#using-dimension-in-report-payload-requests) | | Mars 2026 |
| **Avancerad API-rapport för datumtrender**<br/> Ny guide för avancerad rapport för Adobe Analytics 2.0-API med datumtrender. Skapa avancerade API-rapporter för datumtrender med hjälp av jämförelser och segment för datumintervall. [Läs mer](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/reports/advanced/) | | Mars 2026 |

## Korrigeringar i Adobe Analytics

**Activity Map**:
**Analysis Workspace**: AN-442813, AN-442410, AN-441943, AN-441717, AN-434855, AN-431409, AN-429 777, AN-429048, AN-428892, AN-428189, AN-425215
**Klassificeringar**: AN-443453, AN-443275, AN-443148, AN-442906, AN-442232, AN-442207, AN-442 4148, AN-442133, AN-441937, AN-441901, AN-441807, AN-441671, AN-44133, AN-4413 02, AN-441149, AN-441132, AN-441085, AN-441048, AN-440846, AN-440727, AN-44071 6, AN-440511, AN-440496, AN-432100
**Dataflöden och Data Warehouse**: AN-442211, AN-441719, AN-441183, AN-441011, AN-440625, AN-438953
**Migrering**: AN-442467, AN-440380, AN-440357
**Exporterar**:
**Report Builder**: AN-441136, AN-438147, AN-425150
**Rapportering**: AN-441506, AN-440919, AN-440545, AN-440300
**Rapportsviter**: AN-439429, AN-439423, AN-430988
**Schemalagda rapporter**:
**Segmentering**:
**Annan**: AN-423359, AN-406242, AN-397985


## EOL-meddelanden (End-of-life) {#eol}

| EOL-produkt eller -funktion | Datum tillagt eller uppdaterat | Beskrivning |
| --- | --- | --- |
| **Förbättringar av direktuppspelningsbearbetning** | 14 januari 2026 | Adobe planerar att förbättra och ändra formateringen av LiveStream-nyttolaster. Dessa uppdateringar ger bättre överensstämmelse mellan LiveStream och andra Adobe Analytics-funktioner, som Analysis Workspace. Det finns en slutpunkt för förhandsgranskning som gör att du kan testa de planerade ändringarna. I [Versionsinformation för LiveStream](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/livestream/release-notes/) finns en fullständig lista över ändringar och information om slutpunkter för förhandsgranskning. Adobe planerar en hård övergång till det uppdaterade nyttolastformatet den 13 april 2026. |
| **Borttagning av TLS 1.2-chiffersviter** | 11 februari 2026 | Meddelande till administratörer: Adobe planerar att ta bort stödet för följande TLS 1.2-chiffersviter från Adobe datainsamlingsservrar den 27 maj 2026.<ul><li>`TLS_ECDHE_ECDSA_WITH_AES_128_CBC_SHA`</li><li>`TLS_ECDHE_ECDSA_WITH_AES_256_CBC_SHA`</li><li>`TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA`</li><li>`TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA`</li><li>`TLS_RSA_WITH_AES_128_CBC_SHA`</li><li>`TLS_RSA_WITH_AES_256_CBC_SHA`</li><li>`TLS_RSA_WITH_AES_128_GCM_SHA256`</li><li>`TLS_RSA_WITH_AES_256_GCM_SHA384`</li></ul><p>Ingen kundåtgärd krävs för de flesta implementeringar. Den här ändringen påverkar i första hand analysdata som skickas från äldre inbyggda program som använder inaktuella TLS-bibliotek och ett fåtal webbbesökare i inaktuella webbläsare eller operativsystem. Genom att ta bort stödet för dessa chiffreringssviter förbättras säkerheten och Adobe anpassas till moderna krypteringsstandarder. Färre än 0,1 % av datainsamlingstrafiken är för närvarande beroende av dessa chiffersviter.</p> |
| **Äldre Report Builder** | 18 juni 2025 | Det gamla Report Builder-tillägget upphör i juni 2026. Alla användare bör börja uppgradera sina äldre arbetsböcker till [nya Report Builder](/help/analyze/report-builder/rb-overview.md). Nya Report Builder är tillgängligt för både Adobe Analytics- och Customer Journey Analytics-kunder. Den har [nästan funktionsparitet](/help/analyze/report-builder/convert-workbooks.md#unsupported) plus många nya, praktiska funktioner och gränssnittsförbättringar. För att underlätta uppgraderingsprocessen innehåller nya Report Builder en smidig arbetsbokskonverteringsfunktion. Nya Report Builder finns bara som tillägg via Microsoft Store. Många organisationer måste ha en intern process för godkännande innan tillägget kan göras tillgängligt för användarna. Ge lite tid åt den här processen och börja arbeta med organisationen nu för att se till att du hinner uppgradera dina arbetsböcker innan EOL-datumet. |
| **Åtkomst via äldre domäner eller via äldre enkel inloggning** | 10 april 2025 | Adobe planerar att uppdatera hur användare använder Adobe Analytics för att förbättra säkerheten och effektivisera inloggningen. Som en del av denna insats kommer åtkomst via äldre domäner eller via äldre enkel inloggning (SSO), inklusive `my.omniture.com`, att upphöra permanent den **2 januari 2026**. Efter detta datum kommer äldre inloggningsuppgifter och äldre enkel inloggning inte längre att fungera. Alla användare måste logga in via `experience.adobe.com` med sina Adobe Experience Cloud ID:n. Om du behöver hjälp med ditt Experience Cloud ID kontaktar du Adobe Analytics-administratören eller [Adobe kundtjänst](https://helpx.adobe.com/contact.html). |
| **Adobe Analytics API (version 1.4)** | 17 juli 2024 | Den **12 augusti 2026** kommer följande API-tjänster för Analytics Legacy att ha nått slutet på sin livstid och stängas, och aktuella integreringar som byggts med dessa tjänster kommer att sluta fungera:<ul><li>Adobe Analytics API (version 1.4)</li><li>Adobe Analytics WSSE-autentisering</li></ul><p>Integreringar som använder Adobe Analytics API (version 1.4) måste migrera till [Adobe Analytics 2.0 API](https://developer.adobe.com/analytics-apis/docs/2.0/) medan WSSE-integreringar måste migrera till ett OAuth-baserat autentiseringsprotokoll i [Adobe Developer Console](https://developer.adobe.com/console).</p><p>Se [Vanliga frågor om Adobe Analytics 1.4 API EOL &#x200B;](https://developer.adobe.com/analytics-apis/docs/1.4/guides/eol/) för svar på vanliga frågor och ytterligare vägledning.</p> |


## AppMeasurement

De senaste uppdateringarna för AppMeasurement finns i [AppMeasurement versionsinformation](https://github.com/adobe/appmeasurement/releases).


## Relaterade resurser

* [Information om föregående version för 2025](/help/release-notes/2025.md)
* [Versionsinformation för Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html)
* [Versionsinformation för direktuppspelande medietjänster](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html)
* Den senaste releaseuppdateringen för [Adobe Experience Cloud-produkter](https://business.adobe.com/products/adobe-experience-cloud-products.html)
