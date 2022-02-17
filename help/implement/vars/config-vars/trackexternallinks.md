---
title: trackExternalLinks
description: Aktivera eller inaktivera automatisk länkspårning för att avsluta länkar.
feature: Variables
exl-id: a34d4ffa-ff82-460e-af7d-1a4be85fc631
source-git-commit: b3c74782ef6183fa63674b98e4c0fc39fc09441b
workflow-type: tm+mt
source-wordcount: '180'
ht-degree: 1%

---

# trackExternalLinks

Adobe har möjlighet att spåra utgående länkar utan att behöva ställa in [`tl()`](../functions/tl-method.md) metod för varje avslutningslänk. Aktivera den här variabeln om du vill använda automatisk länkspårning för slutlänkar.

När det är aktiverat jämför AppMeasurement alla klickade länk-URL:er med värden i [`linkInternalFilters`](linkinternalfilters.md) och [`linkExternalFilters`](linkexternalfilters.md). Om det finns en matchning utlöses ett avslutningslänkspårningsanrop automatiskt.

## Spåra utgående länkar med hjälp av taggar i Adobe Experience Platform

Spåra utgående länkar är en kryssruta under [!UICONTROL Link Tracking] när du konfigurerar Adobe Analytics-tillägget.

1. Logga in på [Användargränssnitt för datainsamling](https://experience.adobe.com/data-collection) med inloggningsuppgifterna för ditt AdobeID.
2. Klicka på önskad egenskap.
3. Gå till [!UICONTROL Extensions] klickar du på [!UICONTROL Configure] under Adobe Analytics.
4. Expandera [!UICONTROL Link Tracking] dragspelspanel, som visar [!UICONTROL Track outbound links] kryssrutan.

Klicka i kryssrutan om du vill aktivera automatisk spårning av avslutningslänk.

## s.trackExternalLinks in AppMeasurement och anpassad kodredigerare

The `s.trackExternalLinks` är ett booleskt värde som aktiverar eller inaktiverar automatisk spårning av avslutningslänk. Om du inte vill spåra utgående länkar eller vill ringa `tl()` metod för att spåra avslutslänkar, ange variabeln till `false`.

```js
s.trackExternalLinks = true;
```
