---
description: Länka till Adobe Analytics Admin API på github.
title: Vanliga frågor om Adobe Analytics 1.4 API EOL
feature: Admin Tools
role: Admin
source-git-commit: da96c049f7cfb73496416c2d8a7f4dcbc8f2303e
workflow-type: tm+mt
source-wordcount: '801'
ht-degree: 0%

---

# Vanliga frågor om Adobe Analytics 1.4 API EOL

## Tillkännagivande om upphörande av livslängd

**Vad tas bort?**

* Adobe Analytics 1.4 API:er

* Adobe Analytics WSSE-autentisering

**När avslutas det?**

Dessa tjänster upphör den 12 augusti 2026. Efter detta datum är de inte längre tillgängliga.

## 1,4 API:er

**Vad är de här tjänsterna?**

[Adobe Analytics 1.4-API:erna](https://developer.adobe.com/analytics-apis/docs/1.4/) är en samling API:er som innehåller en mängd olika åtgärder, till exempel rapportering, klassificeringar, dataflöden och rapportsvitskonfigurationer.

**Vad behöver jag göra för att migrera?**

[API:erna för Adobe Analytics 2.0](https://developer.adobe.com/analytics-apis/docs/2.0/) erbjuder en migreringsväg framåt för 1.4 API-användare. Kunder som för närvarande använder 1.4 API:er kan migrera sina integreringar till 2.0 API:er (samma API:er som Adobe Analytics-programmet är beroende av) och dra nytta av de senaste funktionerna.

Med API:erna för 2.0 kan du utföra nästan alla åtgärder som du kan utföra i användargränssnittet för Analytics, som att rapportera eller hantera komponenter som segment och beräknade värden.

**Har API:erna för 2.0 samma funktioner som API:erna för 1.4?**
Alla funktioner som är tillgängliga i 1.4 API:er kan utföras med [ Adobe Analytics 2.0 API:er ](https://developer.adobe.com/analytics-apis/docs/2.0/) . Vissa funktioner har samma funktioner som finns i 1.4-API:erna, vilket gör att du kan utföra nästan alla åtgärder som du kan utföra i Analytics-användargränssnittet, till exempel rapportera eller hantera komponenter som segment och beräknade värden.

## WSSE-autentisering

**Vad är de här tjänsterna?**

WSSE-autentisering är ett äldre autentiseringsprotokoll som stöds av API:erna i Analytics 1.4. Den har ersatts av de OAuth-baserade autentiseringsalternativen som finns i [Adobe Developer Console](https://developer.adobe.com/console/home).

**Vad behöver jag göra för att migrera?**

WSSE-kunder måste uppdatera sina autentiseringar för att kunna använda de autentiseringsuppgifter som tillhandahålls i Adobe Developer Console. Det gör du genom att logga in på [Adobe Developer Console](https://developer.adobe.com/console/home) och skapa ett projekt för din API-integrering med Analytics 2.0. Välj mellan autentiseringsmetoderna OAuth User och OAuth Server-to-Server.

## Frågor

F: **Påverkar detta mina befintliga Adobe-I/O-projekt för analys-API:erna?**

S: Alla befintliga projekt som använder API:erna i Analytics 1.4 påverkas. Dessa integreringar måste migreras till [Adobe Analytics 2.0-API:erna](https://developer.adobe.com/analytics-apis/docs/2.0/) före slutdatumet för EOL.

F: **Jag har delat mina inloggningsuppgifter för Adobe med en annan produkt eller ett annat program som använder API:erna för Analytics. Påverkas de?**

S: Om produkten eller programmet använder dina WSSE-autentiseringsuppgifter och/eller anropar API:erna i Analytics 1.4 påverkas den och måste migreras innan slutdatumet för EOL. Kontakta produkt- eller programleverantören om du vill ha mer information om deras migreringsplaner och tidslinje.

F: **Jag är inte säker på vilket Adobe Analytics API vi använder.**

S: Du kan identifiera vilket API du använder genom den adress som anropas i integreringen.

Adobe Analytics 1.4 API:er nås genom att anropa någon av URL:erna nedan:
* https://api.omniture.com
* https://api3.omniture.com
* https://api4.omniture.com
* https://api5.omniture.com

[API:erna för Adobe Analytics 2.0](https://developer.adobe.com/analytics-apis/docs/2.0/) nås genom att anropa följande URL:
* https://analytics.adobe.io

Om du använder api*.omniture.com måste du migrera till [Adobe Analytics 2.0-API:erna](https://developer.adobe.com/analytics-apis/docs/2.0/).

F: **Är Adobe Analytics 2.0-API:erna identiska med 1.4-API:erna? Om inte, vilka är de största skillnaderna?**

S: Adobe Analytics 2.0-API:erna är inte identiska med 1.4-API:erna, men de erbjuder jämförbara funktioner, inklusive följande fördelar:

* Snabbare svarstider med enklare och effektivare frågetyper, vilket eliminerar behovet av avsökning

* Programmatisk funktion för frågor och dynamiska rapportuppdateringar

* Smidigare felhantering

* Flexibla funktioner för att åstadkomma allt du kan åstadkomma med Analysis Workspace

* Överensstämmelse och matchning av API-anrop till gränssnittsåtgärder

* Tillgång till alla Attribution IQ som används i Analysis Workspace

* Åtkomst till alla algoritmer för avvikelseidentifiering som används i Analysis Workspace

* Möjlighet att integrera med andra Experience Cloud-produkter

* Ökad kapacitet för flera uppdelningsrapporter

* Tillgång till de senaste analysfunktionerna

I guiden [Migrera till Adobe Analytics 2.0 API:er](https://developer.adobe.com/analytics-apis/docs/2.0/guides/migration/) beskrivs de viktigaste skillnaderna mellan 1.4- och 2.0-API:erna. Ytterligare information finns också i [Vanliga frågor om API:t för Analytics 2.0](https://developer.adobe.com/analytics-apis/docs/2.0/guides/faq/).

F: **Påverkar datainsamlingen?**

S: Adobe Analytics 1.4 EOL påverkar inte taggningslösningarna, till exempel Taggar (tidigare Adobe Launch), WebSDK eller AppMeasurement.js. Om du däremot använder 1.4-API:erna för datakällor eller klassificeringar för att samla in eller förbättra dina data måste du migrera dessa arbetsflöden till API:erna för Adobe Analytics 2.0. Mer information finns i [2.0 API Endpoints guide](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/).

F: **Påverkar API:t för datainmatning?**

S: Nej, API:t för datainfogning påverkas inte av Adobe Analytics 1.4 EOL.

F: **Vad gör jag om min fråga inte besvaras i vanliga frågor?**

S: Om du har frågor kontaktar du Adobe.

