---
title: linkURL
description: Åsidosätt den automatiskt genererade länken URL AppMeasurement använder i länkspårningsanrop.
feature: Variables
exl-id: 15d6e423-d9fc-4f84-ad39-0bd91399cde4
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '144'
ht-degree: 1%

---

# linkURL

När ett anrop om länkspårning skickas till Adobe identifierar datainsamlingsservrarna automatiskt URL:en. Använd `linkURL` variabel som åsidosätter den identifierade URL:en.

## Länk-URL med Web SDK

Länk-URL är [mappas för Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/implementation/aep-edge/variable-mapping.html) under XDM-fältet `web.webInteraction.URL`.

## Länk-URL med Adobe Analytics-tillägget

Det finns inget dedikerat fält i Adobe Analytics-tillägget som kan använda den här variabeln. Använd den anpassade kodredigeraren efter AppMeasurement-syntax.

## s.linkURL i AppMeasurement och den anpassade kodredigeraren för Analytics-tillägget

The `s.linkURL` variabeln är en sträng som innehåller webbläsarens URL när användaren klickar på länken. Den här variabeln fyller inte i några dimensioner som är tillgängliga i rapporter.

```js
s.linkURL = "https://example.com";
```

Om det tredje argumentet i [tl()](../functions/tl-method.md) metoden är inte inställd, `linkURL` används i stället.
