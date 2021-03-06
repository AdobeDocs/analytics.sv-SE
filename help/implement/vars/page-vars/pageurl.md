---
title: pageURL
description: Åsidosätt den automatiskt insamlade sidans URL på din webbplats.
feature: Variables
exl-id: 411f894d-c31f-4d07-9568-b0b02786735d
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '299'
ht-degree: 0%

---

# pageURL

AppMeasurement samlar automatiskt in sidans URL i varje träff. Om du vill åsidosätta sidans URL som samlas in automatiskt av AppMeasurement kan du använda den här variabeln. I de flesta fall behöver du inte ange den här variabeln.

>[!NOTE]
>
>Den här variabeln är inte en tillgänglig dimension i Analysis Workspace. Det är bara tillgängligt i Data warehouse och Dataflöden. Dessutom kan datainsamlingsservrar i Adobe ta bort den här dimensionen från alla [länkspårning](/help/implement/vars/functions/tl-method.md) bildbegäranden. Om du vill använda sidans URL som en dimension i Analysis Workspace eller om du vill använda den här dimensionen i länkspårningsträffar bör du skicka `pageURL` variabel till [eVar](evar.md) på varje träff.

## Sid-URL med Web SDK

Sidans URL är [mappas för Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/implementation/aep-edge/variable-mapping.html) under XDM-fältet `web.webPageDetails.URL`.

## Sidans URL med Adobe Analytics-tillägget

Analystillägget i Adobe Experience Platform Data Collection fyller automatiskt i sidans URL. Du kan dock ange åsidosättning av sidans URL när du konfigurerar Analytics-tillägget (globala variabler) eller under regler.

1. Logga in på [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) med inloggningsuppgifterna för ditt AdobeID.
2. Klicka på den önskade taggegenskapen.
3. Gå till **[!UICONTROL Rules]** och sedan klicka på önskad regel (eller skapa en regel).
4. Under **[!UICONTROL Actions]** klickar du på en befintlig **[!UICONTROL Adobe Analytics - Set Variables]** eller klicka på +-ikonen.
5. Ange **[!UICONTROL Extension]** till Adobe Analytics och **[!UICONTROL Action Type]** till **[!UICONTROL Set Variables]**.
6. Leta reda på **[!UICONTROL Page URL]** -avsnitt.

Du kan ange sidans URL till valfritt strängvärde.

## s.pageURL i AppMeasurement och den anpassade kodredigeraren för Analytics-tillägget

The `s.pageURL` variabeln är en sträng som innehåller sidans URL. AppMeasurement samlar automatiskt in den här variabeln, men du kan åsidosätta dess värde om du vill.

```js
s.pageURL = "https://example.com";
```

Om du vill använda sidans URL som en dimension i rapporter bör du använda följande i implementeringen:

```js
// Set eVar1 to page URL without protocol or query strings
s.eVar1 = window.location.hostname + window.location.pathname;
```

Om du använder `digitalData` [datalager](../../prepare/data-layer.md):

```js
s.pageURL = digitalData.page.pageInfo.destinationURL;
```
