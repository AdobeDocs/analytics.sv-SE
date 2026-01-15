---
title: Aktuella versionsinformation för Adobe Analytics
description: Visa den aktuella versionsinformationen för Adobe Analytics
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 69aa42b1949944b59740222073635be72c4bd6ab
workflow-type: tm+mt
source-wordcount: '1225'
ht-degree: 0%

---

# Aktuell versionsinformation för Adobe Analytics (januari 2026)

**Senast uppdaterad**: 14 januari 2026

Versionsinformationen gäller januari 2026-versionsperioden. Adobe Analytics-releaser fungerar på en [kontinuerlig leveransmodell](releases.md), vilket ger en mer skalbar, fasad metod för driftsättning av funktioner. Därför uppdateras versionsinformationen flera gånger i månaden. Kontrollera dem regelbundet.

## Nya funktioner eller förbättringar {#features}

| Funktion | Beskrivning | [Startar](releases.md) | [Allmän tillgänglighet](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Regelverktyget för klassificeringsuppsättningar** | Funktionen Regelbyggaren är nu tillgänglig i klassificeringsuppsättningar. Du definierar regler inom en klassificeringsuppsättnings kontext. Regler tillämpas (när de aktiveras) på alla kombinationer av rapportsviter och nyckeldimensioner som prenumererar på klassificeringsuppsättningen.<p>(Dokumentationslänk som ska följas.)</p> |  | 30 januari 2026 |
| **Förbättrade dataflöden** | Följande förbättringar är nu tillgängliga för dataflöden:<ul><li>Förbättrad användarupplevelse.</li><li>Ny upplevelse för att skapa och hantera kolumnmallar.</li><li>Nu kan du välja när du vill skapa en kolumnmall för återanvändning i framtida dataflöden. Du kan också ta bort, redigera och kopiera mallar.<br/>Tidigare resulterade varje datafeed som skapades i en ny kolumnmall, som resulterade i ett stort antal oanvända kolumnmallar och inget sätt att ta bort eller hantera dem.</li><li>Lägg till och filtrera efter taggar.</li><li>Visa historiken för dataflödesjobb. (När begärandeperioden började, när den började, slutfördes o.s.v.)</li><li>Skicka om eller bearbeta dataflöden på nytt. (Från sidan Jobbhistorik)</li><li>Tillåt sena träffar. Du kan nu inkludera data som kommer efter att datafeedjobbet har slutfört databearbetningen inom den angivna rapporteringsfrekvensen.</li><li>När du väljer ett slutdatum för en datafeed inkluderas det slutdatum som du väljer som den sista dagen i dataflödet.<br/>Tidigare har slutdatumet uteslutits från dataflödet.</li><li>Det går nu att exportera med 15 minuters intervall, men den är inte tillgänglig som standard. För att det här alternativet ska bli tillgängligt i din miljö måste du först kontakta Adobe kundtjänst och begära att rapportsviten är konfigurerad för att stödja 15-minuters export.</li></ul><p>**Obs!** Med de här förbättringarna uppdateras även URL:er till datafeeds sidor i Adobe Analytics. Uppdatera befintliga bokmärken så att de pekar på de nya dataflödena senast 30 april 2026.</p>(Dokumentationslänk som ska följas.)</p> | 20 januari 2026 | 10 februari 2026 |
| **Sortera tabeller efter flera kolumner** | Nu kan du sortera data i en frihandstabell efter flera kolumner i Analysis Workspace, oavsett om det är dimensioner eller mätvärden.<p>När du sorterar data för flera kolumner sorteras data efter den prioritet som du tilldelar varje kolumn. Prioritetsnumrering visas bredvid sorteringsikonen.</p><p>(Dokumentationslänk att följa.)<!-- For more information, see "Filter and sort freeform tables". (need to move info to this article from "Include multiple dimension columns in a freeform table") --></p> | 28 januari 2026 | 18 februari 2026 |
| **Direktuppspelande medietjänster: Supportschemadata** | Nu kan du överföra schemalagda data från tidigare direktuppspelat mediematerial för att enklare och exaktare spåra tittandet.<p>Nedan följer exempel på live-innehåll som stöds vid schemalagd dataöverföring:</p><ul><li>FAST-plattformar (Free Ad Supported TV)</li><li>Lokala strömmar</li><li>Livesporter</li></ul><p>När du överför schemadata kan du spåra visningsdata för enskilda program som kördes under den tid du angav i överföringsfilen. Du kan till och med samla in visningsdata för specifika ämnen eller programsegment.</p><p>Dessa funktioner är tillgängliga oavsett hur du implementerade Streaming Media Collection.</p><p>Tidigare var det svårt att knyta en given session till specifika program när man analyserade direktinnehåll, och det var inte möjligt att knyta en given session till enskilda ämnen eller programsegment.</p><p>Mer information finns i [Överför schemadata för att spåra livematerial](https://experienceleague.adobe.com/en/docs/media-analytics/using/media-use-cases/track-schedule-data)</p> | 29 oktober 2025 | Första halvåret 2026<p>(Ursprungligen planerat att släppas den 29 oktober 2025)</p> |

## Korrigeringar i Adobe Analytics

**Activity Map**:
**Analysis Workspace**: AN-423389, AN-422636, AN-422482, AN-422027, AN-421134, AN-420187, AN-406 271, AN-406188, AN-405997, AN-405983, AN-405796, AN-405033, AN-404893, AN-4048 71, AN-404842, AN-404713, AN-404502, AN-404353, AN-404352, AN-404048, AN-40252 3, AN-396149, AN-390990, AN-390728, AN-390646, AN-383484, AN-376980, AN-371729 AN-347570
**Klassifikationer**: AN-423985, AN-423092, AN-423067, AN-422913, AN-422908, AN-422793, AN-422 785, AN-422745, AN-422705, AN-422422, AN-422126, AN-422098, AN-422077, AN-4220 58, AN-421999, AN-421698, AN-421351, AN-406583, AN-406295, AN-406123, AN-40605 2, AN-404743, AN-404372
**Datainsamling**: AN-422488
**Dataflöden och Data Warehouse**: AN-423186, AN-422789, AN-42239, AN-421552, AN-421393, AN-421339, AN-44 21231, AN-420149, AN-406345, AN-406217, AN-405073, AN-404822, AN-404774, AN-38 9691
**Sekretess**:
**Report Builder**: AN-422120, AN-421937, AN-406296, AN-402951, AN-399748
**Rapportering**:
**Schemalagda rapporter**: AN-423087, AN-422686
**Segmentjämförelse**:
**Annan**: AN-423401, AN-422819, AN-422775, AN-422626, AN-42238, AN-422160, AN-44 22071, AN-421687, AN-420045, AN-404891, AN-404608, AN-390912


## EOL-meddelanden (End-of-life) {#eol}

| EOL-produkt eller -funktion | Datum tillagt eller uppdaterat | Beskrivning |
| --- | --- | --- |
| **Förbättringar av direktuppspelningsbearbetning** | 14 januari 2026 | Adobe planerar att förbättra och ändra formateringen av LiveStream-nyttolaster. Dessa uppdateringar ger bättre överensstämmelse mellan LiveStream och andra Adobe Analytics-funktioner, som Analysis Workspace. Det finns en slutpunkt för förhandsgranskning som gör att du kan testa de planerade ändringarna. I [Versionsinformation för LiveStream] finns en fullständig lista över ändringar och information om slutpunkter för förhandsgranskning. Adobe planerar en hård övergång till det uppdaterade nyttolastformatet den 13 april 2026. |
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
