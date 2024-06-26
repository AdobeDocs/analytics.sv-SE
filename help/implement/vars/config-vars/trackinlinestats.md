---
title: trackInlineStats
description: (Borttaget) Aktivera eller inaktivera ClickMap i implementeringen.
keywords: inaktivera klickkarta
feature: Variables
exl-id: a52adc1d-1be7-4002-b393-7ce66332b483
role: Admin, Developer
source-git-commit: 75ae77c1da1b578639609888e794e13d965ef669
workflow-type: tm+mt
source-wordcount: '177'
ht-degree: 0%

---

# trackInlineStats

>[!IMPORTANT]
>
>Den här variabeln har tagits bort. Se [Aktivera Activity Map](/help/analyze/activity-map/activitymap-getting-started/activitymap-enable.md) i stället.

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
