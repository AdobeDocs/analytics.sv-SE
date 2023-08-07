---
title: Jämför implementeringsmetoder
description: Se fördelarna med varje metod som skickar data till Adobe Analytics.
exl-id: 19353255-6356-4426-a2ef-5a2672a00eca
feature: Implementation Basics
source-git-commit: 61264d9f4ff2f1e961a613b81461efa826bc3d23
workflow-type: tm+mt
source-wordcount: '501'
ht-degree: 3%

---

# Jämför implementeringsmetoder

Jämför de olika metoderna för att implementera Adobe Analytics med varandra. Du kan använda de här tabellerna för att hjälpa din organisation att fastställa det bästa sättet att skicka data till Adobe. Klicka på varje kolumn för mer specifik information.

## Webb

| | [AppMeasurement](/help/implement/js/overview.md) | [Adobe Analytics-tillägg](/help/implement/launch/overview.md) | [Webb-SDK](/help/implement/aep-edge/web-sdk/overview.md#web-sdk) | [Web SDK-tillägg](/help/implement/aep-edge/web-sdk/overview.md#web-sdk-extension) |
| --- | --- | --- | --- | --- |
| Implementeringskrav | Referens `AppMeasurement.js` på varje sida, definiera variabler, skicka data med `s.t()` till Adobe Analytics | Läs in referenstaggar på varje sida med användargränssnittet för datainsamling för att definiera variabler och skicka data till Adobe Analytics | Referens `Alloy.js` på varje sida använder `alloy("sendEvent",{})` för att skapa XDM-objekt och skicka önskade data med Edge Network till Adobe Analytics | Inläsare av referenstaggar på varje sida använder användargränssnittet för datainsamling för att komponera XDM-objekt och skicka önskade data med Edge Network till Adobe Analytics |
| Datamål | Skickat direkt till Adobe Analytics | Skickat direkt till Adobe Analytics | Skickat till Adobe Experience Platform Edge som vidarebefordrar data till Adobe Analytics | Skickat till Adobe Experience Platform Edge som vidarebefordrar data till Adobe Analytics |
| Svårighet att göra implementeringsjusteringar | Kräver åtkomst till webbplatskod för varje implementeringsändring | Ändra webbplatskoden en gång för att installera loader-taggen. Alla ytterligare implementeringsuppdateringar kan göras i användargränssnittet för datainsamling | Kräver åtkomst till webbplatskod för varje implementeringsändring | Ändra webbplatskoden en gång för att installera loader-taggen. Alla ytterligare implementeringsuppdateringar kan göras i användargränssnittet för datainsamling |
| Så här hanteras A4T | A4T-anrop ingår i träffar som skickas till Adobe | A4T-anrop ingår i träffar som skickas till Adobe | A4T-anrop skickas som separata träffar | A4T-anrop skickas som separata träffar |
| Kontextdata | Använd `s.contextData`. | Använd `s.contextData` i egna kodblock | Alla omappade fält skickas automatiskt som `a.x.*` kontextdatavariabler. | Alla omappade fält skickas automatiskt som `a.x.*` kontextdatavariabler. |

{style="table-layout:auto"}

## Mobiler och andra

>[!CAUTION]
>
>Stöd för version 4 Mobile SDK upphörde den 31 augusti 2021. Mer information finns i [Vanliga frågor om att supporten ska upphöra för SDK:er för version 4 för mobila enheter](https://developer.adobe.com/client-sdks/documentation/v4-end-of-life-faq/).


| | [Mobil-SDK](/help/implement/aep-edge/mobile-sdk/overview.md) | [Server-API](/help/implement/aep-edge/server-api/overview.md) |
| --- | --- | --- |
| Implementeringskrav | Läs in referenstaggar i appen och använd sedan direkta API-anrop eller regler i användargränssnittet för datainsamling för att skapa XDM-objekt och skicka önskade data med Edge Network till Adobe Analytics | Använd Edge Network Server-API:er för att komponera XDM-objekt och skicka önskade data med Edge Network till Adobe Analytics |
| Datamål | Skickat till Adobe Experience Platform Edge som vidarebefordrar data till Adobe Analytics | Skickat till Adobe Experience Platform Edge som vidarebefordrar data till Adobe Analytics |
| Svårighet att göra implementeringsjusteringar | Ändra programkoden där direkta API-anrop görs eller gör ändringar i användargränssnittet för datainsamling | Kräver åtkomst till appkod för varje implementeringsändring |
| Så här hanteras A4T | A4T-anrop skickas som separata träffar | A4T-anrop skickas som separata träffar |
| Kontextdata | Alla omappade fält skickas automatiskt som `a.x.*` kontextdatavariabler. | Alla omappade fält skickas automatiskt som `a.x.*` kontextvariabler |

{style="table-layout:auto"}
