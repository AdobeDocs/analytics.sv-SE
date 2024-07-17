---
title: trackInlineStats
description: (Borttaget) Aktivera eller inaktivera ClickMap i implementeringen.
keywords: inaktivera klickkarta
feature: Variables
exl-id: a52adc1d-1be7-4002-b393-7ce66332b483
role: Admin, Developer
source-git-commit: 1cdcc748e50c7eeffa98897006154aa0953ce7e3
workflow-type: tm+mt
source-wordcount: '176'
ht-degree: 0%

---

# trackInlineStats

>[!IMPORTANT]
>
>Den här variabeln tas bort och används inte längre.

ClickMap är en pensionerad funktion i Adobe Analytics som samlar in data om var besökarna klickar och vad de klickar på. Funktionen har ersatts med [Activity Map](/help/analyze/activity-map/overview.md).

När det här alternativet är aktiverat samlar AppMeasurementet in information om länken och skickar dessa data i nästa bildförfrågan. Information från varje klick lagras i en cookie med etiketten `s_sq`.

## Aktivera ClickMap med tillägget Adobe Analytics

[!UICONTROL Enable ClickMap] är en kryssruta under dragspelet [!UICONTROL Link Tracking] när du konfigurerar Adobe Analytics-tillägget.

1. Logga in på [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) med dina inloggningsuppgifter för AdobeID.
2. Klicka på den önskade taggegenskapen.
3. Gå till fliken [!UICONTROL Extensions] och klicka sedan på knappen **[!UICONTROL Configure]** under Adobe Analytics.
4. Expandera dragspelsfliken [!UICONTROL Link Tracking], som visar kryssrutan [!UICONTROL Enable ClickMap].

>[!NOTE]
>
>Den här kryssrutan skiljer sig från kryssrutan [!UICONTROL Use Activity Map] som finns under dragspelet [!UICONTROL Library management].

## s.trackInlineStats i AppMeasurementet och den anpassade kodredigeraren för Analytics-tillägget

`s.trackInlineStats` är ett booleskt värde som aktiverar eller inaktiverar spårning av ClickMap. Eftersom funktionen är inaktiv rekommenderar Adobe inte att du ställer in den här variabeln. Dess standardvärde är `false`.

```js
s.trackInlineStats = false;
```
