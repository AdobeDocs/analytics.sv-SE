---
title: ActivityMap.regionExclusions
description: Filtrera Activity Map-data per region.
role: Admin, Developer
feature: Appmeasurement Implementation
exl-id: 353282aa-860c-45dc-a6b0-8d9f1fa09f13
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '180'
ht-degree: 0%

---

# ActivityMap.regionExclusions

Med variabeln `ActivityMap.regionExclusions` kan du selektivt filtrera eller exkludera Activity Map-data baserat på dimensionsobjekten som samlats in i dimensionen för [&#x200B; Activity Map-regionen &#x200B;](/help/components/dimensions/activity-map-region.md).

## Regionundantag i Web SDK-tillägget

När **[!UICONTROL Enable click data collection]** är aktiverat använder du kodblocket **[!UICONTROL Filter click properties]** för återanrop. I det här kodblocket kan du kontrollera värdet för `content.linkRegion` och antingen ändra värdet eller avbryta insamlingen av länkspårningsdata.

## Regionundantag i Web SDK JavaScript-biblioteket

När [`clickCollectionEnabled`](https://experienceleague.adobe.com/sv/docs/experience-platform/web-sdk/commands/configure/clickcollectionenabled) är aktiverat använder du `filterClickDetails`-återanropet i `clickCollection`-objektet. I det här återanropet kan du kontrollera värdet för `linkRegion` och antingen ändra värdet eller avbryta insamlingen av länkspårningsdata.

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

Det finns inget dedikerat fält i Adobe Analytics-tillägget som kan använda den här variabeln. Använd den anpassade kodredigeraren enligt AppMeasurement-syntax.

## s.ActivityMap.regionExclusions med AppMeasurement

Variabeln `s.ActivityMap.regionExclusions` är en sträng som innehåller kommaavgränsade fraser som ska uteslutas från Activity Map-spårning. Om någon av fraserna matchar det värde som samlats in i dimensionen [Activity Map Region](/help/components/dimensions/activity-map-region.md) tas alla Activity Map-data bort från träffen.

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
