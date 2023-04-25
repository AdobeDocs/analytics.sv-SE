---
title: pageName
description: Namnet på sidan på webbplatsen.
feature: Variables
exl-id: 24ac40a9-f0e7-4534-abf2-2397f5fe16c2
source-git-commit: 6de20d2fbbab6ded6c92f0c6f3536671f4b2ae46
workflow-type: tm+mt
source-wordcount: '251'
ht-degree: 0%

---

# pageName

The `pageName` variabeln lagrar vanligtvis namnet på en viss sida. Det är praktiskt att avgöra vilka enskilda sidor som är mest populära. Den här variabeln fyller i [Sida](/help/components/dimensions/page.md) dimension.

Om variabeln inte definieras för ett visst sidspårningsanrop [`pageURL`](pageurl.md) används i stället.

>[!NOTE]
>
>Datainsamlingsservrar i Adobe tar bort den här dimensionen från alla [länkspårning](/help/implement/vars/functions/tl-method.md) bildbegäranden. Om du vill att den här dimensionen ska visas i länkspårningsträffar bör du kopiera dimensionen till en [eVar](evar.md).

## Sidnamn med Web SDK

Sidan är [mappas för Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/implementation/aep-edge/variable-mapping.html) under XDM-fältet `web.webPageDetails.name`.

## Sidnamn med Adobe Analytics-tillägg

Du kan ange sidnamn antingen när du konfigurerar Analytics-tillägget (globala variabler) eller under regler.

1. Logga in på [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) med inloggningsuppgifterna för ditt AdobeID.
2. Klicka på den önskade taggegenskapen.
3. Gå till [!UICONTROL Rules] och sedan klicka på önskad regel (eller skapa en regel).
4. Under [!UICONTROL Actions]klickar du på en befintlig [!UICONTROL Adobe Analytics - Set Variables] eller klicka på +-ikonen.
5. Ange [!UICONTROL Extension] nedrullningsbar lista till Adobe Analytics och [!UICONTROL Action Type] till [!UICONTROL Set Variables].
6. Leta reda på [!UICONTROL Page name] -avsnitt.

Du kan ange sidnamn till valfritt strängvärde, inklusive dataelement.

## s.pageName i AppMeasurement och den anpassade kodredigeraren i Analytics-tillägget

The `s.pageName` variabeln är en sträng som vanligtvis innehåller sidans namn. Den har ett maxvärde på 100 byte. längre värden trunkeras. Den här trunkeringen innehåller instanser där den återgår till `pageURL` om variabeln är tom.

```js
// Set page name to a static value
s.pageName = "Example page name";

// Set page name to the page's title
s.pageName = window.document.title;
```

Om du använder `digitalData` [datalager](../../prepare/data-layer.md):

```js
s.pageName = digitalData.page.pageInfo.pageName;
```
