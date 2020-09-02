---
title: pageName
description: Namnet på sidan på webbplatsen.
translation-type: tm+mt
source-git-commit: ec6d8e6a3cef3a5fd38d91775c83ab95de47fd55
workflow-type: tm+mt
source-wordcount: '219'
ht-degree: 1%

---


# pageName

Variabeln lagrar vanligtvis namnet på en viss sida `pageName` . Det är praktiskt att avgöra vilka enskilda sidor som är mest populära. Den här variabeln fyller i [siddimensionen](/help/components/dimensions/page.md) .

Om den här variabeln inte definieras för ett visst sidspårningsanrop används [`pageURL`](pageurl.md) variabeln i stället.

>[!NOTE]
>
>Adobe datainsamlingsservrar tar bort den här dimensionen från alla [länkspårningsbildbegäranden](/help/implement/vars/functions/tl-method.md) . Om du vill att den här dimensionen ska visas i länkspårningsträffar bör du kopiera dimensionen till en [eVar](evar.md).

## Sidnamn i Adobe Experience Platform Launch

Du kan ange sidnamn antingen när du konfigurerar Analytics-tillägget (globala variabler) eller under regler.

1. Logga in på [launch.adobe.com](https://launch.adobe.com) med inloggningsuppgifterna för ditt AdobeID.
2. Klicka på önskad egenskap.
3. Gå till [!UICONTROL Rules] fliken och klicka sedan på önskad regel (eller skapa en regel).
4. Under [!UICONTROL Actions]klickar du på en befintlig [!UICONTROL Adobe Analytics - Set Variables] åtgärd eller på +-ikonen.
5. Ställ in listrutan [!UICONTROL Extension] till Adobe Analytics och [!UICONTROL Action Type] till [!UICONTROL Set Variables].
6. Leta rätt på [!UICONTROL Page name] avsnittet.

Du kan ange sidnamn till valfritt strängvärde, inklusive dataelement.

## s.pageName i AppMeasurement and Launch custom code editor

Variabeln är en sträng som vanligtvis innehåller sidans namn. `s.pageName` Den har ett maxvärde på 100 byte. längre värden trunkeras. Den här trunkeringen innehåller instanser där den återgår till `pageURL` om variabeln är tom.

```js
// Set page name to a static value
s.pageName = "Example page name";

// Set page name to the page's title
s.pageName = window.document.title;
```

Om du använder `digitalData` datalagret [](../../prepare/data-layer.md):

```js
s.pageName = digitalData.page.pageInfo.pageName;
```
