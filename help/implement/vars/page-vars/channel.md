---
title: kanal
description: Fyll i dimensionen Webbplatsavsnitt.
feature: Appmeasurement Implementation
exl-id: f494a051-a296-4f1c-9044-04a8b59376fa
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '182'
ht-degree: 0%

---

# kanal

Variabeln `channel` lagrar vanligtvis den del av webbplatsen där en viss sida finns. Det är praktiskt att avgöra vilka grupper på din webbplats som är populärast. Den här variabeln fyller i dimensionen Webbplatsavsnitt.

## Kanal med SDK för webben

Kanalen mappas till följande variabler:

* [XDM-objekt](/help/implement/aep-edge/xdm-var-mapping.md): `web.webPageDetails.siteSection`
* [Dataobjekt](/help/implement/aep-edge/data-var-mapping.md): `data.__adobe.analytics.channel` eller `data.__adobe.analytics.ch`

## Kanal med Adobe Analytics-tillägget

Du kan ange kanal antingen när du konfigurerar Analytics-tillägget (globala variabler) eller under regler.

1. Logga in på [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) med dina inloggningsuppgifter för AdobeID.
2. Klicka på den önskade taggegenskapen.
3. Gå till fliken [!UICONTROL Rules] och klicka sedan på önskad regel (eller skapa en regel).
4. Klicka på en befintlig [!UICONTROL Adobe Analytics - Set Variables]-åtgärd under [!UICONTROL Actions] eller klicka på +-ikonen.
5. Ange Adobe Analytics i listrutan [!UICONTROL Extension] och [!UICONTROL Action Type] till [!UICONTROL Set Variables].
6. Leta reda på avsnittet [!UICONTROL Channel].

Du kan ställa in kanalen på valfritt strängvärde eller dataelement.

## s.channel in AppMeasurement and the Analytics extension custom code editor

Variabeln `s.channel` är en sträng som vanligtvis innehåller sidans webbplatsavsnitt. Det har ett maxvärde på 100 byte. Ju längre värde, desto trunkeras.

```js
s.channel = "Example site section";
```

Om `digitalData` [datalagret](../../prepare/data-layer.md) används:

```js
s.channel = digitalData.page.category.primaryCategory;
```
