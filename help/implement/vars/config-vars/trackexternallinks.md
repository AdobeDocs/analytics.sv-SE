---
title: trackExternalLinks
description: Aktivera eller inaktivera automatisk länkspårning för att avsluta länkar.
feature: Variables
exl-id: a34d4ffa-ff82-460e-af7d-1a4be85fc631
role: Admin, Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '298'
ht-degree: 0%

---

# trackExternalLinks

Med Adobe kan du spåra utgående länkar utan att manuellt ange metoden [`tl()`](../functions/tl-method.md) för varje avslutningslänk. Aktivera den här variabeln om du vill använda automatisk länkspårning för att avsluta länkar.

När det här alternativet är aktiverat jämför AppMeasurementet alla klickade länk-URL:er med värden i [`linkInternalFilters`](linkinternalfilters.md) och [`linkExternalFilters`](linkexternalfilters.md). Om det finns en matchning utlöses ett avslutningslänkspårningsanrop automatiskt.

## Aktivera eller inaktivera klicksamling med Web SDK-tillägget

Använd kryssrutan [!UICONTROL Enable click data collection] när du konfigurerar Web SDK. Den här kryssrutan hanterar både avslutnings- och nedladdningslänkar.

1. Logga in på [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) med dina inloggningsuppgifter för AdobeID.
1. Klicka på den önskade taggegenskapen.
1. Gå till fliken [!UICONTROL Extensions] och klicka sedan på knappen **[!UICONTROL Configure]** under [!UICONTROL Adobe Experience Platform Web SDK].
1. Klicka i kryssrutan **[!UICONTROL Enable click data collection]** under [!UICONTROL Data Collection].

## Aktivera eller inaktivera klicksamlingen manuellt för att implementera Web SDK

Konfigurera SDK med [`clickCollectionEnabled`](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html#clickCollectionEnabled). Fältet är ett booleskt värde som avgör om data som är associerade med länkklick samlas in automatiskt. Dess standardvärde är `true`. Ange värdet `false` om du vill inaktivera automatisk länkspårning. Den här inställningen hanterar automatisk länkspårning för både hämtnings- och avslutslänkar.

```json
alloy("configure", {
  "clickCollectionEnabled": true
});
```

## Spåra utgående länkar med Adobe Analytics-tillägget

Spåra utgående länkar är en kryssruta i dragspelet [!UICONTROL Link Tracking] när du konfigurerar Adobe Analytics-tillägget.

1. Logga in på [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) med dina inloggningsuppgifter för AdobeID.
2. Klicka på den önskade taggegenskapen.
3. Gå till fliken [!UICONTROL Extensions] och klicka sedan på knappen **[!UICONTROL Configure]** under Adobe Analytics.
4. Expandera dragspelsfliken [!UICONTROL Link Tracking], som visar kryssrutan [!UICONTROL Track outbound links].

Klicka i kryssrutan om du vill aktivera automatisk spårning av avslutningslänk.

## s.trackExternalLinks in AppMeasurement och den anpassade kodredigeraren för Analytics-tillägget

`s.trackExternalLinks` är ett booleskt värde som aktiverar eller inaktiverar automatisk spårning av avslutningslänk. Om du inte vill spåra utgående länkar, eller föredrar att anropa metoden `tl()` manuellt för att spåra avslutslänkar, anger du den här variabeln till `false`.

```js
s.trackExternalLinks = true;
```
