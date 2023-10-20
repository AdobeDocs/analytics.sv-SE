---
title: trackInlineStats
description: Aktivera eller inaktivera ClickMap i implementeringen.
keywords: inaktivera klickkarta
feature: Variables
exl-id: a52adc1d-1be7-4002-b393-7ce66332b483
source-git-commit: a3df69f7de45ba3694e1212e5c16a10bb4602cd6
workflow-type: tm+mt
source-wordcount: '178'
ht-degree: 1%

---

# trackInlineStats

>[!IMPORTANT]
>
>Den här variabeln har tagits bort. Se [Aktivera Activity Map](/help/analyze/activity-map/activitymap-getting-started/activitymap-getting-started-admins/activitymap-enable.md) i stället.

ClickMap är en pensionerad funktion i Adobe Analytics som samlar in data om var besökarna klickar och vad de klickar på. Funktionen har ersatts med [Activity Map](/help/analyze/activity-map/activity-map.md).

När det här alternativet är aktiverat samlar AppMeasurementet in information om länken och skickar dessa data i nästa bildförfrågan. Information från varje klick lagras i en cookie som är märkt `s_sq`.

## Aktivera ClickMap med tillägget Adobe Analytics

[!UICONTROL Enable ClickMap] är en kryssruta under [!UICONTROL Link Tracking] när du konfigurerar Adobe Analytics-tillägget.

1. Logga in på [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) med inloggningsuppgifterna för ditt AdobeID.
2. Klicka på den önskade taggegenskapen.
3. Gå till [!UICONTROL Extensions] klickar du på **[!UICONTROL Configure]** under Adobe Analytics.
4. Expandera [!UICONTROL Link Tracking] dragspelspanel, som visar [!UICONTROL Enable ClickMap] kryssrutan.

>[!NOTE]
>
>Den här kryssrutan skiljer sig från [!UICONTROL Use Activity Map] kryssrutan, som finns under [!UICONTROL Library management] dragspelspanel.

## s.trackInlineStats i AppMeasurementet och den anpassade kodredigeraren för Analytics-tillägget

The `s.trackInlineStats` är ett booleskt värde som aktiverar eller inaktiverar spårning av ClickMap. Eftersom funktionen är inaktiv rekommenderar Adobe inte att du ställer in den här variabeln. Standardvärdet är `false`.

```js
s.trackInlineStats = false;
```
