---
title: pageURL
description: Åsidosätt den automatiskt insamlade sidans URL på din webbplats.
translation-type: tm+mt
source-git-commit: ec6d8e6a3cef3a5fd38d91775c83ab95de47fd55
workflow-type: tm+mt
source-wordcount: '259'
ht-degree: 1%

---


# pageURL

AppMeasurement samlar automatiskt in sidans URL i varje träff. Om du vill åsidosätta sidans URL som samlas in automatiskt av AppMeasurement kan du använda den här variabeln. I de flesta fall behöver du inte ange den här variabeln.

>[!NOTE]
>
>Den här variabeln är inte en tillgänglig dimension i Analysis Workspace. Det är bara tillgängligt i Data warehouse och Dataflöden. Dessutom kan datainsamlingsservrar i Adobe ta bort den här dimensionen från alla [länkspårningsbegäranden](/help/implement/vars/functions/tl-method.md) . Om du vill använda sidans URL som en dimension i Analysis Workspace eller om du vill använda den här dimensionen i länkspårningsträffar bör du skicka `pageURL` variabeln till en [eVar](evar.md) för varje träff.

## Page URL in Adobe Experience Platform Launch

Sidans URL fylls i automatiskt. Du kan dock ange åsidosättning av sidans URL när du konfigurerar Analytics-tillägget (globala variabler) eller under regler.

1. Logga in på [launch.adobe.com](https://launch.adobe.com) med inloggningsuppgifterna för ditt AdobeID.
2. Klicka på önskad egenskap.
3. Gå till **[!UICONTROL Rules]** fliken och klicka sedan på önskad regel (eller skapa en regel).
4. Under **[!UICONTROL Actions]** klickar du på en befintlig **[!UICONTROL Adobe Analytics - Set Variables]** åtgärd eller på +-ikonen.
5. Ställ in listrutan **[!UICONTROL Extension]** till Adobe Analytics och **[!UICONTROL Action Type]** till **[!UICONTROL Set Variables]**.
6. Leta rätt på **[!UICONTROL Page URL]** avsnittet.

Du kan ange sidans URL till valfritt strängvärde.

## s.pageURL i AppMeasurement and Launch custom code editor

Variabeln `s.pageURL` är en sträng som innehåller sidans URL. AppMeasurement samlar automatiskt in den här variabeln, men du kan åsidosätta dess värde om du vill.

```js
s.pageURL = "https://example.com";
```

Om du vill använda sidans URL som en dimension i rapporter bör du använda följande i implementeringen:

```js
// Set eVar1 to page URL without protocol or query strings
s.eVar1 = window.location.hostname + window.location.pathname;
```

Om du använder `digitalData` datalagret [](../../prepare/data-layer.md):

```js
s.pageURL = digitalData.page.pageInfo.destinationURL;
```
