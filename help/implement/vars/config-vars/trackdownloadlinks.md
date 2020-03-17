---
title: trackDownloadLinks
description: Aktivera eller inaktivera automatisk länkspårning för nedladdningslänkar.
translation-type: tm+mt
source-git-commit: 04b97e93a95691132680d4da197dc62eb2b9fdd1

---


# trackDownLoadLinks

Adobe ger möjlighet att spåra nedladdningslänkar utan att manuellt ange `tl()` funktionen för varje nedladdningslänk. Aktivera den här variabeln om du vill använda automatisk länkspårning för hämtningslänkar.

När det är aktiverat jämför AppMeasurement alla klickade länk-URL:er med värden i `downloadLinkFileTypes`. Om det finns en matchning aktiveras ett spårningsanrop för nedladdningslänk automatiskt.

## Spåra nedladdningslänkar i Adobe Experience Platform Launch

Spåra hämtningslänkar är en kryssruta i dragspelet [!UICONTROL Link Tracking] när du konfigurerar Adobe Analytics-tillägget.

1. Logga in på [launch.adobe.com](https://launch.adobe.com) med inloggningsuppgifterna för ditt AdobeID.
2. Klicka på önskad egenskap.
3. Gå till [!UICONTROL Extensions] fliken och klicka sedan på [!UICONTROL Configure] knappen under Adobe Analytics.
4. Expandera dragspelsfliken så att [!UICONTROL Link Tracking] kryssrutan visas [!UICONTROL Track download links] .

Klicka i kryssrutan om du vill aktivera automatisk spårning av nedladdningslänk.

## s.trackDownloadLinks in AppMeasurement and Launch custom code editor

Det här `s.trackDownloadLinks` är ett booleskt värde som aktiverar eller inaktiverar automatisk länkspårning för hämtning. Om du inte vill spåra nedladdningslänkar, eller vill anropa funktionen manuellt för att spåra nedladdningar, ställer du in den här variabeln på `tl()` `false`.

```js
s.trackDownloadLinks = true;
```
