---
title: kanal
description: Fyll i dimensionen Webbplatsavsnitt.
feature: Variables
exl-id: f494a051-a296-4f1c-9044-04a8b59376fa
role: Admin, Developer
source-git-commit: 12347957a7a51dc1f8dfb46d489b59a450c2745a
workflow-type: tm+mt
source-wordcount: '182'
ht-degree: 0%

---

# kanal

The `channel` variabeln lagrar vanligtvis den del av webbplatsen där en viss sida finns. Det är praktiskt att avgöra vilka grupper på din webbplats som är populärast. Den här variabeln fyller i dimensionen Webbplatsavsnitt.

## Kanal med Web SDK

Kanalen mappas till följande variabler:

* [XDM-objekt](/help/implement/aep-edge/xdm-var-mapping.md): `web.webPageDetails.siteSection`
* [Dataobjekt](/help/implement/aep-edge/data-var-mapping.md): `data.__adobe.analytics.channel` eller `data.__adobe.analytics.ch`

## Kanal med Adobe Analytics-tillägget

Du kan ange kanal antingen när du konfigurerar Analytics-tillägget (globala variabler) eller under regler.

1. Logga in på [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) med inloggningsuppgifterna för ditt AdobeID.
2. Klicka på den önskade taggegenskapen.
3. Gå till [!UICONTROL Rules] och sedan klicka på önskad regel (eller skapa en regel).
4. Under [!UICONTROL Actions]klickar du på en befintlig [!UICONTROL Adobe Analytics - Set Variables] eller klicka på +-ikonen.
5. Ange [!UICONTROL Extension] nedrullningsbar lista till Adobe Analytics och [!UICONTROL Action Type] till [!UICONTROL Set Variables].
6. Leta reda på [!UICONTROL Channel] -avsnitt.

Du kan ställa in kanalen på valfritt strängvärde eller dataelement.

## s.channel in AppMeasurement and the Analytics extension custom code editor

The `s.channel` variabeln är en sträng som vanligtvis innehåller sidans webbplatsavsnitt. Det har ett maxvärde på 100 byte. Ju längre värde, desto trunkeras.

```js
s.channel = "Example site section";
```

Om du använder `digitalData` [datalager](../../prepare/data-layer.md):

```js
s.channel = digitalData.page.category.primaryCategory;
```
