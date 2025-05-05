---
title: Implementera Adobe Analytics med Adobe Experience Platform Web SDK
description: Använd Web SDK för att skicka data till Adobe Analytics.
exl-id: 97f8d650-247f-4386-b4d2-699f3dab0467
feature: Implementation Basics
role: Admin, Developer, Leader
source-git-commit: d6c16d8841110e3382248f4c9ce3c2f2e32fe454
workflow-type: tm+mt
source-wordcount: '210'
ht-degree: 0%

---

# Implementera Adobe Analytics med Adobe Experience Platform Web SDK

Du kan använda [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/web-sdk/home.html?lang=sv-SE) för att skicka data till Adobe Analytics. Det finns två huvudmetoder för att implementera Web SDK, och varje metod har två implementeringstyper:

| | **Migrera från AppMeasurementet** | **Ren implementering av Web SDK** |
| --- | --- | --- |
| **Använd taggar** | [Migrera från analystillägget till Web SDK-tillägget](analytics-extension-to-web-sdk.md) | [Skicka data till Adobe Analytics med Web SDK-tillägget](web-sdk-tag-extension.md) |
| **Använd JavaScript** | [Migrera från AppMeasurement till Web SDK JavaScript-biblioteket](appmeasurement-to-web-sdk.md) | [Skicka data till Adobe Analytics med Web SDK JavaScript-biblioteket](web-sdk-javascript-library.md) |

Om din organisation behöver en ny Web SDK-implementering och planerar att använda Customer Journey Analytics i framtiden rekommenderar Adobe en ren Web SDK-implementering med ditt eget schema. Se [Importera data via Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/sv/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/edge-network/aepwebsdk) i användarhandboken för Customer Journey Analytics.

## Ytterligare resurser

Taggar kan anpassas mycket. Läs mer om hur du får ut mesta möjliga av Adobe Analytics genom att inkludera rätt data i implementeringen.

- [Taggar, dokumentation](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html?lang=sv-SE#): Lär dig hur gränssnittet fungerar och vilka tillägg som är tillgängliga.

- [Adobe Experience Platform Web SDK-dokumentation](https://experienceleague.adobe.com/docs/web-sdk.html?lang=sv-SE)
