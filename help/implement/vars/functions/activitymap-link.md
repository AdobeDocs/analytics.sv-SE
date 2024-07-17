---
title: ActivityMap.link
description: Anpassa hur Activity Map ska samla in länken som klickas.
feature: Variables
role: Admin, Developer
source-git-commit: 72b38970e573b928e4dc4a8c8efdbfb753be0f4e
workflow-type: tm+mt
source-wordcount: '292'
ht-degree: 0%

---

# ActivityMap.link

Variabeln `ActivityMap.link` gör att du kan åsidosätta logiken som Activity Map använder för att ange länkvärden. Den här variabeln är användbar i områden där du vill ha mer kontroll än vad [`ActivityMap.linkExclusions`](../config-vars/activitymap-linkexclusions.md) erbjuder.

>[!CAUTION]
>Den här variabeln åsidosätter helt logiken i Activity Map. Om du ställer in en åsidosättningsfunktion här som returnerar felaktiga värden kan datainsamlingsproblem uppstå med Activity Map och övertäckningen Activity Map.

## Åsidosätta länkvärden med Web SDK

Du kan använda [`OnBeforeLinkClickSend`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/onbeforelinkclicksend)-återanrop för att ändra Web SDK-nyttolasten eller avbryta sändning av data.

## Länkåsidosättning med Adobe Analytics-tillägget

Det finns inget dedikerat fält i Adobe Analytics-tillägget som kan använda den här variabeln. Använd den anpassade kodredigeraren enligt AppMeasurementen syntax.

## ActivityMap.link i AppMeasurementet och den anpassade kodredigeraren för Analytics-tillägget

Tilldela variabeln en funktion som:

* Tar emot elementet HTML som du klickade på, och
* Returnerar ett strängvärde. Det här strängvärdet är det slutliga värdet som används för dimensionen [Activity Map Link](/help/components/dimensions/activity-map-link.md).

Om returvärdet är [false](https://developer.mozilla.org/en-US/docs/Glossary/Falsy) rensas alla kontextdatavariabler i Activity Map och inga länkdata spåras.

## Exempel

Använd bara rubrikattributet från `<a>`-taggar. Om rubrikattributet inte finns spåras ingen länk.

```js
s.ActivityMap.link = function(clickedElement) {
  var linkId;
  if (clickedElement && clickedElement.tagName.toUpperCase() === 'A') {
    linkId = clickedElement.getAttribute('title');
  }
  return linkId;
}
```

Returnera det manuellt angivna länknamnet i `s.tl` om det finns, annars returneras länkens URL.

```js
s.ActivityMap.link = function(ele, linkName) {
  if (linkName) {
    return linkName;
  }
  if (ele && ele.tagName == 'A' && ele.href) {
    return ele.href;
  }
}
```

I stället för att helt ersätta standardlänklogiken kan du ändra den villkorligt.

```html
<script>
  // Copy the original link function
  var originalLinkFunction = s.ActivityMap.link;
  // Return the link name from s.tl, a modified activity map value, or the original activity map value
  s.ActivityMap.link = function(element,linkName)
  {
    return linkName || customFunction(element) || originalLinkFunction(element,linkName);
  };
</script>

<button type="button" onclick="s.tl(this,'o',customFunction(this)">Add To Cart</button>
```

1. Om `linkName` skickas anropades metoden av `tl()`. Returnera det som `tl()` skickade som `linkName`.
2. När det anropas av Activity Map skickas aldrig `linkName`, så anropa `customFunction()` med länkelementet. Du kan använda valfri anpassad funktion som du vill returnera ett värde.
3. Om inget av de ovanstående returvärdena anges, använder du länknamnet som normalt samlas in som reserv.
