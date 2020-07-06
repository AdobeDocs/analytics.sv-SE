---
title: pageURL
description: Åsidosätt den automatiskt insamlade sidans URL på din webbplats.
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '286'
ht-degree: 1%

---


# pageURL

AppMeasurement samlar automatiskt in sidans URL i varje träff. Om du vill åsidosätta sidans URL som samlas in automatiskt av AppMeasurement kan du använda den här variabeln. I de flesta fall behöver du inte ange den här variabeln.

>[!NOTE]
>
>Den här variabeln är inte en tillgänglig dimension i Analysis Workspace. Det är bara tillgängligt i Data warehouse och Dataflöden. Om du vill använda sidans URL som en dimension i Analysis Workspace bör du skicka variabeln till en eVar vid varje träff. `pageURL`

Ibland är URL-adresser längre än 255 byte. AppMeasurement använder frågesträngsparametern för de första 255 byten i URL:en i bildbegäranden. `g` Om en URL är längre än 255 byte lagras resten av URL:en i `-g` frågesträngsparametern. Protokoll- och frågesträngar i URL:en ingår i den här variabeln.

## Page URL in Adobe Experience Platform Launch

Sidans URL fylls i automatiskt. Du kan dock ange åsidosättning av sidans URL när du konfigurerar Analytics-tillägget (globala variabler) eller enligt regler.

1. Logga in på [launch.adobe.com](https://launch.adobe.com) med inloggningsuppgifterna för ditt AdobeID.
2. Klicka på önskad egenskap.
3. Gå till [!UICONTROL Rules] fliken och klicka sedan på önskad regel (eller skapa en regel).
4. Under [!UICONTROL Actions]klickar du på en befintlig [!UICONTROL Adobe Analytics - Set Variables] åtgärd eller på +-ikonen.
5. Ställ in listrutan [!UICONTROL Extension] på Adobe Analytics och [!UICONTROL Action Type] till [!UICONTROL Set Variables].
6. Leta rätt på [!UICONTROL Page URL] avsnittet.

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
