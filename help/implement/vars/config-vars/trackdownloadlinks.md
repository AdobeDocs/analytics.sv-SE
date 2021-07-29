---
title: trackDownloadLinks
description: Aktivera eller inaktivera automatisk länkspårning för nedladdningslänkar.
exl-id: d92f722b-d605-40ad-bb55-ec71219a47e3
source-git-commit: 1a49c2a6d90fc670bd0646d6d40738a87b74b8eb
workflow-type: tm+mt
source-wordcount: '178'
ht-degree: 0%

---

# trackDownLoadLinks

I Adobe kan du spåra hämtningslänkar utan att manuellt ange [`tl()`](../functions/tl-method.md)-metoden för varje hämtningslänk. Aktivera den här variabeln om du vill använda automatisk länkspårning för hämtningslänkar.

När det är aktiverat jämför AppMeasurement alla klickade länk-URL:er med värden i [`linkDownloadFileTypes`](linkdownloadfiletypes.md). Om det finns en matchning aktiveras ett spårningsanrop för nedladdningslänk automatiskt.

## Spåra nedladdningslänkar med hjälp av taggar i Adobe Experience Platform

Spåra hämtningslänkar är en kryssruta under dragspelet [!UICONTROL Link Tracking] när du konfigurerar Adobe Analytics-tillägget.

1. Logga in på [användargränssnittet för datainsamling](https://experience.adobe.com/data-collection) med inloggningsuppgifterna för ditt Adobe-ID.
2. Klicka på önskad egenskap.
3. Gå till fliken [!UICONTROL Extensions] och klicka sedan på knappen [!UICONTROL Configure] under Adobe Analytics.
4. Expandera dragspelet [!UICONTROL Link Tracking], som visar kryssrutan [!UICONTROL Track download links].

Klicka i kryssrutan om du vill aktivera automatisk spårning av nedladdningslänk.

## s.trackDownloadLinks in AppMeasurement and custom code editor

`s.trackDownloadLinks` är ett booleskt värde som aktiverar eller inaktiverar automatisk länkspårning för hämtning. Om du inte vill spåra nedladdningslänkar, eller om du föredrar att anropa metoden `tl()` manuellt för att spåra nedladdningar, anger du den här variabeln till `false`.

```js
s.trackDownloadLinks = true;
```
