---
title: Implementera Adobe Analytics med Adobe Experience Platform Edge
description: Översikt över hur du använder XDM-data från Experience Platform i Adobe Analytics
exl-id: 7d8de761-86e3-499a-932c-eb27edd5f1a3
feature: Implementation Basics
role: Admin, Developer, Leader
source-git-commit: 8e701a3da6f04ccf2d7ac3abd10c6df86feb00a7
workflow-type: tm+mt
source-wordcount: '395'
ht-degree: 0%

---

# Implementera Adobe Analytics med Adobe Experience Platform Edge Network

Med Adobe Experience Platform Edge Network kan du skicka data till flera produkter på en central plats. Edge Network vidarebefordrar lämplig information till de önskade produkterna. Med det här konceptet kan ni konsolidera implementeringsinsatser, särskilt genom att sprida flera datalösningar.

Adobe erbjuder tre sätt att skicka data till Edge Network:

* **[Adobe Experience Platform Web SDK](web-sdk/overview.md)**: Använd Web SDK-tillägget i Adobe Experience Platform Data Collection för att skicka data till Edge.
* **[Adobe Experience Platform Mobile SDK](mobile-sdk/overview.md)**: Använd Mobile SDK-tillägget i Adobe Experience Platform Data Collection för att skicka data till Edge.
* **[Adobe Experience Platform Edge Network API](api/overview.md)**: Skicka data direkt till Edge Network med ett API.

## Hur Adobe Analytics hanterar Edge Network data

Data som skickas till Adobe Experience Platform Edge Network kan ha följande två format:

* XDM-objekt: Följ scheman baserat på [XDM (Experience Data Model)](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=sv). XDM ger flexibilitet vad gäller vilka fält som definieras som en del av händelser. När händelser når Adobe Analytics översätts de till ett format som Adobe Analytics kan hantera.
* Dataobjekt: Skicka data till Edge Network med specifika fält som mappats till Adobe Analytics. Edge Network identifierar förekomsten av dessa fält och vidarebefordrar dem till Adobe Analytics utan att behöva följa ett schema.

Edge Network använder följande logik för att avgöra vilka sidor i Adobe Analytics som visas och vilka länkhändelser som används:

| XDM-nyttolasten innehåller... | Adobe Analytics... |
|---|---|
| `xdm.web.webPageDetails.name` eller `xdm.web.webPageDetails.URL` och nej `xdm.web.webInteraction.type` | hanterar nyttolast för en **sidvy** |
| `xdm.eventType = web.webPageDetails.pageViews` | hanterar nyttolast för en **sidvy** |
| `xdm.web.webInteraction.type` och (`xdm.web.webInteraction.name` eller `xdm.web.webInteraction.url`) | hanterar nyttolast för en **link-händelse** |
| `xdm.web.webInteraction.type` och (`xdm.web.webPageDetails.name` eller `xdm.web.webPageDetails.url`) | hanterar nyttolast för en **link-händelse** <br/>Anger även `xdm.web.webPageDetails.name` och `xdm.web.webPageDetails.URL` som `null` |
| no `xdm.web.webInteraction.type` and (no `xdm.webPageDetails.name` and no `xdm.web.webPageDetails.URL`) | släpper nyttolasten och ignorerar data |

{style="table-layout:auto"}

Förutom att differentiera sidvyer och länkklick finns följande logik som avgör om vissa händelser kategoriseras som A4T eller ignoreras.

| XDM-nyttolasten innehåller... | Adobe Analytics... |
| --- | --- |
| `xdm.eventType = display` eller <br/>`xdm.eventType = decisioning.propositionDisplay` eller <br/>`xdm.eventType = personalization.request` eller <br/>`xdm.eventType = decisioning.propositionFetch` och `xdm._experience.decisioning` | behandlar nyttolast som ett **A4T**-anrop. |
| `xdm.eventType = display` eller <br/>`xdm.eventType = decisioning.propositionDisplay` eller <br/>`xdm.eventType = personalization.request` eller <br/>`xdm.eventType = decisioning.propositionFetch` och nej `xdm._experience.decisioning` | släpper nyttolasten och ignorerar data |
| `xdm.eventType = click` eller `xdm.eventType = decisioning.propositionInteract` och `xdm._experience.decisioning` och inte `web.webInteraction.type` | behandlar nyttolast som ett **A4T**-anrop. |
| `xdm.eventType = click` eller `xdm.eventType = decisioning.propositionInteract` och nej `xdm._experience.decisioning` och nej `web.webInteraction.type` | släpper nyttolasten och ignorerar data. |

{style="table-layout:auto"}

Mer information finns i schemafältgruppen [Adobe Analytics ExperienceEvent Full Extension](https://experienceleague.adobe.com/docs/experience-platform/xdm/field-groups/event/analytics-full-extension.html).
