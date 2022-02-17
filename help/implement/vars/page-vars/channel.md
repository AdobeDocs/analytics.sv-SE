---
title: kanal
description: Fyll i dimensionen 'Platsavsnitt'.
feature: Variables
exl-id: f494a051-a296-4f1c-9044-04a8b59376fa
source-git-commit: b3c74782ef6183fa63674b98e4c0fc39fc09441b
workflow-type: tm+mt
source-wordcount: '161'
ht-degree: 1%

---

# kanal

The `channel` variabeln lagrar vanligtvis den del av webbplatsen där en viss sida finns. Det är praktiskt att avgöra vilka grupper på din webbplats som är populärast. Den här variabeln fyller i dimensionen &#39;Platsavsnitt&#39;.

## Kanal med taggar i Adobe Experience Platform

Du kan ange kanal antingen när du konfigurerar Analytics-tillägget (globala variabler) eller under regler.

1. Logga in på [Användargränssnitt för datainsamling](https://experience.adobe.com/data-collection) med inloggningsuppgifterna för ditt AdobeID.
2. Klicka på önskad egenskap.
3. Gå till [!UICONTROL Rules] och sedan klicka på önskad regel (eller skapa en regel).
4. Under [!UICONTROL Actions]klickar du på en befintlig [!UICONTROL Adobe Analytics - Set Variables] eller klicka på +-ikonen.
5. Ange [!UICONTROL Extension] till Adobe Analytics och [!UICONTROL Action Type] till [!UICONTROL Set Variables].
6. Leta reda på [!UICONTROL Channel] -avsnitt.

Du kan ställa in kanalen på valfritt strängvärde eller dataelement.

## s.channel in AppMeasurement and custom code editor

The `s.channel` variabeln är en sträng som vanligtvis innehåller sidans webbplatsavsnitt. Den har ett maxvärde på 100 byte. längre värden trunkeras.

```js
s.channel = "Example site section";
```

Om du använder `digitalData` [datalager](../../prepare/data-layer.md):

```js
s.channel = digitalData.page.category.primaryCategory;
```
