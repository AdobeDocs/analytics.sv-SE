---
title: trackExternalLinks
description: Aktivera eller inaktivera automatisk länkspårning för att avsluta länkar.
exl-id: a34d4ffa-ff82-460e-af7d-1a4be85fc631
source-git-commit: 1a49c2a6d90fc670bd0646d6d40738a87b74b8eb
workflow-type: tm+mt
source-wordcount: '180'
ht-degree: 1%

---

# trackExternalLinks

Med Adobe kan du spåra utgående länkar utan att manuellt ange [`tl()`](../functions/tl-method.md)-metoden för varje avslutningslänk. Aktivera den här variabeln om du vill använda automatisk länkspårning för slutlänkar.

När det är aktiverat jämför AppMeasurement alla klickade länk-URL:er med värden i [`linkInternalFilters`](linkinternalfilters.md) och [`linkExternalFilters`](linkexternalfilters.md). Om det finns en matchning utlöses ett avslutningslänkspårningsanrop automatiskt.

## Spåra utgående länkar med hjälp av taggar i Adobe Experience Platform

Spåra utgående länkar är en kryssruta under dragspelet [!UICONTROL Link Tracking] när du konfigurerar Adobe Analytics-tillägget.

1. Logga in på [användargränssnittet för datainsamling](https://experience.adobe.com/data-collection) med inloggningsuppgifterna för ditt Adobe-ID.
2. Klicka på önskad egenskap.
3. Gå till fliken [!UICONTROL Extensions] och klicka sedan på knappen [!UICONTROL Configure] under Adobe Analytics.
4. Expandera dragspelet [!UICONTROL Link Tracking], som visar kryssrutan [!UICONTROL Track outbound links].

Klicka i kryssrutan om du vill aktivera automatisk spårning av avslutningslänk.

## s.trackExternalLinks in AppMeasurement och anpassad kodredigerare

`s.trackExternalLinks` är ett booleskt värde som aktiverar eller inaktiverar automatisk spårning av avslutningslänk. Om du inte vill spåra utgående länkar, eller föredrar att anropa metoden `tl()` manuellt för att spåra avslutslänkar, anger du den här variabeln till `false`.

```js
s.trackExternalLinks = true;
```
