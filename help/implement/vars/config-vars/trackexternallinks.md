---
title: trackExternalLinks
description: Aktivera eller inaktivera automatisk länkspårning för att avsluta länkar.
feature: Variables
exl-id: a34d4ffa-ff82-460e-af7d-1a4be85fc631
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '309'
ht-degree: 0%

---

# trackExternalLinks

Adobe har möjlighet att spåra utgående länkar utan att behöva ställa in [`tl()`](../functions/tl-method.md) metod för varje avslutningslänk. Aktivera den här variabeln om du vill använda automatisk länkspårning för slutlänkar.

När det är aktiverat jämför AppMeasurement alla klickade länk-URL:er med värden i [`linkInternalFilters`](linkinternalfilters.md) och [`linkExternalFilters`](linkexternalfilters.md). Om det finns en matchning utlöses ett avslutningslänkspårningsanrop automatiskt.

## Aktivera eller inaktivera klicksamling med Web SDK-tillägget

Använd [!UICONTROL Enable click data collection] när du konfigurerar Web SDK. Den här kryssrutan hanterar både avslutnings- och hämtningslänkar.

1. Logga in på [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) med inloggningsuppgifterna för ditt AdobeID.
1. Klicka på den önskade taggegenskapen.
1. Gå till [!UICONTROL Extensions] klickar du på **[!UICONTROL Configure]** knapp under [!UICONTROL Adobe Experience Platform Web SDK].
1. Under [!UICONTROL Data Collection]klickar du på **[!UICONTROL Enable click data collection]** kryssrutan.

## Aktivera eller inaktivera klicksamlingen manuellt för att implementera Web SDK

Konfigurera SDK med [`clickCollectionEnabled`](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html#clickCollectionEnabled). Fältet är ett booleskt värde som avgör om data som är associerade med länkklick samlas in automatiskt. Standardvärdet är `true`. Ange det här värdet till `false` om du vill inaktivera automatisk länkspårning. Den här inställningen hanterar automatisk länkspårning för både hämtnings- och avslutslänkar.

```json
alloy("configure", {
  "clickCollectionEnabled": true
});
```

## Spåra utgående länkar med Adobe Analytics-tillägget

Spåra utgående länkar är en kryssruta under [!UICONTROL Link Tracking] när du konfigurerar Adobe Analytics-tillägget.

1. Logga in på [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) med inloggningsuppgifterna för ditt AdobeID.
2. Klicka på den önskade taggegenskapen.
3. Gå till [!UICONTROL Extensions] klickar du på **[!UICONTROL Configure]** under Adobe Analytics.
4. Expandera [!UICONTROL Link Tracking] dragspelspanel, som visar [!UICONTROL Track outbound links] kryssrutan.

Klicka i kryssrutan om du vill aktivera automatisk spårning av avslutningslänk.

## s.trackExternalLinks in AppMeasurement och den anpassade kodredigeraren för Analytics-tillägget

The `s.trackExternalLinks` är ett booleskt värde som aktiverar eller inaktiverar automatisk spårning av avslutningslänk. Om du inte vill spåra utgående länkar eller vill ringa `tl()` metod för att spåra avslutslänkar, ange variabeln till `false`.

```js
s.trackExternalLinks = true;
```
