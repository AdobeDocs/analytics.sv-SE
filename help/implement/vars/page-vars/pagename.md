---
title: pageName
description: Namnet på sidan på webbplatsen.
feature: Variables
exl-id: 24ac40a9-f0e7-4534-abf2-2397f5fe16c2
role: Admin, Developer
source-git-commit: 5ef92db2f5edb5fded497dddedd56abd49d8a019
workflow-type: tm+mt
source-wordcount: '245'
ht-degree: 0%

---

# pageName

Variabeln `pageName` lagrar vanligtvis namnet på en viss sida. Det är praktiskt att avgöra vilka enskilda sidor som är mest populära. Den här variabeln fyller i dimensionen [Sida](/help/components/dimensions/page.md).

Om variabeln inte definieras för ett visst sidspårningsanrop används variabeln [`pageURL`](pageurl.md) i stället.

>[!NOTE]
>
>Datainsamlingsservrar i Adobe tar bort den här dimensionen från alla [länkspårning](/help/implement/vars/functions/tl-method.md) -bildbegäranden. Om du vill att den här dimensionen ska visas i länkspårningsträffar bör du kopiera dimensionen till en [eVar](evar.md).

## Sidnamn med Web SDK

Sidnamnet mappas till följande variabler:

* [XDM-objekt](/help/implement/aep-edge/xdm-var-mapping.md): `xdm.web.webPageDetails.name`
* [Dataobjekt](/help/implement/aep-edge/data-var-mapping.md): `data.__adobe.analytics.pageName`

## Sidnamn med Adobe Analytics-tillägg

Du kan ange sidnamn antingen när du konfigurerar Analytics-tillägget (globala variabler) eller under regler.

1. Logga in på [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) med dina inloggningsuppgifter för AdobeID.
2. Klicka på den önskade taggegenskapen.
3. Gå till fliken [!UICONTROL Rules] och klicka sedan på önskad regel (eller skapa en regel).
4. Klicka på en befintlig [!UICONTROL Adobe Analytics - Set Variables]-åtgärd under [!UICONTROL Actions] eller klicka på +-ikonen.
5. Ange Adobe Analytics i listrutan [!UICONTROL Extension] och [!UICONTROL Action Type] till [!UICONTROL Set Variables].
6. Leta reda på avsnittet [!UICONTROL Page name].

Du kan ange sidnamn till valfritt strängvärde, inklusive dataelement.

## s.pageName i AppMeasurementet och den anpassade kodredigeraren för Analytics-tillägget

Variabeln `s.pageName` är en sträng som vanligtvis innehåller sidans namn. Det har ett maxvärde på 100 byte. Ju längre värde, desto trunkeras. Den här trunkeringen innehåller instanser där den återgår till `pageURL` om variabeln är tom.

```js
// Set page name to a static value
s.pageName = "Example page name";

// Set page name to the page's title
s.pageName = window.document.title;
```

Om `digitalData` [datalagret](../../prepare/data-layer.md) används:

```js
s.pageName = digitalData.page.pageInfo.pageName;
```
