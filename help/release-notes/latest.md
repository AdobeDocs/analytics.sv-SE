---
title: Aktuella versionsinformation för Adobe Analytics
description: Visa den aktuella versionsinformationen för Adobe Analytics
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 3825f46c204ec2725babb1ac10b06488bdb746fa
workflow-type: tm+mt
source-wordcount: '1318'
ht-degree: 0%

---

# Aktuell versionsinformation för Adobe Analytics (oktober 2025-utgåvan)

**Senast uppdaterad**: 14 oktober 2025

Versionsinformationen gäller från oktober till början av november 2025. Adobe Analytics-releaser fungerar på en [kontinuerlig leveransmodell](releases.md), vilket ger en mer skalbar, fasad metod för driftsättning av funktioner. Därför uppdateras versionsinformationen flera gånger i månaden. Kontrollera dem regelbundet.

## Nya funktioner eller förbättringar {#features}

| Funktion | Beskrivning | [Startar](releases.md) | [Allmän tillgänglighet](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Filtervillkor ingår i radinvisualiseringar och miniatyrbilder** | Alla sökfiltervillkor som du tillämpar på ett frihandsfilter finns nu alltid med i miniatyrbilder. Dessutom kan du inkludera sökfiltervillkor i all visning av anslutna rader.<p>Du kan konfigurera radvisualiseringar så att de omfattar sökfiltervillkor genom att välja miniatyrdiagram i kolumnrubriken för mätvärden i den anslutna tabellen.</p><p>Tidigare ingick inte sökfiltervillkor i miniatyrdiagram eller anslutna linjevisualiseringar.</p><p>Mer information finns i [Visa trenddata för en frihandstabell](/help/analyze/analysis-workspace/visualizations/freeform-table/freeform-table-trended-data.md).</p> | | 15 oktober 2025 |
| **Analysera AI-trafik med ett nytt dimensionsobjekt för referenstyp** | Ett nytt dimensionsobjekt av typen Referent kommer att vara tillgängligt för att analysera trafik som kommer från AI-verktyg. <p>Detta nya sidobjekt, Conversational AI tools, grupperar referensdomäner för viktiga AI-verktyg så att du kan se trender för hela gruppen. Den inledande listan över referensdomäner i den nya kategorin omfattar (men är inte begränsad till):</p><ul><li>chatgpt.com</li><li>claude.ai</li><li>m365.cloud.microsoft</li><li>grok.com</li><li>gemini.google.com</li><li>perplexity.ai</li></ul><p>Det nya dimensionsobjektet kommer att vara tillgängligt i alla Adobe Analytics-relaterade verktyg som Analysis Workspace, Report Builder, Data Warehouse, Data Feeds och så vidare.</p><p>Tänk på följande när du använder den här nya dimensionsobjektet:</p><ul><li>Det är inte alltid möjligt att skilja på hänvisartrafik som kommer från resultat i&quot;AI-läge&quot; i en sökmotor jämfört med resultat från klickningar från traditionella sökresultat.</li><li>Det nya AI-verktygen för konversationer fokuserar på större leverantörer med störst trafik. En ny trend visar ett ökande antal personifieringswebbplatser med domäner som liknar de vanligaste leverantörerna av AI-verktyg. Detta beror troligen på den enkelhet med vilken individer eller grupper kan skapa egna AI-verktyg och lägga upp dem på internet. Eftersom detta är ett område som utvecklas snabbt bör du kontakta Adobe supportteam om du upptäcker att en populär webbplats inte ingår.</li><li>Refererartypsdimensionen, inklusive det nya dimensionsobjektet för konversationsbaserade AI-verktyg, är bara tillgänglig för data som bearbetas av Adobe Analytics. </li></ul><p>Mer information om det här nya dimensionsobjektet finns i [Refererartyp](/help/components/dimensions/referrer-type.md), som innehåller dimensionsobjektet [Konversella AI-verktyg](/help/components/dimensions/referrer-type.md#conversational-ai-tools). Dimensionsobjektet innehåller en fördefinierad lista med AI-chattbotar.</p><p>Allmän information om hur du analyserar AI-trafik med Adobe Analytics finns i [Analysera trafik från konversationsbaserade AI-verktyg](/help/technotes/ai-traffic.md).</p> |   | 15 oktober 2025 |
| **Direktuppspelande medietjänster: Supportschemadata** | Nu kan du överföra schemalagda data från tidigare direktuppspelat mediematerial för att enklare och exaktare spåra tittandet.<p>Nedan följer exempel på live-innehåll som stöds vid schemalagd dataöverföring:</p><ul><li>FAST-plattformar (Free Ad Supported TV)</li><li>Lokala strömmar</li><li>Livesporter</li></ul><p>När du överför schemadata kan du spåra visningsdata för enskilda program som kördes under den tid du angav i överföringsfilen. Du kan till och med samla in visningsdata för specifika ämnen eller programsegment.</p><p>Dessa funktioner är tillgängliga oavsett hur du implementerade Streaming Media Collection.</p><p>Tidigare var det svårt att knyta en given session till specifika program när man analyserade direktinnehåll, och det var inte möjligt att knyta en given session till enskilda ämnen eller programsegment.</p><p>Mer information finns i [Överför schemadata för att spåra livematerial](https://experienceleague.adobe.com/en/docs/media-analytics/using/media-use-cases/track-schedule-data)</p> | 29 oktober 2025 | Första halvåret 2026<p>(Ursprungligen planerat att släppas den 29 oktober 2025)</p> |
| **Direktuppspelande medietjänster: Uppdaterade XDM-fält för insamling av strömmande mediedata i Adobe Experience Platform** | När du samlar in strömmande mediedata i Adobe Experience Platform bör XDM-fältsökvägarna som visas under rubriken&quot;XDM-fältsökväg&quot; i dokumentationen för direktuppspelningsmediaparametrarna inte längre användas. I stället måste kunder som implementerat Analytics-källkopplingen för att samla in strömmande mediedata till plattformen före 9 maj 2025 migrera sina befintliga konfigurationer till MediaReporting-fältsökvägarna, vilket visas under rubriken&quot;Rapportera XDM-fältsökväg&quot; i dokumentationen för Streaming Media-parametrar.<p> De här fältsökvägarna finns på följande sidor och markeras som &quot;Undertryckta&quot;: [Parametrar för ljud- och videoinnehåll](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/variables/audio-video-parameters), [Lägg till parametrar](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/variables/ad-parameters), [Kapitelparametrar](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/variables/chapter-parameters), [Parametrar för spelartillstånd](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/variables/player-state-parameters) och [Kvalitetsparametrar](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/variables/quality-parameters). (Ingen åtgärd krävs för kunder som implementerar källkopplingen för Analytics efter 9 maj 2025 och som redan använder enbart XDM-sökvägar för mediaReporting.)</p><p>Inmatningen av data i de borttagna XDM-fältsökvägarna fortsätter till slutet av oktober 2025. Efter det kommer inaktuella fältsökvägar att tas bort helt och inte längre visas i användargränssnittet för Adobe Experience Platform Schema, och data skickas endast med fältsökvägarna för mediaReporting.</p><p>Mer information finns i [Migrera en Analytics Source Connector-implementering till uppdaterade XDM-direktuppspelningsmediefält](https://experienceleague.adobe.com/en/docs/media-analytics/using/media-use-cases/xdm-updates/updated-xdm-fields).</p><p>Kontakta Adobe Consulting-tjänsterna eller kontoteamet för att få migreringssupport. </p> |  | Oktober 2025 |
| **Skapa Adobe Analytics 2.0 API Report Suite** | Skapa rapportsviter i Adobe Analytics med 2.0 API:er. Den nya POST-metoden ersätter 1.4-rapportsvitens API-generering som förberedelse för den kommande borttagningen av 1.4-API:erna. | | 25 oktober 2025 |

## Korrigeringar i Adobe Analytics

**Activity Map**:
**Analysis Workspace**: AN-399209, AN-397146, AN-394992, AN-390795
**Klassificeringar**: AN-400583, AN-399205, AN-398580, AN-398257, AN-395921, AN-394973
**Datainsamling**:
**Dataflöden och Data Warehouse**: AN-400938, AN-399075, AN-398924, AN-398573, AN-396574, AN-393946
**Sekretess**:
**Report Builder**: AN-401127, AN-400618, AN-392971, AN-391692
**Rapportering**:
**Schemalagda rapporter**:
**Segmentjämförelse**:
**Annan**: AN-396084


## EOL-meddelanden (End-of-life) {#eol}

| EOL-produkt eller -funktion | Datum tillagt eller uppdaterat | Beskrivning |
| --- | --- | --- |
| **Äldre Report Builder** | 18 juni 2025 | Det gamla Report Builder-tillägget upphör i juni 2026. Alla användare bör börja uppgradera sina äldre arbetsböcker till [nya Report Builder](/help/analyze/report-builder/rb-overview.md). Nya Report Builder är tillgängligt för både Adobe Analytics- och Customer Journey Analytics-kunder. Den har [nästan funktionsparitet](/help/analyze/report-builder/convert-workbooks.md#unsupported) plus många nya, praktiska funktioner och gränssnittsförbättringar. För att underlätta uppgraderingsprocessen innehåller nya Report Builder en smidig arbetsbokskonverteringsfunktion. Nya Report Builder finns bara som tillägg via Microsoft Store. Många organisationer måste ha en intern process för godkännande innan tillägget kan göras tillgängligt för användarna. Ge lite tid åt den här processen och börja arbeta med organisationen nu för att se till att du hinner uppgradera dina arbetsböcker innan EOL-datumet. |
| **Åtkomst via äldre domäner eller via äldre enkel inloggning** | 10 april 2025 | Adobe planerar att uppdatera hur användare använder Adobe Analytics för att förbättra säkerheten och effektivisera inloggningen. Som en del av denna insats kommer åtkomst via äldre domäner eller via äldre enkel inloggning (SSO), inklusive `my.omniture.com`, att upphöra permanent den **2 januari 2026**. Efter detta datum kommer äldre inloggningsuppgifter och äldre enkel inloggning inte längre att fungera. Alla användare måste logga in via `experience.adobe.com` med sina Adobe Experience Cloud ID:n. Om du behöver hjälp med ditt Experience Cloud ID kontaktar du Adobe Analytics-administratören eller [Adobe kundtjänst](https://helpx.adobe.com/contact.html). |
| **Adobe Analytics API (version 1.4)** | 17 juli 2024 | Den **12 augusti 2026** kommer följande API-tjänster för Analytics Legacy att ha nått slutet på sin livstid och stängas, och aktuella integreringar som byggts med dessa tjänster kommer att sluta fungera:<ul><li>Adobe Analytics API (version 1.4)</li><li>Adobe Analytics WSSE-autentisering</li></ul><p>Integreringar som använder Adobe Analytics API (version 1.4) måste migrera till [Adobe Analytics 2.0 API](https://developer.adobe.com/analytics-apis/docs/2.0/) medan WSSE-integreringar måste migrera till ett OAuth-baserat autentiseringsprotokoll i [Adobe Developer Console](https://developer.adobe.com/console).</p><p>Se [Vanliga frågor om Adobe Analytics 1.4 API EOL ](https://developer.adobe.com/analytics-apis/docs/1.4/guides/eol/) för svar på vanliga frågor och ytterligare vägledning.</p> |


## AppMeasurement

De senaste uppdateringarna för AppMeasurement finns i [AppMeasurement versionsinformation](https://github.com/adobe/appmeasurement/releases).


## Relaterade resurser

* [Information om föregående version för 2025](/help/release-notes/2025.md)
* [Versionsinformation för Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html)
* [Versionsinformation för direktuppspelande medietjänster](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html)
* Den senaste releaseuppdateringen för [Adobe Experience Cloud-produkter](https://business.adobe.com/products/adobe-experience-cloud-products.html)
