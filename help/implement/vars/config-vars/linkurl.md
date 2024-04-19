---
title: linkURL
description: Åsidosätt det automatiskt genererade länk-URL-AppMeasurementet som används i länkspårningsanrop.
feature: Variables
exl-id: 15d6e423-d9fc-4f84-ad39-0bd91399cde4
role: Admin, Developer
source-git-commit: 8be75c04177e97949811c17c7a87b04cce7b3de4
workflow-type: tm+mt
source-wordcount: '158'
ht-degree: 0%

---

# linkURL

När ett anrop om länkspårning skickas till Adobe identifierar datainsamlingsservrarna automatiskt URL:en. Använd `linkURL` variabel som åsidosätter den identifierade URL:en.

Det finns inga dimensioner i Analysis Workspace som rapporterar om den här variabeln. Den fyller i `page_event_var1` kolumn i [Dataflöden](/help/export/analytics-data-feed/data-feed-overview.md).

## Länk-URL med Web SDK

Länk-URL mappas till följande variabler:

* [XDM-objekt](/help/implement/aep-edge/xdm-var-mapping.md): `web.webInteraction.URL`
* [Dataobjekt](/help/implement/aep-edge/data-var-mapping.md): `data.__adobe.analytics.linkURL` eller `data.__adobe.analytics.pev1`

## Länk-URL med Adobe Analytics-tillägget

Det finns inget dedikerat fält i Adobe Analytics-tillägget som kan använda den här variabeln. Använd den anpassade kodredigeraren enligt AppMeasurementen syntax.

## s.linkURL i AppMeasurementet och den anpassade kodredigeraren för Analytics-tillägget

The `s.linkURL` variabeln är en sträng som innehåller webbläsarens URL när användaren klickar på länken. Den här variabeln fyller inte i några dimensioner som är tillgängliga i rapporter.

```js
s.linkURL = "https://example.com";
```

Om det tredje argumentet i [tl()](../functions/tl-method.md) -metoden är inte inställd, `linkURL` används i stället.
