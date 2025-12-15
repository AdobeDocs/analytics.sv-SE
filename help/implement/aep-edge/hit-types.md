---
title: Edge Network händelsetyper i Adobe Analytics
description: Hur Adobe Analytics tolkar händelser som tagits emot från Edge Network.
feature: Implementation Basics
role: Admin, Developer
exl-id: 31085025-9c38-4375-8dfb-4fded6542ca7
source-git-commit: 0096a53505b3b1bc925c813c2c6c11ee3c7ee0c0
workflow-type: tm+mt
source-wordcount: '425'
ht-degree: 0%

---

# Edge Network händelsetyper i Adobe Analytics

Adobe Analytics behandlar träffar på olika sätt beroende på vilka funktioner du anropar i AppMeasurement. [`s.t`](/help/implement/vars/functions/t-method.md) och [`s.tl`](/help/implement/vars/functions/tl-method.md) inkluderar eller utelämnar till exempel vissa dimensioner och stegvisa [sidvyer](/help/components/metrics/page-views.md) på ett annat sätt. Adobe Experience Platform innehåller bara kommandot [`sendEvent`](https://experienceleague.adobe.com/sv/docs/experience-platform/collection/js/commands/sendevent/overview). Specifika egenskaper i nyttolasten [`xdm`](https://experienceleague.adobe.com/sv/docs/experience-platform/collection/js/commands/sendevent/xdm) eller [`data`](https://experienceleague.adobe.com/sv/docs/experience-platform/collection/js/commands/sendevent/data) avgör hur data tolkas i Adobe Analytics.

Edge Network använder följande logik för att fastställa Adobe Analytics [sidvisningar](/help/components/metrics/page-views.md) och [länkhändelser](/help/components/metrics/page-events.md):

## Sidvyer och länkhändelser med objektet `xdm`

| XDM-nyttolasten innehåller... | Adobe Analytics... |
|---|---|
| `xdm.web.webPageDetails.name` eller `xdm.web.webPageDetails.URL` och nej `xdm.web.webInteraction.type` | hanterar nyttolast för en **sidvy** |
| `xdm.eventType = web.webpagedetails.pageViews` | hanterar nyttolast för en **sidvy** |
| `xdm.web.webInteraction.type` och (`xdm.web.webPageDetails.name` eller `xdm.web.webPageDetails.URL`) | hanterar nyttolast för en **link-händelse** <br/>Anger även `xdm.web.webPageDetails.name` och `xdm.web.webPageDetails.URL` som `null` |
| `xdm.web.webInteraction.type` och (`xdm.web.webInteraction.name` eller `xdm.web.webInteraction.URL`) | hanterar nyttolast för en **link-händelse** <br/>Anger även `xdm.web.webPageDetails.name` och `xdm.web.webPageDetails.URL` till `null` om det finns |
| no `xdm.web.webInteraction.type` och no `xdm.web.webPageDetails.name` och no `xdm.web.webPageDetails.URL` | släpper nyttolasten och ignorerar data |

>[!TIP]
>
>XDM-fältnamn i nyttolasten är skiftlägeskänsliga (till exempel `webPageDetails.URL`). Fältet `xdm.eventType` är ett strängvärde med en egen uppsättning godkända värden, och skiftläget i dessa värden kanske inte matchar XDM-fältnamn. Godkända värden finns i fältet `eventType` i klassen [XDM ExperienceEvent](https://experienceleague.adobe.com/sv/docs/experience-platform/xdm/classes/experienceevent#eventType).

+++Minimal sidvy med `xdm` fält

```json
{
  "xdm": {
    "web": {
      "webPageDetails": {
        "name": "Example page",
        "URL": "https://example.com/page"
      }
    }
  }
}
```

+++

+++Minimal sidvy med `xdm.eventType`

```json
{
  "xdm": {
    "eventType": "web.webpagedetails.pageViews"
  }
}
```

+++

+++Minimal länkhändelse med rekommenderade fält

```json
{
  "xdm": {
    "web": {
      "webInteraction": {
        "type": "other",
        "name": "Header nav: Pricing",
        "URL": "https://example.com/pricing"
      }
    }
  }
}
```

+++

## Sidvyer och länkhändelser med objektet `data`

| Dataobjektets nyttolast innehåller.. | Adobe Analytics... |
|---|---|
| `data.__adobe.analytics.pageName` eller `data.__adobe.analytics.pageURL` och nej `data.__adobe.analytics.linkType` | hanterar nyttolast för en **sidvy** |
| `data.__adobe.analytics.linkType` och (`data.__adobe.analytics.linkName` eller `data.__adobe.analytics.linkURL`) | hanterar nyttolast för en **link-händelse** <br/>Anger även `data.__adobe.analytics.pageName` och `data.__adobe.analytics.pageURL` som `null` |
| no `data.__adobe.analytics.linkType` och no `data.__adobe.analytics.pageName` och no `data.__adobe.analytics.pageURL` | släpper nyttolasten och ignorerar data |

+++Minimal sidvy med `data` fält

```json
{
  "data": {
    "__adobe": {
      "analytics": {
        "pageName": "Example page",
        "pageURL": "https://example.com/page"
      }
    }
  }
}
```

+++

+++Minimal länkhändelse med `data` fält

```json
{
  "data": {
    "__adobe": {
      "analytics": {
        "linkType": "o",
        "linkName": "Header nav: Pricing",
        "linkURL": "https://example.com/pricing"
      }
    }
  }
}
```

+++

>[!NOTE]
>
>Om du inkluderar både ett `xdm`-objekt och ett `data`-objekt i samma nyttolast, söker Adobe Analytics igenom båda objekten efter respektive fält.

## A4T och beslutsrelaterade händelser

Förutom att differentiera sidvyer och länkhändelser avgör följande logik om vissa beslutshändelser kategoriseras som A4T eller ignoreras.

| XDM-nyttolasten innehåller... | Adobe Analytics... |
|---|---|
| `xdm.eventType = decisioning.propositionDisplay` och `xdm._experience.decisioning` | behandlar nyttolast som ett **A4T**-anrop. |
| `xdm.eventType = decisioning.propositionDisplay` och inte `xdm._experience.decisioning` | släpper nyttolasten och ignorerar data |
| `xdm.eventType = decisioning.propositionInteract` och `xdm._experience.decisioning` och inte `xdm.web.webInteraction.type` | behandlar nyttolast som ett **A4T**-anrop. |
| `xdm.eventType = decisioning.propositionInteract` och inte `xdm._experience.decisioning` och inte `xdm.web.webInteraction.type` | släpper nyttolasten och ignorerar data. |
| `xdm.eventType = decisioning.propositionFetch` | släpper nyttolasten och ignorerar data |

>[!TIP]
>
>Följande `eventType`-värden är inaktuella. Observera att dessa värden påverkar logiken på samma sätt som deras nuvarande motsvarigheter:
>
>* Händelsetypen `display` är inaktuell. Använd `decisioning.propositionDisplay` i stället.
>* Händelsetypen `click` är inaktuell. Använd `decisioning.propositionInteract` i stället.
>* Händelsetypen `personalization.request` är inaktuell. Använd `decisioning.propositionFetch` i stället.

+++Minimal A4T-visning

```json
{
  "xdm": {
    "eventType": "decisioning.propositionDisplay",
    "_experience": {
      "decisioning": {
        "propositions": [
          {
            "id": "example-proposition-id",
            "scope": "example-scope",
            "scopeDetails": { "decisionProvider": "AJO" }
          }
        ],
        "propositionEventType": { "display": 1 }
      }
    }
  }
}
```

+++

+++Minimal A4T-interaktion

```json
{
  "xdm": {
    "eventType": "decisioning.propositionInteract",
    "_experience": {
      "decisioning": {
        "propositions": [
          {
            "id": "example-proposition-id",
            "scope": "example-scope",
            "scopeDetails": { "decisionProvider": "AJO" }
          }
        ],
        "propositionEventType": { "interact": 1 }
      }
    }
  }
}
```

+++

Mer information finns i schemafältgruppen [Adobe Analytics ExperienceEvent Full Extension](https://experienceleague.adobe.com/sv/docs/experience-platform/xdm/field-groups/event/analytics-full-extension).
