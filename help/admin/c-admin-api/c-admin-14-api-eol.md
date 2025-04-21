---
description: Information om Adobe Analytics 1.4 API-meddelande om att livscykeln upphör.
title: Vanliga frågor om Adobe Analytics 1.4 API EOL
feature: Admin Tools
role: Admin
exl-id: 88769032-a7cd-4ca8-958f-3300a4bfe71f
source-git-commit: 73c0210ac931f3e7f823e033a3bffdc22e159ddb
workflow-type: tm+mt
source-wordcount: '534'
ht-degree: 0%

---

# Vanliga frågor om Adobe Analytics 1.4 API EOL

Adobe planerar att upphöra med Adobe Analytics 1.4 API den **12 augusti 2026**. Efter detta datum är de inte längre tillgängliga. Detta meddelande påverkar direkt följande:

* Adobe Analytics 1.4 API:er, exklusive API:n för datainfogning
* Adobe Analytics WSSE-autentisering

## 1,4 API:er

[Adobe Analytics 1.4-API:erna](https://developer.adobe.com/analytics-apis/docs/1.4/) innehåller ett stort antal åtgärder, till exempel rapportering, klassificeringar, dataflöden och rapportsvitskonfigurationer. De har börjat gälla till förmån för [Adobe Analytics 2.0-API:erna](https://developer.adobe.com/analytics-apis/docs/2.0/). Med API:erna för 2.0 kan du utföra nästan alla åtgärder som du kan utföra i användargränssnittet för Analytics, som att rapportera eller hantera komponenter som segment och beräknade värden.

Adobe erbjuder en [migreringssökväg](https://developer.adobe.com/analytics-apis/docs/2.0/guides/migration/) för 1.4 API-användare. Du kan migrera dina integreringar till 2.0-API:erna (samma API:er som Adobe Analytics-programmet är beroende av) och dra nytta av de senaste funktionerna. Alla funktioner som är tillgängliga i 1.4 API:er kan utföras med [Adobe Analytics 2.0 API:er](https://developer.adobe.com/analytics-apis/docs/2.0/).

## WSSE-autentisering

WSSE-autentisering är ett äldre autentiseringsprotokoll som stöds av API:erna i Analytics 1.4. Den har ersatts av de OAuth-baserade autentiseringsalternativen som finns i [Adobe Developer Console](https://developer.adobe.com/console/home). Projekt som använder WSSE-autentisering måste uppdatera sina autentiseringsuppgifter till de som har etablerats i Adobe Developer Console. Det gör du genom att logga in på [Adobe Developer Console](https://developer.adobe.com/console/home) och skapa ett projekt för din API-integrering med Analytics 2.0. Välj autentiseringsmetoden OAuth User eller OAuth Server-to-Server.

## Vanliga frågor och svar

+++**Påverkar detta mina befintliga Adobe IO-projekt för API:erna för analyser?**

Befintliga projekt som använder API:erna i Analytics 1.4 påverkas. Dessa integreringar måste migreras till [Adobe Analytics 2.0-API:erna](https://developer.adobe.com/analytics-apis/docs/2.0/) före slutdatumet för EOL.

+++

+++**Jag har delat mina Adobe-autentiseringsuppgifter med en annan produkt eller ett annat program som använder API:erna för Analytics. Påverkas de?**

Om produkten eller programmet använder WSSE-autentiseringsuppgifter och/eller anropar API:er för Analytics 1.4 påverkas den och måste migreras före slutdatumet för EOL. Kontakta produkt- eller programleverantören för mer information om migreringsplanerna och tidslinjen.

+++

+++**Hur kan jag avgöra vilket API som används i mitt projekt?**

Bas-URL:en som API-anropen anropar avgör vilken API-version projektet använder. API:erna för Adobe Analytics 1.4 använder följande URL:er:
* `https://api.omniture.com`
* `https://api3.omniture.com`
* `https://api4.omniture.com`
* `https://api5.omniture.com`

[API:erna för Adobe Analytics 2.0](https://developer.adobe.com/analytics-apis/docs/2.0/) använder följande URL:

* `https://analytics.adobe.io`

Om något av dina API-projekt använder `api*.omniture.com`, används API:erna i Adobe Analytics 1.4 och måste migreras till API:erna för 2.0.

+++

+++**Påverkar detta datainsamlingen?**

Adobe Analytics 1.4 EOL påverkar inte taggningslösningarna, till exempel Tags (tidigare Adobe Launch), Web SDK eller AppMeasurement. Om du däremot använder 1.4-API:erna för datakällor eller klassificeringar för att förbättra dina data måste du migrera dessa arbetsflöden till API:erna för Adobe Analytics 2.0.

API:t för datainfogning påverkas inte av det här meddelandet. Adobe planerar att fortsätta ha stöd för API:t för datainmatning, men Adobe rekommenderar att du använder [API:t för datainmatning i grupp](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/bulk-data-insertion/) i stället.

+++

Om du har ytterligare frågor om det här meddelandet om att produkten har upphört att gälla som inte besvaras på den här sidan kontaktar du Adobe Account Team.
