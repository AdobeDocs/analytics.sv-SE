---
title: Implementera Adobe Analytics med Adobe Experience Platform Edge
description: Översikt över hur du använder XDM-data från Experience Platform i Adobe Analytics
exl-id: 7d8de761-86e3-499a-932c-eb27edd5f1a3
feature: Implementation Basics
role: Admin, Developer, Leader
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '510'
ht-degree: 0%

---

# Implementera Adobe Analytics med Adobe Experience Platform Edge Network

Med Adobe Experience Platform Edge Network kan du skicka data till flera produkter på en central plats. Edge Network vidarebefordrar lämplig information till de önskade produkterna. Med det här konceptet kan ni konsolidera implementeringsinsatser, särskilt genom att sprida flera datalösningar. Adobe Analytics är en av de produkter som du kan skicka data till med Edge Network.

## Hur Adobe Analytics hanterar Edge Network data

Eftersom data som skickas till Edge Network och AppMeasurement fungerar annorlunda avgör Edge Network nyttolast hur Adobe Analytics hanterar träffen. Mer information finns i [Edge Network händelsetyper i Adobe Analytics](hit-types.md).

Data som skickas till Adobe Experience Platform Edge Network kan ha följande tre format: **XDM-objekt**, **Dataobjekt** och **Kontextdata**. När en datastream skickar data till Adobe Analytics, översätts de till ett format som Adobe Analytics kan hantera.

## `xdm` objekt

Följ scheman som du skapar baserat på [XDM](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/home) (Experience Data Model). XDM ger flexibilitet vad gäller vilka fält som definieras som en del av händelser. Om du vill använda ett fördefinierat schema som är specifikt för Adobe Analytics kan du lägga till [Adobe Analytics ExperienceEvent-schemafältgruppen](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/field-groups/event/analytics-full-extension) i ditt schema. När du har lagt till det kan du fylla i det här schemat med hjälp av objektet `xdm` i Web SDK och skicka data till en rapportserie. När data kommer till Edge Network översätts XDM-objektet till ett format som Adobe Analytics förstår.

Mer information om en fullständig referens till XDM-fält och hur de mappas till Analytics-variabler finns i [Mappning av XDM-objektvariabeln till Adobe Analytics](xdm-var-mapping.md).

>[!TIP]
>
>Om du planerar att gå över till [Customer Journey Analytics](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-landing) i framtiden rekommenderar Adobe att du inte använder Adobe Analytics schemafältgrupp. I stället rekommenderar Adobe [att du skapar ett eget schema](https://experienceleague.adobe.com/en/docs/analytics-platform/using/compare-aa-cja/upgrade-to-cja/schema/cja-upgrade-schema-architect) och använder datastream-mappning för att fylla i de önskade Analytics-variablerna. Den här strategin låser inte in dig i ett schema med props och eVars när du är redo att gå över till Customer Journey Analytics.

## `data` objekt

Som ett alternativ till att använda objektet `xdm` kan du använda objektet `data` i stället. Dataobjektet är inriktat på implementeringar som för närvarande använder AppMeasurement, vilket gör uppgraderingen till Web SDK mycket enklare. Edge Network identifierar att det finns fält som är specifika för Adobe Analytics utan att du behöver anpassa dig till ett schema.

Se [Variabelmappning av dataobjekt till Adobe Analytics](data-var-mapping.md) för en fullständig referens till dataobjektfält och hur de mappas till Analytics-variabler.

## Sammanhangsdatavariabler

Skicka data till Edge Network i valfritt format. Alla fält som inte automatiskt mappas till `xdm` eller `data` objektfält inkluderas som [kontextdatavariabler](/help/implement/vars/page-vars/contextdata.md) när de vidarebefordras till Adobe Analytics. Du måste sedan använda [Bearbetningsregler](/help/admin/tools/manage-rs/edit-settings/general/processing-rules/pr-overview.md) för att mappa de önskade fälten till deras respektive Analytics-variabler.

Om du till exempel har ett anpassat XDM-schema som ser ut så här:

```json
{
  "xdm": {
    "key": "value",
    "animal": {
      "species": "Raven",
      "size": "13 inches"
    },
    "array": [
      "v0",
      "v1",
      "v2"
    ],
    "objectArray":[{
      "ad1": "300x200",
      "ad2": "60x240",
      "ad3": "600x50"
    }]
  }
}
```

Då är de här fälten de kontextdatanycklar som är tillgängliga i bearbetningsregelgränssnittet:

```javascript
a.x.key // value
a.x.animal.species // Raven
a.x.animal.size // 13 inches
a.x.array.0 // v0
a.x.array.1 // v1
a.x.array.2 // v2
a.x.objectarray.0.ad1 // 300x200
a.x.objectarray.1.ad2 // 60x240
a.x.objectarray.2.ad3 // 600x50
```
