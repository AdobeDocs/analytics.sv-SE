---
title: trackDownloadLinks
description: Aktivera eller inaktivera automatisk länkspårning för nedladdningslänkar.
feature: Variables
exl-id: d92f722b-d605-40ad-bb55-ec71219a47e3
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '307'
ht-degree: 0%

---

# trackDownLoadLinks

Adobe ger möjlighet att spåra nedladdningslänkar utan att behöva ställa in [`tl()`](../functions/tl-method.md) för varje nedladdningslänk. Aktivera den här variabeln om du vill använda automatisk länkspårning för hämtningslänkar.

När det är aktiverat jämför AppMeasurement alla klickade länk-URL:er med värden i [`linkDownloadFileTypes`](linkdownloadfiletypes.md). Om det finns en matchning aktiveras ett spårningsanrop för nedladdningslänk automatiskt.

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

## Spåra nedladdningslänkar med Adobe Analytics-tillägget

Spåra nedladdningslänkar är en kryssruta under [!UICONTROL Link Tracking] när du konfigurerar Adobe Analytics-tillägget.

1. Logga in på [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) med inloggningsuppgifterna för ditt AdobeID.
2. Klicka på den önskade taggegenskapen.
3. Gå till [!UICONTROL Extensions] klickar du på **[!UICONTROL Configure]** under Adobe Analytics.
4. Expandera [!UICONTROL Link Tracking] dragspelspanel, som visar [!UICONTROL Track download links] kryssrutan.

Klicka i kryssrutan om du vill aktivera automatisk spårning av nedladdningslänk.

## s.trackDownloadLinks in AppMeasurement and the Analytics extension custom code editor

The `s.trackDownloadLinks` är ett booleskt värde som aktiverar eller inaktiverar automatisk länkspårning för hämtning. Om du inte vill spåra nedladdningslänkar eller vill ringa `tl()` metod för att spåra hämtningar, ange variabeln till `false`.

```js
s.trackDownloadLinks = true;
```
