---
title: Aktuella versionsinformation för Adobe Analytics
description: Visa den aktuella versionsinformationen för Adobe Analytics
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 89cc33528d3907d955a543f3e43774a1065e149a
workflow-type: tm+mt
source-wordcount: '1468'
ht-degree: 0%

---

# Aktuell versionsinformation för Adobe Analytics (mars 2026)

**Senast uppdaterad**: 11 mars 2026

Versionsinformationen gäller mars 2026-utgåvan. Adobe Analytics-releaser fungerar på en [kontinuerlig leveransmodell](releases.md), vilket ger en mer skalbar, fasad metod för driftsättning av funktioner. Versionsinformationen uppdateras därför flera gånger i månaden. Kontrollera dem regelbundet.

## Nya funktioner eller förbättringar {#features}

| Funktion och beskrivning | [Startar](releases.md) | [Allmän tillgänglighet](releases.md) |
| ----------- | ---------- | ---- |
| **Panelindelning**<br/> Listrutan för en panel erbjuder nu ytterligare funktioner för att [dela upp](/help/analyze/analysis-workspace/c-panels/panels.md#break-down-a-panel) (i stället för segmentering) en panel baserat på en dimension. | 31 mars 2026 | 31 mars 2026 |
| **Sortera tabeller efter flera kolumner** <br/>Nu kan du sortera data i en frihandstabell efter flera kolumner i Analysis Workspace, oavsett om det är dimensioner eller mätvärden.<p>När du sorterar data för flera kolumner sorteras data efter den prioritet som du tilldelar varje kolumn. Prioritetsnumrering visas bredvid sorteringsikonen.</p><p>Mer information finns i [Filtrera och sortera tabeller på frihand](/help/analyze/analysis-workspace/visualizations/freeform-table/filter-and-sort.md).</p> | 28 januari 2026 | 4 mars 2026 <p>(ursprungligen planerat till den 18 februari 2026)</p> |
| **Report Builder: Administratörssynlighet för alla schemalagda arbetsböcker**<br/> Report Builder Excel-tillägget innehåller ett nytt filteralternativ som gör att administratörer kan visa alla schemalagda arbetsböcker för en viss organisation, oavsett vem som har schemalagt dem. Det här filteralternativet är bara tillgängligt för Analytics-administratörer. Den är tillgänglig både på fliken Arbetsbok och på fliken Äldre när du visar schemalagda arbetsböcker.<p>Möjligheten att visa alla schemalagda arbetsböcker är särskilt användbar vid migrering av arbetsböcker mellan distribuerade team, eftersom administratörer enkelt kan hitta alla äldre arbetsböcker innan de migreras.</p><p>Tidigare kunde administratörer bara se de arbetsböcker som de har schemalagt, inte de som har schemalagts av andra användare.</p><p>Mer information finns i [Hanterade schemalagda arbetsböcker](/help/analyze/report-builder/manage-schedules-reportbuilder.md).</p> | | 10 mars 2026 |
| **Uppdatera till funktionen Approximate Count Distinct**<br/> Den HLL-sannolikhetsalgoritm som används i funktionen Approximate Count Distinct uppdateras snart. Resultatet för tal som använder den här funktionen kan ändras något från historiska tal enligt följande:</p><ul><li>När mycket små mängder unika värden räknas kommer resultatet att förbättras så att exakta räkningar används i stället för uppskattningar.</li><li>När du räknar med något större kommer antalet uppskattningar att behålla samma noggrannhet som före den här uppdateringen (uppskattningarna är exakta inom 5 procent av det exakta talet, 95 procent av tiden).</li></ul><p>Mer information om funktionen Approximate Count Distinct finns i [Distinkt antal](/help/components/calculated-metrics/cm-reference/cm-adv-functions.md#approximate-count-distinct) i [Avancerade funktioner](/help/components/calculated-metrics/cm-reference/cm-adv-functions.md)</p> | | 10 mars 2026 |
| **Självstudiekurs (tips) för Analysis Workspace**<br/> Det finns nu en ny praktisk självstudiekurs som kan vägleda nya användare genom grunderna i att använda paneler, visualiseringar och komponenter i Analysis Workspace. <p>Mer information finns på [Adobe Analytics landningssida](/help/analyze/landing.md).</p> | | 18 mars 2026 |
| **Förbättringar av utrullningsvisualisering**<br/> Utfallsvisualiseringen innehåller följande förbättringar:<ul><li>En förbättrad dra-och-släpp-funktion.<br/>Håll muspekaren över en kontaktyta och dra den till en ny plats i visualiseringen.<br/>Tidigare var du tvungen att klicka på redigeringsikonen på kontaktytan innan du drog den.</li><li>Tydligare språk när du kombinerar kontaktytor med dra-och-släpp.<br/>När du drar en kontaktyta till en annan kontaktyta visas texten Kombinera, vilket anger att de två kontaktytorna kombineras.<br/>Tidigare visades texten&quot;Lägg till&quot;, oavsett om kontaktytan flyttades till en ny plats inom visualiseringen eller kombinerades med en annan kontaktyta.</li><li>Omarbetade verktygstips.<br/>De verktygstips som visas när du hovrar över en kontaktyta är mer intuitiva och lättlästa.</li><li>En mer identifierbar snabbmeny.<br/>Verktygstips innehåller ett nytt&quot;Klicka för att analysera&quot;-alternativ som ger smidig åtkomst till snabbmenyn för kontaktytan.<br/>Tidigare var snabbmenyn bara tillgänglig när du högerklickade på en kontaktyta.</li></ul><p>Mer information finns i [Konfigurera en utfallsvisualisering](/help/analyze/analysis-workspace/visualizations/fallout/configuring-fallout.md).</p> | | 25 mars 2026 |
| **Använd en uppdelning på en panel**<br/> Du kan nu använda en uppdelning på en panel. När du använder en uppdelning på panelnivå används den indelade uppdelningen på alla kolumner i alla frihandstabeller på panelen. | Mars 2026 | Maj 2026 |
| **Direktuppspelande medietjänster: Stöd för schemadata** <br/>Du kan nu överföra schemalagda data från tidigare direktuppspelningsmediainnehåll för att enklare och mer korrekt spåra tittarskap.<p>Nedan följer exempel på live-innehåll som stöds vid schemalagd dataöverföring:</p><ul><li>FAST-plattformar (Free Ad Supported TV)</li><li>Lokala strömmar</li><li>Livesporter</li></ul><p>När du överför schemadata kan du spåra visningsdata för enskilda program som kördes under den tid du angav i överföringsfilen. Du kan till och med samla in visningsdata för specifika ämnen eller programsegment.</p><p>Dessa funktioner är tillgängliga oavsett hur du implementerade Streaming Media Collection.</p><p>Tidigare var det svårt att knyta en given session till specifika program när man analyserade direktinnehåll, och det var inte möjligt att knyta en given session till enskilda ämnen eller programsegment.</p><p>Mer information finns i [Överför schemadata för att spåra livematerial](https://experienceleague.adobe.com/en/docs/media-analytics/using/media-use-cases/track-schedule-data)</p> | 29 oktober 2025 | Första halvåret 2026<p>(Ursprungligen planerat att släppas den 29 oktober 2025)</p> |

## Korrigeringar i Adobe Analytics

**Activity Map**:
**Analysis Workspace**: AN-440336, AN-440216, AN-440121, AN-438445, AN-438216, AN-437856, AN-437 776, AN-437765, AN-437365, AN-432793, AN-432094, AN-431557, AN-431200, AN-4296 21, AN-429424, AN-427973, AN-426089, AN-425883, AN-424359
**Klassificeringar**: AN-440143, AN-439891, AN-439844, AN-438994, AN-438057, AN-438052, AN-437 986, AN-437896, AN-435387, AN-435335, AN-435150, AN-433050, AN-432062, AN-4318 73, AN-429642
**Dataflöden och Data Warehouse**: AN-439441, AN-437086, AN-433064, AN-432121, AN-431755, AN-428239, AN-4 27049, AN-425036, AN-424972, AN-423509, AN-335417, AN-283958, AN-256948
**Migrering**:
**Exporterar**: AN-432030
**Report Builder**: AN-437895, AN-437083, AN-434288, AN-434209, AN-433224, AN-430622
**Rapportering**: AN-434545, AN-431206, AN-428043
**Schemalagda rapporter**:
**Segmentering**:
**Annan**: AN-440076, AN-434783, AN-434542, AN-434233, AN-43368, AN-432138, AN-4 31322, AN-431012, AN-429067, AN-423285


## EOL-meddelanden (End-of-life) {#eol}

| EOL-produkt eller -funktion | Datum tillagt eller uppdaterat | Beskrivning |
| --- | --- | --- |
| **Förbättringar av direktuppspelningsbearbetning** | 14 januari 2026 | Adobe planerar att förbättra och ändra formateringen av LiveStream-nyttolaster. Dessa uppdateringar ger bättre överensstämmelse mellan LiveStream och andra Adobe Analytics-funktioner, som Analysis Workspace. Det finns en slutpunkt för förhandsgranskning som gör att du kan testa de planerade ändringarna. I [Versionsinformation för LiveStream](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/livestream/release-notes/) finns en fullständig lista över ändringar och information om slutpunkter för förhandsgranskning. Adobe planerar en hård övergång till det uppdaterade nyttolastformatet den 13 april 2026. |
| **Borttagning av TLS 1.2-chiffersviter** | 11 februari 2026 | Meddelande till administratörer: Adobe planerar att ta bort stödet för följande TLS 1.2-chiffersviter från Adobe datainsamlingsservrar den 27 maj 2026.<ul><li>`TLS_ECDHE_ECDSA_WITH_AES_128_CBC_SHA`</li><li>`TLS_ECDHE_ECDSA_WITH_AES_256_CBC_SHA`</li><li>`TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA`</li><li>`TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA`</li><li>`TLS_RSA_WITH_AES_128_CBC_SHA`</li><li>`TLS_RSA_WITH_AES_256_CBC_SHA`</li><li>`TLS_RSA_WITH_AES_128_GCM_SHA256`</li><li>`TLS_RSA_WITH_AES_256_GCM_SHA384`</li></ul><p>Ingen kundåtgärd krävs för de flesta implementeringar. Den här ändringen påverkar i första hand analysdata som skickas från äldre inbyggda program som använder inaktuella TLS-bibliotek och ett fåtal webbbesökare i inaktuella webbläsare eller operativsystem. Genom att ta bort stödet för dessa chiffreringssviter förbättras säkerheten och Adobe anpassas till moderna krypteringsstandarder. Färre än 0,1 % av datainsamlingstrafiken är för närvarande beroende av dessa chiffersviter.</p> |
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
