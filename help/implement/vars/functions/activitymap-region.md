---
title: ActivityMap.region
description: Anpassa hur Activity Map samlar in det område som du klickar på.
feature: Appmeasurement Implementation
role: Admin, Developer
exl-id: 9bbdb124-b865-4431-8a98-9814c3f2e65c
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '202'
ht-degree: 0%

---

# ActivityMap.region

Variabeln `ActivityMap.region` gör att du kan åsidosätta logiken som används i Activity Map för att ange regionvärden. Den här variabeln är användbar i områden där du vill ha mer kontroll än vad [`ActivityMap.regionExclusions`](../config-vars/activitymap-regionexclusions.md) erbjuder.

>[!CAUTION]
>Den här variabeln åsidosätter helt Activity Map logik. Om du ställer in en åsidosättningsfunktion här som returnerar felaktiga värden kan datainsamlingsproblem uppstå med Activity Map-dimensioner och Activity Map-övertäckningen.

## Åsidosätta regionsvärden med Web SDK

Du kan använda [`OnBeforeLinkClickSend`](https://experienceleague.adobe.com/sv/docs/experience-platform/web-sdk/commands/configure/onbeforelinkclicksend)-återanrop för att ändra SDK-nyttolasten för webben eller avbryta sändning av data.

## Regionåsidosättning med Adobe Analytics-tillägg

Det finns inget dedikerat fält i Adobe Analytics-tillägget som kan använda den här variabeln. Använd den anpassade kodredigeraren enligt AppMeasurement-syntax.

## ActivityMap.region i AppMeasurement och den anpassade kodredigeraren för Analytics-tillägget

Tilldela variabeln en funktion som:

* Tar emot det HTML-element som du klickade på, och
* Returnerar ett strängvärde. Det här strängvärdet är det slutliga värdet som används för dimensionen [Activity Map Region](/help/components/dimensions/activity-map-region.md).

Om returvärdet är [false](https://developer.mozilla.org/en-US/docs/Glossary/Falsy) rensas alla Activity Map-kontextdatavariabler och inga länkdata spåras.

## Exempel

Använd ett gement taggnamn som region:

```js
s.ActivityMap.region = function(clickedElement) {
  while (clickedElement && (clickedElement = clickedElement.parentNode)) {
    var regionId = clickedElement.tagName;
    if (regionId) {
      return regionId.toLowerCase();
    }
  }
}
```

Använd specifika önskade klassnamn som region:

```js
s.ActivityMap.region = function(ele) {
  var className,
  classNames = {
    'header': 1,
    'navbar': 1,
    'left-content': 1,
    'main-content': 1,
    'footer': 1,
  };
  while ((ele && (ele = ele.parentNode))) {
    if ((className = ele.className)) {
      let classes = className.split(' ');
      for (let i = 0; i < classes.length; i++) {
        if (classNames[classes[i]]) {
          return classes[i];
        }
      }
    }
  }
  return "BODY";
}
```
