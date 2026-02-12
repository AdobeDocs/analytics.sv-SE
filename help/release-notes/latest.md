---
title: Aktuella versionsinformation för Adobe Analytics
description: Visa den aktuella versionsinformationen för Adobe Analytics
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: d1d08ded701ad68628179874aa6ac21e59ad08dc
workflow-type: tm+mt
source-wordcount: '1440'
ht-degree: 0%

---

# Aktuell versionsinformation för Adobe Analytics (februari 2026)

**Senast uppdaterad**: 11 februari 2026

Versionskommentarerna gäller versionsperioden från februari 2026. Adobe Analytics-releaser fungerar på en [kontinuerlig leveransmodell](releases.md), vilket ger en mer skalbar, fasad metod för driftsättning av funktioner. Versionsinformationen uppdateras därför flera gånger i månaden. Kontrollera dem regelbundet.

## Nya funktioner eller förbättringar {#features}

| Funktion och beskrivning | [Startar](releases.md) | [Allmän tillgänglighet](releases.md) |
| ----------- | ---------- | ---- |
| **Förbättrade dataflöden** <p>Följande förbättringar är nu tillgängliga för dataflöden:</p><ul><li>Förbättrad användarupplevelse.</li><li>Ny upplevelse för att skapa och hantera kolumnmallar.</li><li>Nu kan du välja när du vill skapa en kolumnmall för återanvändning i framtida dataflöden. Du kan också ta bort, redigera och kopiera mallar.<br/>Tidigare resulterade varje datafeed som skapades i en ny kolumnmall, som resulterade i ett stort antal oanvända kolumnmallar och inget sätt att ta bort eller hantera dem.</li><li>Lägg till och filtrera efter taggar.</li><li>Visa historiken för dataflödesjobb. (När begärandeperioden började, när den började, slutfördes o.s.v.)</li><li>Skicka om eller bearbeta dataflöden på nytt. (Från sidan Jobbhistorik)</li><li>Tillåt sena träffar. Du kan nu inkludera data som kommer efter att datafeedjobbet har slutfört databearbetningen inom den angivna rapporteringsfrekvensen.</li><li>När du väljer ett slutdatum för en datafeed inkluderas det slutdatum som du väljer som den sista dagen i dataflödet.<br/>Tidigare har slutdatumet uteslutits från dataflödet.</li><li>Det går nu att exportera med 15 minuters intervall, men den är inte tillgänglig som standard. För att det här alternativet ska bli tillgängligt i din miljö måste du först kontakta Adobe kundtjänst och begära att rapportsviten är konfigurerad för att stödja 15-minuters export.</li></ul><p>**Obs!** Med de här förbättringarna uppdateras även URL:er till datafeeds sidor i Adobe Analytics. Uppdatera befintliga bokmärken så att de pekar på de nya dataflödena senast 30 april 2026.</p><p>Mer information finns i [Skapa en datafeed](/help/export/analytics-data-feed/create-feed.md) och [Hantera dataflöden](/help/export/analytics-data-feed/df-manage-feeds.md).</p> | 20 januari 2026 | 24 februari 2026<p>(Ursprungligen planerat att släppas den 10 februari 2026)</p> |
| **Sortera tabeller efter flera kolumner** <p>Nu kan du sortera data i en frihandstabell efter flera kolumner i Analysis Workspace, oavsett om det är dimensioner eller mätvärden.</p><p>När du sorterar data för flera kolumner sorteras data efter den prioritet som du tilldelar varje kolumn. Prioritetsnumrering visas bredvid sorteringsikonen.</p><p>Mer information finns i [Filtrera och sortera tabeller på frihand](/help/analyze/analysis-workspace/visualizations/freeform-table/filter-and-sort.md).</p> | 28 januari 2026 | Mars <p>(ursprungligen planerat till den 18 februari 2026)</p> |
| **Uppdatera till funktionen Approximate Count Distinct**<p>Den HLL-algoritm som används i funktionen Approximate Count Distinct kommer snart att uppdateras. Resultatet för tal som använder den här funktionen kan ändras något från historiska tal enligt följande:</p><ul><li>När mycket små mängder unika värden räknas kommer resultatet att förbättras så att exakta räkningar används i stället för uppskattningar.</li><li>När du räknar med något större kommer antalet uppskattningar att behålla samma noggrannhet som före den här uppdateringen (uppskattningarna är exakta inom 5 procent av det exakta talet, 95 procent av tiden).</li></ul><p>Mer information om funktionen Approximate Count Distinct finns i [Distinkt antal](/help/components/calculated-metrics/cm-reference/cm-adv-functions.md#approximate-count-distinct) i [Avancerade funktioner](/help/components/calculated-metrics/cm-reference/cm-adv-functions.md)</p> |  | Mars 2026 |
| **Direktuppspelande medietjänster: Supportschemadata** <p>Nu kan du överföra schemalagda data från tidigare direktuppspelat mediematerial för att enklare och exaktare spåra tittandet.</p><p>Nedan följer exempel på live-innehåll som stöds vid schemalagd dataöverföring:</p><ul><li>FAST-plattformar (Free Ad Supported TV)</li><li>Lokala strömmar</li><li>Livesporter</li></ul><p>När du överför schemadata kan du spåra visningsdata för enskilda program som kördes under den tid du angav i överföringsfilen. Du kan till och med samla in visningsdata för specifika ämnen eller programsegment.</p><p>Dessa funktioner är tillgängliga oavsett hur du implementerade Streaming Media Collection.</p><p>Tidigare var det svårt att knyta en given session till specifika program när man analyserade direktinnehåll, och det var inte möjligt att knyta en given session till enskilda ämnen eller programsegment.</p><p>Mer information finns i [Överför schemadata för att spåra livematerial](https://experienceleague.adobe.com/en/docs/media-analytics/using/media-use-cases/track-schedule-data)</p> | 29 oktober 2025 | Första halvåret 2026<p>(Ursprungligen planerat att släppas den 29 oktober 2025)</p> |
| **Ny API-guide för Adobe Analytics 2.0 Report Suites** <p>Skapa, hämta, uppdatera och ta bort API:er för rapportsviten. Mer information finns i [API-referenshandboken för Adobe Analytics 2.0 Report Suite](https://developer.adobe.com/analytics-apis/docs/2.0/apis/report-suites/) och [API-slutpunktshandboken för Adobe Analytics 2.0 &#x200B;](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/report-suites/).</p> | | Ute nu |
| **Ny rapportguide för avvikelseidentifiering för Adobe Analytics 2.0 API** <p>Skapa en automatisk API-rapport för avvikelseidentifiering. Mer information finns i [API-rapportslutpunktshandboken för avvikelseidentifiering](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/reports/anomaly/).</p> | | Ute nu |
| **Ny rapportguide för grundläggande Adobe Analytics 2.0-API Basic Date Trended** <p>Skapa en automatisk API-rapport om grundläggande KPI-trender för datum Mer information finns i [API-rapportslutpunktshandboken för avvikelseidentifiering](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/reports/kpi/).</p> | | Ute nu |

## Korrigeringar i Adobe Analytics

**Activity Map**:
**Analysis Workspace**: AN-424997, AN-424194, AN-425515, AN-423174, AN-425207, AN-428834, AN-306 540, AN-426014, AN-427801
**Klassifikationer**: AN-422723, AN-424467, AN-423724, AN-424003, AN-425217, AN-396062, AN-422 744, AN-425456, AN-425271, AN-425655, AN-424894, AN-429236
**Dataflöden och Data Warehouse**: AN-427082, AN-405154, AN-406512, AN-423594, AN-425283, AN-425208, AN-4 22510, AN-421189, AN-428986, AN-426724, AN-401525, AN-426884, AN-425146
**Migrering**: AN-421192, AN-423443
**Sekretess**:
**Report Builder**: AN-391415, AN-425125
**Rapportering**: AN-422123, AN-425817, AN-421097, AN-422249, AN-403446, AN-424727, AN-4 26791, AN-427985
**Schemalagda rapporter**: AN-425484, AN-425137
**Segmentering**: AN-428905, AN-428232
**Annan**: AN-425054, AN-420190, AN-42248


## EOL-meddelanden (End-of-life) {#eol}

| EOL-produkt eller -funktion | Datum tillagt eller uppdaterat | Beskrivning |
| --- | --- | --- |
| **Förbättringar av direktuppspelningsbearbetning** | 14 januari 2026 | Adobe planerar att förbättra och ändra formateringen av LiveStream-nyttolaster. Dessa uppdateringar ger bättre överensstämmelse mellan LiveStream och andra Adobe Analytics-funktioner, som Analysis Workspace. Det finns en slutpunkt för förhandsgranskning som gör att du kan testa de planerade ändringarna. I [Versionsinformation för LiveStream](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/livestream/release-notes/) finns en fullständig lista över ändringar och information om slutpunkter för förhandsgranskning. Adobe planerar en hård övergång till det uppdaterade nyttolastformatet den 13 april 2026. |
| **Borttagning av TLS 1.2-chiffersviter** | 11 februari 2026 | Meddelande till administratörer: Adobe planerar att ta bort stödet för följande TLS 1.2-chiffersviter från Adobe datainsamlingsservrar den 27 maj 2026.<ul><li>`TLS_ECDHE_ECDSA_WITH_AES_128_CBC_SHA`</li><li>`TLS_ECDHE_ECDSA_WITH_AES_256_CBC_SHA`</li><li>`TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA`</li><li>`TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA`</li><li>`TLS_RSA_WITH_AES_128_CBC_SHA`</li><li>`TLS_RSA_WITH_AES_256_CBC_SHA`</li></ul><p>Ingen kundåtgärd krävs för de flesta implementeringar. Den här ändringen påverkar i första hand analysdata som skickas från äldre inbyggda program som använder inaktuella TLS-bibliotek och ett fåtal webbbesökare i inaktuella webbläsare eller operativsystem. Genom att ta bort stödet för dessa chiffreringssviter förbättras säkerheten och Adobe anpassas till moderna krypteringsstandarder. Färre än 0,1 % av datainsamlingstrafiken är för närvarande beroende av dessa chiffersviter.</p> |
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
