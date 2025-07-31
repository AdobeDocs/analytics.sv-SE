---
title: Edge Network händelsetyper i Adobe Analytics
description: Hur Adobe Analytics tolkar händelser som tagits emot från Edge Network.
feature: Implementation Basics
role: Admin, Developer
source-git-commit: 8d369bd3be3ae9c075e490e108666728a2cff5dc
workflow-type: tm+mt
source-wordcount: '223'
ht-degree: 0%

---

# Edge Network händelsetyper i Adobe Analytics

Adobe Analytics behandlar träffar på olika sätt beroende på vilka funktioner du anropar i AppMeasurement. [`s.t`](/help/implement/vars/functions/t-method.md) och [`s.tl`](/help/implement/vars/functions/tl-method.md) inkluderar eller utelämnar till exempel vissa dimensioner och stegvisa sidvyer på olika sätt. Adobe Experience Platform innehåller bara kommandot `sendEvent`. Specifika egenskaper i `xdm`-nyttolasten avgör hur data tolkas i Adobe Analytics.

Edge Network använder följande logik för att avgöra vilka sidor i Adobe Analytics som visas och vilka länkhändelser som används:

| XDM-nyttolasten innehåller... | Adobe Analytics... |
|---|---|
| `xdm.web.webPageDetails.name` eller `xdm.web.webPageDetails.URL` och nej `xdm.web.webInteraction.type` | hanterar nyttolast för en **sidvy** |
| `xdm.eventType = web.webPageDetails.pageViews` | hanterar nyttolast för en **sidvy** |
| `xdm.web.webInteraction.type` och (`xdm.web.webInteraction.name` eller `xdm.web.webInteraction.url`) | hanterar nyttolast för en **link-händelse** |
| `xdm.web.webInteraction.type` och (`xdm.web.webPageDetails.name` eller `xdm.web.webPageDetails.url`) | hanterar nyttolast för en **link-händelse** <br/>Anger även `xdm.web.webPageDetails.name` och `xdm.web.webPageDetails.URL` som `null` |
| no `xdm.web.webInteraction.type` and (no `xdm.webPageDetails.name` and no `xdm.web.webPageDetails.URL`) | släpper nyttolasten och ignorerar data |

Förutom att differentiera sidvyer och länkklick finns följande logik som avgör om vissa händelser kategoriseras som A4T eller ignoreras.

| XDM-nyttolasten innehåller... | Adobe Analytics... |
| --- | --- |
| `xdm.eventType = display` eller <br/>`xdm.eventType = decisioning.propositionDisplay` eller <br/>`xdm.eventType = personalization.request` eller <br/>`xdm.eventType = decisioning.propositionFetch` och `xdm._experience.decisioning` | behandlar nyttolast som ett **A4T**-anrop. |
| `xdm.eventType = display` eller <br/>`xdm.eventType = decisioning.propositionDisplay` eller <br/>`xdm.eventType = personalization.request` eller <br/>`xdm.eventType = decisioning.propositionFetch` och nej `xdm._experience.decisioning` | släpper nyttolasten och ignorerar data |
| `xdm.eventType = click` eller `xdm.eventType = decisioning.propositionInteract` och `xdm._experience.decisioning` och inte `web.webInteraction.type` | behandlar nyttolast som ett **A4T**-anrop. |
| `xdm.eventType = click` eller `xdm.eventType = decisioning.propositionInteract` och nej `xdm._experience.decisioning` och nej `web.webInteraction.type` | släpper nyttolasten och ignorerar data. |

Mer information finns i schemafältgruppen [Adobe Analytics ExperienceEvent Full Extension](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/field-groups/event/analytics-full-extension).
