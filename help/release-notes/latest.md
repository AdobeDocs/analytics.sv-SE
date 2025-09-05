---
title: Aktuella versionsinformation för Adobe Analytics
description: Visa den aktuella versionsinformationen för Adobe Analytics
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: fcc165536d77284e002cb2ba6b7856be1fdb3e14
workflow-type: tm+mt
source-wordcount: '1145'
ht-degree: 0%

---

# Aktuell versionsinformation för Adobe Analytics (augusti 2025-utgåvan)

**Senast uppdaterad**: 13 augusti 2025

Versionsanteckningarna gäller från den 13 augusti till den 16 september 2025. Adobe Analytics-releaser fungerar på en [kontinuerlig leveransmodell](releases.md), vilket ger en mer skalbar, fasad metod för driftsättning av funktioner. Därför uppdateras versionsinformationen flera gånger i månaden. Kontrollera dem regelbundet.

## Nya funktioner eller förbättringar {#features}

| Funktion | Beskrivning | [Startar](releases.md) | [Allmän tillgänglighet](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Analysera AI-trafik med ett nytt dimensionsobjekt för referenstyp** | I oktober kommer ett nytt dimensionsobjekt av typen Referer att finnas tillgängligt för att analysera trafik som kommer från AI-verktyg. <p>Detta nya sidobjekt, Conversational AI tools, grupperar referensdomäner för viktiga AI-verktyg så att du kan se trender för hela gruppen. Den inledande listan över referensdomäner i den nya kategorin omfattar (men är inte begränsad till):</p><ul><li>chatgpt.com</li><li>claude.ai</li><li>m365.cloud.microsoft</li><li>grok.com</li><li>gemini.google.com</li><li>perplexity.ai</li></ul><p>Det nya dimensionsobjektet kommer att vara tillgängligt i alla Adobe Analytics-relaterade verktyg som Analysis Workspace, Report Builder, Data Warehouse, Data Feeds och så vidare.</p><p>Tänk på följande när du använder den här nya dimensionsobjektet:</p><ul><li>Det är inte alltid möjligt att skilja på hänvisartrafik som kommer från resultat i&quot;AI-läge&quot; i en sökmotor jämfört med resultat från klickningar från traditionella sökresultat.</li><li>Det nya AI-verktygen för konversationer fokuserar på större leverantörer med störst trafik. En ny trend visar ett ökande antal personifieringswebbplatser med domäner som liknar de vanligaste leverantörerna av AI-verktyg. Detta beror troligen på den enkelhet med vilken individer eller grupper kan skapa egna AI-verktyg och lägga upp dem på internet. Eftersom detta är ett område som utvecklas snabbt bör du kontakta Adobe supportteam om du upptäcker att en populär webbplats inte ingår.</li><li>Refererartypsdimensionen, inklusive det nya dimensionsobjektet för konversationsbaserade AI-verktyg, är bara tillgänglig för data som bearbetas av Adobe Analytics. </li></ul><p>(Dokumentationslänk som ska följas.)</p> |   | Oktober 2025 |
| **Projekt som hämtas som PDF-filer hämtas till din arbetsstation** | När du laddar ned ett projekt som PDF laddas PDF ned till nedladdningsmappen på din arbetsstation. <p>Tidigare startades PDF på en ny webbläsarflik med en unik URL när du laddade ned ett projekt som PDF.</p><p>Mer information finns i [Hämta projekt och data](/help/analyze/analysis-workspace/curate-share/download-send.md)</p> |  | 25 augusti 2025 |
| **Borttagna projekt är omedelbart inte tillgängliga av URL och tas bort från schemalagda leveranser** | Projekt som tas bort raderas omedelbart från schemalagda leveranser och är inte längre tillgängliga via sin URL.<p>Tidigare ingick projekt i schemalagda leveranser och de kunde nås med sin URL i 60 dagar efter att de tagits bort.</p><p>Mer information om hur du tar bort projekt finns i [Projektöversikt](/help/analyze/analysis-workspace/build-workspace-project/freeform-overview.md).</p> | | Slutet av augusti 2025 |
| **Direktuppspelande medietjänster: Uppdaterade XDM-fält för insamling av strömmande mediedata i Adobe Experience Platform** | När du samlar in strömmande mediedata i Adobe Experience Platform bör XDM-fältsökvägarna som visas under rubriken&quot;XDM-fältsökväg&quot; i dokumentationen för direktuppspelningsmediaparametrarna inte längre användas. I stället måste kunder som implementerat Analytics-källkopplingen för att samla in strömmande mediedata till plattformen före 9 maj 2025 migrera sina befintliga konfigurationer till MediaReporting-fältsökvägarna, vilket visas under rubriken&quot;Rapportera XDM-fältsökväg&quot; i dokumentationen för Streaming Media-parametrar.<p> De här fältsökvägarna finns på följande sidor och markeras som &quot;Undertryckta&quot;: [Parametrar för ljud- och videoinnehåll](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/variables/audio-video-parameters), [Lägg till parametrar](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/variables/ad-parameters), [Kapitelparametrar](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/variables/chapter-parameters), [Parametrar för spelartillstånd](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/variables/player-state-parameters) och [Kvalitetsparametrar](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/variables/quality-parameters). (Ingen åtgärd krävs för kunder som implementerar källkopplingen för Analytics efter 9 maj 2025 och som redan använder enbart XDM-sökvägar för mediaReporting.)</p><p>Inmatningen av data i de borttagna XDM-fältsökvägarna fortsätter till slutet av oktober 2025. Efter det kommer inaktuella fältsökvägar att tas bort helt och inte längre visas i användargränssnittet för Adobe Experience Platform Schema, och data skickas endast med fältsökvägarna för mediaReporting.</p><p>Mer information finns i [Migrera en Analytics Source Connector-implementering till uppdaterade XDM-direktuppspelningsmediefält](https://experienceleague.adobe.com/en/docs/media-analytics/using/media-use-cases/xdm-updates/updated-xdm-fields).</p><p>Kontakta Adobe Consulting-tjänsterna eller kontoteamet för att få migreringssupport. </p> |  | Oktober 2025 |

## Korrigeringar i Adobe Analytics

**Activity Map**: AN-389205; AN-384186
**Analysis Workspace**: AN-390102; AN-389066; AN-38841; AN-388687; AN-388478; AN-387089; AN-387 044; AN-384560; AN-379213; AN-351639
**Klassificeringar**: AN-390442; AN-390385; AN-389953; AN-389703; AN-389321; AN-389116; AN-388 833; AN-388717; AN-387987; AN-383329
**Datainsamling**: AN-389320
**Dataflöden och Data Warehouse**: AN-389702; AN-388136; AN-387779; AN-384369; AN-383075; AN-380307
**Sekretess**:
**Report Builder**: AN-389336; AN-382775
**Rapportering**: AN-390398
**Schemalagda rapporter**:
**Segmentjämförelse**:
**Annan**: AN-388180; AN-383164; AN-366532


## EOL-meddelanden (End-of-life) {#eol}

| EOL-produkt eller -funktion | Datum tillagt eller uppdaterat | Beskrivning |
| --- | --- | --- |
| **Äldre Report Builder** | 18 juni 2025 | Det gamla Report Builder-tillägget upphör i juni 2026. Alla användare bör börja uppgradera sina äldre arbetsböcker till [nya Report Builder](/help/analyze/report-builder/rb-overview.md). Nya Report Builder är tillgängligt för både Adobe Analytics- och Customer Journey Analytics-kunder. Den har [nästan funktionsparitet](/help/analyze/report-builder/convert-workbooks.md#unsupported) plus många nya, praktiska funktioner och gränssnittsförbättringar. För att underlätta uppgraderingsprocessen innehåller nya Report Builder en smidig arbetsbokskonverteringsfunktion. Nya Report Builder finns bara som tillägg via Microsoft Store. Många organisationer måste ha en intern process för godkännande innan tillägget kan göras tillgängligt för användarna. Ge lite tid åt den här processen och börja arbeta med organisationen nu för att se till att du hinner uppgradera dina arbetsböcker innan EOL-datumet. |
| **Åtkomst via äldre domäner eller via äldre enkel inloggning** | 10 april 2025 | Adobe planerar att uppdatera hur användare använder Adobe Analytics för att förbättra säkerheten och effektivisera inloggningen. Som en del av denna insats kommer åtkomst via äldre domäner eller via äldre enkel inloggning (SSO), inklusive `my.omniture.com`, att upphöra permanent den **2 januari 2026**. Efter detta datum kommer äldre inloggningsuppgifter och äldre enkel inloggning inte längre att fungera. Alla användare måste logga in via `experience.adobe.com` med sina Adobe Experience Cloud ID:n. Om du behöver hjälp med ditt Experience Cloud ID kontaktar du Adobe Analytics-administratören eller [Adobe kundtjänst](https://helpx.adobe.com/contact.html). |
| **Adobe Analytics API (version 1.4)** | 17 juli 2024 | Den **12 augusti 2026** kommer följande API-tjänster för Analytics Legacy att ha nått slutet på sin livstid och stängas, och aktuella integreringar som byggts med dessa tjänster kommer att sluta fungera:<ul><li>Adobe Analytics API (version 1.4)</li><li>Adobe Analytics WSSE-autentisering</li></ul><p>Integreringar som använder Adobe Analytics API (version 1.4) måste migrera till [Adobe Analytics 2.0 API](https://developer.adobe.com/analytics-apis/docs/2.0/) medan WSSE-integreringar måste migrera till ett OAuth-baserat autentiseringsprotokoll i [Adobe Developer Console](https://developer.adobe.com/console).</p><p>Se [Vanliga frågor om Adobe Analytics 1.4 API EOL ](/help/admin/c-admin-api/c-admin-14-api-eol.md) för svar på vanliga frågor och ytterligare vägledning.</p> |


## AppMeasurement

De senaste uppdateringarna för AppMeasurement finns i [AppMeasurement versionsinformation](https://github.com/adobe/appmeasurement/releases).


## Relaterade resurser

* [Information om föregående version för 2025](/help/release-notes/2025.md)
* [Versionsinformation för Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html)
* [Versionsinformation för direktuppspelande medietjänster](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html)
* Den senaste releaseuppdateringen för [Adobe Experience Cloud-produkter](https://business.adobe.com/products/adobe-experience-cloud-products.html)
