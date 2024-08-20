---
title: Aktuella versionsinformation för Adobe Analytics
description: Visa den aktuella versionsinformationen för Adobe Analytics
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: f7d36ac8de37633ccbe725865dbaeecee532f47e
workflow-type: tm+mt
source-wordcount: '719'
ht-degree: 1%

---

# Aktuell versionsinformation för Adobe Analytics (augusti 2024)

**Senast uppdaterad**: 14 augusti 2024

Versionsanteckningarna gäller den 14 augusti till september 2024. Adobe Analytics-releaser fungerar på en [kontinuerlig leveransmodell](releases.md), vilket ger en mer skalbar, fasad metod för driftsättning av funktioner. Därför uppdateras versionsinformationen flera gånger i månaden. Kontrollera dem regelbundet.

## Nya funktioner eller förbättringar {#features}

| Funktion | Beskrivning | [Startar](releases.md) | [Allmän tillgänglighet](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Förbättringar av Web SDK för länkspårning** | Det finns flera märkbara förbättringar i den senaste versionen av Web SDK runt länkspårning, som är till direkt nytta för Activity Map. Dessa nya funktioner är tillgängliga både i Web SDK JavaScript-biblioteket och i Web SDK-taggtillägget.<ul><li>Händelsegruppering: När en besökare klickar på en intern länk kan du välja att gruppera händelsedata på nästa sida i stället för att utlösa ett separat händelseanrop för länkspårning. Den här förbättringen minskar antalet händelser som Web SDK använder jämfört med avtalsgränsen.</li><li>Filtrera klickningsegenskaper: Ett nytt återanrop som ersätter `OnBeforeLinkClickSend`. Du kan använda det här återanropet för att filtrera eller dölja länkrelaterade data innan du skickar dem till Adobe.</li></ul><p>Mer information finns i [clickCollection](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/clickcollection) i användarhandboken för Web SDK.</p> | Öppna Beta började 10 juli 2024 | 18 juli 2024 |

{style="table-layout:auto"}

## Korrigeringar i Adobe Analytics

* Korrigerade ett problem där flera okända värden visades i Workspace (AN-353632)
* Ett problem har korrigerats där e-postmeddelandet inte skickades efter att nya kunder eller nya produktprofiler för Analytics lagts till i Admin Console (AN-350930)

### Korrigeringar för andra analyser

AN-354361; AN-354248; AN-354211; AN-354324; AN-351532; AN-349808; AN-347831; AN-4 353777; AN-354092; AN-354064; AN-354202; AN-354006; AN-354097; AN-352548; AN-3 53819; AN-353818; AN-353628; AN-353747; AN-353527; AN-353490; AN-352647; AN-35 2656; AN-351274; AN-352135; AN-351519; AN-344906; AN-353697; AN-354499; AN-354 402; AN-354062; AN-353905; AN-353932; AN-354142; AN-354194; AN-354182; AN-3537 58; AN-353039; AN-353612; AN-350799; AN-354414; AN-354636; AN-354249; AN-35363 7; AN-350949; AN-349402; AN-355103; AN-354174; AN-353823; AN-354819; AN-354215; AN-354219; AN-354040; AN-354763; AN-354597; AN-354478; AN-354528; AN-35435

## Viktiga meddelanden för Adobe Analytics-administratörer {#admin}

| Meddelande | Datum tillagt eller uppdaterat | Beskrivning |
| ----------- | ---------- | ---------- |
| **13-månaders förfallodatum för sparad`cust_visids`** | 20 augusti 2024 | Den 20 augusti 2024 **-utgåvan av motorn för bearbetning av analysträffar tvingar fram ett 13-månaders förfallodatum för sparad `cust_visids`.** Om rapportsviten har Aktivera besökarinställning aktiverat, används den här inställningen för att hitta `cust_visid` för en `visid_high/visid_low value` utan `cust_visid` i träffen. Tidigare var mappningen av en `cust_visid` för en `visid_high/visid_low` inte giltig. Om 13 månader eller mer har gått sedan `visid_high/visid_low` fick en `cust_visid` för en träff i den här versionen upphör mappningen att gälla. |

{style="table-layout:auto"}

## EOL-meddelanden (End-of-life) {#eol}

| EOL-produkt eller -funktion | Datum tillagt eller uppdaterat | Beskrivning |
| --- | --- | --- |
| **EOL för Adobe Analytics API (version 1.4)** | 17 juli 2024 | Den **12 augusti 2026** kommer följande API-tjänster för Analytics Legacy att sluta fungera och de kommer att stängas, och aktuella integreringar som skapats med dessa tjänster kommer att sluta fungera:<ul><li>Adobe Analytics API (version 1.4)</li><li>Adobe Analytics WSSE-autentisering</li></ul><p>Integreringar som använder Adobe Analytics API (version 1.4) måste migrera till [Adobe Analytics 2.0 API](https://developer.adobe.com/analytics-apis/docs/2.0/) medan WSSE-integreringar måste migrera till ett OAuth-baserat autentiseringsprotokoll i [Adobe Developer Console](https://developer.adobe.com/console).</p><p>Se [Vanliga frågor om Adobe Analytics 1.4 API EOL ](/help/admin/c-admin-api/c-admin-14-api-eol.md) för svar på vanliga frågor och ytterligare vägledning.</p> |
| **Migrering till autentiseringsuppgifter för Adobe I/O OAuth Server-till-Server** | 11 maj 2023 | Adobe Analytics API- och LiveStream-kunder som använder Adobe I/O JWT-autentiseringsuppgifter måste migrera till autentiseringsuppgifterna för Adobe I/O OAuth Server-till-Server senast **1 januari 2025**. Adobe I/O tillåter inte att nya JWT-autentiseringsuppgifter skapas från och med 1 maj 2024. Kunder som använder JWT måste skapa en ny OAuth Server-till-Server-autentiseringsuppgift eller migrera sina befintliga JWT-autentiseringsuppgifter till en OAuth Server-till-Server-autentiseringsuppgift. Kunderna måste även uppdatera sina klientprogram för att kunna använda de nya autentiseringsuppgifterna för OAuth Server-till-Server. <ul><li>[Migrerar från JWT-autentiseringsuppgifter ](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)</li><li>[Implementeringsguide för nya och gamla program med OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)<li>[Använder de nya autentiseringsuppgifterna för OAuth Server-till-server](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)</li><li>[Vanliga frågor](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)</li></ul> |

{style="table-layout:auto"}

## AppMeasurement

De senaste uppdateringarna av AppMeasurement (version 2.26.0) finns i [AppMeasurementet för JavaScript versionsinformation](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html).


## Relaterade resurser

* [Information om föregående version för 2024](/help/release-notes/2024.md)
* [Versionsinformation för Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html)
* [Versionsinformation om tilläggsprogrammet för direktuppspelad mediasamling](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html)
* Den senaste releaseuppdateringen för [Adobe Experience Cloud-produkter](https://business.adobe.com/products/adobe-experience-cloud-products.html)
