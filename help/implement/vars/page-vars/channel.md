---
title: kanal
description: Fyll i dimensionen 'Platsavsnitt'.
translation-type: tm+mt
source-git-commit: ec6d8e6a3cef3a5fd38d91775c83ab95de47fd55
workflow-type: tm+mt
source-wordcount: '157'
ht-degree: 2%

---


# kanal

Variabeln lagrar vanligtvis den del av webbplatsen som en viss sida finns på `channel` . Det är praktiskt att avgöra vilka grupper på din webbplats som är populärast. Den här variabeln fyller i dimensionen &#39;Platsavsnitt&#39;.

## Kanal i Adobe Experience Platform Launch

Du kan ange kanal antingen när du konfigurerar Analytics-tillägget (globala variabler) eller under regler.

1. Logga in på [launch.adobe.com](https://launch.adobe.com) med inloggningsuppgifterna för ditt AdobeID.
2. Klicka på önskad egenskap.
3. Gå till [!UICONTROL Rules] fliken och klicka sedan på önskad regel (eller skapa en regel).
4. Under [!UICONTROL Actions]klickar du på en befintlig [!UICONTROL Adobe Analytics - Set Variables] åtgärd eller på +-ikonen.
5. Ställ in listrutan [!UICONTROL Extension] till Adobe Analytics och [!UICONTROL Action Type] till [!UICONTROL Set Variables].
6. Leta rätt på [!UICONTROL Channel] avsnittet.

Du kan ställa in kanalen på valfritt strängvärde eller dataelement.

## s.channel in AppMeasurement and Launch custom code editor

Variabeln `s.channel` är en sträng som vanligtvis innehåller sidans webbplatsavsnitt. Den har ett maxvärde på 100 byte. längre värden trunkeras.

```js
s.channel = "Example site section";
```

Om du använder `digitalData` datalagret [](../../prepare/data-layer.md):

```js
s.channel = digitalData.page.category.primaryCategory;
```
