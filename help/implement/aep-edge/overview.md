---
title: Implementera Adobe Analytics med Adobe Experience Platform Edge
description: Översikt över hur du använder XDM-data från Experience Platform i Adobe Analytics
exl-id: 7d8de761-86e3-499a-932c-eb27edd5f1a3
feature: Implementation Basics
role: Admin, Developer, Leader
source-git-commit: 4453c2aa2ea70ef4d00b2bc657285287f3250c65
workflow-type: tm+mt
source-wordcount: '357'
ht-degree: 0%

---

# Implementera Adobe Analytics med Adobe Experience Platform Edge Network

Med Adobe Experience Platform Edge Network kan du skicka data till flera produkter på en central plats. Edge Network vidarebefordrar lämpliga uppgifter till de önskade produkterna. Med det här konceptet kan ni konsolidera implementeringsinsatser, särskilt genom att sprida flera datalösningar.

Adobe erbjuder tre sätt att skicka data till Edge Network:

* **[Adobe Experience Platform Web SDK](web-sdk/overview.md)**: Använd Web SDK-tillägget i Adobe Experience Platform Data Collection för att skicka data till Edge.
* **[Adobe Experience Platform Mobile SDK](mobile-sdk/overview.md)**: Använd Mobile SDK-tillägget i Adobe Experience Platform Data Collection för att skicka data till Edge.
* **[Adobe Experience Platform Edge Network Server-API](server-api/overview.md)**: Skicka data direkt till Edge med ett API.



## Hur Adobe Analytics hanterar data från Edge Network

Data som skickas till Adobe Experience Platform Edge Network kan ha följande två format:

* XDM-objekt: Följ scheman baserat på [XDM (Experience Data Model)](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=sv). XDM ger flexibilitet vad gäller vilka fält som definieras som en del av händelser. När händelser når Adobe Analytics översätts de till ett format som Adobe Analytics kan hantera.
* Dataobjekt: Skicka data till Edge Network med hjälp av specifika fält som mappats till Adobe Analytics. Edge Network identifierar förekomsten av dessa fält och vidarebefordrar dem till Adobe Analytics utan att behöva följa ett schema.

I Edge Network används följande logik för att avgöra vilka sidor i Adobe Analytics som visas och vilka länkhändelser som används:

| XDM-nyttolasten innehåller... | Adobe Analytics... |
|---|---|
| `xdm.web.webPageDetails.name` eller `xdm.web.webPageDetails.URL` och nej `xdm.web.webInteraction.type` | hanterar nyttolast för en **sidvy** |
| `xdm.web.webInteraction.type` och (`xdm.web.webInteraction.name` eller `xdm.web.webInteraction.url`) | hanterar nyttolast för en **link-händelse** |
| `web.webInteraction.type` och (`web.webPageDetails.name` eller `web.webPageDetails.url`) | anser att nyttolast är en **link-händelse** <br/>`web.webPageDetails.name` och `web.webPageDetails.URL` är inställda på `null` |
| no `web.webInteraction.type` and (no `webPageDetails.name` and no `web.webPageDetails.URL`) | släpper nyttolasten och ignorerar data |
| `xdm.eventType = display` eller <br/>`xdm.eventType = decisioning.propositionDisplay` eller <br/>`xdm.eventType = personalization.request` eller <br/>`xdm.eventType = decisioning.propositionFetch` och `xdm._experience.decisioning` | behandlar nyttolast som ett **A4T**-anrop. |
| `xdm.eventType = display` eller <br/>`xdm.eventType = decisioning.propositionDisplay` eller <br/>`xdm.eventType = personalization.request` eller <br/>`xdm.eventType = decisioning.propositionFetch` och nej `xdm._experience.decisioning` | släpper nyttolasten och ignorerar data |
| `xdm.eventType = click` eller `xdm.eventType = decisioning.propositionInteract` och `xdm._experience.decisioning` och inte `web.webInteraction.type` | behandlar nyttolast som ett **A4T**-anrop. |
| `xdm.eventType = click` eller `xdm.eventType = decisioning.propositionInteract` och nej `xdm._experience.decisioning` och nej `web.webInteraction.type` | släpper nyttolasten och ignorerar data. |

{style="table-layout:auto"}

Mer information finns i schemafältgruppen [Adobe Analytics ExperienceEvent Full Extension](https://experienceleague.adobe.com/docs/experience-platform/xdm/field-groups/event/analytics-full-extension.html).
