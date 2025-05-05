---
title: ActivityMap.region
description: Anpassa hur Activity Map samlar in det område som du klickar på.
feature: Variables
role: Admin, Developer
source-git-commit: 1fb57590714ad2412323416289dee967eef07fad
workflow-type: tm+mt
source-wordcount: '202'
ht-degree: 0%

---

# ActivityMap.region

Variabeln `ActivityMap.region` gör att du kan åsidosätta logiken som Activity Map använder för att ange regionvärden. Den här variabeln är användbar i områden där du vill ha mer kontroll än vad [`ActivityMap.regionExclusions`](../config-vars/activitymap-regionexclusions.md) erbjuder.

>[!CAUTION]
>Den här variabeln åsidosätter helt logiken i Activity Map. Om du ställer in en åsidosättningsfunktion här som returnerar felaktiga värden kan datainsamlingsproblem uppstå med Activity Map och övertäckningen Activity Map.

## Åsidosätta regionsvärden med Web SDK

Du kan använda [`OnBeforeLinkClickSend`](https://experienceleague.adobe.com/sv/docs/experience-platform/web-sdk/commands/configure/onbeforelinkclicksend)-återanrop för att ändra Web SDK-nyttolasten eller avbryta sändning av data.

## Regionåsidosättning med Adobe Analytics-tillägg

Det finns inget dedikerat fält i Adobe Analytics-tillägget som kan använda den här variabeln. Använd den anpassade kodredigeraren enligt AppMeasurementen syntax.

## ActivityMap.region i AppMeasurementet och den anpassade kodredigeraren för Analytics-tillägget

Tilldela variabeln en funktion som:

* Tar emot elementet HTML som du klickade på, och
* Returnerar ett strängvärde. Det här strängvärdet är det slutliga värdet som används för dimensionen [Activity Map region](/help/components/dimensions/activity-map-region.md).

Om returvärdet är [false](https://developer.mozilla.org/en-US/docs/Glossary/Falsy) rensas alla kontextdatavariabler i Activity Map och inga länkdata spåras.

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
