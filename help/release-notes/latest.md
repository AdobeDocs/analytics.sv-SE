---
title: Aktuella versionsinformation för Adobe Analytics
description: Visa den aktuella versionsinformationen för Adobe Analytics
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 924f5f670d2f29269a5ba6623079e839f1fe8122
workflow-type: tm+mt
source-wordcount: '700'
ht-degree: 2%

---

# Aktuell versionsinformation för Adobe Analytics (februari 2025)

**Senast uppdaterad**: 21 februari 2024

Versionsanteckningarna gäller från den 11 februari till mitten av mars 2025. Adobe Analytics-releaser fungerar på en [kontinuerlig leveransmodell](releases.md), vilket ger en mer skalbar, fasad metod för driftsättning av funktioner. Därför uppdateras versionsinformationen flera gånger i månaden. Kontrollera dem regelbundet.

## Nya funktioner eller förbättringar {#features}

| Funktion | Beskrivning | [Startar](releases.md) | [Allmän tillgänglighet](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Kvarhållningsperiod för transaktions-ID** | Kvarhållningsperioden för transaktions-ID på 90 dagar förlängdes till 25 månader. Variabeln `transactionID` identifierar en transaktion unikt så att träffen kan koppla till data som överförts via datakällor. Läs mer [här](https://experienceleague.adobe.com/en/docs/analytics/implementation/vars/page-vars/transactionid) och [här](https://experienceleague.adobe.com/en/docs/analytics/import/data-sources/transactionid). |  | 20 februari 2025 |
| **API-referens för datafeeds** | [Referens](https://adobedocs.github.io/analytics-2.0-apis/?urls.primaryName=Data%20Feeds%20APIs) för API:t för datafeeds är nu tillgänglig. |  | 30 januari 2025 |
| **API:t för livesystem - klientimplementering** | Använd Livesream-klientimplementeringen för att förbruka data från Livestream. [Läs mer](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/livestream/clientcode/) |  | 18 februari 2025 |
| **Uppdatera till klassificerings-API** | Du kan nu ta bort enskilda klassificeringsfält eller nycklar från servern. Detta är ett alternativ till att ta bort en hel klassificeringsdatamängd med metoden DELETE. [Läs mer](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/classifications/remove-values/) |  | 18 februari 2025 |


## Korrigeringar i Adobe Analytics

**Analysis Workspace**: AN-359974; AN-366212; AN-368460
**Klassifikationer**: AN-367186; AN-367328; AN-368548
**Komponentmigrering**: AN-364529; AN-366398; AN-367509;
**Dataflöden**: AN-365685; AN-366745; AN-367256; AN-367349; AN-368363
**Data Warehouse**: AN-368178; AN-368331;
**Mobilapp**: AN-367137
**Plattform**: AN-351924; AN-365540; AN-365866; AN-366898; AN-367856; AN-367933
**Report Builder**: AN-366456; AN-366655;
**Virtuella rapportsviter**: AN-367411
**VISTA-regler**: AN-365331

## Viktiga meddelanden för Adobe Analytics-administratörer {#admin}

| Meddelande | Datum tillagt eller uppdaterat | Beskrivning |
| ----------- | ---------- | ---------- |
| **Kommande uppdatering av kontextdatafältet för analyser`a.locale`** | 21 februari 2025 | Den 5 mars 2025 uppdateras Analytics-kontextdatafältet `a.locale` när data samlas in via Experience Edge. När data skickas till Adobe Analytics med Experience Edge fylls analysfälten i baserat på en mappning av XDM-fält. Mappningen för `c.a.locale` refererar till ett XDM-fält som inte är standard, `xdm.environment.language`. Det här fältet uppdateras för att referera till rätt fält, `xdm.environment._dc.language`.  Mappningen fortsätter att referera till `xdm.environment.language` för bakåtkompatibilitet. Om båda fälten anges för kontinuitet har `xdm.environment.language` företräde. Du kan visa den fullständiga listan över mappningar från XDM till standardanalysfält [här](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/xdm-var-mapping). |
| **Icke-kampanjkunder förlorar åtkomst till utlösare** | 16 oktober 2023 | Den 30 januari 2025 förlorade Adobe Analytics-kunder som inte har någon Adobe Campaign-licens åtkomsten till möjligheten att konfigurera och använda [utlösare](https://experienceleague.adobe.com/en/docs/core-services/interface/services/triggers). Kunderna måste antingen köpa Campaign, eller planera för att sluta använda Triggers, eller undersöka andra Adobe-verktyg som erbjuder Triggers-funktioner. |

## EOL-meddelanden (End-of-life) {#eol}

| EOL-produkt eller -funktion | Datum tillagt eller uppdaterat | Beskrivning |
| --- | --- | --- |
| **Migrering till autentiseringsuppgifter för Adobe I/O OAuth Server-till-Server** | 17 januari 2025 | Adobe Analytics API- och LiveStream-kunder som använder Adobe I/O JWT-autentiseringsuppgifter måste migrera till Adobe I/O OAuth Server-till-Server-autentiseringsuppgifter senast den **30 juni 2025**. Adobe I/O tillåter inte att nya JWT-autentiseringsuppgifter skapas från och med 1 maj 2024. Kunder som använder JWT måste skapa en ny OAuth Server-till-Server-autentiseringsuppgift eller migrera sina befintliga JWT-autentiseringsuppgifter till en OAuth Server-till-Server-autentiseringsuppgift. Kunderna måste även uppdatera sina klientprogram för att kunna använda de nya autentiseringsuppgifterna för OAuth Server-till-Server. <ul><li>[Migrerar från JWT-autentiseringsuppgifter ](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)</li><li>[Implementeringsguide för nya och gamla program med OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)<li>[Använder de nya autentiseringsuppgifterna för OAuth Server-till-server](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)</li><li>[Vanliga frågor](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)</li></ul> |
| **EOL för Adobe Analytics API (version 1.4)** | 17 juli 2024 | Den **12 augusti 2026** kommer följande API-tjänster för Analytics Legacy att ha nått slutet på sin livstid och stängas, och aktuella integreringar som byggts med dessa tjänster kommer att sluta fungera:<ul><li>Adobe Analytics API (version 1.4)</li><li>Adobe Analytics WSSE-autentisering</li></ul><p>Integreringar som använder Adobe Analytics API (version 1.4) måste migrera till [Adobe Analytics 2.0 API](https://developer.adobe.com/analytics-apis/docs/2.0/) medan WSSE-integreringar måste migrera till ett OAuth-baserat autentiseringsprotokoll i [Adobe Developer Console](https://developer.adobe.com/console).</p><p>Se [Vanliga frågor om Adobe Analytics 1.4 API EOL ](/help/admin/c-admin-api/c-admin-14-api-eol.md) för svar på vanliga frågor och ytterligare vägledning.</p> |


## AppMeasurement

De senaste uppdateringarna av AppMeasurement-versioner (version 2.26.0) finns i [Versionsinformation för AppMeasurement för JavaScript](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html).


## Relaterade resurser

* [Information om föregående version för 2024](/help/release-notes/2024.md)
* [Versionsinformation för Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html)
* [Versionsinformation för direktuppspelad mediainsamling](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html)
* Den senaste releaseuppdateringen för [Adobe Experience Cloud-produkter](https://business.adobe.com/products/adobe-experience-cloud-products.html)
