---
title: ActivityMap.linkExclusions
description: Filtrera Activity Map-data efter länknamn.
role: Admin, Developer
feature: Appmeasurement Implementation
exl-id: 9fc95016-362d-4c21-806e-e23adce9b6f7
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '188'
ht-degree: 0%

---

# ActivityMap.linkExclusions

Med variabeln `ActivityMap.linkExclusions` kan du selektivt filtrera eller exkludera Activity Map-data baserat på texten i dimensionen [ Activity Map Link](/help/components/dimensions/activity-map-link.md) .

## Länkundantag i Web SDK-tillägget

När **[!UICONTROL Enable click data collection]** är aktiverat använder du kodblocket **[!UICONTROL Filter click properties]** för återanrop. I det här kodblocket kan du kontrollera värdet för `content.linkName` och antingen ändra värdet eller avbryta insamlingen av länkspårningsdata.

## Länkundantag i Web SDK JavaScript-biblioteket

När [`clickCollectionEnabled`](https://experienceleague.adobe.com/sv/docs/experience-platform/web-sdk/commands/configure/clickcollectionenabled) är aktiverat använder du `filterClickDetails`-återanropet i `clickCollection`-objektet. I det här återanropet kan du kontrollera värdet för `linkName` och antingen ändra värdet eller avbryta insamlingen av länkspårningsdata.

```js
alloy("configure", {
  clickCollectionEnabled: true,
  clickCollection: {
    filterClickDetails: function(content) {
      // If the link is a clickable telephone number, anonymize it
      if(content.linkUrl.includes("tel:")) {
        content.linkName = content.linkUrl = "Phone number";
      }
      // If the link is an email address, anonymize it
      if(content.linkUrl.includes("mailto:")) {
        content.linkName = content.linkUrl = "Email address";
      }
    }
  }
});
```

## Länkundantag med Adobe Analytics-tillägget

Det finns inget dedikerat fält i Adobe Analytics-tillägget som kan använda den här variabeln. Använd den anpassade kodredigeraren enligt AppMeasurement-syntax.

## s.ActivityMap.linkExclusions med AppMeasurement

Variabeln `s.ActivityMap.linkExclusions` är en sträng som innehåller kommaavgränsade värden för fraser som ska uteslutas från Activity Map-spårning. Om någon av fraserna matchar det värde som samlats in i dimensionen [Activity Map Link](/help/components/dimensions/activity-map-link.md) tas alla Activity Map-data bort från träffen. Observera att den här variabeln tittar på `linkName`, inte `linkUrl`.

```html
<script>
  var s = s_gi("examplersid");
  s.ActivityMap.linkExclusions = "Contact";
</script>

<!-- Clicking this link tracks normally -->
<a href="products.html">View our products</a>

<!-- Activity Map data is not tracked for this link -->
<a href="mailto:user@example.com">Contact this user</a>
```
