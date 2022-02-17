---
title: trackDownloadLinks
description: Aktivera eller inaktivera automatisk länkspårning för nedladdningslänkar.
feature: Variables
exl-id: d92f722b-d605-40ad-bb55-ec71219a47e3
source-git-commit: b3c74782ef6183fa63674b98e4c0fc39fc09441b
workflow-type: tm+mt
source-wordcount: '178'
ht-degree: 0%

---

# trackDownLoadLinks

Adobe ger möjlighet att spåra nedladdningslänkar utan att behöva ställa in [`tl()`](../functions/tl-method.md) för varje nedladdningslänk. Aktivera den här variabeln om du vill använda automatisk länkspårning för hämtningslänkar.

När det är aktiverat jämför AppMeasurement alla klickade länk-URL:er med värden i [`linkDownloadFileTypes`](linkdownloadfiletypes.md). Om det finns en matchning aktiveras ett spårningsanrop för nedladdningslänk automatiskt.

## Spåra nedladdningslänkar med hjälp av taggar i Adobe Experience Platform

Spåra nedladdningslänkar är en kryssruta under [!UICONTROL Link Tracking] när du konfigurerar Adobe Analytics-tillägget.

1. Logga in på [Användargränssnitt för datainsamling](https://experience.adobe.com/data-collection) med inloggningsuppgifterna för ditt AdobeID.
2. Klicka på önskad egenskap.
3. Gå till [!UICONTROL Extensions] klickar du på [!UICONTROL Configure] under Adobe Analytics.
4. Expandera [!UICONTROL Link Tracking] dragspelspanel, som visar [!UICONTROL Track download links] kryssrutan.

Klicka i kryssrutan om du vill aktivera automatisk spårning av nedladdningslänk.

## s.trackDownloadLinks in AppMeasurement and custom code editor

The `s.trackDownloadLinks` är ett booleskt värde som aktiverar eller inaktiverar automatisk länkspårning för hämtning. Om du inte vill spåra nedladdningslänkar eller vill ringa `tl()` metod för att spåra hämtningar, ange variabeln till `false`.

```js
s.trackDownloadLinks = true;
```
