---
title: trackExternalLinks
description: Aktivera eller inaktivera automatisk länkspårning för att avsluta länkar.
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# trackExternalLinks

Adobe ger möjlighet att spåra utgående länkar utan att manuellt ange [`tl()`](../functions/tl-method.md) metod för varje avslutningslänk. Aktivera den här variabeln om du vill använda automatisk länkspårning för slutlänkar.

När det är aktiverat jämför AppMeasurement alla klickade länk-URL:er med värden i [`linkInternalFilters`](linkinternalfilters.md) och [`linkExternalFilters`](linkexternalfilters.md). Om det finns en matchning utlöses ett avslutningslänkspårningsanrop automatiskt.

## Spåra utgående länkar i Adobe Experience Platform Launch

Spåra utgående länkar är en kryssruta i dragspelet [!UICONTROL Link Tracking] när du konfigurerar Adobe Analytics-tillägget.

1. Logga in på [launch.adobe.com](https://launch.adobe.com) med inloggningsuppgifterna för ditt AdobeID.
2. Klicka på önskad egenskap.
3. Gå till [!UICONTROL Extensions] fliken och klicka sedan på [!UICONTROL Configure] knappen under Adobe Analytics.
4. Expandera dragspelsfliken så att [!UICONTROL Link Tracking] kryssrutan visas [!UICONTROL Track outbound links] .

Klicka i kryssrutan om du vill aktivera automatisk spårning av avslutningslänk.

## s.trackExternalLinks in AppMeasurement and Launch custom code editor

Det här `s.trackExternalLinks` är ett booleskt värde som aktiverar eller inaktiverar automatisk spårning av avslutningslänk. Om du inte vill spåra utgående länkar, eller vill anropa metoden manuellt för att spåra avslutslänkar, anger du den här variabeln som `tl()` `false`.

```js
s.trackDownloadLinks = true;
```
