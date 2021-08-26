---
title: Mappa XDM-data till Analytics manuellt
description: Mappa XDM-data manuellt från Experience Platform till Adobe Analytics
exl-id: 6d973b35-1558-435c-9ae5-80c012d4e7ba
source-git-commit: 7cb2489c2deaf8e75c71589895314067a010caf8
workflow-type: tm+mt
source-wordcount: '353'
ht-degree: 0%

---

# Mappa XDM-data till Analytics manuellt

Adobe Experience Platform (AEP) Web SDK innehåller hjälpmedel som hjälper dig att manuellt mappa data mellan plattformen och Analytics.

För XDM-data som inte automatiskt mappas till Analytics kan du lägga till [kontextdata](https://experienceleague.adobe.com/docs/analytics/implementation/vars/page-vars/contextdata.html) så att de matchar ditt [schema](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html). Sedan kan den användas av Analytics [bearbetningsregler](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/processing-rules/processing-rules-configuration/t-processing-rules.html) för att fylla i Analytics-variabler.

Du kan också använda en standarduppsättning med åtgärder och produktlistor för att skicka eller hämta data med [AEP Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en).

## Kontextdata

XDM-data som ska användas av Analytics förenklas med punktnotation och blir tillgängliga som `contextData`. I följande lista över värdepar visas ett exempel på `context data`:

```javascript
{
          "bh": "900",
          "bw": "1680",
          "c": "24",
          "c.a.d.key.[0]": "value1",
          "c.a.d.key.[1]": "value2",
          "c.a.d.object.key1": "value1",
          "c.a.d.object.key2.[0]": "value2",
          "c.a.x.environment.browserdetails.javascriptenabled": "true",
          "c.a.x.environment.type": "browser",
          "cust_hit_time_gmt": "1579781427",
          "g": "https://example.com/home",
          "gn": "home",
          "j": "1.8.5",
          "k": "Y",
          "s": "1680x1050",
          "tnta": "218287:1:0|0,218287:1:0|2,218287:1:0|1,218287:1:0|32767,218287:1:0|1,218287:1:0|0,218287:1:0|1,218287:1:0|0,218287:1:0|1",
          "user_agent": "Mozilla/5.0 AppleWebKit/537.36 Safari/537.36",
          "v": "Y"
        }
```

## Behandlingsregler

Alla data som samlas in av edge-nätverket kan nås via [bearbetningsregler](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/processing-rules/processing-rules-configuration/t-processing-rules.html). I Analytics kan ni använda bearbetningsregler för att införliva kontextdata i Analytics-variabler.

I följande regel är Analytics till exempel inställt på att fylla i **interna söktermer (eVar2)** med data som är associerade med **a.x_atag.search.term(Context Data)**.

![](assets/examplerule.png)


## XDM-schema

Experience Platform använder scheman för att beskriva datastrukturen på ett konsekvent och återanvändbart sätt. Genom att definiera data på ett enhetligt sätt i olika system blir det enklare att behålla sin betydelse och därmed få värde av data. Kontextdata för analyser fungerar med strukturen som definieras av schemat.

I följande exempel visas hur kommandot [`event`](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/tracking-events.html) kan användas med alternativet `xdm` för att skicka och hämta data med AEP Web SDK. I det här exemplet matchar kommandot `event` schemat [ExperienceEvent Commerce Details](https://github.com/adobe/xdm/blob/1c22180490558e3c13352fe3e0540cb7e93c69ca/docs/reference/context/experienceevent-commerce.schema.md) så att värdena productListItems `name` och `SKU` spåras:


```
alloy("event",{
  "xdm":{
    "commerce":{
      "productViews":{
        "value":1
      }
    },
    "productListItems":[
      {
        "SKU":"HT105",
        "name":"Large Field Hat",
      },
      {
        "SKU":"HT104",
        "name":"Small Field Hat",
      }
    ]
  }
});
```

Mer information om att spåra händelser med AEP Web SDK finns i [Spåra händelser](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/tracking-events.html).
