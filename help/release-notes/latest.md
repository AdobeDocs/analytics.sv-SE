---
title: Aktuella versionsinformation för Adobe Analytics
description: Visa den aktuella versionsinformationen för Adobe Analytics
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 2d42a824510fa03825a10da3837801ee662f687c
workflow-type: tm+mt
source-wordcount: '719'
ht-degree: 1%

---

# Aktuell versionsinformation för Adobe Analytics (23 oktober 2024)


**Senast uppdaterad**: 23 oktober 2024

Versionsinformationen omfattar frisläppningsperioden 16 oktober 2024 till slutet av 2024. Adobe Analytics-releaser fungerar på en [kontinuerlig leveransmodell](releases.md), vilket ger en mer skalbar, fasad metod för driftsättning av funktioner. Därför uppdateras versionsinformationen flera gånger i månaden. Kontrollera dem regelbundet.

## Nya funktioner eller förbättringar {#features}

| Funktion | Beskrivning | [Startar](releases.md) | [Allmän tillgänglighet](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Nytt Report Builder för Adobe Analytics** | Det nya Report Builder-programmet ger Adobe Analytics en större uppdatering, inklusive bättre prestanda, smidigt användargränssnitt, 2.0-API-stöd och stöd för Microsoft Excel i Mac, Windows och webbläsare. Det här programmet kan användas tillsammans med det äldre programmet, men inte i samma fil. Det finns en uppgraderingsfunktion för att uppgradera äldre arbetsböcker till det nya programmet. [Läs mer](https://experienceleague.adobe.com/en/docs/analytics/analyze/report-builder/report-buider-overview) |  | 16 oktober 2024 |
| **JSON-export för migrering av taggimplementering till Web SDK-taggar** | Den här uppdateringen av tillägget Analytics-taggar är relaterad till migrering till Web SDK. Du kan använda den här uppdateringen av Adobe Analytics-tillägget som en del av arbetsflödet för att återskapa dina tilläggskonfigurationer med Web SDK-tillägget. I Adobe Analytics-taggtillägget kan du visa inställningar för eVars, props och händelser som JSON, som kan exporteras för redigering och inkluderas i Web SDK-tillägget. |  | 23 oktober 2024 |

## Korrigeringar i Adobe Analytics

Analysis Workspace: AN-356287; AN-358435; AN-359456; AN-359826; AN-360215
Administratörsverktyg: AN-342485; AN-347931; AN-348704; AN-357723; AN-358453; AN-358717; AN-35954 8; AN-360136
Klassificeringar: AN-359025; AN-359283; AN-359368; AN-359710; AN-359752; AN-359759; AN-35979; AN-359887; AN-360543; AN-360566; AN-360612; AN-360741; AN-360942; AN-360952
Enhetsövergripande analys: AN-359210
Kundattribut: AN-357897
Datainsamling: AN-351131; AN-351309; AN-355678; AN-359856
Dataflöden: AN-359699
API för datareparation: AN-360256
Datakällor: AN-359290
Data Warehouse: AN-359820
Overage Alerts: AN-358132


## Viktiga meddelanden för Adobe Analytics-administratörer {#admin}

| Meddelande | Datum tillagt eller uppdaterat | Beskrivning |
| ----------- | ---------- | ---------- |
| **Icke-kampanjkunder förlorar åtkomst till utlösare** | 16 oktober 2024 | Den 30 januari 2025 förlorar Adobe Analytics-kunder som inte har någon Adobe Campaign-licens åtkomsten till möjligheten att konfigurera och använda [utlösare](https://experienceleague.adobe.com/en/docs/core-services/interface/services/triggers). Kunderna måste antingen köpa Campaign, eller planera för att sluta använda Triggers, eller titta på andra Adobe-verktyg som erbjuder Triggers-funktioner. |
| **Ytterligare implementeringsinformation i XDM-fält mappas automatiskt** | 11 september 2024 | När du använder Adobe Experience Platform Edge Network för att skicka data till Adobe Analytics mappas XDM-fälten `xdm.implementationdetails.name` och `xdm.implementationdetails.environment` nu alltid till kontextdatavariabler `c.a.x.implementationdetails.name` och `c.a.x.implementationdetails.environment`. Tidigare hindrade vissa scenarier dessa värden från att fyllas i. Justera eventuella relevanta bearbetningsregler för att passa tillgängligheten för dessa värden. |

## EOL-meddelanden (End-of-life) {#eol}

| EOL-produkt eller -funktion | Datum tillagt eller uppdaterat | Beskrivning |
| --- | --- | --- |
| **EOL för Adobe Analytics API (version 1.4)** | 17 juli 2024 | Den **12 augusti 2026** kommer följande API-tjänster för Analytics Legacy att ha nått slutet på sin livstid och stängas, och aktuella integreringar som byggts med dessa tjänster kommer att sluta fungera:<ul><li>Adobe Analytics API (version 1.4)</li><li>Adobe Analytics WSSE-autentisering</li></ul><p>Integreringar som använder Adobe Analytics API (version 1.4) måste migrera till [Adobe Analytics 2.0 API](https://developer.adobe.com/analytics-apis/docs/2.0/) medan WSSE-integreringar måste migrera till ett OAuth-baserat autentiseringsprotokoll i [Adobe Developer Console](https://developer.adobe.com/console).</p><p>Se [Vanliga frågor om Adobe Analytics 1.4 API EOL ](/help/admin/c-admin-api/c-admin-14-api-eol.md) för svar på vanliga frågor och ytterligare vägledning.</p> |
| **Migrering till autentiseringsuppgifter för Adobe I/O OAuth Server-till-Server** | 11 maj 2023 | Adobe Analytics API- och LiveStream-kunder som använder Adobe I/O JWT-autentiseringsuppgifter måste migrera till autentiseringsuppgifterna för Adobe I/O OAuth Server-till-Server senast **1 januari 2025**. Adobe I/O tillåter inte att nya JWT-autentiseringsuppgifter skapas från och med 1 maj 2024. Kunder som använder JWT måste skapa en ny OAuth Server-till-Server-autentiseringsuppgift eller migrera sina befintliga JWT-autentiseringsuppgifter till en OAuth Server-till-Server-autentiseringsuppgift. Kunderna måste även uppdatera sina klientprogram för att kunna använda de nya autentiseringsuppgifterna för OAuth Server-till-Server. <ul><li>[Migrerar från JWT-autentiseringsuppgifter ](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)</li><li>[Implementeringsguide för nya och gamla program med OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)<li>[Använder de nya autentiseringsuppgifterna för OAuth Server-till-server](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)</li><li>[Vanliga frågor](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)</li></ul> |


## AppMeasurement

De senaste uppdateringarna av AppMeasurement (version 2.26.0) finns i [AppMeasurementet för JavaScript versionsinformation](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html).


## Relaterade resurser

* [Information om föregående version för 2024](/help/release-notes/2024.md)
* [Versionsinformation för Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html)
* [Versionsinformation om tilläggsprogrammet för direktuppspelad mediasamling](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html)
* Den senaste releaseuppdateringen för [Adobe Experience Cloud-produkter](https://business.adobe.com/products/adobe-experience-cloud-products.html)
