---
title: ActivityMap.regionIDAttribute
description: Ändra attributet som Activity Map letar efter för att bestämma regionen.
feature: Variables
role: Admin, Developer
source-git-commit: 05010d58ba2a3376473097e9d4543ee4415e83e1
workflow-type: tm+mt
source-wordcount: '220'
ht-degree: 0%

---

# ActivityMap.regionIDAttribute

Variabeln `ActivityMap.regionIDAttribute` gör att du kan ändra attributet som Activity Map letar efter när du fastställer dimensionen för [ Activity Map region ](/help/components/dimensions/activity-map-region.md) . Om din webbplats är strukturerad på ett sätt som gör attributet `id` mindre användbart för regionen Activity Map kan du ställa in den här variabeln så att den tittar på ett annat attribut.

## Region-ID-attribut i Web SDK-tillägget

När **[!UICONTROL Enable click data collection]** är aktiverat använder du kodblocket **[!UICONTROL Filter click properties]** för återanrop. I det här kodblocket kan du kontrollera värdet för `content.clickedElement` och antingen ändra värdet eller avbryta insamlingen av länkspårningsdata.

## Region-ID-attribut i Web SDK JavaScript-biblioteket

När [`clickCollectionEnabled`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/clickcollectionenabled) är aktiverat använder du `filterClickDetails`-återanropet i `clickCollection`-objektet. I det här återanropet kan du kontrollera värdet för `clickedElement` och anpassa logiken för den insamlade regionen.

```js
alloy("configure", {
  clickCollectionEnabled: true,
  clickCollection: {
    filterClickDetails: function(content) {
      // If the clicked element was in a table, set the region to the contents of the data-custom attribute
      // If the clicked element was not in a table, or if the data-custom attribute doesn't exist, leave region as-is
      content.region = content.clickedElement.closest('table')?.getAttribute('data-custom') || content.region;
    }
  }
});
```

## Region-ID-attribut med Adobe Analytics-tillägg

Det finns inget dedikerat fält i Adobe Analytics-tillägget som kan använda den här variabeln. Använd den anpassade kodredigeraren enligt AppMeasurementen syntax.

## s.ActivityMap.regionIDAttribute med AppMeasurement

Variabeln `s.ActivityMap.regionIDAttribute` är en sträng som representerar attributet som avgör dimensionen för [Activity Map-regionen](/help/components/dimensions/activity-map-region.md). Den här variabeln är inställd på `id` som standard. Om du ändrar den här variabeln letar Activity Map inte längre efter attributet `id`, men söker fortfarande efter andra villkor för att avgöra område (till exempel semantiska element).

```html
<script>
  var s = s_gi("examplersid");
  s.ActivityMap.regionIDAttribute = "data-custom";
</script>

<!-- Clicking any of these links populates the region dimension with 'left-nav' -->
<div id="676967617A656C6C65" data-custom="left-nav">
  <a href="index.html">Home</a>
  <a href="products.html">View our products</a>
  <a href="contact.html">Contact us</a>
</div>
```
