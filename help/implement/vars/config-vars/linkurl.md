---
title: linkURL
description: Åsidosätt det automatiskt genererade länk-URL-AppMeasurementet som används i länkspårningsanrop.
feature: Variables
exl-id: 15d6e423-d9fc-4f84-ad39-0bd91399cde4
role: Admin, Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '138'
ht-degree: 0%

---

# linkURL

När ett anrop om länkspårning skickas till Adobe identifierar datainsamlingsservrarna automatiskt URL:en. Använd `linkURL` variabel som åsidosätter den identifierade URL:en.

## Länk-URL med Web SDK

Länk-URL är [mappas för Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/implementation/aep-edge/variable-mapping.html) under XDM-fältet `web.webInteraction.URL`.

## Länk-URL med Adobe Analytics-tillägget

Det finns inget dedikerat fält i Adobe Analytics-tillägget som kan använda den här variabeln. Använd den anpassade kodredigeraren enligt AppMeasurementen syntax.

## s.linkURL i AppMeasurementet och den anpassade kodredigeraren för Analytics-tillägget

The `s.linkURL` variabeln är en sträng som innehåller webbläsarens URL när användaren klickar på länken. Den här variabeln fyller inte i några dimensioner som är tillgängliga i rapporter.

```js
s.linkURL = "https://example.com";
```

Om det tredje argumentet i [tl()](../functions/tl-method.md) -metoden är inte inställd, `linkURL` används i stället.
