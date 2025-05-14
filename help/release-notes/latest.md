---
title: Aktuella versionsinformation för Adobe Analytics
description: Visa den aktuella versionsinformationen för Adobe Analytics
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 9c6da2c1ed5bc2c016da16a5bb821f0064e1ae4f
workflow-type: tm+mt
source-wordcount: '689'
ht-degree: 1%

---

# Aktuell versionsinformation för Adobe Analytics (majversionen 2025)

**Senast uppdaterad**: 14 maj 2025

Versionsinformationen gäller från den 18 april till den 18 juni 2025. Adobe Analytics-releaser fungerar på en [kontinuerlig leveransmodell](releases.md), vilket ger en mer skalbar, fasad metod för driftsättning av funktioner. Därför uppdateras versionsinformationen flera gånger i månaden. Kontrollera dem regelbundet.

## Nya funktioner eller förbättringar {#features}

| Funktion | Beskrivning | [Startar](releases.md) | [Allmän tillgänglighet](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Analysis Workspace vänstra panel öppnas inte längre och stängs vid hovring** | Den vänstra panelen i Analysis Workspace används för att lägga till saker som komponenter, paneler och visualiseringar i ditt projekt. Alternativet att tillfälligt öppna den vänstra panelen genom att hålla markören över en av ikonerna längst till vänster är inte längre tillgängligt. Istället klickar du på någon av de här ikonerna för att hålla panelen öppen. Klicka sedan på samma ikon för att stänga den. |  | 29 maj 2025 |


## Korrigeringar i Adobe Analytics

**Varningar**: AN-378351
**Analysis Workspace**: AN-363521; AN-367366; AN-373575; AN-374238; AN-374295; AN-374382; AN-376 938; AN-377176; AN-377467; AN-377942
**Resursöverföring**: AN-373381
**Klassifikationer**: AN-373166; AN-373479; AN-376074; AN-377337; AN-377505
**Komponenter**: AN-314468
**Dataflöden**: AN-370241; AN-375267; AN-376940
**Datakällor**: AN-375259
**Data Warehouse**: AN-370415; AN-372090;
**Plattform**: AN-365681; AN-372306; AN-372616;
**Realtidsrapportering**: AN-365681
**Report Builder**: AN-371395
**Segmentering**: AN-373576; AN-375858
**Virtuella rapportsviter**: AN-377948; AN-377952
**Vista-regler**: AN-373292

## Viktiga meddelanden för Adobe Analytics-administratörer {#admin}

| Meddelande | Datum tillagt eller uppdaterat | Beskrivning |
| ----------- | ---------- | ---------- |
| **Analysis Workspace vänstra panel öppnas inte längre och stängs vid hovring** | Den vänstra panelen i Analysis Workspace används för att lägga till saker som komponenter, paneler och visualiseringar i ditt projekt. Alternativet att tillfälligt öppna den vänstra panelen genom att hålla markören över en av ikonerna längst till vänster är inte längre tillgängligt. Istället klickar du på någon av de här ikonerna för att hålla panelen öppen. Klicka sedan på samma ikon för att stänga den. |  | 29 maj 2025 |


## EOL-meddelanden (End-of-life) {#eol}

| EOL-produkt eller -funktion | Datum tillagt eller uppdaterat | Beskrivning |
| --- | --- | --- |
| **Åtkomst via äldre domäner eller via äldre enkel inloggning** | 10 april 2025 | Adobe planerar att uppdatera hur användare använder Adobe Analytics för att förbättra säkerheten och effektivisera inloggningen. Som en del av denna insats kommer åtkomst via äldre domäner eller via äldre enkel inloggning (SSO), inklusive `my.omniture.com`, att upphöra permanent den **2 januari 2026**. Efter detta datum kommer äldre inloggningsuppgifter och äldre enkel inloggning inte längre att fungera. Alla användare måste logga in via `experience.adobe.com` med sina Adobe Experience Cloud ID:n. Om du behöver hjälp med ditt Experience Cloud ID kontaktar du Adobe Analytics-administratören eller [Adobe kundtjänst](https://helpx.adobe.com/contact.html). |
| **Migrering till autentiseringsuppgifter för Adobe I/O OAuth Server-till-Server** | 17 januari 2025 | Adobe Analytics API- och LiveStream-kunder som använder Adobe I/O JWT-autentiseringsuppgifter måste migrera till Adobe I/O OAuth Server-till-Server-autentiseringsuppgifter senast den **30 juni 2025**. Adobe I/O tillåter inte att nya JWT-autentiseringsuppgifter skapas från och med 1 maj 2024. Kunder som använder JWT måste skapa en ny OAuth Server-till-Server-autentiseringsuppgift eller migrera sina befintliga JWT-autentiseringsuppgifter till en OAuth Server-till-Server-autentiseringsuppgift. Kunderna måste även uppdatera sina klientprogram för att kunna använda de nya autentiseringsuppgifterna för OAuth Server-till-Server. <ul><li>[Migrerar från JWT-autentiseringsuppgifter ](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration)</li><li>[Implementeringsguide för nya och gamla program med OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation)<li>[Använder de nya autentiseringsuppgifterna för OAuth Server-till-server](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation)</li><li>[Vanliga frågor](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs)</li></ul> |
| **EOL för Adobe Analytics API (version 1.4)** | 17 juli 2024 | Den **12 augusti 2026** kommer följande API-tjänster för Analytics Legacy att ha nått slutet på sin livstid och stängas, och aktuella integreringar som byggts med dessa tjänster kommer att sluta fungera:<ul><li>Adobe Analytics API (version 1.4)</li><li>Adobe Analytics WSSE-autentisering</li></ul><p>Integreringar som använder Adobe Analytics API (version 1.4) måste migrera till [Adobe Analytics 2.0 API](https://developer.adobe.com/analytics-apis/docs/2.0/) medan WSSE-integreringar måste migrera till ett OAuth-baserat autentiseringsprotokoll i [Adobe Developer Console](https://developer.adobe.com/console).</p><p>Se [Vanliga frågor om Adobe Analytics 1.4 API EOL ](/help/admin/c-admin-api/c-admin-14-api-eol.md) för svar på vanliga frågor och ytterligare vägledning.</p> |


## AppMeasurement

De senaste uppdateringarna för AppMeasurement finns i [AppMeasurement versionsinformation](https://github.com/adobe/appmeasurement/releases).


## Relaterade resurser

* [Information om föregående version för 2025](/help/release-notes/2025.md)
* [Versionsinformation för Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html)
* [Versionsinformation för direktuppspelad mediainsamling](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html)
* Den senaste releaseuppdateringen för [Adobe Experience Cloud-produkter](https://business.adobe.com/products/adobe-experience-cloud-products.html)
