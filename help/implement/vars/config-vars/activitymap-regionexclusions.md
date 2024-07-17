---
title: ActivityMap.regionExclusions
description: Filtrera Activity Map data efter region.
role: Admin, Developer
feature: Variables
source-git-commit: 05010d58ba2a3376473097e9d4543ee4415e83e1
workflow-type: tm+mt
source-wordcount: '180'
ht-degree: 0%

---

# ActivityMap.regionExclusions

Med variabeln `ActivityMap.regionExclusions` kan du selektivt filtrera eller exkludera Activity Map-data baserat på dimensionsobjekten som samlats in i dimensionen [Activity Map-region](/help/components/dimensions/activity-map-region.md).

## Regionundantag i Web SDK-tillägget

När **[!UICONTROL Enable click data collection]** är aktiverat använder du kodblocket **[!UICONTROL Filter click properties]** för återanrop. I det här kodblocket kan du kontrollera värdet för `content.linkRegion` och antingen ändra värdet eller avbryta insamlingen av länkspårningsdata.

## Regionundantag i JavaScript-biblioteket för Web SDK

När [`clickCollectionEnabled`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/clickcollectionenabled) är aktiverat använder du `filterClickDetails`-återanropet i `clickCollection`-objektet. I det här återanropet kan du kontrollera värdet för `linkRegion` och antingen ändra värdet eller avbryta insamlingen av länkspårningsdata.

```js
alloy("configure", {
  clickCollectionEnabled: true,
  clickCollection: {
    filterClickDetails: function(content) {
      // If the clicked region has personal links in it, don't send click data
      if(content.linkRegion.includes("personal")) {
        return false;
      }
    }
  }
});
```

## Regionundantag som använder Adobe Analytics-tillägget

Det finns inget dedikerat fält i Adobe Analytics-tillägget som kan använda den här variabeln. Använd den anpassade kodredigeraren enligt AppMeasurementen syntax.

## s.ActivityMap.regionExclusions med AppMeasurementet

Variabeln `s.ActivityMap.regionExclusions` är en sträng som innehåller kommaavgränsade fraser som ska uteslutas från spårning i Activity Map. Om någon av fraserna matchar det värde som samlats in i dimensionen [Activity Map region](/help/components/dimensions/activity-map-region.md) tas alla data från Activity Map bort från träffen.

```html
<script>
  var s = s_gi("examplersid");
  s.ActivityMap.regionExclusions = "contact";
</script>

<!-- Clicking any of these links tracks normally. -->
<!-- While "contact" is present, it is not tracked in region. The region is "nav" -->
<nav>
  <a href="index.html">Home</a>
  <a href="products.html">View our products</a>
  <a href="contact.html">Contact us</a>
</nav>

<!-- Activity Map data is not tracked for any of these links. -->
<!-- All these links belong to the region "Personal contact information" -->
<div id="personal-contact-information">
 <a href="mailto:user@example.com">Example user</a>
 <a href="mailto:user2@example.com">Example user 2</a>
 <a href="mailto:user3@example.com">Example user 3</a>
</div>
```
