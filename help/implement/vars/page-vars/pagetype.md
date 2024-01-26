---
title: pageType
description: Kontrollera om den aktuella sidan är ett 404-fel.
feature: Variables
exl-id: e61ef82d-b583-4230-b904-5ea3584910be
role: Admin, Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '205'
ht-degree: 0%

---

# pageType

The `pageType` variabeln är en flagga som används för att ange felsidor på din plats, till exempel 404 fel. Om variabeln innehåller strängen `errorPage`fyller den i&quot;Sidor som inte hittas&quot; [dimension](/help/components/dimensions/pages-not-found.md) och [mått](/help/components/metrics/pages-not-found.md).

>[!IMPORTANT]
>
>Ange inte den här variabeln på icke-felsidor.

## Sidtyp med Web SDK

Sidtypen är [mappas för Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/implementation/aep-edge/variable-mapping.html) under XDM-fältet `web.webPageDetails.isErrorPage`. Det här XDM-fältet är booleskt; ange det till `true` för att flagga det som en felsida, eller `false` om det inte är en felsida. Adobe översätter automatiskt booleskt värde till strängvärdet `errorPage` när det skickas till en analysrapportsserie.

## Sidtyp med Adobe Analytics-tillägg

Det finns inget dedikerat fält i Adobe Analytics-tillägget som kan använda den här variabeln. Använd den anpassade kodredigeraren enligt AppMeasurementen syntax.

## s.pageType i AppMeasurementet och den anpassade kodredigeraren för Analytics-tillägget

The `s.pageType` variabeln är en sträng där värdet `errorPage` är dess enda giltiga värde. Ange den här variabeln till det här värdet på alla felsidor på webbplatsen, till exempel på 404 sidor.

```js
s.pageType = "errorPage";
```

>[!TIP]
>
>Använd en eVar för att samla in felkoden så att du kan få mer information om vilka specifika fel som besökarna stöter på på din webbplats.
