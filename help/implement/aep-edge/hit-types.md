---
title: Edge Network händelsetyper i Adobe Analytics
description: Hur Adobe Analytics tolkar händelser som tagits emot från Edge Network.
feature: Implementation Basics
role: Admin, Developer
exl-id: 31085025-9c38-4375-8dfb-4fded6542ca7
source-git-commit: 6e500007e10086c0ff8108856a3563d7702f1130
workflow-type: tm+mt
source-wordcount: '274'
ht-degree: 0%

---

# Edge Network händelsetyper i Adobe Analytics

Adobe Analytics behandlar träffar på olika sätt beroende på vilka funktioner du anropar i AppMeasurement. [`s.t`](/help/implement/vars/functions/t-method.md) och [`s.tl`](/help/implement/vars/functions/tl-method.md) inkluderar eller utelämnar till exempel vissa dimensioner och stegvisa sidvyer på olika sätt. Adobe Experience Platform innehåller bara kommandot `sendEvent`. Specifika egenskaper i `xdm`-nyttolasten avgör hur data tolkas i Adobe Analytics.

Edge Network använder följande logik för att avgöra vilka sidor i Adobe Analytics som visas och vilka länkhändelser som används:

| XDM-nyttolasten innehåller... | Adobe Analytics... |
|---|---|
| `xdm.web.webPageDetails.name` eller `xdm.web.webPageDetails.URL` och nej `xdm.web.webInteraction.type` | hanterar nyttolast för en **sidvy** |
| `xdm.eventType = web.webPageDetails.pageViews` | hanterar nyttolast för en **sidvy** |
| `xdm.web.webInteraction.type` och (`xdm.web.webPageDetails.name` eller `xdm.web.webPageDetails.url`) | hanterar nyttolast för en **link-händelse** <br/>Anger även `xdm.web.webPageDetails.name` och `xdm.web.webPageDetails.URL` som `null` |
| no `xdm.web.webInteraction.type` och no `xdm.webPageDetails.name` och no `xdm.web.webPageDetails.URL` | släpper nyttolasten och ignorerar data |

| Dataobjektets nyttolast innehåller.. | Adobe Analytics... |
|---|---|
| `data.__adobe.analytics.pageName` eller `data.__adobe.analytics.pageURL` och nej `data.__adobe.analytics.linkType` | hanterar nyttolast för en **sidvy** |
| `data.__adobe.analytics.linkType` och (`data.__adobe.analytics.linkName` eller `data.__adobe.analytics.linkURL`) | hanterar nyttolast för en **link-händelse** <br/>Anger även `data.__adobe.analytics.pageName` och `data.__adobe.analytics.pageURL` som `null` |
| no `data.__adobe.analytics.linkType` och no `data.__adobe.analytics.pageName` och no `data.__adobe.analytics.pageURL` | släpper nyttolasten och ignorerar data |

>[!NOTE]
>
>Om du inkluderar både ett `xdm`-objekt och ett `data`-objekt i samma nyttolast, söker Adobe Analytics igenom båda objekten efter respektive fält.

Förutom att differentiera sidvyer och länkklick finns följande logik som avgör om vissa händelser kategoriseras som A4T eller ignoreras.

| XDM-nyttolasten innehåller... | Adobe Analytics... |
|---|---|
| `xdm.eventType = display` eller <br/>`xdm.eventType = decisioning.propositionDisplay` eller <br/>`xdm.eventType = personalization.request` eller <br/>`xdm.eventType = decisioning.propositionFetch` och `xdm._experience.decisioning` | behandlar nyttolast som ett **A4T**-anrop. |
| `xdm.eventType = display` eller <br/>`xdm.eventType = decisioning.propositionDisplay` eller <br/>`xdm.eventType = personalization.request` eller <br/>`xdm.eventType = decisioning.propositionFetch` och nej `xdm._experience.decisioning` | släpper nyttolasten och ignorerar data |
| `xdm.eventType = click` eller `xdm.eventType = decisioning.propositionInteract` och `xdm._experience.decisioning` och inte `web.webInteraction.type` | behandlar nyttolast som ett **A4T**-anrop. |
| `xdm.eventType = click` eller `xdm.eventType = decisioning.propositionInteract` och nej `xdm._experience.decisioning` och nej `web.webInteraction.type` | släpper nyttolasten och ignorerar data. |

Mer information finns i schemafältgruppen [Adobe Analytics ExperienceEvent Full Extension](https://experienceleague.adobe.com/sv/docs/experience-platform/xdm/field-groups/event/analytics-full-extension).
