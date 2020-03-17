---
title: trackExternalLinks
description: Aktivera eller inaktivera automatisk länkspårning för att avsluta länkar.
translation-type: tm+mt
source-git-commit: 04b97e93a95691132680d4da197dc62eb2b9fdd1

---


# trackExternalLinks

Adobe ger möjlighet att spåra utgående länkar utan att manuellt ange `tl()` funktionen för varje avslutningslänk. Aktivera den här variabeln om du vill använda automatisk länkspårning för slutlänkar.

När det är aktiverat jämför AppMeasurement alla klickade länk-URL:er med värden i `linkInternalFilters` och `linkExternalFilters`. Om det finns en matchning utlöses ett avslutningslänkspårningsanrop automatiskt.

## Spåra utgående länkar i Adobe Experience Platform Launch

Spåra utgående länkar är en kryssruta i dragspelet [!UICONTROL Link Tracking] när du konfigurerar Adobe Analytics-tillägget.

1. Logga in på [launch.adobe.com](https://launch.adobe.com) med inloggningsuppgifterna för ditt AdobeID.
2. Klicka på önskad egenskap.
3. Gå till [!UICONTROL Extensions] fliken och klicka sedan på [!UICONTROL Configure] knappen under Adobe Analytics.
4. Expandera dragspelsfliken så att [!UICONTROL Link Tracking] kryssrutan visas [!UICONTROL Track outbound links] .

Klicka i kryssrutan om du vill aktivera automatisk spårning av avslutningslänk.

## s.trackExternalLinks in AppMeasurement and Launch custom code editor

Det här `s.trackExternalLinks` är ett booleskt värde som aktiverar eller inaktiverar automatisk spårning av avslutningslänk. Om du inte vill spåra utgående länkar, eller föredrar att anropa funktionen manuellt för att spåra avslutslänkar, ställer du in den här variabeln på `tl()` `false`.

```js
s.trackDownloadLinks = true;
```
