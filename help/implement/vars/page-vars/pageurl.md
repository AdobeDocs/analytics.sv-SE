---
title: pageURL
description: Åsidosätt den automatiskt insamlade sidans URL på din webbplats.
feature: Appmeasurement Implementation
exl-id: 411f894d-c31f-4d07-9568-b0b02786735d
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '293'
ht-degree: 0%

---

# pageURL

AppMeasurement samlar automatiskt in sidans URL i varje träff. Om du vill åsidosätta sidans URL som samlas in automatiskt av AppMeasurement kan du använda den här variabeln. I de flesta fall behöver du inte ange den här variabeln.

>[!NOTE]
>
>Denna variabel är inte en tillgänglig dimension i Analysis Workspace. Det är bara tillgängligt i Data Warehouse och Dataflöden. Dessutom tar Adobe datainsamlingsservrar bort den här dimensionen från alla [länkspårning](/help/implement/vars/functions/tl-method.md) -bildbegäranden. Om du vill använda sidans URL som en dimension i Analysis Workspace eller vill att den här dimensionen ska visas i länkspårningsträffar, bör du skicka variabeln `pageURL` till en [eVar](evar.md) för varje träff.

## Sid-URL med Web SDK

Sidans URL mappas till följande variabler:

* [XDM-objekt](/help/implement/aep-edge/xdm-var-mapping.md): `xdm.web.webPageDetails.URL`
* [Dataobjekt](/help/implement/aep-edge/data-var-mapping.md): `data.__adobe.analytics.pageURL` eller `data.__adobe.analytics.g`

## Sidans URL med Adobe Analytics-tillägget

Analystillägget i Adobe Experience Platform Data Collection fyller automatiskt i sidans URL. Du kan dock ange åsidosättning av sidans URL när du konfigurerar Analytics-tillägget (globala variabler) eller under regler.

1. Logga in på [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) med dina inloggningsuppgifter för AdobeID.
2. Klicka på den önskade taggegenskapen.
3. Gå till fliken **[!UICONTROL Rules]** och klicka sedan på önskad regel (eller skapa en regel).
4. Klicka på en befintlig **[!UICONTROL Adobe Analytics - Set Variables]**-åtgärd under **[!UICONTROL Actions]** eller klicka på +-ikonen.
5. Ange Adobe Analytics i listrutan **[!UICONTROL Extension]** och **[!UICONTROL Action Type]** till **[!UICONTROL Set Variables]**.
6. Leta reda på avsnittet **[!UICONTROL Page URL]**.

Du kan ange sidans URL till valfritt strängvärde.

## s.pageURL i AppMeasurement och den anpassade kodredigeraren för Analytics-tillägget

Variabeln `s.pageURL` är en sträng som innehåller sidans URL. AppMeasurement samlar automatiskt in variabeln, men du kan åsidosätta dess värde om du vill.

```js
s.pageURL = "https://example.com";
```

Om du vill använda sidans URL som en dimension i rapporter bör du använda följande i implementeringen:

```js
// Set eVar1 to page URL without protocol or query strings
s.eVar1 = window.location.hostname + window.location.pathname;
```

Om `digitalData` [datalagret](../../prepare/data-layer.md) används:

```js
s.pageURL = digitalData.page.pageInfo.destinationURL;
```
