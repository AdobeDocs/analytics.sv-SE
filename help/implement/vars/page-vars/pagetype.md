---
title: pageType
description: Kontrollera om den aktuella sidan är ett 404-fel.
feature: Variables
exl-id: e61ef82d-b583-4230-b904-5ea3584910be
role: Admin, Developer
source-git-commit: 5ef92db2f5edb5fded497dddedd56abd49d8a019
workflow-type: tm+mt
source-wordcount: '201'
ht-degree: 0%

---

# pageType

Variabeln `pageType` är en flagga som används för att ange felsidor på din plats, till exempel 404 fel. Om den här variabeln innehåller strängen `errorPage` fylls [dimension](/help/components/dimensions/pages-not-found.md) och [mått](/help/components/metrics/pages-not-found.md) i.

>[!IMPORTANT]
>
>Ange inte den här variabeln på icke-felsidor.

## Sidtyp med Web SDK

Kanalen mappas till följande variabler:

* [XDM-objekt](/help/implement/aep-edge/xdm-var-mapping.md): `xdm.web.webPageDetails.isErrorPage` - det här XDM-fältet är booleskt; ange det till `true` för att flagga det som en felsida, eller `false` om det inte är en felsida.
* [Dataobjekt](/help/implement/aep-edge/data-var-mapping.md): `data.__adobe.analytics.pageType` - det här dataobjektfältet är en sträng. Ange det till `"errorPage"` för att flagga det som en sådan.

## Sidtyp med Adobe Analytics-tillägg

Det finns inget dedikerat fält i Adobe Analytics-tillägget som kan använda den här variabeln. Använd den anpassade kodredigeraren enligt AppMeasurementen syntax.

## s.pageType i AppMeasurementet och den anpassade kodredigeraren för Analytics-tillägget

Variabeln `s.pageType` är en sträng där värdet `errorPage` är dess enda giltiga värde. Ange den här variabeln till det här värdet på alla felsidor på webbplatsen, till exempel på 404 sidor.

```js
s.pageType = "errorPage";
```

>[!TIP]
>
>Använd en eVar för att samla in felkoden så att du kan få mer information om vilka specifika fel som besökarna stöter på på din webbplats.
