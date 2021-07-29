---
title: kanal
description: Fyll i dimensionen 'Platsavsnitt'.
exl-id: f494a051-a296-4f1c-9044-04a8b59376fa
source-git-commit: 1a49c2a6d90fc670bd0646d6d40738a87b74b8eb
workflow-type: tm+mt
source-wordcount: '161'
ht-degree: 1%

---

# kanal

Variabeln `channel` lagrar vanligtvis den del av webbplatsen där en viss sida finns. Det är praktiskt att avgöra vilka grupper på din webbplats som är populärast. Den här variabeln fyller i dimensionen &#39;Platsavsnitt&#39;.

## Kanal med taggar i Adobe Experience Platform

Du kan ange kanal antingen när du konfigurerar Analytics-tillägget (globala variabler) eller under regler.

1. Logga in på [användargränssnittet för datainsamling](https://experience.adobe.com/data-collection) med inloggningsuppgifterna för ditt Adobe-ID.
2. Klicka på önskad egenskap.
3. Gå till fliken [!UICONTROL Rules] och klicka sedan på önskad regel (eller skapa en regel).
4. Klicka på en befintlig [!UICONTROL Adobe Analytics - Set Variables]-åtgärd under [!UICONTROL Actions] eller klicka på +-ikonen.
5. Ange listrutan [!UICONTROL Extension] till Adobe Analytics och [!UICONTROL Action Type] till [!UICONTROL Set Variables].
6. Gå till avsnittet [!UICONTROL Channel].

Du kan ställa in kanalen på valfritt strängvärde eller dataelement.

## s.channel in AppMeasurement and custom code editor

Variabeln `s.channel` är en sträng som vanligtvis innehåller sidans platsavsnitt. Den har ett maxvärde på 100 byte. längre värden trunkeras.

```js
s.channel = "Example site section";
```

Om du använder `digitalData` [datalagret](../../prepare/data-layer.md):

```js
s.channel = digitalData.page.category.primaryCategory;
```
