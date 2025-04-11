---
title: Aktuella versionsinformation för Adobe Analytics
description: Visa den aktuella versionsinformationen för Adobe Analytics
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: d81412790f5658d90890c48eca50548cd57b4b48
workflow-type: tm+mt
source-wordcount: '678'
ht-degree: 2%

---

# Aktuell versionsinformation för Adobe Analytics (mars 2025-utgåvan)

**Senast uppdaterad**: 11 april 2025

Versionsanteckningarna gäller från 5 mars till 5 maj 2025. Adobe Analytics-releaser fungerar på en [kontinuerlig leveransmodell](releases.md), vilket ger en mer skalbar, fasad metod för driftsättning av funktioner. Därför uppdateras versionsinformationen flera gånger i månaden. Kontrollera dem regelbundet.

## Nya funktioner eller förbättringar {#features}

| Funktion | Beskrivning | [Startar](releases.md) | [Allmän tillgänglighet](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Analyslager** | Analytics Inventory ger en omfattande översikt över er Adobe Analytics-miljö, inklusive antalet projekt och komponenter, rapportsviter, användare med mera. Genom att automatisera inventeringsprocessen kan ni snabbt förstå vad ni behöver för att gå över från Adobe Analytics till Customer Journey Analytics. Detta gör övergången enklare och snabbare. [Läs mer](https://experienceleague.adobe.com/en/docs/analytics/admin/admin-tools/analytics-inventory) |  | 26 mars 2025 |
| **Uppdatera till kontextdatafältet för analyser`a.locale`** | Den här uppdateringen ändrar hur kontextdatafältet `a.locale` för Analytics anges när data samlas in via Experience Edge. När data skickas till Adobe Analytics med Experience Edge fylls analysfälten i baserat på en mappning av XDM-fält. Mappningen för `c.a.locale` refererar till ett XDM-fält som inte är standard, `xdm.environment.language`. Det här fältet uppdateras för att referera till rätt fält, `xdm.environment._dc.language`.<p>Mappningen fortsätter att referera till `xdm.environment.language` för bakåtkompatibilitet. Om båda fälten är angivna har `xdm.environment.language` prioritet för kontinuitet. Du kan visa den fullständiga listan över mappningar från XDM till standardanalysfält [här](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/xdm-var-mapping). | | 5 mars 2025 |
| **Customer Journey Analytics - uppgraderingsguide** | Här kan du skapa en stegvis guide för uppgradering från Adobe Analytics till Customer Journey Analytics. Den här guiden är anpassad efter din organisation och tar hänsyn till din nuvarande Adobe Analytics-miljö, dina avsedda användningsområden för Customer Journey Analytics samt tidsbesparande transaktioner som din organisation vill göra.<p>Logga in på [!DNL Customer Journey Analytics] och välj sedan **[!UICONTROL Upgrade to Customer Journey Analytics]** på fliken **[!UICONTROL Workspace]** för att börja generera din anpassade guide.<p>[Läs mer](https://experienceleague.adobe.com/en/docs/analytics-platform/using/compare-aa-cja/upgrade-to-cja/cja-upgrade-recommendations#recommended-upgrade-steps-for-most-organizations) |  | 11 mars 2025 |
| **Endast Data Warehouse-dimensioner** | Baserat på kundens feedback har vi beslutat oss för att omvärdera. Vi kommer inte att släppa den automatiska funktionen som endast fungerar för Data Warehouse som tidigare meddelats. | | TBD |


## Korrigeringar i Adobe Analytics

**Activity Map**: AN-361038
**Administratörsverktyg**: AN-362178; AN-369483
**Analytics API 1.4**: AN-369615
**Analysis Workspace**: AN-353491; AN-363403; AN-367230; AN-367313; AN-368582; AN-369821; AN-370 227;
**Klassificeringar**: AN-369848; AN-370196; AN-370226; AN-370437
**Dataflöden**: AN-366162; AN-368906; AN-369066; AN-369087; AN-369225; AN-369798
**Datastyrning**: AN-365157
**Datakällor**: AN-367550
**Platform**: AN-363931
**Report Builder**: AN-367460; AN-368975

## Viktiga meddelanden för Adobe Analytics-administratörer {#admin}

| Meddelande | Datum tillagt eller uppdaterat | Beskrivning |
| ----------- | ---------- | ---------- |
| Ej tillämpligt |  |  |

## EOL-meddelanden (End-of-life) {#eol}

| EOL-produkt eller -funktion | Datum tillagt eller uppdaterat | Beskrivning |
| --- | --- | --- |
| **Migrering till autentiseringsuppgifter för Adobe I/O OAuth Server-till-Server** | 17 januari 2025 | Adobe Analytics API- och LiveStream-kunder som använder Adobe I/O JWT-autentiseringsuppgifter måste migrera till Adobe I/O OAuth Server-till-Server-autentiseringsuppgifter senast den **30 juni 2025**. Adobe I/O tillåter inte att nya JWT-autentiseringsuppgifter skapas från och med 1 maj 2024. Kunder som använder JWT måste skapa en ny OAuth Server-till-Server-autentiseringsuppgift eller migrera sina befintliga JWT-autentiseringsuppgifter till en OAuth Server-till-Server-autentiseringsuppgift. Kunderna måste även uppdatera sina klientprogram för att kunna använda de nya autentiseringsuppgifterna för OAuth Server-till-Server. <ul><li>[Migrerar från JWT-autentiseringsuppgifter ](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)</li><li>[Implementeringsguide för nya och gamla program med OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)<li>[Använder de nya autentiseringsuppgifterna för OAuth Server-till-server](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)</li><li>[Vanliga frågor](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)</li></ul> |
| **EOL för Adobe Analytics API (version 1.4)** | 17 juli 2024 | Den **12 augusti 2026** kommer följande API-tjänster för Analytics Legacy att ha nått slutet på sin livstid och stängas, och aktuella integreringar som byggts med dessa tjänster kommer att sluta fungera:<ul><li>Adobe Analytics API (version 1.4)</li><li>Adobe Analytics WSSE-autentisering</li></ul><p>Integreringar som använder Adobe Analytics API (version 1.4) måste migrera till [Adobe Analytics 2.0 API](https://developer.adobe.com/analytics-apis/docs/2.0/) medan WSSE-integreringar måste migrera till ett OAuth-baserat autentiseringsprotokoll i [Adobe Developer Console](https://developer.adobe.com/console).</p><p>Se [Vanliga frågor om Adobe Analytics 1.4 API EOL ](/help/admin/c-admin-api/c-admin-14-api-eol.md) för svar på vanliga frågor och ytterligare vägledning.</p> |


## AppMeasurement

De senaste uppdateringarna för AppMeasurement finns i [AppMeasurement versionsinformation](https://github.com/adobe/appmeasurement/releases).


## Relaterade resurser

* [Information om föregående version för 2025](/help/release-notes/2025.md)
* [Versionsinformation för Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html)
* [Versionsinformation för direktuppspelad mediainsamling](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html)
* Den senaste releaseuppdateringen för [Adobe Experience Cloud-produkter](https://business.adobe.com/products/adobe-experience-cloud-products.html)
