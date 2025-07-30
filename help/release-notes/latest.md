---
title: Aktuella versionsinformation för Adobe Analytics
description: Visa den aktuella versionsinformationen för Adobe Analytics
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 698b8f6cb9529f9742c2e3d9f1556b7913ebf0bb
workflow-type: tm+mt
source-wordcount: '647'
ht-degree: 1%

---

# Aktuell versionsinformation för Adobe Analytics (juli 2025)

**Senast uppdaterad**: 30 juli 2025

Versionsanteckningarna gäller från 7 juli till 15 augusti 2025. Adobe Analytics-releaser fungerar på en [kontinuerlig leveransmodell](releases.md), vilket ger en mer skalbar, fasad metod för driftsättning av funktioner. Därför uppdateras versionsinformationen flera gånger i månaden. Kontrollera dem regelbundet.

## Nya funktioner eller förbättringar {#features}

| Funktion | Beskrivning | [Startar](releases.md) | [Allmän tillgänglighet](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Livesream TNT-fält med algoritmer** | Livesream håller på att uppdateras för att säkerställa att tekniken fortsätter att vara modern och stabil. Som en del av den uppdateringen, om ditt TNT-fält har en algoritm, börjar vi att införliva TNT-fältet i Livesream-utdata. Detta inkluderar dock endast de element som tidigare stöddes: `campaignId`, `recipeId`, `trafficType`, `actionId` och `actionName`. Det övergripande TNT-schemat för Livestream ändras inte. |   | Juli 7,2025 |
| **Navigeringen till användargränssnittet för kundattribut har uppdaterats** | Användargränssnittet för kundattribut är nu tillgängligt direkt från programväljaren i Adobe Experience Cloud. Välj **[!UICONTROL Customer Attributes]** i listrutan (i stället för att gå till [!UICONTROL People] > [!UICONTROL Customer Attributes]) och uppdatera bokmärkena.  Uppdateringen innehåller vissa förbättringar av användargränssnittet. | 1 juli 2025 | 31 juli 2025 |

## Korrigeringar i Adobe Analytics

**Activity Map**: AN-360987
**Analysis Workspace**: AN-378094; AN-380979; AN-382908; AN-387652;
**Klassifikationer**: AN-382412; AN-383157; AN-384616; AN-384803; AN-385933; AN-387320; AN-387 351; AN-387832; AN-387833; AN-387839; AN-387915;
**Datainsamling**: AN-387661
**Dataflöden**: AN-375172; AN-384369; AN-387859; AN-387952; AN-388155;
**Plattform**: AN-382813; AN-386627; AN-386815
**Sekretess**: AN-384390
**Report Builder**: AN-388035
**Rapportering**: AN-380441
**Schemalagda rapporter**: AN-378280; AN-378331
**Segmentjämförelse**: AN-368766


## EOL-meddelanden (End-of-life) {#eol}

| EOL-produkt eller -funktion | Datum tillagt eller uppdaterat | Beskrivning |
| --- | --- | --- |
| **Äldre Report Builder** | 18 juni 2025 | Det gamla Report Builder-tillägget upphör i juni 2026. Alla användare bör börja uppgradera sina äldre arbetsböcker till [nya Report Builder](https://experienceleague.adobe.com/en/docs/analytics/analyze/report-builder/rb-overview). Nya Report Builder är tillgängligt för både Adobe Analytics- och Customer Journey Analytics-kunder. Den har [nästan funktionsparitet](https://experienceleague.adobe.com/en/docs/analytics/analyze/report-builder/convert-workbooks#unsupported) plus många nya, praktiska funktioner och gränssnittsförbättringar. För att underlätta uppgraderingsprocessen innehåller nya Report Builder en smidig arbetsbokskonverteringsfunktion. Nya Report Builder finns bara som tillägg via Microsoft Store. Många organisationer måste ha en intern process för godkännande innan tillägget kan göras tillgängligt för användarna. Ge lite tid åt den här processen och börja arbeta med organisationen nu för att se till att du hinner uppgradera dina arbetsböcker innan EOL-datumet. |
| **Åtkomst via äldre domäner eller via äldre enkel inloggning** | 10 april 2025 | Adobe planerar att uppdatera hur användare använder Adobe Analytics för att förbättra säkerheten och effektivisera inloggningen. Som en del av denna insats kommer åtkomst via äldre domäner eller via äldre enkel inloggning (SSO), inklusive `my.omniture.com`, att upphöra permanent den **2 januari 2026**. Efter detta datum kommer äldre inloggningsuppgifter och äldre enkel inloggning inte längre att fungera. Alla användare måste logga in via `experience.adobe.com` med sina Adobe Experience Cloud ID:n. Om du behöver hjälp med ditt Experience Cloud ID kontaktar du Adobe Analytics-administratören eller [Adobe kundtjänst](https://helpx.adobe.com/contact.html). |
| **Adobe Analytics API (version 1.4)** | 17 juli 2024 | Den **12 augusti 2026** kommer följande API-tjänster för Analytics Legacy att ha nått slutet på sin livstid och stängas, och aktuella integreringar som byggts med dessa tjänster kommer att sluta fungera:<ul><li>Adobe Analytics API (version 1.4)</li><li>Adobe Analytics WSSE-autentisering</li></ul><p>Integreringar som använder Adobe Analytics API (version 1.4) måste migrera till [Adobe Analytics 2.0 API](https://developer.adobe.com/analytics-apis/docs/2.0/) medan WSSE-integreringar måste migrera till ett OAuth-baserat autentiseringsprotokoll i [Adobe Developer Console](https://developer.adobe.com/console).</p><p>Se [Vanliga frågor om Adobe Analytics 1.4 API EOL ](/help/admin/c-admin-api/c-admin-14-api-eol.md) för svar på vanliga frågor och ytterligare vägledning.</p> |


## AppMeasurement

De senaste uppdateringarna för AppMeasurement finns i [AppMeasurement versionsinformation](https://github.com/adobe/appmeasurement/releases).


## Relaterade resurser

* [Information om föregående version för 2025](/help/release-notes/2025.md)
* [Versionsinformation för Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html)
* [Versionsinformation för direktuppspelad mediainsamling](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html)
* Den senaste releaseuppdateringen för [Adobe Experience Cloud-produkter](https://business.adobe.com/products/adobe-experience-cloud-products.html)
