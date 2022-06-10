---
title: trackInlineStats
description: Aktivera eller inaktivera aktivitetskartan i implementeringen.
keywords: inaktivera aktivitetskarta
feature: Variables
exl-id: a52adc1d-1be7-4002-b393-7ce66332b483
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '207'
ht-degree: 0%

---

# trackInlineStats

Aktivitetskartan är en funktion i Adobe Analytics som samlar in data om var besökarna klickar och vad de klickar på. Du kan visa dessa data i Analytics-rapporter eller genom att använda en webbläsartilläggsövertäckning. Aktivera den här variabeln om du vill använda funktioner för aktivitetskarta.

När det här alternativet är aktiverat samlar AppMeasurement in information om länken och skickar dessa data i nästa bildförfrågan. Information från varje klick lagras i en cookie med etiketten `s_sq`.

## Activity Map med Web SDK

Web SDK har ännu inte stöd för datainsamling från Activity Map.

## Aktivera Klickkarta med Adobe Analytics-tillägget

[!UICONTROL Enable Clickmap] är en kryssruta under [!UICONTROL Link Tracking] när du konfigurerar Adobe Analytics-tillägget.

1. Logga in på [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) med inloggningsuppgifterna för ditt AdobeID.
2. Klicka på den önskade taggegenskapen.
3. Gå till [!UICONTROL Extensions] klickar du på **[!UICONTROL Configure]** under Adobe Analytics.
4. Expandera [!UICONTROL Link Tracking] dragspelspanel, som visar [!UICONTROL Enable Clickmap] kryssrutan.

Klicka i kryssrutan för att aktivera spårning av aktivitetskarta.

## s.trackInlineStats i AppMeasurement och den anpassade kodredigeraren i Analytics-tillägget

The `s.trackInlineStats` är ett booleskt värde som aktiverar eller inaktiverar spårning av aktivitetskarta. Standardvärdet är `false`. Ange det här värdet till `true` om du vill aktivera datainsamling för aktivitetskarta.

```js
s.trackInlineStats = true;
```
