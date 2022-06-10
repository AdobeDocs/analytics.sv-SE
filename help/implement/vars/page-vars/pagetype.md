---
title: pageType
description: Kontrollera om den aktuella sidan är ett 404-fel.
feature: Variables
exl-id: e61ef82d-b583-4230-b904-5ea3584910be
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '140'
ht-degree: 1%

---

# pageType

The `pageType` variabeln är en flagga som används för att ange felsidor på din plats, till exempel 404 fel. Om variabeln innehåller strängen `errorPage`fyller den i dimensionen &quot;Sidor hittades inte&quot;.

>[!IMPORTANT]
>
>Ange inte den här variabeln på icke-felsidor.

## Sidtyp med Adobe Analytics-tillägg

Det finns inget dedikerat fält i Adobe Analytics-tillägget som kan använda den här variabeln. Använd den anpassade kodredigeraren efter AppMeasurement-syntax.

## s.pageType i AppMeasurement och den anpassade kodredigeraren för Analytics-tillägget

The `s.pageType` variabeln är en sträng där värdet `errorPage` är dess enda giltiga värde. Ange den här variabeln till det här värdet på alla felsidor på webbplatsen, till exempel på 404 sidor.

```js
s.pageType = "errorPage";
```

>[!TIP]
>
>Använd en eVar för att samla in felkoden så att du kan få mer information om vilka specifika fel som besökarna stöter på på din webbplats.
