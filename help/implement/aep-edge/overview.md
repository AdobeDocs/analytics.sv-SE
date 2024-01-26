---
title: Implementera Adobe Analytics med Adobe Experience Platform Edge
description: Översikt över hur du använder XDM-data från Experience Platform i Adobe Analytics
exl-id: 7d8de761-86e3-499a-932c-eb27edd5f1a3
feature: Implementation Basics
role: Admin, Developer, Leader
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '324'
ht-degree: 0%

---

# Implementera Adobe Analytics med Adobe Experience Platform Edge

Med Adobe Experience Platform Edge kan ni skicka data till flera produkter på en central plats. Experience Edge vidarebefordrar lämplig information till önskade produkter. Med det här konceptet kan ni konsolidera implementeringsinsatser, särskilt genom att sprida flera datalösningar.

Adobe erbjuder tre sätt att skicka data till Experience Edge:

* **[Adobe Experience Platform Web SDK](web-sdk/overview.md)**: Använd Web SDK-tillägget i Adobe Experience Platform Data Collection för att skicka data till Edge.
* **[Adobe Experience Platform Mobile SDK](mobile-sdk/overview.md)**: Använd SDK-tillägget för mobiler i Adobe Experience Platform Data Collection för att skicka data till Edge.
* **[API för Adobe Experience Platform Edge Network Server](server-api/overview.md)**: Skicka data direkt till Edge med ett API.



## Hur Adobe Analytics hanterar Experience Edge-data

Data som skickas till Experience Edge måste överensstämma med scheman som baseras på [XDM (Experience Data Model)](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=sv). XDM ger flexibilitet vad gäller vilka fält som definieras som en del av händelser. När händelser når Adobe Analytics översätts dessa händelser till mer strukturerade data som Adobe Analytics kan hantera: sidvisningar eller länkhändelser.

XDM anger inte själv hur sidvyer och länkhändelser ska definieras och instruerar inte heller Adobe Analytics hur nyttolasten ska hanteras. Exempel: vissa XDM-fält i rutan som verkar vara relaterade till sidvyer eller länkhändelser, som `eventType`, `web.webPageDetails.pageViews`, eller `web.webInteraction.linkEvents` är helt implementeringsagnostiska och har ingen relevans för Adobe Analytics.

För att kunna hantera sidvyer och länkhändelser på rätt sätt, används följande logik för data som skickas till Adobe Experience Edge-nätverket och vidarebefordras till Adobe Analytics.

| XDM-nyttolasten innehåller... | Adobe Analytics... |
|---|---|
| `web.webPageDetails.name` eller `web.webPageDetails.URL` och nej `web.webInteraction.type` | hanterar nyttolast en **sidvy** |
| `web.webInteraction.type` och (`web.webInteraction.name` eller `web.webInteraction.url`) | hanterar nyttolast en **link-händelse** |
| `web.webInteraction.type` och (`web.webPageDetails.name` eller `web.webPageDetails.url`) | hanterar nyttolast en **link-händelse** <br/>`web.webPageDetails.name` och `web.webPageDetails.URL` är inställda på `null` |
| no `web.webInteraction.type` och (nej) `webPageDetails.name` och nej `web.webPageDetails.URL`) | släpper nyttolasten och ignorerar data |

{style="table-layout:auto"}

