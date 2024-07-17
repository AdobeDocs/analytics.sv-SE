---
title: Aktuella versionsinformation för Adobe Analytics
description: Visa den aktuella versionsinformationen för Adobe Analytics
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: cb0eab15dac6d679e9f912010045e6be2e47df4a
workflow-type: tm+mt
source-wordcount: '732'
ht-degree: 1%

---

# Aktuell versionsinformation för Adobe Analytics (juli 2024)

**Senast uppdaterad**: 17 juli 2024

Versionsanteckningarna gäller den 17 juli 2024 till augusti 2024. Adobe Analytics-releaser fungerar på en [kontinuerlig leveransmodell](releases.md), vilket ger en mer skalbar, fasad metod för driftsättning av funktioner. Därför uppdateras versionsinformationen flera gånger i månaden. Kontrollera dem regelbundet.

## Nya funktioner eller förbättringar {#features}

| Funktion | Beskrivning | [Startar](releases.md) | [Allmän tillgänglighet](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Förbättringar av Web SDK för länkspårning** | Det finns flera märkbara förbättringar i den senaste versionen av Web SDK runt länkspårning, som är till direkt nytta för Activity Map. Dessa nya funktioner är tillgängliga både i Web SDK JavaScript-biblioteket och i Web SDK-taggtillägget.<ul><li>Händelsegruppering: När en besökare klickar på en intern länk kan du välja att gruppera händelsedata på nästa sida i stället för att utlösa ett separat händelseanrop för länkspårning. Den här förbättringen minskar antalet händelser som Web SDK använder jämfört med avtalsgränsen.</li><li>Filtrera klickningsegenskaper: Ett nytt återanrop som ersätter `OnBeforeLinkClickSend`. Du kan använda det här återanropet för att filtrera eller dölja länkrelaterade data innan du skickar dem till Adobe.</li></ul><p>Mer information finns i [clickCollection](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/clickcollection) i användarhandboken för Web SDK.</p> | Öppna Beta började 10 juli 2024 | TBD |

{style="table-layout:auto"}

## Korrigeringar i Adobe Analytics

* Ett problem som gjorde att användare inte kunde logga in på analysgränssnittet (AN-352953) har åtgärdats
* Korrigerade ett problem som hindrade användare från att logga in på mobilappen Analytics (AN-352463)
* Korrigerade ett fel som förhindrade hämtning av projektet som PDF (AN-352680)
* Korrigerade ett problem där klassificeringar inte importerades (AN-352178)

### Korrigeringar för andra analyser

AN-352905; AN-352902; AN-352693; AN-352659; AN-352619;
AN-352577; AN-352575; AN-352572; AN-352571; AN-352549; AN-352501; AN-352499; AN 352478; AN-352466; AN-352437; AN-352378; AN-352355; AN-352341; AN-352318; AN-3 52297; AN-352272; AN-352267; AN-352263; AN-352088; AN-352019; AN-352018; AN-35 1978; AN-351908; AN-351809; AN-351750; AN-351689; AN-351624; AN-351564; AN-351 524; AN-351507; AN-351416; AN-351414; AN-351405; AN-351299; AN-351283; AN-3512 31; AN-350710; AN-349912; AN-349786; AN-348300; AN-348061; AN-347865; AN-34767 6; AN-347478; AN-343611; AN-343114; AN-334124

## Viktiga meddelanden för Adobe Analytics-administratörer {#admin}

| Meddelande | Datum tillagt eller uppdaterat | Beskrivning |
| ----------- | ---------- | ---------- |
| **13-månaders förfallodatum för sparad`cust_visids`** | 22 maj 2024 | En kommande version av motorn för bearbetning av träff i Analytics, **som är avsedd för juli 2024**, kommer att börja tillämpa en 13-månaders förfallotid på sparad `cust_visids`. Om rapportsviten har Aktivera besökarinställning aktiverat, används den här inställningen för att hitta `cust_visid` för en `visid_high/visid_low value` utan `cust_visid` i träffen. För närvarande finns det ingen förfallotid för mappningen av en `cust_visid` för en `visid_high/visid_low`. Om 13 månader eller mer har gått sedan `visid_high/visid_low` fick en `cust_visid` för en träff i den här versionen upphör mappningen att gälla. |

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
