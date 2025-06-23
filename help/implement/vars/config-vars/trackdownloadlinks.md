---
title: trackDownloadLinks
description: Aktivera eller inaktivera automatisk länkspårning för nedladdningslänkar.
feature: Appmeasurement Implementation
exl-id: d92f722b-d605-40ad-bb55-ec71219a47e3
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '296'
ht-degree: 0%

---

# trackDownLoadLinks

I Adobe kan du spåra hämtningslänkar utan att manuellt ange metoden [`tl()`](../functions/tl-method.md) för varje hämtningslänk. Aktivera den här variabeln om du vill använda automatisk länkspårning för hämtningslänkar.

När den är aktiverad jämför AppMeasurement alla klickade länk-URL:er med värden i [`linkDownloadFileTypes`](linkdownloadfiletypes.md). Om det finns en matchning aktiveras ett spårningsanrop för nedladdningslänk automatiskt.

## Aktivera eller inaktivera klicksamlingen med Web SDK-tillägget

Använd kryssrutan [!UICONTROL Enable click data collection] när du konfigurerar Web SDK. Den här kryssrutan hanterar både avslutnings- och nedladdningslänkar.

1. Logga in på [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) med dina inloggningsuppgifter för AdobeID.
1. Klicka på den önskade taggegenskapen.
1. Gå till fliken [!UICONTROL Extensions] och klicka sedan på knappen **[!UICONTROL Configure]** under [!UICONTROL Adobe Experience Platform Web SDK].
1. Klicka i kryssrutan **[!UICONTROL Enable click data collection]** under [!UICONTROL Data Collection].

## Aktivera eller inaktivera klicksamlingen manuellt för att implementera Web SDK

Konfigurera SDK med [`clickCollectionEnabled`](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html?lang=sv-SE#clickCollectionEnabled). Fältet är ett booleskt värde som avgör om data som är associerade med länkklick samlas in automatiskt. Dess standardvärde är `true`. Ange värdet `false` om du vill inaktivera automatisk länkspårning. Den här inställningen hanterar automatisk länkspårning för både hämtnings- och avslutslänkar.

```json
alloy("configure", {
  "clickCollectionEnabled": true
});
```

## Spåra nedladdningslänkar med Adobe Analytics-tillägget

Spåra hämtningslänkar är en kryssruta i dragspelet [!UICONTROL Link Tracking] när du konfigurerar Adobe Analytics-tillägget.

1. Logga in på [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) med dina inloggningsuppgifter för AdobeID.
2. Klicka på den önskade taggegenskapen.
3. Gå till fliken [!UICONTROL Extensions] och klicka sedan på knappen **[!UICONTROL Configure]** under Adobe Analytics.
4. Expandera dragspelsfliken [!UICONTROL Link Tracking], som visar kryssrutan [!UICONTROL Track download links].

Klicka i kryssrutan om du vill aktivera automatisk spårning av nedladdningslänk.

## s.trackDownloadLinks in AppMeasurement and the Analytics extension custom code editor

`s.trackDownloadLinks` är ett booleskt värde som aktiverar eller inaktiverar automatisk länkspårning för hämtning. Om du inte vill spåra hämtningslänkar eller vill anropa metoden `tl()` manuellt för att spåra hämtningar anger du den här variabeln till `false`.

```js
s.trackDownloadLinks = true;
```
